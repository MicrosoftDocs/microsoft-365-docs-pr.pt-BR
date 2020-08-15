---
title: Proteger contas de administradores globais no seu ambiente de teste do Microsoft 365 for Enterprise
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/12/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom:
- TLG
- Ent_TLGs
description: Use estas etapas para proteger as contas de administrador global no seu ambiente de teste do Microsoft 365 for Enterprise.
ms.openlocfilehash: fff09ca41ff0b648d46b5c33f753affc01242264
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46695177"
---
# <a name="protect-global-administrator-accounts-in-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="7f633-103">Proteger contas de administradores globais no seu ambiente de teste do Microsoft 365 for Enterprise</span><span class="sxs-lookup"><span data-stu-id="7f633-103">Protect global administrator accounts in your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="7f633-104">*Este guia de laboratório de teste só pode ser usado para o Microsoft 365 para ambientes de teste corporativos.*</span><span class="sxs-lookup"><span data-stu-id="7f633-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="7f633-105">Você pode impedir ataques digitais em sua organização, garantindo que suas contas de administrador sejam o mais seguras possível.</span><span class="sxs-lookup"><span data-stu-id="7f633-105">You can prevent digital attacks on your organization by ensuring that your administrator accounts are as secure as possible.</span></span> <span data-ttu-id="7f633-106">Este artigo descreve como usar as políticas de acesso condicional do Azure Active Directory (Azure AD) para proteger contas de administrador global.</span><span class="sxs-lookup"><span data-stu-id="7f633-106">This article describes how to use Azure Active Directory (Azure AD) conditional access policies to protect global administrator accounts.</span></span>

<span data-ttu-id="7f633-107">Há duas fases para proteger as contas de administrador global no seu ambiente de teste do Microsoft 365 for Enterprise:</span><span class="sxs-lookup"><span data-stu-id="7f633-107">There are two phases to protecting global administrator accounts in your Microsoft 365 for enterprise test environment:</span></span>

1.  <span data-ttu-id="7f633-108">Crie o ambiente de teste do Microsoft 365 for Enterprise.</span><span class="sxs-lookup"><span data-stu-id="7f633-108">Create the Microsoft 365 for enterprise test environment.</span></span>
2.  <span data-ttu-id="7f633-109">Proteger sua conta de administrador global dedicado.</span><span class="sxs-lookup"><span data-stu-id="7f633-109">Protect your dedicated global administrator account.</span></span>

![Guias do Laboratório de Teste do Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="7f633-111">Clique [aqui](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) para ver um mapa visual de todos os artigos na pilha do Guia de Laboratório de Teste do Microsoft 365 para empresas.</span><span class="sxs-lookup"><span data-stu-id="7f633-111">Click [here](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack.</span></span>

## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="7f633-112">Fase 1: desenvolver seu ambiente de teste do Microsoft 365 for Enterprise</span><span class="sxs-lookup"><span data-stu-id="7f633-112">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="7f633-113">Se você só quiser testar a proteção da conta de administrador global de forma leve com os requisitos mínimos, siga as instruções em [configuração básica leve](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="7f633-113">If you just want to test global administrator account protection in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="7f633-114">Se você quiser testar a proteção da conta de administrador global em uma empresa simulada, siga as instruções em [autenticação de passagem](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="7f633-114">If you want to test global administrator account protection in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="7f633-115">Testando a proteção da conta de administrador global não requer o ambiente de teste corporativo simulado, que inclui uma intranet simulada conectada à Internet e a sincronização de diretórios para um Active Directory Domain Services (AD DS).</span><span class="sxs-lookup"><span data-stu-id="7f633-115">Testing global administrator account protection does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS).</span></span> <span data-ttu-id="7f633-116">É fornecida aqui como uma opção para que você possa testar a proteção da conta de administrador global e experimentá-la em um ambiente que represente uma organização típica.</span><span class="sxs-lookup"><span data-stu-id="7f633-116">It is provided here as an option so that you can test global administrator account protection and experiment with it in an environment that represents a typical organization.</span></span> 
  
## <a name="phase-2-configure-conditional-access-policies"></a><span data-ttu-id="7f633-117">Fase 2: configurar políticas de acesso condicional</span><span class="sxs-lookup"><span data-stu-id="7f633-117">Phase 2: Configure conditional access policies</span></span>

<span data-ttu-id="7f633-118">Primeiro, crie uma nova conta de usuário como administrador global dedicado.</span><span class="sxs-lookup"><span data-stu-id="7f633-118">First, create a new user account as a dedicated global administrator.</span></span>

1. <span data-ttu-id="7f633-119">Em uma guia separada, abra o [centro de administração do Microsoft 365](https://admin.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="7f633-119">On a separate tab, open the [Microsoft 365 admin center](https://admin.microsoft.com/).</span></span>
2. <span data-ttu-id="7f633-120">Clique em **usuários > usuários ativos**e, em seguida, clique em **Adicionar um usuário**.</span><span class="sxs-lookup"><span data-stu-id="7f633-120">Click **Users > Active users**, and then click **Add a user**.</span></span>
3. <span data-ttu-id="7f633-121">No painel **Adicionar usuário** , digite **DedicatedAdmin** em **nome**, nome para **exibição**e nome de **usuário**.</span><span class="sxs-lookup"><span data-stu-id="7f633-121">In the **Add user** pane, type **DedicatedAdmin** in **First name**, **Display name**, and **Username**.</span></span>
4. <span data-ttu-id="7f633-122">Clique em **senha**, clique em **deixe-me criar a senha**e digite uma senha forte.</span><span class="sxs-lookup"><span data-stu-id="7f633-122">Click **Password**, click **Let me create the password**, and then type a strong password.</span></span> <span data-ttu-id="7f633-123">Registre a senha dessa nova conta em um local seguro.</span><span class="sxs-lookup"><span data-stu-id="7f633-123">Record the password for this new account in a secure location.</span></span>
5. <span data-ttu-id="7f633-124">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="7f633-124">Click **Next**.</span></span>
6. <span data-ttu-id="7f633-125">No painel **atribuir licenças de produtos** , selecione **Microsoft 365 E5**e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="7f633-125">In the **Assign product licenses** pane, select **Microsoft 365 E5**, and then click **Next**.</span></span>
7. <span data-ttu-id="7f633-126">No painel **configurações opcionais** , clique em **funções**e selecione **acesso do centro de administração** e **administrador global**. Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="7f633-126">In the **Optional settings** pane, click **Roles**, and then select **Admin center access** and **Global admin**. Click **Next**.</span></span>
8. <span data-ttu-id="7f633-127">No painel **você está quase concluído** , clique em **concluir adição**e, em seguida, clique em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="7f633-127">On the **You're almost done** pane, click **Finish adding**, and then click **Close**.</span></span>

<span data-ttu-id="7f633-128">Em seguida, crie um novo grupo chamado GlobalAdmins e adicione a conta DedicatedAdmin a ele.</span><span class="sxs-lookup"><span data-stu-id="7f633-128">Next, create a new group named GlobalAdmins and add the DedicatedAdmin account to it.</span></span>

1. <span data-ttu-id="7f633-129">Na guia **centro de administração do Microsoft 365** , clique em **grupos** na navegação à esquerda e, em seguida, clique em **grupos**.</span><span class="sxs-lookup"><span data-stu-id="7f633-129">On the **Microsoft 365 admin center** tab, click **Groups** in the left navigation, and then click **Groups**.</span></span>
2. <span data-ttu-id="7f633-130">Clique em **Adicionar um grupo**.</span><span class="sxs-lookup"><span data-stu-id="7f633-130">Click **Add a group**.</span></span>
3. <span data-ttu-id="7f633-131">No painel **escolher um tipo de grupo** , selecione **segurança**e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="7f633-131">In the **Choose a group type** pane, select **Security**, and then click **Next**.</span></span>
4. <span data-ttu-id="7f633-132">No painel **Configurar o básico** , clique em **Criar grupo**e, em seguida, clique em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="7f633-132">In the **Set up the basics** pane, click **Create group**, and then click **Close**.</span></span>
5. <span data-ttu-id="7f633-133">No painel **revisar e concluir a adição de grupo** , digite **GlobalAdmins**e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="7f633-133">In the **Review and finish adding group** pane, type **GlobalAdmins**, and then click **Next**.</span></span>
7. <span data-ttu-id="7f633-134">Na lista de grupos, clique no grupo **GlobalAdmins** .</span><span class="sxs-lookup"><span data-stu-id="7f633-134">In the list of groups, click the **GlobalAdmins** group.</span></span>
8. <span data-ttu-id="7f633-135">No painel **GlobalAdmins** , clique em **Membros**e, em seguida, clique em **Exibir todos e gerenciar Membros**.</span><span class="sxs-lookup"><span data-stu-id="7f633-135">In the **GlobalAdmins** pane, click **Members**, and then click **View all and manage members**.</span></span>
9. <span data-ttu-id="7f633-136">No painel **GlobalAdmins** , clique em **adicionar membros**, selecione a conta **DedicatedAdmin** e a conta de administrador global e clique em **salvar > fechar > fechar**.</span><span class="sxs-lookup"><span data-stu-id="7f633-136">In the **GlobalAdmins** pane, click **Add members**, select the **DedicatedAdmin** account and your global admin account, and then click **Save > Close > Close**.</span></span>

<span data-ttu-id="7f633-137">Em seguida, crie políticas de acesso condicional para exigir a autenticação multifator para contas de administrador global e para negar a autenticação se o risco de entrada for médio ou alto.</span><span class="sxs-lookup"><span data-stu-id="7f633-137">Next, create conditional access policies to require multifactor authentication for global administrator accounts and to deny authentication if the sign-in risk is medium or high.</span></span>

<span data-ttu-id="7f633-138">Essa primeira política requer que todas as contas de administrador global usem MFA.</span><span class="sxs-lookup"><span data-stu-id="7f633-138">This first policy requires that all global administrator accounts use MFA.</span></span>

1. <span data-ttu-id="7f633-139">Em uma nova guia do navegador, vá para [https://portal.azure.com](https://portal.azure.com) .</span><span class="sxs-lookup"><span data-stu-id="7f633-139">In a new tab of your browser, go to [https://portal.azure.com](https://portal.azure.com).</span></span>
2. <span data-ttu-id="7f633-140">Clique em **Azure Active Directory > segurança > acesso condicional**.</span><span class="sxs-lookup"><span data-stu-id="7f633-140">Click **Azure Active Directory > Security > Conditional Access**.</span></span>
3. <span data-ttu-id="7f633-141">No painel **acesso condicional – políticas** , clique em **política de linha de base: exigir MFA para administradores (visualização)**.</span><span class="sxs-lookup"><span data-stu-id="7f633-141">In the **Conditional access – Policies** pane, click **Baseline policy: Require MFA for admins (preview)**.</span></span>
4. <span data-ttu-id="7f633-142">No painel **diretiva de linha de base** , clique em **usar política imediatamente > salvar**.</span><span class="sxs-lookup"><span data-stu-id="7f633-142">In the **Baseline policy** pane, click **Use policy immediately > Save**.</span></span>

<span data-ttu-id="7f633-143">Essa segunda política bloqueia o acesso à autenticação de conta de administrador global quando o risco de entrada é médio ou alto.</span><span class="sxs-lookup"><span data-stu-id="7f633-143">This second policy blocks access to global administrator account authentication when the sign-in risk is medium or high.</span></span>

1. <span data-ttu-id="7f633-144">No painel **acesso condicional – políticas** , clique em **nova política**.</span><span class="sxs-lookup"><span data-stu-id="7f633-144">In the **Conditional access – Policies** pane, click **New policy**.</span></span>
2. <span data-ttu-id="7f633-145">No painel **novo** , digite **administradores globais** em **nome**.</span><span class="sxs-lookup"><span data-stu-id="7f633-145">In the **New** pane, type **Global administrators** in **Name**.</span></span>
3. <span data-ttu-id="7f633-146">Na seção **atribuições** , clique em **usuários e grupos**.</span><span class="sxs-lookup"><span data-stu-id="7f633-146">In the **Assignments** section, click **Users and groups**.</span></span>
4. <span data-ttu-id="7f633-147">Na guia **incluir** do painel **usuários e grupos** , clique em **Selecionar usuários e grupos > usuários e grupos > selecionar**.</span><span class="sxs-lookup"><span data-stu-id="7f633-147">On the **Include** tab of the **Users and groups** pane, click **Select users and groups > Users and groups > Select**.</span></span>
5. <span data-ttu-id="7f633-148">No painel **selecionar** , clique no grupo **GlobalAdmins** e, em seguida, clique em **selecionar > concluído**.</span><span class="sxs-lookup"><span data-stu-id="7f633-148">In the **Select** pane, click the **GlobalAdmins** group, and then click **Select > Done**.</span></span>
6. <span data-ttu-id="7f633-149">Na seção **atribuições** , clique em **condições**.</span><span class="sxs-lookup"><span data-stu-id="7f633-149">In the **Assignments** section, click **Conditions**.</span></span>
7. <span data-ttu-id="7f633-150">No painel **condições** , clique em **risco de entrada**, clique em **Sim** para **Configurar**, clique **em alta** e **média**e, em seguida, clique em **selecionar** e **concluir**.</span><span class="sxs-lookup"><span data-stu-id="7f633-150">In the **Conditions** pane, click **Sign-in risk**, click **Yes** for **Configure**, click **High** and **Medium**, and then click **Select** and **Done**.</span></span>
8. <span data-ttu-id="7f633-151">Na seção **controles de acesso** do painel **novo** , clique em **conceder**.</span><span class="sxs-lookup"><span data-stu-id="7f633-151">In the **Access controls** section of the **New** pane, click **Grant**.</span></span>
9. <span data-ttu-id="7f633-152">No painel **conceder** , clique em **bloquear acesso**e, em seguida, clique em **selecionar**.</span><span class="sxs-lookup"><span data-stu-id="7f633-152">In the **Grant** pane, click **Block access**, and then click **Select**.</span></span>
10. <span data-ttu-id="7f633-153">No painel **novo** , **clique em ativar** para **habilitar a política**e clique em **criar**.</span><span class="sxs-lookup"><span data-stu-id="7f633-153">In the **New** pane, click **On** for **Enable policy**, and then click **Create**.</span></span>
11. <span data-ttu-id="7f633-154">Feche as guias **portal do Azure** e **centro de administração do Microsoft 365** .</span><span class="sxs-lookup"><span data-stu-id="7f633-154">Close the **Azure portal** and **Microsoft 365 admin center** tabs.</span></span>

<span data-ttu-id="7f633-155">Para testar a primeira política, saia e entre com a conta DedicatedAdmin.</span><span class="sxs-lookup"><span data-stu-id="7f633-155">To test the first policy, sign out and sign in with the DedicatedAdmin account.</span></span> <span data-ttu-id="7f633-156">Você deve ser solicitado a configurar a MFA.</span><span class="sxs-lookup"><span data-stu-id="7f633-156">You should be prompted to configure MFA.</span></span> <span data-ttu-id="7f633-157">Isso demonstra que a primeira política está sendo aplicada.</span><span class="sxs-lookup"><span data-stu-id="7f633-157">This demonstrates that the first policy is being applied.</span></span>

## <a name="next-step"></a><span data-ttu-id="7f633-158">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="7f633-158">Next step</span></span>

<span data-ttu-id="7f633-159">Explorar recursos e funcionalidades adicionais de [identidade](m365-enterprise-test-lab-guides.md#identity) no ambiente de teste.</span><span class="sxs-lookup"><span data-stu-id="7f633-159">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="7f633-160">Confira também</span><span class="sxs-lookup"><span data-stu-id="7f633-160">See also</span></span>

[<span data-ttu-id="7f633-161">Roteiro de identidade</span><span class="sxs-lookup"><span data-stu-id="7f633-161">Identity roadmap</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="7f633-162">Guias do Laboratório de Teste do Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="7f633-162">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="7f633-163">Visão geral do Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="7f633-163">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="7f633-164">Documentação da Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="7f633-164">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
