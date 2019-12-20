---
title: Proteger contas de administradores globais no ambiente de teste do Microsoft 365 Enterprise
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
description: Use estas etapas para proteger contas de administrador global no ambiente de teste do Microsoft 365 Enterprise.
ms.openlocfilehash: 32e5983532c89c6ada106ed32d8ef3eabd5dc569
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/19/2019
ms.locfileid: "40801378"
---
# <a name="protect-global-administrator-accounts-in-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="a63ee-103">Proteger contas de administradores globais no ambiente de teste do Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="a63ee-103">Protect global administrator accounts in your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="a63ee-104">*Este Guia de Laboratório de Testes pode ser usado apenas em ambientes de teste do Microsoft 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="a63ee-104">*This Test Lab Guide can only be used for Microsoft 365 Enterprise test environments.*</span></span>

<span data-ttu-id="a63ee-105">Você pode impedir ataques digitais em sua organização, garantindo que suas contas de administrador sejam o mais seguras possível.</span><span class="sxs-lookup"><span data-stu-id="a63ee-105">You can prevent digital attacks on your organization by ensuring that your administrator accounts are as secure as possible.</span></span> <span data-ttu-id="a63ee-106">Este artigo descreve como usar as políticas de acesso condicional do Azure Active Directory (Azure AD) para proteger contas de administrador global.</span><span class="sxs-lookup"><span data-stu-id="a63ee-106">This article describes how to use Azure Active Directory (Azure AD) conditional access policies to protect global administrator accounts.</span></span>

<span data-ttu-id="a63ee-107">Há duas fases para proteger as contas de administrador global no seu ambiente de teste do Microsoft 365 Enterprise:</span><span class="sxs-lookup"><span data-stu-id="a63ee-107">There are two phases to protecting global administrator accounts in your Microsoft 365 Enterprise test environment:</span></span>

1.  <span data-ttu-id="a63ee-108">Criar o ambiente de teste do Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="a63ee-108">Create the Microsoft 365 Enterprise test environment.</span></span>
2.  <span data-ttu-id="a63ee-109">Proteger sua conta de administrador global dedicado.</span><span class="sxs-lookup"><span data-stu-id="a63ee-109">Protect your dedicated global administrator account.</span></span>

![Guias de laboratório de teste da Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="a63ee-111">Clique [aqui](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) para ver um mapa visual de todos os artigos da pilha do Guia de Laboratório de Teste do Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="a63ee-111">Click [here](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>

## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="a63ee-112">Fase 1: Criar o ambiente de teste do Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="a63ee-112">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="a63ee-113">Se você só quiser testar a proteção da conta de administrador global de forma leve com os requisitos mínimos, siga as instruções em [configuração básica leve](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="a63ee-113">If you just want to test global administrator account protection in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="a63ee-114">Se você quiser testar a proteção da conta de administrador global em uma empresa simulada, siga as instruções em [autenticação de passagem](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="a63ee-114">If you want to test global administrator account protection in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="a63ee-115">Testando a proteção da conta de administrador global não requer o ambiente de teste corporativo simulado, que inclui uma intranet simulada conectada à Internet e a sincronização de diretórios para um Active Directory Domain Services (AD DS).</span><span class="sxs-lookup"><span data-stu-id="a63ee-115">Testing global administrator account protection does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS).</span></span> <span data-ttu-id="a63ee-116">É fornecida aqui como uma opção para que você possa testar a proteção da conta de administrador global e experimentá-la em um ambiente que represente uma organização típica.</span><span class="sxs-lookup"><span data-stu-id="a63ee-116">It is provided here as an option so that you can test global administrator account protection and experiment with it in an environment that represents a typical organization.</span></span> 
  
## <a name="phase-2-configure-conditional-access-policies"></a><span data-ttu-id="a63ee-117">Fase 2: configurar políticas de acesso condicional</span><span class="sxs-lookup"><span data-stu-id="a63ee-117">Phase 2: Configure conditional access policies</span></span>

<span data-ttu-id="a63ee-118">Primeiro, crie uma nova conta de usuário como administrador global dedicado.</span><span class="sxs-lookup"><span data-stu-id="a63ee-118">First, create a new user account as a dedicated global administrator.</span></span>

1. <span data-ttu-id="a63ee-119">Em uma guia separada, abra o [centro de administração do Microsoft 365](https://admin.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="a63ee-119">On a separate tab, open the [Microsoft 365 admin center](https://admin.microsoft.com/).</span></span>
2. <span data-ttu-id="a63ee-120">Clique em **usuários > usuários ativos**e, em seguida, clique em **Adicionar um usuário**.</span><span class="sxs-lookup"><span data-stu-id="a63ee-120">Click **Users > Active users**, and then click **Add a user**.</span></span>
3. <span data-ttu-id="a63ee-121">No painel **Adicionar usuário** , digite **DedicatedAdmin** em **nome**, nome para **exibição**e nome de **usuário**.</span><span class="sxs-lookup"><span data-stu-id="a63ee-121">In the **Add user** pane, type **DedicatedAdmin** in **First name**, **Display name**, and **Username**.</span></span>
4. <span data-ttu-id="a63ee-122">Clique em **senha**, clique em **deixe-me criar a senha**e digite uma senha forte.</span><span class="sxs-lookup"><span data-stu-id="a63ee-122">Click **Password**, click **Let me create the password**, and then type a strong password.</span></span> <span data-ttu-id="a63ee-123">Registre a senha dessa nova conta em um local seguro.</span><span class="sxs-lookup"><span data-stu-id="a63ee-123">Record the password for this new account in a secure location.</span></span>
5. <span data-ttu-id="a63ee-124">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="a63ee-124">Click **Next**.</span></span>
6. <span data-ttu-id="a63ee-125">No painel **atribuir licenças de produtos** , selecione **Microsoft 365 E5** ou **Office 365 E5**e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="a63ee-125">In the **Assign product licenses** pane, select **Microsoft 365 E5** or **Office 365 E5**, and then click **Next**.</span></span>
7. <span data-ttu-id="a63ee-126">No painel **configurações opcionais** , clique em **funções**e selecione **acesso do centro de administração** e **administrador global**. Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="a63ee-126">In the **Optional settings** pane, click **Roles**, and then select **Admin center access** and **Global admin**. Click **Next**.</span></span>
8. <span data-ttu-id="a63ee-127">No painel **você está quase concluído** , clique em **concluir adição**e, em seguida, clique em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="a63ee-127">On the **You're almost done** pane, click **Finish adding**, and then click **Close**.</span></span>

<span data-ttu-id="a63ee-128">Em seguida, crie um novo grupo chamado GlobalAdmins e adicione a conta DedicatedAdmin a ele.</span><span class="sxs-lookup"><span data-stu-id="a63ee-128">Next, create a new group named GlobalAdmins and add the DedicatedAdmin account to it.</span></span>

1. <span data-ttu-id="a63ee-129">Na guia **centro de administração do Microsoft 365** , clique em **grupos** na navegação à esquerda e, em seguida, clique em **grupos**.</span><span class="sxs-lookup"><span data-stu-id="a63ee-129">On the **Microsoft 365 admin center** tab, click **Groups** in the left navigation, and then click **Groups**.</span></span>
2. <span data-ttu-id="a63ee-130">Clique em **Adicionar um grupo**.</span><span class="sxs-lookup"><span data-stu-id="a63ee-130">Click **Add a group**.</span></span>
3. <span data-ttu-id="a63ee-131">No painel **escolher um tipo de grupo** , selecione **segurança**e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="a63ee-131">In the **Choose a group type** pane, select **Security**, and then click **Next**.</span></span>
4. <span data-ttu-id="a63ee-132">No painel **Configurar o básico** , clique em **Criar grupo**e, em seguida, clique em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="a63ee-132">In the **Set up the basics** pane, click **Create group**, and then click **Close**.</span></span>
5. <span data-ttu-id="a63ee-133">No painel **revisar e concluir a adição de grupo** , digite **GlobalAdmins**e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="a63ee-133">In the **Review and finish adding group** pane, type **GlobalAdmins**, and then click **Next**.</span></span>
7. <span data-ttu-id="a63ee-134">Na lista de grupos, clique no grupo **GlobalAdmins** .</span><span class="sxs-lookup"><span data-stu-id="a63ee-134">In the list of groups, click the **GlobalAdmins** group.</span></span>
8. <span data-ttu-id="a63ee-135">No painel **GlobalAdmins** , clique em **Membros**e, em seguida, clique em **Exibir todos e gerenciar Membros**.</span><span class="sxs-lookup"><span data-stu-id="a63ee-135">In the **GlobalAdmins** pane, click **Members**, and then click **View all and manage members**.</span></span>
9. <span data-ttu-id="a63ee-136">No painel **GlobalAdmins** , clique em **adicionar membros**, selecione a conta **DedicatedAdmin** e a conta de administrador global e clique em **salvar > fechar > fechar**.</span><span class="sxs-lookup"><span data-stu-id="a63ee-136">In the **GlobalAdmins** pane, click **Add members**, select the **DedicatedAdmin** account and your global admin account, and then click **Save > Close > Close**.</span></span>

<span data-ttu-id="a63ee-137">Em seguida, crie políticas de acesso condicional para exigir a autenticação multifator para contas de administrador global e para negar a autenticação se o risco de entrada for médio ou alto.</span><span class="sxs-lookup"><span data-stu-id="a63ee-137">Next, create conditional access policies to require multifactor authentication for global administrator accounts and to deny authentication if the sign-in risk is medium or high.</span></span>

<span data-ttu-id="a63ee-138">Essa primeira política requer que todas as contas de administrador global usem MFA.</span><span class="sxs-lookup"><span data-stu-id="a63ee-138">This first policy requires that all global administrator accounts use MFA.</span></span>

1. <span data-ttu-id="a63ee-139">Em uma nova guia do navegador, vá para [https://portal.azure.com](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="a63ee-139">In a new tab of your browser, go to [https://portal.azure.com](https://portal.azure.com).</span></span>
2. <span data-ttu-id="a63ee-140">Clique em **Azure Active Directory > segurança > acesso condicional**.</span><span class="sxs-lookup"><span data-stu-id="a63ee-140">Click **Azure Active Directory > Security > Conditional Access**.</span></span>
3. <span data-ttu-id="a63ee-141">No painel **acesso condicional – políticas** , clique em **política de linha de base: exigir MFA para administradores (visualização)**.</span><span class="sxs-lookup"><span data-stu-id="a63ee-141">In the **Conditional access – Policies** pane, click **Baseline policy: Require MFA for admins (preview)**.</span></span>
4. <span data-ttu-id="a63ee-142">No painel **diretiva de linha de base** , clique em **usar política imediatamente > salvar**.</span><span class="sxs-lookup"><span data-stu-id="a63ee-142">In the **Baseline policy** pane, click **Use policy immediately > Save**.</span></span>

<span data-ttu-id="a63ee-143">Essa segunda política bloqueia o acesso à autenticação de conta de administrador global quando o risco de entrada é médio ou alto.</span><span class="sxs-lookup"><span data-stu-id="a63ee-143">This second policy blocks access to global administrator account authentication when the sign-in risk is medium or high.</span></span>

1. <span data-ttu-id="a63ee-144">No painel **acesso condicional – políticas** , clique em **nova política**.</span><span class="sxs-lookup"><span data-stu-id="a63ee-144">In the **Conditional access – Policies** pane, click **New policy**.</span></span>
2. <span data-ttu-id="a63ee-145">No painel **novo** , digite **administradores globais** em **nome**.</span><span class="sxs-lookup"><span data-stu-id="a63ee-145">In the **New** pane, type **Global administrators** in **Name**.</span></span>
3. <span data-ttu-id="a63ee-146">Na seção **atribuições** , clique em **usuários e grupos**.</span><span class="sxs-lookup"><span data-stu-id="a63ee-146">In the **Assignments** section, click **Users and groups**.</span></span>
4. <span data-ttu-id="a63ee-147">Na guia **incluir** do painel **usuários e grupos** , clique em **Selecionar usuários e grupos > usuários e grupos > selecionar**.</span><span class="sxs-lookup"><span data-stu-id="a63ee-147">On the **Include** tab of the **Users and groups** pane, click **Select users and groups > Users and groups > Select**.</span></span>
5. <span data-ttu-id="a63ee-148">No painel **selecionar** , clique no grupo **GlobalAdmins** e, em seguida, clique em **selecionar > concluído**.</span><span class="sxs-lookup"><span data-stu-id="a63ee-148">In the **Select** pane, click the **GlobalAdmins** group, and then click **Select > Done**.</span></span>
6. <span data-ttu-id="a63ee-149">Na seção **atribuições** , clique em **condições**.</span><span class="sxs-lookup"><span data-stu-id="a63ee-149">In the **Assignments** section, click **Conditions**.</span></span>
7. <span data-ttu-id="a63ee-150">No painel **condições** , clique em **risco de entrada**, clique em **Sim** para **Configurar**, clique **em alta** e **média**e, em seguida, clique em **selecionar** e **concluir**.</span><span class="sxs-lookup"><span data-stu-id="a63ee-150">In the **Conditions** pane, click **Sign-in risk**, click **Yes** for **Configure**, click **High** and **Medium**, and then click **Select** and **Done**.</span></span>
8. <span data-ttu-id="a63ee-151">Na seção **controles de acesso** do painel **novo** , clique em **conceder**.</span><span class="sxs-lookup"><span data-stu-id="a63ee-151">In the **Access controls** section of the **New** pane, click **Grant**.</span></span>
9. <span data-ttu-id="a63ee-152">No painel **conceder** , clique em **bloquear acesso**e, em seguida, clique em **selecionar**.</span><span class="sxs-lookup"><span data-stu-id="a63ee-152">In the **Grant** pane, click **Block access**, and then click **Select**.</span></span>
10. <span data-ttu-id="a63ee-153">No painel **novo** , **clique em ativar** para **habilitar a política**e clique em **criar**.</span><span class="sxs-lookup"><span data-stu-id="a63ee-153">In the **New** pane, click **On** for **Enable policy**, and then click **Create**.</span></span>
11. <span data-ttu-id="a63ee-154">Feche as guias **portal do Azure** e **centro de administração do Microsoft 365** .</span><span class="sxs-lookup"><span data-stu-id="a63ee-154">Close the **Azure portal** and **Microsoft 365 admin center** tabs.</span></span>

<span data-ttu-id="a63ee-155">Para testar a primeira política, saia e entre com a conta DedicatedAdmin.</span><span class="sxs-lookup"><span data-stu-id="a63ee-155">To test the first policy, sign out and sign in with the DedicatedAdmin account.</span></span> <span data-ttu-id="a63ee-156">Você deve ser solicitado a configurar a MFA.</span><span class="sxs-lookup"><span data-stu-id="a63ee-156">You should be prompted to configure MFA.</span></span> <span data-ttu-id="a63ee-157">Isso demonstra que a primeira política está sendo aplicada.</span><span class="sxs-lookup"><span data-stu-id="a63ee-157">This demonstrates that the first policy is being applied.</span></span>

<span data-ttu-id="a63ee-158">Consulte a etapa [proteger contas de administrador global](identity-create-protect-global-admins.md#identity-global-admin) na fase de identidade para obter informações e links para proteger suas contas de administrador global em produção.</span><span class="sxs-lookup"><span data-stu-id="a63ee-158">See the [Protect global administrator accounts](identity-create-protect-global-admins.md#identity-global-admin) step in the Identity phase for information and links to protect your global administrator accounts in production.</span></span>

## <a name="next-step"></a><span data-ttu-id="a63ee-159">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="a63ee-159">Next step</span></span>

<span data-ttu-id="a63ee-160">Explorar recursos e funcionalidades adicionais de [identidade](m365-enterprise-test-lab-guides.md#identity) no ambiente de teste.</span><span class="sxs-lookup"><span data-stu-id="a63ee-160">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="a63ee-161">Confira também</span><span class="sxs-lookup"><span data-stu-id="a63ee-161">See also</span></span>

[<span data-ttu-id="a63ee-162">Fase 2: Identidade</span><span class="sxs-lookup"><span data-stu-id="a63ee-162">Phase 2: Identity</span></span>](identity-infrastructure.md)

[<span data-ttu-id="a63ee-163">Guias do Laboratório de Teste do Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="a63ee-163">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="a63ee-164">Implantação do Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="a63ee-164">Microsoft 365 Enterprise deployment</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="a63ee-165">Documentação do Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="a63ee-165">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
