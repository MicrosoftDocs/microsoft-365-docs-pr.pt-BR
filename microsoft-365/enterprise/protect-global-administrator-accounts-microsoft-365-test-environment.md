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
ms.openlocfilehash: 1ae04e4761ed86e087e647464ad522466ed6abef
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487631"
---
# <a name="protect-global-administrator-accounts-in-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="e960a-103">Proteger contas de administradores globais no seu ambiente de teste do Microsoft 365 for Enterprise</span><span class="sxs-lookup"><span data-stu-id="e960a-103">Protect global administrator accounts in your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="e960a-104">*Este guia de laboratório de teste só pode ser usado para o Microsoft 365 para ambientes de teste corporativos.*</span><span class="sxs-lookup"><span data-stu-id="e960a-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="e960a-105">Você pode impedir ataques digitais em sua organização, garantindo que suas contas de administrador sejam o mais seguras possível.</span><span class="sxs-lookup"><span data-stu-id="e960a-105">You can prevent digital attacks on your organization by ensuring that your administrator accounts are as secure as possible.</span></span> 

<span data-ttu-id="e960a-106">Este artigo descreve como usar as políticas de acesso condicional do Azure Active Directory (Azure AD) para proteger contas de administrador global.</span><span class="sxs-lookup"><span data-stu-id="e960a-106">This article describes how to use Azure Active Directory (Azure AD) conditional access policies to protect global administrator accounts.</span></span>

<span data-ttu-id="e960a-107">A proteção de contas de administrador global no seu ambiente de teste do Microsoft 365 for Enterprise envolve duas fases:</span><span class="sxs-lookup"><span data-stu-id="e960a-107">Protecting global administrator accounts in your Microsoft 365 for enterprise test environment involves two phases:</span></span>
- [<span data-ttu-id="e960a-108">Fase 1: desenvolver seu ambiente de teste do Microsoft 365 for Enterprise</span><span class="sxs-lookup"><span data-stu-id="e960a-108">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [<span data-ttu-id="e960a-109">Fase 2: configurar políticas de acesso condicional</span><span class="sxs-lookup"><span data-stu-id="e960a-109">Phase 2: Configure conditional access policies</span></span>](#phase-2-configure-conditional-access-policies)

![Guias de Laboratório de Teste do Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="e960a-111">Para obter um mapa Visual para todos os artigos da pilha do guia do laboratório de teste do Microsoft 365 for Enterprise, vá para a [pilha do guia do laboratório de teste da microsoft 365 para empresas](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span><span class="sxs-lookup"><span data-stu-id="e960a-111">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>

## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="e960a-112">Fase 1: desenvolver seu ambiente de teste do Microsoft 365 for Enterprise</span><span class="sxs-lookup"><span data-stu-id="e960a-112">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="e960a-113">Se você quiser testar a proteção da conta de administrador global de forma leve com os requisitos mínimos, siga as instruções em [configuração básica leve](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="e960a-113">If you want to test global administrator account protection in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="e960a-114">Se você quiser testar a proteção da conta de administrador global em uma empresa simulada, siga as instruções em [autenticação de passagem](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="e960a-114">If you want to test global administrator account protection in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="e960a-115">Testando a proteção da conta de administrador global não requer o ambiente de teste corporativo simulado, que inclui uma intranet simulada conectada à Internet e a sincronização de diretórios para um Active Directory Domain Services (AD DS).</span><span class="sxs-lookup"><span data-stu-id="e960a-115">Testing global administrator account protection does not require the simulated enterprise test environment, which includes a simulated intranet connected to the internet and directory synchronization for an Active Directory Domain Services (AD DS).</span></span> <span data-ttu-id="e960a-116">É fornecida aqui como uma opção para que você possa testar a proteção da conta de administrador global e experimentá-la em um ambiente que represente uma organização típica.</span><span class="sxs-lookup"><span data-stu-id="e960a-116">It is provided here as an option so that you can test global administrator account protection and experiment with it in an environment that represents a typical organization.</span></span> 
  
## <a name="phase-2-configure-conditional-access-policies"></a><span data-ttu-id="e960a-117">Fase 2: configurar políticas de acesso condicional</span><span class="sxs-lookup"><span data-stu-id="e960a-117">Phase 2: Configure conditional access policies</span></span>

<span data-ttu-id="e960a-118">Primeiro, crie uma nova conta de usuário como administrador global dedicado.</span><span class="sxs-lookup"><span data-stu-id="e960a-118">First, create a new user account as a dedicated global administrator.</span></span>

1. <span data-ttu-id="e960a-119">Em uma guia separada, abra o [centro de administração do Microsoft 365](https://admin.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="e960a-119">On a separate tab, open the [Microsoft 365 admin center](https://admin.microsoft.com/).</span></span>
2. <span data-ttu-id="e960a-120">Selecione **usuários**  >  **ativos**do usuário e, em seguida, selecione **Adicionar um usuário**.</span><span class="sxs-lookup"><span data-stu-id="e960a-120">Select **Users** > **Active users**, and then select **Add a user**.</span></span>
3. <span data-ttu-id="e960a-121">No painel **Adicionar usuário** , digite **DedicatedAdmin** nas caixas **nome**, nome para **exibição**e nome de **usuário** .</span><span class="sxs-lookup"><span data-stu-id="e960a-121">In the **Add user** pane, enter **DedicatedAdmin** in the **First name**, **Display name**, and **Username** boxes.</span></span>
4. <span data-ttu-id="e960a-122">Selecione **senha**, selecione **deixe-me criar a senha**e, em seguida, digite uma senha forte.</span><span class="sxs-lookup"><span data-stu-id="e960a-122">Select **Password**, select **Let me create the password**, and then enter a strong password.</span></span> <span data-ttu-id="e960a-123">Registre a senha dessa nova conta em um local seguro.</span><span class="sxs-lookup"><span data-stu-id="e960a-123">Record the password for this new account in a secure location.</span></span>
5. <span data-ttu-id="e960a-124">Selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="e960a-124">Select **Next**.</span></span>
6. <span data-ttu-id="e960a-125">No painel **atribuir licenças de produtos** , selecione **Microsoft 365 E5**e, em seguida, selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="e960a-125">In the **Assign product licenses** pane, select **Microsoft 365 E5**, and then select **Next**.</span></span>
7. <span data-ttu-id="e960a-126">No painel **configurações opcionais** , selecione o centro de administração de **funções**de  >  **Admin center access**  >  **administrador global**  >  **próximo**.</span><span class="sxs-lookup"><span data-stu-id="e960a-126">In the **Optional settings** pane, select **Roles** > **Admin center access** > **Global admin** > **Next**.</span></span>
8. <span data-ttu-id="e960a-127">No painel **você está quase concluído** , selecione **concluir adição**e, em seguida, selecione **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="e960a-127">On the **You're almost done** pane, select **Finish adding**, and then select **Close**.</span></span>

<span data-ttu-id="e960a-128">Em seguida, crie um novo grupo chamado GlobalAdmins e adicione a conta DedicatedAdmin a ele.</span><span class="sxs-lookup"><span data-stu-id="e960a-128">Next, create a new group named GlobalAdmins and add the DedicatedAdmin account to it.</span></span>

1. <span data-ttu-id="e960a-129">Na guia **centro de administração do Microsoft 365** , selecione **grupos** na navegação à esquerda e, em seguida, selecione **grupos**.</span><span class="sxs-lookup"><span data-stu-id="e960a-129">On the **Microsoft 365 admin center** tab, select **Groups** in the left navigation, and then select **Groups**.</span></span>
2. <span data-ttu-id="e960a-130">Selecione **Adicionar um grupo**.</span><span class="sxs-lookup"><span data-stu-id="e960a-130">Select **Add a group**.</span></span>
3. <span data-ttu-id="e960a-131">No painel **escolher um tipo de grupo** , selecione **segurança**e, em seguida, selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="e960a-131">In the **Choose a group type** pane, select **Security**, and then select **Next**.</span></span>
4. <span data-ttu-id="e960a-132">No painel **Configurar o básico** , selecione **Criar grupo**e, em seguida, selecione **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="e960a-132">In the **Set up the basics** pane, select **Create group**, and then select **Close**.</span></span>
5. <span data-ttu-id="e960a-133">No painel **revisar e concluir a adição de grupo** , insira **GlobalAdmins**e, em seguida, selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="e960a-133">In the **Review and finish adding group** pane, enter **GlobalAdmins**, and then select **Next**.</span></span>
7. <span data-ttu-id="e960a-134">Na lista de grupos, selecione o grupo **GlobalAdmins** .</span><span class="sxs-lookup"><span data-stu-id="e960a-134">In the list of groups, select the **GlobalAdmins** group.</span></span>
8. <span data-ttu-id="e960a-135">No painel **GlobalAdmins** , selecione **Membros**e, em seguida, selecione **Exibir todos e gerenciar Membros**.</span><span class="sxs-lookup"><span data-stu-id="e960a-135">In the **GlobalAdmins** pane, select **Members**, and then select **View all and manage members**.</span></span>
9. <span data-ttu-id="e960a-136">No painel **GlobalAdmins** , selecione **adicionar membros**, selecione a conta **DedicatedAdmin** e sua conta de administrador global e selecione salvar fechar **Save**  >  **Close**  >  **fechar**.</span><span class="sxs-lookup"><span data-stu-id="e960a-136">In the **GlobalAdmins** pane, select **Add members**, select the **DedicatedAdmin** account and your global admin account, and then select **Save** > **Close** > **Close**.</span></span>

<span data-ttu-id="e960a-137">Em seguida, crie políticas de acesso condicional para exigir a autenticação multifator para contas de administrador global e para negar a autenticação se o risco de entrada for médio ou alto.</span><span class="sxs-lookup"><span data-stu-id="e960a-137">Next, create conditional access policies to require multi-factor authentication for global administrator accounts and to deny authentication if the sign-in risk is medium or high.</span></span>

<span data-ttu-id="e960a-138">Essa primeira política requer que todas as contas de administrador global usem MFA.</span><span class="sxs-lookup"><span data-stu-id="e960a-138">This first policy requires that all global administrator accounts use MFA.</span></span>

1. <span data-ttu-id="e960a-139">Em uma nova guia do navegador, vá para [https://portal.azure.com](https://portal.azure.com) .</span><span class="sxs-lookup"><span data-stu-id="e960a-139">In a new tab of your browser, go to [https://portal.azure.com](https://portal.azure.com).</span></span>
2. <span data-ttu-id="e960a-140">Clique em acesso condicional de segurança **do Azure Active Directory**  >  **Security**  >  **Conditional Access**.</span><span class="sxs-lookup"><span data-stu-id="e960a-140">Click **Azure Active Directory** > **Security** > **Conditional Access**.</span></span>
3. <span data-ttu-id="e960a-141">No painel **acesso condicional – políticas** , selecione **política de linha de base: exigir MFA para administradores (visualização)**.</span><span class="sxs-lookup"><span data-stu-id="e960a-141">In the **Conditional access – Policies** pane, select **Baseline policy: Require MFA for admins (preview)**.</span></span>
4. <span data-ttu-id="e960a-142">No painel **política de linha de base** , selecione **usar política imediatamente > salvar**.</span><span class="sxs-lookup"><span data-stu-id="e960a-142">In the **Baseline policy** pane, select **Use policy immediately > Save**.</span></span>

<span data-ttu-id="e960a-143">Essa segunda política bloqueia o acesso à autenticação de conta de administrador global quando o risco de entrada é médio ou alto.</span><span class="sxs-lookup"><span data-stu-id="e960a-143">This second policy blocks access to global administrator account authentication when the sign-in risk is medium or high.</span></span>

1. <span data-ttu-id="e960a-144">No painel **acesso condicional – políticas** , selecione **nova política**.</span><span class="sxs-lookup"><span data-stu-id="e960a-144">In the **Conditional access – Policies** pane, select **New policy**.</span></span>
2. <span data-ttu-id="e960a-145">No painel **novo** , insira **administradores globais** em **nome**.</span><span class="sxs-lookup"><span data-stu-id="e960a-145">In the **New** pane, enter **Global administrators** in **Name**.</span></span>
3. <span data-ttu-id="e960a-146">Na seção **atribuições** , selecione **usuários e grupos**.</span><span class="sxs-lookup"><span data-stu-id="e960a-146">In the **Assignments** section, select **Users and groups**.</span></span>
4. <span data-ttu-id="e960a-147">Na guia **incluir** do painel **usuários e grupos** , selecione Selecionar **usuários e grupos**  >  **usuários e grupos**  >  **selecionar**.</span><span class="sxs-lookup"><span data-stu-id="e960a-147">On the **Include** tab of the **Users and groups** pane, select **Select users and groups** > **Users and groups** > **Select**.</span></span>
5. <span data-ttu-id="e960a-148">No painel **selecionar** , selecione o grupo **GlobalAdmins** **e selecione**  >  **concluído**.</span><span class="sxs-lookup"><span data-stu-id="e960a-148">In the **Select** pane, select the **GlobalAdmins** group, and then select **Select** > **Done**.</span></span>
6. <span data-ttu-id="e960a-149">Na seção **atribuições** , selecione **condições**.</span><span class="sxs-lookup"><span data-stu-id="e960a-149">In the **Assignments** section, select **Conditions**.</span></span>
7. <span data-ttu-id="e960a-150">No painel **condições** , selecione **risco de entrada**, selecione **Sim** para **Configurar**, selecione **alta** e **média**e, em seguida, selecione **selecionar** e **concluir**.</span><span class="sxs-lookup"><span data-stu-id="e960a-150">In the **Conditions** pane, select **Sign-in risk**, select **Yes** for **Configure**, select **High** and **Medium**, and then select **Select** and **Done**.</span></span>
8. <span data-ttu-id="e960a-151">Na seção **controles de acesso** do painel **novo** , selecione **conceder**.</span><span class="sxs-lookup"><span data-stu-id="e960a-151">In the **Access controls** section of the **New** pane, select **Grant**.</span></span>
9. <span data-ttu-id="e960a-152">No painel **conceder** , selecione **bloquear acesso**e selecione **selecionar**.</span><span class="sxs-lookup"><span data-stu-id="e960a-152">In the **Grant** pane, select **Block access**, and then select **Select**.</span></span>
10. <span data-ttu-id="e960a-153">No painel **novo** , selecione **Ativar** para **habilitar política**e, em seguida, selecione **criar**.</span><span class="sxs-lookup"><span data-stu-id="e960a-153">In the **New** pane, select **On** for **Enable policy**, and then select **Create**.</span></span>
11. <span data-ttu-id="e960a-154">Feche as guias **portal do Azure** e **centro de administração do Microsoft 365** .</span><span class="sxs-lookup"><span data-stu-id="e960a-154">Close the **Azure portal** and **Microsoft 365 admin center** tabs.</span></span>

<span data-ttu-id="e960a-155">Para testar a primeira política, saia e entre com a conta DedicatedAdmin.</span><span class="sxs-lookup"><span data-stu-id="e960a-155">To test the first policy, sign out and sign in with the DedicatedAdmin account.</span></span> <span data-ttu-id="e960a-156">Você deve ser solicitado a configurar a MFA.</span><span class="sxs-lookup"><span data-stu-id="e960a-156">You should be prompted to configure MFA.</span></span> <span data-ttu-id="e960a-157">Isso demonstra que a primeira política está sendo aplicada.</span><span class="sxs-lookup"><span data-stu-id="e960a-157">This demonstrates that the first policy is being applied.</span></span>

## <a name="next-step"></a><span data-ttu-id="e960a-158">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="e960a-158">Next step</span></span>

<span data-ttu-id="e960a-159">Explorar recursos e funcionalidades adicionais de [identidade](m365-enterprise-test-lab-guides.md#identity) no ambiente de teste.</span><span class="sxs-lookup"><span data-stu-id="e960a-159">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="e960a-160">Confira também</span><span class="sxs-lookup"><span data-stu-id="e960a-160">See also</span></span>

[<span data-ttu-id="e960a-161">Roteiro de identidade</span><span class="sxs-lookup"><span data-stu-id="e960a-161">Identity roadmap</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="e960a-162">Guias do Laboratório de Teste do Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="e960a-162">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="e960a-163">Visão geral do Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="e960a-163">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="e960a-164">Documentação da Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="e960a-164">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
