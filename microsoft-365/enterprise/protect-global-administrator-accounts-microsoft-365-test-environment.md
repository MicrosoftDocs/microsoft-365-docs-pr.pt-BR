---
title: Proteger contas de administradores globais no ambiente de teste do Microsoft 365 Enterprise
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/16/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom:
- TLG
- Ent_TLGs
description: Use estas etapas para proteger contas de administrador global no ambiente de teste do Microsoft 365 Enterprise.
ms.openlocfilehash: 86b2d325fc710fd8b387bc37cad5f8ea60df001d
ms.sourcegitcommit: 3b2d3e2b38c4860db977e73dda119a465c669fa4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/26/2019
ms.locfileid: "33353053"
---
# <a name="protect-global-administrator-accounts-in-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="1fe77-103">Proteger contas de administradores globais no ambiente de teste do Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="1fe77-103">Protect global administrator accounts in your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="1fe77-104">Você pode impedir ataques digitais em sua organização, garantindo que suas contas de administrador sejam o mais seguras possível.</span><span class="sxs-lookup"><span data-stu-id="1fe77-104">You can prevent digital attacks on your organization by ensuring that your administrator accounts are as secure as possible.</span></span> <span data-ttu-id="1fe77-105">Este artigo descreve como usar as políticas de acesso condicional do Azure Active Directory (Azure AD) para proteger contas de administrador global.</span><span class="sxs-lookup"><span data-stu-id="1fe77-105">This article describes how to use Azure Active Directory (Azure AD) conditional access policies to protect global administrator accounts.</span></span>

<span data-ttu-id="1fe77-106">Há duas fases para proteger as contas de administrador global no seu ambiente de teste do Microsoft 365 Enterprise:</span><span class="sxs-lookup"><span data-stu-id="1fe77-106">There are two phases to protecting global administrator accounts in your Microsoft 365 Enterprise test environment:</span></span>

1.  <span data-ttu-id="1fe77-107">Criar o ambiente de teste do Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="1fe77-107">Create the Microsoft 365 Enterprise test environment.</span></span>
2.  <span data-ttu-id="1fe77-108">Proteger sua conta de administrador global dedicado.</span><span class="sxs-lookup"><span data-stu-id="1fe77-108">Protect your dedicated global administrator account.</span></span>

![Guias de laboratório de teste do Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="1fe77-110">Clique [aqui](https://aka.ms/m365etlgstack) para ver um mapa visual de todos os artigos na pilha do Guia do Test Lab do Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="1fe77-110">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>

## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="1fe77-111">Fase 1: criar seu ambiente de teste do Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="1fe77-111">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="1fe77-112">Se você só quiser testar a proteção da conta de administrador global de forma leve com os requisitos mínimos, siga as instruções em [configuração básica leve](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="1fe77-112">If you just want to test global administrator account protection in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="1fe77-113">Se você quiser testar a proteção da conta de administrador global em uma empresa simulada, siga as instruções em [autenticação de passagem](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="1fe77-113">If you want to test global administrator account protection in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>

  
> [!NOTE]
> <span data-ttu-id="1fe77-114">Testando a proteção da conta de administrador global não requer o ambiente de teste corporativo simulado, que inclui uma intranet simulada conectada à Internet e a sincronização de diretórios para um Active Directory Domain Services (AD DS).</span><span class="sxs-lookup"><span data-stu-id="1fe77-114">Testing global administrator account protection does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS).</span></span> <span data-ttu-id="1fe77-115">É fornecida aqui como uma opção para que você possa testar a proteção da conta de administrador global e experimentá-la em um ambiente que represente uma organização típica.</span><span class="sxs-lookup"><span data-stu-id="1fe77-115">It is provided here as an option so that you can test global administrator account protection and experiment with it in an environment that represents a typical organization.</span></span> 
  
## <a name="phase-2-configure-conditional-access-policies"></a><span data-ttu-id="1fe77-116">Fase 2: configurar políticas de acesso condicional</span><span class="sxs-lookup"><span data-stu-id="1fe77-116">Phase 2: Configure conditional access policies</span></span>

<span data-ttu-id="1fe77-117">Primeiro, crie uma nova conta de usuário como administrador global dedicado.</span><span class="sxs-lookup"><span data-stu-id="1fe77-117">First, create a new user account as a dedicated global administrator.</span></span>

1. <span data-ttu-id="1fe77-118">Em uma guia separada, abra o [centro de administração do Microsoft 365](https://admin.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="1fe77-118">On a separate tab, open the [Microsoft 365 admin center](https://admin.microsoft.com/).</span></span>
2. <span data-ttu-id="1fe77-119">Em **usuários ativos**, clique em **Adicionar um usuário**.</span><span class="sxs-lookup"><span data-stu-id="1fe77-119">Under **Active users**, click **Add a user**.</span></span>
3. <span data-ttu-id="1fe77-120">Na página **novo usuário** , digite **DedicatedAdmin** em **nome**, nome para **exibição**e nome de **usuário**.</span><span class="sxs-lookup"><span data-stu-id="1fe77-120">On the **New user** page, type **DedicatedAdmin** in **First name**, **Display name**, and **Username**.</span></span>
4. <span data-ttu-id="1fe77-121">Clique em **senha**, clique em **deixe-me criar a senha**e digite uma senha forte.</span><span class="sxs-lookup"><span data-stu-id="1fe77-121">Click **Password**, click **Let me create the password**, and then type a strong password.</span></span> <span data-ttu-id="1fe77-122">Registre a senha dessa nova conta em um local seguro.</span><span class="sxs-lookup"><span data-stu-id="1fe77-122">Record the password for this new account in a secure location.</span></span>
5. <span data-ttu-id="1fe77-123">Clear **faça com que este usuário altere sua senha quando entrar pela primeira vez**.</span><span class="sxs-lookup"><span data-stu-id="1fe77-123">Clear **Make this user change their password when they first sign in**.</span></span>
6. <span data-ttu-id="1fe77-124">Clique em **funções**e, em seguida, clique em **administrador global**.</span><span class="sxs-lookup"><span data-stu-id="1fe77-124">Click **Roles**, and then click **Global administrator**.</span></span>
7. <span data-ttu-id="1fe77-125">Clique em **licenças de produto**e, em seguida, ative as licenças do **Enterprise Mobility + Security E5** e **Office 365 Enterprise E5** no.</span><span class="sxs-lookup"><span data-stu-id="1fe77-125">Click **Product licenses**, and then turn the **Enterprise Mobility + Security E5** and **Office 365 Enterprise E5 licenses** on.</span></span>
8. <span data-ttu-id="1fe77-126">Clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="1fe77-126">Click **Add**.</span></span>
9. <span data-ttu-id="1fe77-127">Na **página usuário foi adicionado**, desmarque **Enviar senha no email**e clique em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="1fe77-127">On the **User was added page**, clear **Send password in email**, and then click **Close**.</span></span>

<span data-ttu-id="1fe77-128">Em seguida, crie um novo grupo chamado GlobalAdmins e adicione a conta DedicatedAdmin a ele.</span><span class="sxs-lookup"><span data-stu-id="1fe77-128">Next, create a new group named GlobalAdmins and add the DedicatedAdmin account to it.</span></span>

1. <span data-ttu-id="1fe77-129">Na guia **centro de administração do Microsoft 365** , clique no ícone de grupos na navegação à esquerda e, em seguida, clique em **grupos**.</span><span class="sxs-lookup"><span data-stu-id="1fe77-129">On the **Microsoft 365 admin center** tab, click the groups icon in the left navigation, and then click **Groups**.</span></span>
2. <span data-ttu-id="1fe77-130">Clique em **Adicionar um grupo**.</span><span class="sxs-lookup"><span data-stu-id="1fe77-130">Click **Add a group**.</span></span>
3. <span data-ttu-id="1fe77-131">Na página **novo grupo** , digite **GlobalAdmins**.</span><span class="sxs-lookup"><span data-stu-id="1fe77-131">On the **New Group** page, type **GlobalAdmins**.</span></span>
4. <span data-ttu-id="1fe77-132">Clique em **selecionar proprietário** clique em sua conta de administrador global e, em seguida, clique em **Adicionar > fechar**.</span><span class="sxs-lookup"><span data-stu-id="1fe77-132">Click **Select owner** click your global administrator account, and then click **Add > Close**.</span></span>
5. <span data-ttu-id="1fe77-133">Na lista de grupos, clique no grupo **GlobalAdmins** .</span><span class="sxs-lookup"><span data-stu-id="1fe77-133">In the list of groups, click the **GlobalAdmins** group.</span></span>
6. <span data-ttu-id="1fe77-134">Na página **GlobalAdmins** , clique em **Editar para membro**e, em seguida, clique em **adicionar membros**.</span><span class="sxs-lookup"><span data-stu-id="1fe77-134">On the **GlobalAdmins** page, click **Edit for Member**, and then click **Add members**.</span></span>
7. <span data-ttu-id="1fe77-135">Na lista, clique na conta **DedicatedAdmin** e, em seguida, clique em **salvar _GT_ fechar > fechar o centro de administração do >**.</span><span class="sxs-lookup"><span data-stu-id="1fe77-135">In the list, click the **DedicatedAdmin** account, and then click **Save > Close > Close > Admin center**.</span></span>

<span data-ttu-id="1fe77-136">Em seguida, crie políticas de acesso condicional para exigir a autenticação multifator para contas de administrador global e para negar a autenticação se o risco de entrada for médio ou alto.</span><span class="sxs-lookup"><span data-stu-id="1fe77-136">Next, create conditional access policies to require multifactor authentication for global administrator accounts and to deny authentication if the sign-in risk is medium or high.</span></span>

<span data-ttu-id="1fe77-137">Essa primeira política requer que todas as contas de administrador global usem MFA.</span><span class="sxs-lookup"><span data-stu-id="1fe77-137">This first policy requires that all global administrator accounts use MFA.</span></span>

1. <span data-ttu-id="1fe77-138">Em uma nova guia do navegador, vá para [https://portal.azure.com](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="1fe77-138">In a new tab of your browser, go to [https://portal.azure.com](https://portal.azure.com).</span></span>
2. <span data-ttu-id="1fe77-139">Clique em **Azure Active Directory > acesso condicional**.</span><span class="sxs-lookup"><span data-stu-id="1fe77-139">Click **Azure Active Directory > Conditional access**.</span></span>
3. <span data-ttu-id="1fe77-140">Na folha **acesso condicional – políticas** , clique em **política de linha de base: exigir MFA para administradores (visualização)**.</span><span class="sxs-lookup"><span data-stu-id="1fe77-140">On the **Conditional access – Policies** blade, click **Baseline policy: Require MFA for admins (preview)**.</span></span>
4. <span data-ttu-id="1fe77-141">Nas **políticas de linha de base...**</span><span class="sxs-lookup"><span data-stu-id="1fe77-141">On the **Baseline policies…**</span></span> <span data-ttu-id="1fe77-142">lâmina, clique em **usar política imediatamente _GT_ salvar**.</span><span class="sxs-lookup"><span data-stu-id="1fe77-142">blade, click **Use policy immediately > Save**.</span></span>

<span data-ttu-id="1fe77-143">Essa segunda política bloqueia o acesso à autenticação de conta de administrador global quando o risco de entrada é médio ou alto.</span><span class="sxs-lookup"><span data-stu-id="1fe77-143">This second policy blocks access to global administrator account authentication when the sign-in risk is medium or high.</span></span>

1. <span data-ttu-id="1fe77-144">Na folha **acesso condicional – políticas** , clique em **nova política**.</span><span class="sxs-lookup"><span data-stu-id="1fe77-144">On the **Conditional access – Policies** blade, click **New policy**.</span></span>
2. <span data-ttu-id="1fe77-145">Na **nova** folha, digite **administradores globais** em **nome**.</span><span class="sxs-lookup"><span data-stu-id="1fe77-145">On the **New** blade, type **Global administrators** in **Name**.</span></span>
3. <span data-ttu-id="1fe77-146">Na seção **atribuições** , clique em **usuários e grupos**.</span><span class="sxs-lookup"><span data-stu-id="1fe77-146">In the **Assignments** section, click **Users and groups**.</span></span>
4. <span data-ttu-id="1fe77-147">Na guia **incluir** da folha **usuários e grupos** , clique em **Selecionar usuários e grupos _GT_ usuários e grupos > selecionar**.</span><span class="sxs-lookup"><span data-stu-id="1fe77-147">On the **Include** tab of the **Users and groups** blade, click **Select users and groups > Users and groups > Select**.</span></span>
5. <span data-ttu-id="1fe77-148">Na folha **selecionar** , clique em **GlobalAdmins _GT_ selecionar > concluído**.</span><span class="sxs-lookup"><span data-stu-id="1fe77-148">On the **Select** blade, click the **GlobalAdmins > Select > Done**.</span></span>
6. <span data-ttu-id="1fe77-149">Na seção **atribuições** , clique em **condições**.</span><span class="sxs-lookup"><span data-stu-id="1fe77-149">In the **Assignments** section, click **Conditions**.</span></span>
7. <span data-ttu-id="1fe77-150">Na folha **condições** , clique em **risco de entrada**, clique em **Sim** para **Configurar**, clique **em alta** e **média**e, em seguida, clique em **selecionar** e **concluir**.</span><span class="sxs-lookup"><span data-stu-id="1fe77-150">On the **Conditions** blade, click **Sign-in risk**, click **Yes** for **Configure**, click **High** and **Medium**, and then click **Select** and **Done**.</span></span>
8. <span data-ttu-id="1fe77-151">Na seção **controles de acesso** da **nova** folha, clique em **conceder**.</span><span class="sxs-lookup"><span data-stu-id="1fe77-151">In the **Access controls** section of the **New** blade, click **Grant**.</span></span>
9. <span data-ttu-id="1fe77-152">Na folha **conceder** , clique em **bloquear acesso**e clique em **selecionar**.</span><span class="sxs-lookup"><span data-stu-id="1fe77-152">On the **Grant** blade, click **Block access**, and then click **Select**.</span></span>
10. <span data-ttu-id="1fe77-153">Na **nova** folha, clique em **ativado** para **habilitar a política**e clique em **criar**.</span><span class="sxs-lookup"><span data-stu-id="1fe77-153">On the **New** blade, click **On** for **Enable policy**, and then click **Create**.</span></span>
11. <span data-ttu-id="1fe77-154">Feche as guias **portal do Azure** e **centro de administração do Microsoft 365** .</span><span class="sxs-lookup"><span data-stu-id="1fe77-154">Close the **Azure portal** and **Microsoft 365 admin center** tabs.</span></span>

<span data-ttu-id="1fe77-155">Para testar a primeira política, saia e entre com a conta DedicatedAdmin.</span><span class="sxs-lookup"><span data-stu-id="1fe77-155">To test the first policy, sign out and sign in with the DedicatedAdmin account.</span></span> <span data-ttu-id="1fe77-156">Você deve ser solicitado a configurar o MFA na conta de usuário.</span><span class="sxs-lookup"><span data-stu-id="1fe77-156">You should be prompted to configure MFA on the user account.</span></span> <span data-ttu-id="1fe77-157">Isso demonstra que a primeira política está sendo aplicada.</span><span class="sxs-lookup"><span data-stu-id="1fe77-157">This demonstrates that the first policy is being applied.</span></span>

<span data-ttu-id="1fe77-158">Consulte a etapa [proteger contas de administrador global](identity-designate-protect-admin-accounts.md#identity-global-admin) na fase de identidade para obter informações e links para proteger suas contas de administrador global em produção.</span><span class="sxs-lookup"><span data-stu-id="1fe77-158">See the [Protect global administrator accounts](identity-designate-protect-admin-accounts.md#identity-global-admin) step in the Identity phase for information and links to protect your global administrator accounts in production.</span></span>

## <a name="next-step"></a><span data-ttu-id="1fe77-159">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="1fe77-159">Next step</span></span>

<span data-ttu-id="1fe77-160">Explorar recursos e funcionalidades adicionais de [identidade](m365-enterprise-test-lab-guides.md#identity) no ambiente de teste.</span><span class="sxs-lookup"><span data-stu-id="1fe77-160">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="1fe77-161">Confira também</span><span class="sxs-lookup"><span data-stu-id="1fe77-161">See also</span></span>

[<span data-ttu-id="1fe77-162">Fase 2: Identidade</span><span class="sxs-lookup"><span data-stu-id="1fe77-162">Phase 2: Identity</span></span>](identity-infrastructure.md)

[<span data-ttu-id="1fe77-163">Guias do Laboratório de Teste do Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="1fe77-163">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="1fe77-164">Implantação do Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="1fe77-164">Microsoft 365 Enterprise deployment</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="1fe77-165">Documentação do Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="1fe77-165">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
