---
title: Configurar políticas de acesso condicional
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
- M365-Campaigns
- m365solution-smb
ms.custom:
- Adm_O365
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
description: Saiba como exigir MFA e configurar políticas de acesso condicional para o Microsoft 365 para empresas.
ms.openlocfilehash: dcb79ed060dd15fd288cdcfb9e3739a788f5fbc2
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50912181"
---
# <a name="require-multi-factor-authentication-and-set-up-conditional-access-policies"></a><span data-ttu-id="9e712-103">Exigir autenticação multifacional e configurar políticas de acesso condicional</span><span class="sxs-lookup"><span data-stu-id="9e712-103">Require multi-factor authentication and set up conditional access policies</span></span>

<span data-ttu-id="9e712-104">Você protege o acesso aos seus dados com autenticação multifacional e políticas de acesso condicional.</span><span class="sxs-lookup"><span data-stu-id="9e712-104">You protect access to your data with multi-factor authentication and conditional access policies.</span></span> <span data-ttu-id="9e712-105">Eles adicionam segurança adicional substancial.</span><span class="sxs-lookup"><span data-stu-id="9e712-105">These add substantial additional security.</span></span> <span data-ttu-id="9e712-106">A Microsoft fornece um conjunto de políticas de acesso condicional de linha de base recomendadas para todos os clientes.</span><span class="sxs-lookup"><span data-stu-id="9e712-106">Microsoft provides a set of baseline conditional access policies that are recommended for all customers.</span></span> <span data-ttu-id="9e712-107">As políticas de linha de base são um conjunto de políticas predefinidas que ajudam a proteger as organizações contra muitos ataques comuns.</span><span class="sxs-lookup"><span data-stu-id="9e712-107">Baseline policies are a set of predefined policies that help protect organizations against many common attacks.</span></span> <span data-ttu-id="9e712-108">Esses ataques comuns podem incluir spray de senha, repetição e phishing.</span><span class="sxs-lookup"><span data-stu-id="9e712-108">These common attacks can include password spray, replay, and phishing.</span></span>

<span data-ttu-id="9e712-109">Essas políticas exigem que os administradores e usuários insiram uma segunda forma de autenticação (chamada autenticação multifatória ou MFA) em determinadas condições.</span><span class="sxs-lookup"><span data-stu-id="9e712-109">These policies require admins and users to enter a second form of authentication (called multi-factor authentication, or MFA) under certain conditions.</span></span> <span data-ttu-id="9e712-110">Por exemplo, se um usuário em sua organização tentar entrar no Microsoft 365 de um país diferente ou de um dispositivo desconhecido, a entrada pode ser considerada arriscada.</span><span class="sxs-lookup"><span data-stu-id="9e712-110">For example, if a user in your organization tries to sign in to Microsoft 365 from a different country or from an unknown device, the sign-in might be considered risky.</span></span> <span data-ttu-id="9e712-111">O usuário deve fornecer uma forma extra de autenticação (como uma impressão digital ou um código) para provar sua identidade.</span><span class="sxs-lookup"><span data-stu-id="9e712-111">The user must provide an extra form of authentication (such as a fingerprint or a code) to prove their identity.</span></span>

<span data-ttu-id="9e712-112">Atualmente, as políticas de linha de base incluem as seguintes políticas:</span><span class="sxs-lookup"><span data-stu-id="9e712-112">Currently, the baseline policies include the following policies:</span></span>

- <span data-ttu-id="9e712-113">Configurar no Centro de administração do Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="9e712-113">Set up in Microsoft 365 admin center:</span></span>
  - <span data-ttu-id="9e712-114">**Exigir MFA para administradores**: requer autenticação multifatória para as funções de administrador mais privilegiadas, incluindo o administrador global.</span><span class="sxs-lookup"><span data-stu-id="9e712-114">**Require MFA for admins**: Requires multi-factor authentication for the most privileged administrator roles, including global administrator.</span></span>
  - <span data-ttu-id="9e712-115">**Proteção do usuário final**: requer autenticação multifafa para os usuários somente quando uma login é arriscada.</span><span class="sxs-lookup"><span data-stu-id="9e712-115">**End-user protection**: Requires multi-factor authentication for users only when a sign-in is risky.</span></span> 
- <span data-ttu-id="9e712-116">Configurar no portal do Azure Active Directory:</span><span class="sxs-lookup"><span data-stu-id="9e712-116">Set up in Azure Active Directory portal:</span></span>
  - <span data-ttu-id="9e712-117">**Bloquear autenticação herdada**: aplicativos cliente mais antigos e alguns novos aplicativos não usam protocolos de autenticação mais novos, mais seguros.</span><span class="sxs-lookup"><span data-stu-id="9e712-117">**Block legacy authentication**: Older client apps and some new apps don't use newer, more secure, authentication protocols.</span></span> <span data-ttu-id="9e712-118">Esses aplicativos mais antigos podem ignorar políticas de acesso condicional e obter acesso não autorizado ao seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="9e712-118">These older apps can bypass conditional access policies and gain unauthorized access to your environment.</span></span> <span data-ttu-id="9e712-119">Essa política bloqueia o acesso de clientes que não suportam acesso condicional.</span><span class="sxs-lookup"><span data-stu-id="9e712-119">This policy blocks access from clients that don't support conditional access.</span></span> 
  - <span data-ttu-id="9e712-120">**Exigir MFA para Gerenciamento de Serviço**: requer autenticação multifacional para acesso a ferramentas de gerenciamento, incluindo o portal do Azure (onde você configura políticas de linha de base).</span><span class="sxs-lookup"><span data-stu-id="9e712-120">**Require MFA for Service Management**: Requires multi-factor authentication for access to management tools, including Azure portal (where you configure baseline policies).</span></span>

<span data-ttu-id="9e712-121">Recomendamos que você habilita todas essas políticas de linha de base.</span><span class="sxs-lookup"><span data-stu-id="9e712-121">We recommend that you enable all of these baseline policies.</span></span> <span data-ttu-id="9e712-122">Depois que essas políticas são habilitadas, os administradores e os usuários serão solicitados a se registrarem para a Autenticação Multifator do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="9e712-122">After these policies are enabled, admins and users will be prompted to register for Azure AD Multifactor Authentication.</span></span>

<span data-ttu-id="9e712-123">Para obter mais informações sobre essas políticas, consulte [O que são políticas de linha de base](/azure/active-directory/conditional-access/concept-baseline-protection)?</span><span class="sxs-lookup"><span data-stu-id="9e712-123">For more information about these policies, see [What are baseline policies](/azure/active-directory/conditional-access/concept-baseline-protection)?</span></span>

## <a name="require-mfa"></a><span data-ttu-id="9e712-124">Exigir MFA</span><span class="sxs-lookup"><span data-stu-id="9e712-124">Require MFA</span></span>

<span data-ttu-id="9e712-125">Para exigir que todos os usuários entre com uma segunda forma de ID:</span><span class="sxs-lookup"><span data-stu-id="9e712-125">To require that all users sign in with a second form of ID:</span></span>

1. <span data-ttu-id="9e712-126">Vá para o centro de administração em <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a> e escolha **Instalação**.</span><span class="sxs-lookup"><span data-stu-id="9e712-126">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a> and choose **Setup**.</span></span>

2. <span data-ttu-id="9e712-127">Na página Instalação, escolha **Exibir** no **cartão Tornar entrar mais** seguro.</span><span class="sxs-lookup"><span data-stu-id="9e712-127">On the Setup page, choose **View** in the **Make sign-in more secure** card.</span></span>

    ![Tornar o cartão de acesso mais seguro.](../media/setupmfa.png)
3. <span data-ttu-id="9e712-129">Na página Tornar a conexão mais segura, escolha **Começar**.</span><span class="sxs-lookup"><span data-stu-id="9e712-129">On the Make sign-in more secure page, choose **Get started**.</span></span>

4. <span data-ttu-id="9e712-130">No painel Fortalecer a segurança de entrada, selecione  as caixas de seleção ao lado de Exigir autenticação multifator para administradores e Exigir que os usuários se registrem para autenticação multifator e bloqueiem o acesso se o risco for **detectado**.</span><span class="sxs-lookup"><span data-stu-id="9e712-130">On the Strengthen sign-in security pane, select the check boxes next to **Require multi-factor authentication for admins** and **Require users to register for multi-factor authentication and block access if risk is detected**.</span></span>
    <span data-ttu-id="9e712-131">Certifique-se de excluir a [conta de](m365-campaigns-protect-admin-accounts.md#create-an-emergency-admin-account) administrador de emergência ou "quebra de vidro" do requisito MFA na caixa **Encontrar usuários.**</span><span class="sxs-lookup"><span data-stu-id="9e712-131">Be sure to exclude the [emergency](m365-campaigns-protect-admin-accounts.md#create-an-emergency-admin-account) or "break-glass" admin account from the MFA requirement in the **Find users** box.</span></span>

    ![Fortalecer a página de segurança de canto.](../media/requiremfa.png)

5. <span data-ttu-id="9e712-133">Escolha **Criar política** na parte inferior da página.</span><span class="sxs-lookup"><span data-stu-id="9e712-133">Choose **Create policy** on the bottom of the page.</span></span>

## <a name="set-up-baseline-policies"></a><span data-ttu-id="9e712-134">Configurar políticas de linha de base</span><span class="sxs-lookup"><span data-stu-id="9e712-134">Set up baseline policies</span></span>

1. <span data-ttu-id="9e712-135">Vá para o [portal do Azure](https://portal.azure.com)e navegue até Acesso Condicional de Segurança do **Azure Active Directory** para criar uma nova \>  \>  **política.**</span><span class="sxs-lookup"><span data-stu-id="9e712-135">Go to the [Azure portal](https://portal.azure.com), and then navigate to **Azure Active Directory** \> **Security** \> **Conditional Access** to create a **new policy**.</span></span>

<span data-ttu-id="9e712-136">Consulte as seguintes instruções específicas para cada política:</span><span class="sxs-lookup"><span data-stu-id="9e712-136">See the following specific instructions for each policy:</span></span> <br>
    - [<span data-ttu-id="9e712-137">Exigir MFA para administradores</span><span class="sxs-lookup"><span data-stu-id="9e712-137">Require MFA for admins</span></span>](/azure/active-directory/conditional-access/howto-baseline-protect-administrators) <br>
    - [<span data-ttu-id="9e712-138">Exigir MFA para usuários</span><span class="sxs-lookup"><span data-stu-id="9e712-138">Require MFA for users</span></span>](/azure/active-directory/conditional-access/howto-baseline-protect-end-users) <br>
    - [<span data-ttu-id="9e712-139">Bloquear autenticação herdda</span><span class="sxs-lookup"><span data-stu-id="9e712-139">Block legacy authentication</span></span>](/azure/active-directory/conditional-access/howto-baseline-protect-legacy-auth) <br>
    - [<span data-ttu-id="9e712-140">Exigir MFA para gerenciamento de serviço</span><span class="sxs-lookup"><span data-stu-id="9e712-140">Require MFA for service management</span></span>](/azure/active-directory/conditional-access/howto-baseline-protect-azure)

> [!NOTE]
> <span data-ttu-id="9e712-141">Políticas de visualização não existem mais e os usuários precisarão criar suas próprias políticas.</span><span class="sxs-lookup"><span data-stu-id="9e712-141">Preview policies no longer exist and users will need to create their own policies.</span></span>

<span data-ttu-id="9e712-142">Você pode configurar políticas extras, como exigir aplicativos cliente aprovados.</span><span class="sxs-lookup"><span data-stu-id="9e712-142">You can set up extra policies, such as requiring approved client apps.</span></span> <span data-ttu-id="9e712-143">Para obter mais informações, consulte [a documentação do Acesso Condicional](/azure/active-directory/conditional-access/).</span><span class="sxs-lookup"><span data-stu-id="9e712-143">For more information, see the [Conditional Access documentation](/azure/active-directory/conditional-access/).</span></span>