---
title: Proteger contas de administradores globais no ambiente de teste do Microsoft 365 Enterprise
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/16/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom:
- TLG
- Ent_TLGs
description: Use estas etapas para proteger contas de administrador global no ambiente de teste do Microsoft 365 Enterprise.
ms.openlocfilehash: 89985f99f5471aab87189e78035062add2c6bad9
ms.sourcegitcommit: 9ee873c6a2f738a0c99921e036894b646742e706
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/15/2019
ms.locfileid: "38673327"
---
# <a name="protect-global-administrator-accounts-in-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="cabf0-103">Proteger contas de administradores globais no ambiente de teste do Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="cabf0-103">Protect global administrator accounts in your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="cabf0-104">*Este guia de laboratório de teste só pode ser usado para ambientes de teste do Microsoft 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="cabf0-104">*This Test Lab Guide can only be used for Microsoft 365 Enterprise test environments.*</span></span>

<span data-ttu-id="cabf0-105">Você pode impedir ataques digitais em sua organização, garantindo que suas contas de administrador sejam o mais seguras possível.</span><span class="sxs-lookup"><span data-stu-id="cabf0-105">You can prevent digital attacks on your organization by ensuring that your administrator accounts are as secure as possible.</span></span> <span data-ttu-id="cabf0-106">Este artigo descreve como usar as políticas de acesso condicional do Azure Active Directory (Azure AD) para proteger contas de administrador global.</span><span class="sxs-lookup"><span data-stu-id="cabf0-106">This article describes how to use Azure Active Directory (Azure AD) conditional access policies to protect global administrator accounts.</span></span>

<span data-ttu-id="cabf0-107">Há duas fases para proteger as contas de administrador global no seu ambiente de teste do Microsoft 365 Enterprise:</span><span class="sxs-lookup"><span data-stu-id="cabf0-107">There are two phases to protecting global administrator accounts in your Microsoft 365 Enterprise test environment:</span></span>

1.  <span data-ttu-id="cabf0-108">Criar o ambiente de teste do Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="cabf0-108">Create the Microsoft 365 Enterprise test environment.</span></span>
2.  <span data-ttu-id="cabf0-109">Proteger sua conta de administrador global dedicado.</span><span class="sxs-lookup"><span data-stu-id="cabf0-109">Protect your dedicated global administrator account.</span></span>

![Guias de Laboratório de Teste do Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="cabf0-111">Clique [aqui](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) para ver um mapa visual de todos os artigos da pilha do Guia de Laboratório de Teste do Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="cabf0-111">Click [here](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>

## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="cabf0-112">Fase 1: Criar o ambiente de teste do Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="cabf0-112">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="cabf0-113">Se você só quiser testar a proteção da conta de administrador global de forma leve com os requisitos mínimos, siga as instruções em [configuração básica leve](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="cabf0-113">If you just want to test global administrator account protection in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="cabf0-114">Se você quiser testar a proteção da conta de administrador global em uma empresa simulada, siga as instruções em [autenticação de passagem](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="cabf0-114">If you want to test global administrator account protection in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>

  
> [!NOTE]
> <span data-ttu-id="cabf0-115">Testando a proteção da conta de administrador global não requer o ambiente de teste corporativo simulado, que inclui uma intranet simulada conectada à Internet e a sincronização de diretórios para um Active Directory Domain Services (AD DS).</span><span class="sxs-lookup"><span data-stu-id="cabf0-115">Testing global administrator account protection does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS).</span></span> <span data-ttu-id="cabf0-116">É fornecida aqui como uma opção para que você possa testar a proteção da conta de administrador global e experimentá-la em um ambiente que represente uma organização típica.</span><span class="sxs-lookup"><span data-stu-id="cabf0-116">It is provided here as an option so that you can test global administrator account protection and experiment with it in an environment that represents a typical organization.</span></span> 
  
## <a name="phase-2-configure-conditional-access-policies"></a><span data-ttu-id="cabf0-117">Fase 2: configurar políticas de acesso condicional</span><span class="sxs-lookup"><span data-stu-id="cabf0-117">Phase 2: Configure conditional access policies</span></span>

<span data-ttu-id="cabf0-118">Primeiro, crie uma nova conta de usuário como administrador global dedicado.</span><span class="sxs-lookup"><span data-stu-id="cabf0-118">First, create a new user account as a dedicated global administrator.</span></span>

1. <span data-ttu-id="cabf0-119">Em uma guia separada, abra o [centro de administração do Microsoft 365](https://admin.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="cabf0-119">On a separate tab, open the [Microsoft 365 admin center](https://admin.microsoft.com/).</span></span>
2. <span data-ttu-id="cabf0-120">Em **usuários ativos**, clique em **Adicionar um usuário**.</span><span class="sxs-lookup"><span data-stu-id="cabf0-120">Under **Active users**, click **Add a user**.</span></span>
3. <span data-ttu-id="cabf0-121">Na página **novo usuário** , digite **DedicatedAdmin** em **nome**, nome para **exibição**e nome de **usuário**.</span><span class="sxs-lookup"><span data-stu-id="cabf0-121">On the **New user** page, type **DedicatedAdmin** in **First name**, **Display name**, and **Username**.</span></span>
4. <span data-ttu-id="cabf0-122">Clique em **senha**, clique em **deixe-me criar a senha**e digite uma senha forte.</span><span class="sxs-lookup"><span data-stu-id="cabf0-122">Click **Password**, click **Let me create the password**, and then type a strong password.</span></span> <span data-ttu-id="cabf0-123">Registre a senha dessa nova conta em um local seguro.</span><span class="sxs-lookup"><span data-stu-id="cabf0-123">Record the password for this new account in a secure location.</span></span>
5. <span data-ttu-id="cabf0-124">Clear **faça com que este usuário altere sua senha quando entrar pela primeira vez**.</span><span class="sxs-lookup"><span data-stu-id="cabf0-124">Clear **Make this user change their password when they first sign in**.</span></span>
6. <span data-ttu-id="cabf0-125">Clique em **funções**e, em seguida, clique em **administrador global**.</span><span class="sxs-lookup"><span data-stu-id="cabf0-125">Click **Roles**, and then click **Global administrator**.</span></span>
7. <span data-ttu-id="cabf0-126">Clique em **licenças de produto**e, em seguida, ative as licenças do **Enterprise Mobility + Security E5** e **Office 365 Enterprise E5** no.</span><span class="sxs-lookup"><span data-stu-id="cabf0-126">Click **Product licenses**, and then turn the **Enterprise Mobility + Security E5** and **Office 365 Enterprise E5 licenses** on.</span></span>
8. <span data-ttu-id="cabf0-127">Clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="cabf0-127">Click **Add**.</span></span>
9. <span data-ttu-id="cabf0-128">Na **página usuário foi adicionado**, desmarque **Enviar senha no email**e clique em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="cabf0-128">On the **User was added page**, clear **Send password in email**, and then click **Close**.</span></span>

<span data-ttu-id="cabf0-129">Em seguida, crie um novo grupo chamado GlobalAdmins e adicione a conta DedicatedAdmin a ele.</span><span class="sxs-lookup"><span data-stu-id="cabf0-129">Next, create a new group named GlobalAdmins and add the DedicatedAdmin account to it.</span></span>

1. <span data-ttu-id="cabf0-130">Na guia **centro de administração do Microsoft 365** , clique no ícone de grupos na navegação à esquerda e, em seguida, clique em **grupos**.</span><span class="sxs-lookup"><span data-stu-id="cabf0-130">On the **Microsoft 365 admin center** tab, click the groups icon in the left navigation, and then click **Groups**.</span></span>
2. <span data-ttu-id="cabf0-131">Clique em **Adicionar um grupo**.</span><span class="sxs-lookup"><span data-stu-id="cabf0-131">Click **Add a group**.</span></span>
3. <span data-ttu-id="cabf0-132">Na página **novo grupo** , digite **GlobalAdmins**.</span><span class="sxs-lookup"><span data-stu-id="cabf0-132">On the **New Group** page, type **GlobalAdmins**.</span></span>
4. <span data-ttu-id="cabf0-133">Clique em **selecionar proprietário** clique em sua conta de administrador global e, em seguida, clique em **Adicionar > fechar**.</span><span class="sxs-lookup"><span data-stu-id="cabf0-133">Click **Select owner** click your global administrator account, and then click **Add > Close**.</span></span>
5. <span data-ttu-id="cabf0-134">Na lista de grupos, clique no grupo **GlobalAdmins** .</span><span class="sxs-lookup"><span data-stu-id="cabf0-134">In the list of groups, click the **GlobalAdmins** group.</span></span>
6. <span data-ttu-id="cabf0-135">Na página **GlobalAdmins** , clique em **Editar para membro**e, em seguida, clique em **adicionar membros**.</span><span class="sxs-lookup"><span data-stu-id="cabf0-135">On the **GlobalAdmins** page, click **Edit for Member**, and then click **Add members**.</span></span>
7. <span data-ttu-id="cabf0-136">Na lista, clique na conta **DedicatedAdmin** e, em seguida, clique em **salvar > fechar > fechar o centro de administração do >**.</span><span class="sxs-lookup"><span data-stu-id="cabf0-136">In the list, click the **DedicatedAdmin** account, and then click **Save > Close > Close > Admin center**.</span></span>

<span data-ttu-id="cabf0-137">Em seguida, crie políticas de acesso condicional para exigir a autenticação multifator para contas de administrador global e para negar a autenticação se o risco de entrada for médio ou alto.</span><span class="sxs-lookup"><span data-stu-id="cabf0-137">Next, create conditional access policies to require multifactor authentication for global administrator accounts and to deny authentication if the sign-in risk is medium or high.</span></span>

<span data-ttu-id="cabf0-138">Essa primeira política requer que todas as contas de administrador global usem MFA.</span><span class="sxs-lookup"><span data-stu-id="cabf0-138">This first policy requires that all global administrator accounts use MFA.</span></span>

1. <span data-ttu-id="cabf0-139">Em uma nova guia do navegador, vá para [https://portal.azure.com](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="cabf0-139">In a new tab of your browser, go to [https://portal.azure.com](https://portal.azure.com).</span></span>
2. <span data-ttu-id="cabf0-140">Clique em **Azure Active Directory > acesso condicional**.</span><span class="sxs-lookup"><span data-stu-id="cabf0-140">Click **Azure Active Directory > Conditional access**.</span></span>
3. <span data-ttu-id="cabf0-141">Na folha **acesso condicional – políticas** , clique em **política de linha de base: exigir MFA para administradores (visualização)**.</span><span class="sxs-lookup"><span data-stu-id="cabf0-141">On the **Conditional access – Policies** blade, click **Baseline policy: Require MFA for admins (preview)**.</span></span>
4. <span data-ttu-id="cabf0-142">Nas **políticas de linha de base...**</span><span class="sxs-lookup"><span data-stu-id="cabf0-142">On the **Baseline policies…**</span></span> <span data-ttu-id="cabf0-143">lâmina, clique em **usar política imediatamente > salvar**.</span><span class="sxs-lookup"><span data-stu-id="cabf0-143">blade, click **Use policy immediately > Save**.</span></span>

<span data-ttu-id="cabf0-144">Essa segunda política bloqueia o acesso à autenticação de conta de administrador global quando o risco de entrada é médio ou alto.</span><span class="sxs-lookup"><span data-stu-id="cabf0-144">This second policy blocks access to global administrator account authentication when the sign-in risk is medium or high.</span></span>

1. <span data-ttu-id="cabf0-145">Na folha **acesso condicional – políticas** , clique em **nova política**.</span><span class="sxs-lookup"><span data-stu-id="cabf0-145">On the **Conditional access – Policies** blade, click **New policy**.</span></span>
2. <span data-ttu-id="cabf0-146">Na **nova** folha, digite **administradores globais** em **nome**.</span><span class="sxs-lookup"><span data-stu-id="cabf0-146">On the **New** blade, type **Global administrators** in **Name**.</span></span>
3. <span data-ttu-id="cabf0-147">Na seção **atribuições** , clique em **usuários e grupos**.</span><span class="sxs-lookup"><span data-stu-id="cabf0-147">In the **Assignments** section, click **Users and groups**.</span></span>
4. <span data-ttu-id="cabf0-148">Na guia **incluir** da folha **usuários e grupos** , clique em **Selecionar usuários e grupos > usuários e grupos > selecionar**.</span><span class="sxs-lookup"><span data-stu-id="cabf0-148">On the **Include** tab of the **Users and groups** blade, click **Select users and groups > Users and groups > Select**.</span></span>
5. <span data-ttu-id="cabf0-149">Na folha **selecionar** , clique em **GlobalAdmins > selecionar > concluído**.</span><span class="sxs-lookup"><span data-stu-id="cabf0-149">On the **Select** blade, click the **GlobalAdmins > Select > Done**.</span></span>
6. <span data-ttu-id="cabf0-150">Na seção **atribuições** , clique em **condições**.</span><span class="sxs-lookup"><span data-stu-id="cabf0-150">In the **Assignments** section, click **Conditions**.</span></span>
7. <span data-ttu-id="cabf0-151">Na folha **condições** , clique em **risco de entrada**, clique em **Sim** para **Configurar**, clique **em alta** e **média**e, em seguida, clique em **selecionar** e **concluir**.</span><span class="sxs-lookup"><span data-stu-id="cabf0-151">On the **Conditions** blade, click **Sign-in risk**, click **Yes** for **Configure**, click **High** and **Medium**, and then click **Select** and **Done**.</span></span>
8. <span data-ttu-id="cabf0-152">Na seção **controles de acesso** da **nova** folha, clique em **conceder**.</span><span class="sxs-lookup"><span data-stu-id="cabf0-152">In the **Access controls** section of the **New** blade, click **Grant**.</span></span>
9. <span data-ttu-id="cabf0-153">Na folha **conceder** , clique em **bloquear acesso**e clique em **selecionar**.</span><span class="sxs-lookup"><span data-stu-id="cabf0-153">On the **Grant** blade, click **Block access**, and then click **Select**.</span></span>
10. <span data-ttu-id="cabf0-154">Na **nova** folha, clique em **ativado** para **habilitar a política**e clique em **criar**.</span><span class="sxs-lookup"><span data-stu-id="cabf0-154">On the **New** blade, click **On** for **Enable policy**, and then click **Create**.</span></span>
11. <span data-ttu-id="cabf0-155">Feche as guias **portal do Azure** e **centro de administração do Microsoft 365** .</span><span class="sxs-lookup"><span data-stu-id="cabf0-155">Close the **Azure portal** and **Microsoft 365 admin center** tabs.</span></span>

<span data-ttu-id="cabf0-156">Para testar a primeira política, saia e entre com a conta DedicatedAdmin.</span><span class="sxs-lookup"><span data-stu-id="cabf0-156">To test the first policy, sign out and sign in with the DedicatedAdmin account.</span></span> <span data-ttu-id="cabf0-157">Você deve ser solicitado a configurar o MFA na conta de usuário.</span><span class="sxs-lookup"><span data-stu-id="cabf0-157">You should be prompted to configure MFA on the user account.</span></span> <span data-ttu-id="cabf0-158">Isso demonstra que a primeira política está sendo aplicada.</span><span class="sxs-lookup"><span data-stu-id="cabf0-158">This demonstrates that the first policy is being applied.</span></span>

<span data-ttu-id="cabf0-159">Consulte a etapa [proteger contas de administrador global](identity-create-protect-global-admins.md#identity-global-admin) na fase de identidade para obter informações e links para proteger suas contas de administrador global em produção.</span><span class="sxs-lookup"><span data-stu-id="cabf0-159">See the [Protect global administrator accounts](identity-create-protect-global-admins.md#identity-global-admin) step in the Identity phase for information and links to protect your global administrator accounts in production.</span></span>

## <a name="next-step"></a><span data-ttu-id="cabf0-160">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="cabf0-160">Next step</span></span>

<span data-ttu-id="cabf0-161">Explorar recursos e funcionalidades adicionais de [identidade](m365-enterprise-test-lab-guides.md#identity) no ambiente de teste.</span><span class="sxs-lookup"><span data-stu-id="cabf0-161">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="cabf0-162">Confira também</span><span class="sxs-lookup"><span data-stu-id="cabf0-162">See also</span></span>

[<span data-ttu-id="cabf0-163">Fase 2: Identidade</span><span class="sxs-lookup"><span data-stu-id="cabf0-163">Phase 2: Identity</span></span>](identity-infrastructure.md)

[<span data-ttu-id="cabf0-164">Guias do Laboratório de Teste do Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="cabf0-164">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="cabf0-165">Implantação do Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="cabf0-165">Microsoft 365 Enterprise deployment</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="cabf0-166">Documentação do Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="cabf0-166">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
