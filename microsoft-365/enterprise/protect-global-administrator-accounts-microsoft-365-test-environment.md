---
title: Proteger contas de administrador global em seu ambiente de teste do Microsoft 365 para empresas
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
description: Use estas etapas para proteger contas de administrador global em seu ambiente de teste do Microsoft 365 para empresas.
ms.openlocfilehash: 3eab538b59e460857e2fa195aaacf51051f94d6b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50918877"
---
# <a name="protect-global-administrator-accounts-in-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="32e65-103">Proteger contas de administrador global em seu ambiente de teste do Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="32e65-103">Protect global administrator accounts in your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="32e65-104">*Este Guia de Laboratório de Teste só pode ser usado para o Microsoft 365 para ambientes de teste corporativos.*</span><span class="sxs-lookup"><span data-stu-id="32e65-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="32e65-105">Você pode impedir ataques digitais em sua organização garantindo que suas contas de administrador sejam o mais seguras possível.</span><span class="sxs-lookup"><span data-stu-id="32e65-105">You can prevent digital attacks on your organization by ensuring that your administrator accounts are as secure as possible.</span></span> 

<span data-ttu-id="32e65-106">Este artigo descreve como usar as políticas de acesso condicional do Azure Active Directory (Azure AD) para proteger contas de administrador global.</span><span class="sxs-lookup"><span data-stu-id="32e65-106">This article describes how to use Azure Active Directory (Azure AD) conditional access policies to protect global administrator accounts.</span></span>

<span data-ttu-id="32e65-107">A proteção de contas de administrador global em seu ambiente de teste do Microsoft 365 para empresas envolve duas fases:</span><span class="sxs-lookup"><span data-stu-id="32e65-107">Protecting global administrator accounts in your Microsoft 365 for enterprise test environment involves two phases:</span></span>
- [<span data-ttu-id="32e65-108">Fase 1: criar seu ambiente de teste do Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="32e65-108">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [<span data-ttu-id="32e65-109">Fase 2: Configurar políticas de acesso condicional</span><span class="sxs-lookup"><span data-stu-id="32e65-109">Phase 2: Configure conditional access policies</span></span>](#phase-2-configure-conditional-access-policies)

![Guias de Laboratório de Teste do Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="32e65-111">Para um mapa visual de todos os artigos na pilha guia de laboratório de teste do Microsoft 365 para empresas, vá para [o Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span><span class="sxs-lookup"><span data-stu-id="32e65-111">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>

## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="32e65-112">Fase 1: criar seu ambiente de teste do Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="32e65-112">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="32e65-113">Se você quiser testar a proteção da conta de administrador global de forma leve com os requisitos mínimos, siga as instruções em [Configuração base leve.](lightweight-base-configuration-microsoft-365-enterprise.md)</span><span class="sxs-lookup"><span data-stu-id="32e65-113">If you want to test global administrator account protection in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="32e65-114">Se você quiser testar a proteção de conta de administrador global em uma empresa simulada, siga as instruções em [Autenticação passagem](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="32e65-114">If you want to test global administrator account protection in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="32e65-115">Testar a proteção de conta de administrador global não exige o ambiente de teste empresarial simulado, que inclui uma intranet simulada conectada à Internet e a sincronização de diretórios para um AD DS (Serviços de Domínio do Active Directory).</span><span class="sxs-lookup"><span data-stu-id="32e65-115">Testing global administrator account protection does not require the simulated enterprise test environment, which includes a simulated intranet connected to the internet and directory synchronization for an Active Directory Domain Services (AD DS).</span></span> <span data-ttu-id="32e65-116">Ele é fornecido aqui como uma opção para que você possa testar a proteção da conta de administrador global e experimentá-la em um ambiente que representa uma organização típica.</span><span class="sxs-lookup"><span data-stu-id="32e65-116">It is provided here as an option so that you can test global administrator account protection and experiment with it in an environment that represents a typical organization.</span></span> 
  
## <a name="phase-2-configure-conditional-access-policies"></a><span data-ttu-id="32e65-117">Fase 2: Configurar políticas de acesso condicional</span><span class="sxs-lookup"><span data-stu-id="32e65-117">Phase 2: Configure conditional access policies</span></span>

<span data-ttu-id="32e65-118">Primeiro, crie uma nova conta de usuário como um administrador global dedicado.</span><span class="sxs-lookup"><span data-stu-id="32e65-118">First, create a new user account as a dedicated global administrator.</span></span>

1. <span data-ttu-id="32e65-119">Em uma guia separada, abra o Centro de administração [do Microsoft 365](https://admin.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="32e65-119">On a separate tab, open the [Microsoft 365 admin center](https://admin.microsoft.com/).</span></span>
2. <span data-ttu-id="32e65-120">Selecione **Usuários**  >  **Usuários ativos** e selecione Adicionar um **usuário**.</span><span class="sxs-lookup"><span data-stu-id="32e65-120">Select **Users** > **Active users**, and then select **Add a user**.</span></span>
3. <span data-ttu-id="32e65-121">No painel **Adicionar usuário,** insira **DedicatedAdmin** nas caixas **Nome,** **Nome** de exibição e Nome **de** Usuário.</span><span class="sxs-lookup"><span data-stu-id="32e65-121">In the **Add user** pane, enter **DedicatedAdmin** in the **First name**, **Display name**, and **Username** boxes.</span></span>
4. <span data-ttu-id="32e65-122">Selecione **Senha**, selecione **Deixe-me criar** a senha e insira uma senha forte.</span><span class="sxs-lookup"><span data-stu-id="32e65-122">Select **Password**, select **Let me create the password**, and then enter a strong password.</span></span> <span data-ttu-id="32e65-123">Grave a senha dessa nova conta em um local seguro.</span><span class="sxs-lookup"><span data-stu-id="32e65-123">Record the password for this new account in a secure location.</span></span>
5. <span data-ttu-id="32e65-124">Selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="32e65-124">Select **Next**.</span></span>
6. <span data-ttu-id="32e65-125">No painel **Atribuir licenças de** produto, selecione **Microsoft 365 E5** e selecione **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="32e65-125">In the **Assign product licenses** pane, select **Microsoft 365 E5**, and then select **Next**.</span></span>
7. <span data-ttu-id="32e65-126">No painel **Configurações opcionais,** selecione **Funções**  >  **O Centro de administração acessa o** administrador  >  **global**  >  **Next**.</span><span class="sxs-lookup"><span data-stu-id="32e65-126">In the **Optional settings** pane, select **Roles** > **Admin center access** > **Global admin** > **Next**.</span></span>
8. <span data-ttu-id="32e65-127">No painel **Você está quase pronto,** selecione **Concluir** a adição e, em seguida, selecione **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="32e65-127">On the **You're almost done** pane, select **Finish adding**, and then select **Close**.</span></span>

<span data-ttu-id="32e65-128">Em seguida, crie um novo grupo chamado GlobalAdmins e adicione a conta DedicatedAdmin a ela.</span><span class="sxs-lookup"><span data-stu-id="32e65-128">Next, create a new group named GlobalAdmins and add the DedicatedAdmin account to it.</span></span>

1. <span data-ttu-id="32e65-129">Na guia Centro de administração do **Microsoft 365,** selecione **Grupos** na navegação à esquerda e selecione **Grupos**.</span><span class="sxs-lookup"><span data-stu-id="32e65-129">On the **Microsoft 365 admin center** tab, select **Groups** in the left navigation, and then select **Groups**.</span></span>
2. <span data-ttu-id="32e65-130">Selecione **Adicionar um grupo**.</span><span class="sxs-lookup"><span data-stu-id="32e65-130">Select **Add a group**.</span></span>
3. <span data-ttu-id="32e65-131">No painel **Escolher um tipo de** grupo, selecione **Segurança** e, em seguida, selecione **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="32e65-131">In the **Choose a group type** pane, select **Security**, and then select **Next**.</span></span>
4. <span data-ttu-id="32e65-132">No painel **Configurar as noções básicas,** selecione **Criar grupo** e selecione **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="32e65-132">In the **Set up the basics** pane, select **Create group**, and then select **Close**.</span></span>
5. <span data-ttu-id="32e65-133">No painel **Revisar e concluir a adição de** grupo, insira **GlobalAdmins** e selecione **Next**.</span><span class="sxs-lookup"><span data-stu-id="32e65-133">In the **Review and finish adding group** pane, enter **GlobalAdmins**, and then select **Next**.</span></span>
7. <span data-ttu-id="32e65-134">Na lista de grupos, selecione o **grupo GlobalAdmins.**</span><span class="sxs-lookup"><span data-stu-id="32e65-134">In the list of groups, select the **GlobalAdmins** group.</span></span>
8. <span data-ttu-id="32e65-135">No painel **GlobalAdmins,** selecione **Membros** e selecione **Exibir todos e gerenciar membros**.</span><span class="sxs-lookup"><span data-stu-id="32e65-135">In the **GlobalAdmins** pane, select **Members**, and then select **View all and manage members**.</span></span>
9. <span data-ttu-id="32e65-136">No painel **GlobalAdmins,** selecione **Adicionar** membros, selecione a conta **DedicatedAdmin** e sua conta de administrador global e selecione **Salvar**  >  **Fechar**  >  **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="32e65-136">In the **GlobalAdmins** pane, select **Add members**, select the **DedicatedAdmin** account and your global admin account, and then select **Save** > **Close** > **Close**.</span></span>

<span data-ttu-id="32e65-137">Em seguida, crie políticas de acesso condicional para exigir autenticação multifacional para contas de administrador global e para negar a autenticação se o risco de entrada for médio ou alto.</span><span class="sxs-lookup"><span data-stu-id="32e65-137">Next, create conditional access policies to require multi-factor authentication for global administrator accounts and to deny authentication if the sign-in risk is medium or high.</span></span>

<span data-ttu-id="32e65-138">Esta primeira política exige que todas as contas de administrador global usem MFA.</span><span class="sxs-lookup"><span data-stu-id="32e65-138">This first policy requires that all global administrator accounts use MFA.</span></span>

1. <span data-ttu-id="32e65-139">Em uma nova guia do navegador, vá para [https://portal.azure.com](https://portal.azure.com) .</span><span class="sxs-lookup"><span data-stu-id="32e65-139">In a new tab of your browser, go to [https://portal.azure.com](https://portal.azure.com).</span></span>
2. <span data-ttu-id="32e65-140">Clique em Acesso Condicional de Segurança do **Azure Active**  >    >  Directory.</span><span class="sxs-lookup"><span data-stu-id="32e65-140">Click **Azure Active Directory** > **Security** > **Conditional Access**.</span></span>
3. <span data-ttu-id="32e65-141">No painel **Acesso condicional – Políticas,** selecione Política de linha de **base: Exigir MFA para administradores (visualização)**.</span><span class="sxs-lookup"><span data-stu-id="32e65-141">In the **Conditional access – Policies** pane, select **Baseline policy: Require MFA for admins (preview)**.</span></span>
4. <span data-ttu-id="32e65-142">No painel **Política de** Linha de Base, selecione Usar política imediatamente **> Salvar**.</span><span class="sxs-lookup"><span data-stu-id="32e65-142">In the **Baseline policy** pane, select **Use policy immediately > Save**.</span></span>

<span data-ttu-id="32e65-143">Esta segunda política bloqueia o acesso à autenticação de conta de administrador global quando o risco de entrada é médio ou alto.</span><span class="sxs-lookup"><span data-stu-id="32e65-143">This second policy blocks access to global administrator account authentication when the sign-in risk is medium or high.</span></span>

1. <span data-ttu-id="32e65-144">No painel **Acesso Condicional – Políticas,** selecione **Nova política**.</span><span class="sxs-lookup"><span data-stu-id="32e65-144">In the **Conditional access – Policies** pane, select **New policy**.</span></span>
2. <span data-ttu-id="32e65-145">No **novo** painel, insira **Administradores globais** em **Nome**.</span><span class="sxs-lookup"><span data-stu-id="32e65-145">In the **New** pane, enter **Global administrators** in **Name**.</span></span>
3. <span data-ttu-id="32e65-146">Na seção **Atribuições,** selecione **Usuários e grupos**.</span><span class="sxs-lookup"><span data-stu-id="32e65-146">In the **Assignments** section, select **Users and groups**.</span></span>
4. <span data-ttu-id="32e65-147">Na guia **Incluir** do painel **Usuários e** grupos, selecione Selecionar usuários **e grupos** Usuários e  >  **grupos**  >  **Selecione**.</span><span class="sxs-lookup"><span data-stu-id="32e65-147">On the **Include** tab of the **Users and groups** pane, select **Select users and groups** > **Users and groups** > **Select**.</span></span>
5. <span data-ttu-id="32e65-148">No painel **Selecionar,** selecione o **grupo GlobalAdmins** e selecione **Selecionar**  >  **Feito**.</span><span class="sxs-lookup"><span data-stu-id="32e65-148">In the **Select** pane, select the **GlobalAdmins** group, and then select **Select** > **Done**.</span></span>
6. <span data-ttu-id="32e65-149">Na seção **Atribuições,** selecione **Condições**.</span><span class="sxs-lookup"><span data-stu-id="32e65-149">In the **Assignments** section, select **Conditions**.</span></span>
7. <span data-ttu-id="32e65-150">No painel **Condições,** selecione **Risco** de entrar, selecione **Sim** para **Configurar,** **selecione** Alto e Médio **e** selecione **Selecionar** e **Feito**.</span><span class="sxs-lookup"><span data-stu-id="32e65-150">In the **Conditions** pane, select **Sign-in risk**, select **Yes** for **Configure**, select **High** and **Medium**, and then select **Select** and **Done**.</span></span>
8. <span data-ttu-id="32e65-151">Na seção **Controles de** acesso do **painel Novo,** selecione **Conceder**.</span><span class="sxs-lookup"><span data-stu-id="32e65-151">In the **Access controls** section of the **New** pane, select **Grant**.</span></span>
9. <span data-ttu-id="32e65-152">No painel **Conceder,** selecione **Bloquear acesso** e selecione **Selecionar**.</span><span class="sxs-lookup"><span data-stu-id="32e65-152">In the **Grant** pane, select **Block access**, and then select **Select**.</span></span>
10. <span data-ttu-id="32e65-153">No painel **Novo,** selecione **Ativar para** **Habilitar política** e selecione **Criar**.</span><span class="sxs-lookup"><span data-stu-id="32e65-153">In the **New** pane, select **On** for **Enable policy**, and then select **Create**.</span></span>
11. <span data-ttu-id="32e65-154">Feche as **guias do portal do Azure** e do Centro de administração do Microsoft **365.**</span><span class="sxs-lookup"><span data-stu-id="32e65-154">Close the **Azure portal** and **Microsoft 365 admin center** tabs.</span></span>

<span data-ttu-id="32e65-155">Para testar a primeira política, saia e entre com a conta DedicatedAdmin.</span><span class="sxs-lookup"><span data-stu-id="32e65-155">To test the first policy, sign out and sign in with the DedicatedAdmin account.</span></span> <span data-ttu-id="32e65-156">Você deve ser solicitado a configurar o MFA.</span><span class="sxs-lookup"><span data-stu-id="32e65-156">You should be prompted to configure MFA.</span></span> <span data-ttu-id="32e65-157">Isso demonstra que a primeira política está sendo aplicada.</span><span class="sxs-lookup"><span data-stu-id="32e65-157">This demonstrates that the first policy is being applied.</span></span>

## <a name="next-step"></a><span data-ttu-id="32e65-158">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="32e65-158">Next step</span></span>

<span data-ttu-id="32e65-159">Explorar recursos e funcionalidades adicionais de [identidade](m365-enterprise-test-lab-guides.md#identity) no ambiente de teste.</span><span class="sxs-lookup"><span data-stu-id="32e65-159">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="32e65-160">Confira também</span><span class="sxs-lookup"><span data-stu-id="32e65-160">See also</span></span>

[<span data-ttu-id="32e65-161">Roteiro de identidade</span><span class="sxs-lookup"><span data-stu-id="32e65-161">Identity roadmap</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="32e65-162">Guias do Laboratório de Teste do Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="32e65-162">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="32e65-163">Visão geral do Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="32e65-163">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="32e65-164">Documentação do Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="32e65-164">Microsoft 365 for enterprise documentation</span></span>](/microsoft-365-enterprise/)