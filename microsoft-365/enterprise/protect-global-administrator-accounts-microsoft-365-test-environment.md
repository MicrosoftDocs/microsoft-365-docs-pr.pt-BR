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
ms.openlocfilehash: cded424188447f96e5614f31d3e207bb541d438e
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32290854"
---
# <a name="protect-global-administrator-accounts-in-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="6e043-103">Proteger contas de administradores globais no ambiente de teste do Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="6e043-103">Protect global administrator accounts in your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="6e043-104">Você pode impedir ataques digitais em sua organização, garantindo que suas contas de administrador sejam o mais seguras possível.</span><span class="sxs-lookup"><span data-stu-id="6e043-104">You can prevent digital attacks on your organization by ensuring that your administrator accounts are as secure as possible.</span></span> <span data-ttu-id="6e043-105">Este artigo descreve como usar o Office 365 Cloud app Security e as políticas de acesso condicional do Azure AD para proteger contas de administrador global.</span><span class="sxs-lookup"><span data-stu-id="6e043-105">This article describes how to use Office 365 Cloud App Security and Azure AD conditional access policies to protect global administrator accounts.</span></span>

<span data-ttu-id="6e043-106">Há duas fases para proteger as contas de administrador global no seu ambiente de teste do Microsoft 365 Enterprise:</span><span class="sxs-lookup"><span data-stu-id="6e043-106">There are two phases to protecting global administrator accounts in your Microsoft 365 Enterprise test environment:</span></span>

1.  <span data-ttu-id="6e043-107">Crie o ambiente de teste do Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="6e043-107">Create the Microsoft 365 Enterprise test environment.</span></span>
2.  <span data-ttu-id="6e043-108">Proteger sua conta de administrador global dedicado.</span><span class="sxs-lookup"><span data-stu-id="6e043-108">Protect your dedicated global administrator account.</span></span>

![Guias de laboratório de teste da Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="6e043-110">Clique [aqui](https://aka.ms/m365etlgstack) para ver um mapa visual de todos os artigos da pilha do Guia de Laboratório de Teste do Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="6e043-110">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>

> [!NOTE]
> <span data-ttu-id="6e043-111">O ambiente de teste do Microsoft 365 Enterprise usa versões E5 do Office 365 e Enterprise Management + Security (EMS).</span><span class="sxs-lookup"><span data-stu-id="6e043-111">The Microsoft 365 Enterprise test environment uses E5 versions of Office 365 and Enterprise Management + Security (EMS).</span></span> <span data-ttu-id="6e043-112">O recurso de segurança do Office 365 Cloud app só está disponível na versão E5 do Office 365.</span><span class="sxs-lookup"><span data-stu-id="6e043-112">The Office 365 Cloud App Security feature is only available in the E5 version Office 365.</span></span> 

## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="6e043-113">Fase 1: criar seu ambiente de teste do Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="6e043-113">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="6e043-114">Se você só quiser testar a proteção da conta de administrador global de forma leve com os requisitos mínimos, siga as instruções em [configuração básica leve](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="6e043-114">If you just want to test global administrator account protection in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="6e043-115">Se você quiser testar a proteção da conta de administrador global em uma empresa simulada, siga as instruções em [autenticação de passagem](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="6e043-115">If you want to test global administrator account protection in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>

  
> [!NOTE]
> <span data-ttu-id="6e043-116">Testando a proteção da conta de administrador global não requer o ambiente de teste corporativo simulado, que inclui uma intranet simulada conectada à Internet e a sincronização de diretórios para um Active Directory Domain Services (AD DS).</span><span class="sxs-lookup"><span data-stu-id="6e043-116">Testing global administrator account protection does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS).</span></span> <span data-ttu-id="6e043-117">É fornecida aqui como uma opção para que você possa testar a proteção da conta de administrador global e experimentá-la em um ambiente que represente uma organização típica.</span><span class="sxs-lookup"><span data-stu-id="6e043-117">It is provided here as an option so that you can test global administrator account protection and experiment with it in an environment that represents a typical organization.</span></span> 
  
## <a name="phase-2-configure-cloud-app-security-and-conditional-access-policies"></a><span data-ttu-id="6e043-118">Fase 2: configurar a segurança do aplicativo de nuvem e as políticas de acesso condicional</span><span class="sxs-lookup"><span data-stu-id="6e043-118">Phase 2: Configure Cloud App Security and conditional access policies</span></span>

<span data-ttu-id="6e043-119">Primeiro, crie uma política de segurança de aplicativo em nuvem do Office 365 para monitorar a atividade de conta de administrador global e enviar alertas para o endereço de email de sua conta de administrador global.</span><span class="sxs-lookup"><span data-stu-id="6e043-119">First, create an Office 365 Cloud App Security policy to monitor global administrator account activity and send alerts to the email address of your global administrator account.</span></span> 

1. <span data-ttu-id="6e043-120">Entre no portal de [conformidade do & de segurança do Office 365](https://protection.office.com/) usando sua conta de administrador global.</span><span class="sxs-lookup"><span data-stu-id="6e043-120">Sign in to the [Office 365 Security & Compliance portal](https://protection.office.com/) using your global administrator account.</span></span>
2. <span data-ttu-id="6e043-121">No painel de navegação esquerdo, clique em **alertas _GT_ Gerenciar alertas avançados**.</span><span class="sxs-lookup"><span data-stu-id="6e043-121">In the left navigation pane, click **Alerts > Manage advanced alerts**.</span></span>
3. <span data-ttu-id="6e043-122">Na página **Gerenciar alertas avançados** , clique em **ativar o Office 365 Cloud app Security**e clique em **ir para o Office 365 Cloud app Security**.</span><span class="sxs-lookup"><span data-stu-id="6e043-122">On the **Manage advanced alerts** page, click **Turn on Office 365 Cloud App Security**, and then click **Go to Office 365 Cloud App Security**.</span></span>
4. <span data-ttu-id="6e043-123">Na guia novo **painel** , clique em **controlar políticas de >**.</span><span class="sxs-lookup"><span data-stu-id="6e043-123">On the new **Dashboard** tab, click **Control > Policies**.</span></span>
5. <span data-ttu-id="6e043-124">Na página **política** , clique em **criar política**e em política de **atividade**.</span><span class="sxs-lookup"><span data-stu-id="6e043-124">On the **Policy** page, click **Create policy**, and then click **Activity policy**.</span></span>
6. <span data-ttu-id="6e043-125">Em **nome da política**, digite **atividade administrativa**.</span><span class="sxs-lookup"><span data-stu-id="6e043-125">In **Policy name**, type **Administrative activity**.</span></span>
7. <span data-ttu-id="6e043-126">Em **severidade da política**, clique em **alto**.</span><span class="sxs-lookup"><span data-stu-id="6e043-126">In **Policy severity**, click **High**.</span></span>
8. <span data-ttu-id="6e043-127">Em **categoria**, clique em **contas privilegiadas**.</span><span class="sxs-lookup"><span data-stu-id="6e043-127">In **Category**, click **Privileged accounts**.</span></span>
9. <span data-ttu-id="6e043-128">Em **criar filtros para a política**, em **atividades que correspondem a todos os itens a seguir**, clique em **atividades administrativas**.</span><span class="sxs-lookup"><span data-stu-id="6e043-128">In **Create filters for the policy**, in **Activities matching all of the following**, click **Administrative activity**.</span></span>
10. <span data-ttu-id="6e043-129">Em **alertas**, clique em **Enviar alerta como email**.</span><span class="sxs-lookup"><span data-stu-id="6e043-129">In **Alerts**, click **Send alert as email**.</span></span> <span data-ttu-id="6e043-130">Em **para**, digite o endereço de email da conta de administrador global.</span><span class="sxs-lookup"><span data-stu-id="6e043-130">In **To**, type the email address of your global administrator account.</span></span>
11. <span data-ttu-id="6e043-131">Na parte inferior da página, clique em **criar**.</span><span class="sxs-lookup"><span data-stu-id="6e043-131">At the bottom of the page, click **Create**.</span></span>
12. <span data-ttu-id="6e043-132">Feche a guia **painel** .</span><span class="sxs-lookup"><span data-stu-id="6e043-132">Close the **Dashboard** tab.</span></span>
    
<span data-ttu-id="6e043-133">Em seguida, crie uma nova conta de usuário como administrador global dedicado.</span><span class="sxs-lookup"><span data-stu-id="6e043-133">Next, create a new user account as a dedicated global administrator.</span></span>

1. <span data-ttu-id="6e043-134">Em uma guia separada, abra o [centro de administração do Microsoft 365](https://admin.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="6e043-134">On a separate tab, open the [Microsoft 365 admin center](https://admin.microsoft.com/).</span></span>
2. <span data-ttu-id="6e043-135">Em **usuários ativos**, clique em **Adicionar um usuário**.</span><span class="sxs-lookup"><span data-stu-id="6e043-135">Under **Active users**, click **Add a user**.</span></span>
3. <span data-ttu-id="6e043-136">Na página **novo usuário** , digite **DedicatedAdmin** em **nome**, nome para **exibição**e nome de **usuário**.</span><span class="sxs-lookup"><span data-stu-id="6e043-136">On the **New user** page, type **DedicatedAdmin** in **First name**, **Display name**, and **Username**.</span></span>
4. <span data-ttu-id="6e043-137">Clique em **senha**, clique em **deixe-me criar a senha**e digite uma senha forte.</span><span class="sxs-lookup"><span data-stu-id="6e043-137">Click **Password**, click **Let me create the password**, and then type a strong password.</span></span> <span data-ttu-id="6e043-138">Registre a senha dessa nova conta em um local seguro.</span><span class="sxs-lookup"><span data-stu-id="6e043-138">Record the password for this new account in a secure location.</span></span>
5. <span data-ttu-id="6e043-139">Clear **faça com que este usuário altere sua senha quando entrar pela primeira vez**.</span><span class="sxs-lookup"><span data-stu-id="6e043-139">Clear **Make this user change their password when they first sign in**.</span></span>
6. <span data-ttu-id="6e043-140">Clique em **funções**e, em seguida, clique em **administrador global**.</span><span class="sxs-lookup"><span data-stu-id="6e043-140">Click **Roles**, and then click **Global administrator**.</span></span>
7. <span data-ttu-id="6e043-141">Clique em **licenças de produto**e, em seguida, ative as licenças do **Enterprise Mobility + Security E5** e **Office 365 Enterprise E5** no.</span><span class="sxs-lookup"><span data-stu-id="6e043-141">Click **Product licenses**, and then turn the **Enterprise Mobility + Security E5** and **Office 365 Enterprise E5 licenses** on.</span></span>
8. <span data-ttu-id="6e043-142">Clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="6e043-142">Click **Add**.</span></span>
9. <span data-ttu-id="6e043-143">Na **página usuário foi adicionado**, desmarque **Enviar senha no email**e clique em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="6e043-143">On the **User was added page**, clear **Send password in email**, and then click **Close**.</span></span>

<span data-ttu-id="6e043-144">Em seguida, crie um novo grupo chamado GlobalAdmins e adicione a conta DedicatedAdmin a ele.</span><span class="sxs-lookup"><span data-stu-id="6e043-144">Next, create a new group named GlobalAdmins and add the DedicatedAdmin account to it.</span></span>

1. <span data-ttu-id="6e043-145">Na guia **centro de administração do Microsoft 365** , clique no ícone de grupos na navegação à esquerda e, em seguida, clique em **grupos**.</span><span class="sxs-lookup"><span data-stu-id="6e043-145">On the **Microsoft 365 admin center** tab, click the groups icon in the left navigation, and then click **Groups**.</span></span>
2. <span data-ttu-id="6e043-146">Clique em **Adicionar um grupo**.</span><span class="sxs-lookup"><span data-stu-id="6e043-146">Click **Add a group**.</span></span>
3. <span data-ttu-id="6e043-147">Na página **novo grupo** , digite **GlobalAdmins**.</span><span class="sxs-lookup"><span data-stu-id="6e043-147">On the **New Group** page, type **GlobalAdmins**.</span></span>
4. <span data-ttu-id="6e043-148">Clique em **selecionar proprietário** clique em sua conta de administrador global e, em seguida, clique em **Adicionar > fechar**.</span><span class="sxs-lookup"><span data-stu-id="6e043-148">Click **Select owner** click your global administrator account, and then click **Add > Close**.</span></span>
5. <span data-ttu-id="6e043-149">Na lista de grupos, clique no grupo **GlobalAdmins** .</span><span class="sxs-lookup"><span data-stu-id="6e043-149">In the list of groups, click the **GlobalAdmins** group.</span></span>
6. <span data-ttu-id="6e043-150">Na página **GlobalAdmins** , clique em **Editar para membro**e, em seguida, clique em **adicionar membros**.</span><span class="sxs-lookup"><span data-stu-id="6e043-150">On the **GlobalAdmins** page, click **Edit for Member**, and then click **Add members**.</span></span>
7. <span data-ttu-id="6e043-151">Na lista, clique na conta **DedicatedAdmin** e, em seguida, clique em **salvar _GT_ fechar > fechar o centro de administração do >**.</span><span class="sxs-lookup"><span data-stu-id="6e043-151">In the list, click the **DedicatedAdmin** account, and then click **Save > Close > Close > Admin center**.</span></span>

<span data-ttu-id="6e043-152">Em seguida, crie políticas de acesso condicional para exigir a autenticação multifator para contas de administrador global e para negar a autenticação se o risco de entrada for médio ou alto.</span><span class="sxs-lookup"><span data-stu-id="6e043-152">Next, create conditional access policies to require multifactor authentication for global administrator accounts and to deny authentication if the sign-in risk is medium or high.</span></span>

<span data-ttu-id="6e043-153">Essa primeira política requer que todas as contas de administrador global usem MFA.</span><span class="sxs-lookup"><span data-stu-id="6e043-153">This first policy requires that all global administrator accounts use MFA.</span></span>

1. <span data-ttu-id="6e043-154">Em uma nova guia do navegador, vá para [https://portal.azure.com](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="6e043-154">In a new tab of your browser, go to [https://portal.azure.com](https://portal.azure.com).</span></span>
2. <span data-ttu-id="6e043-155">Clique em **Azure Active Directory > acesso condicional**.</span><span class="sxs-lookup"><span data-stu-id="6e043-155">Click **Azure Active Directory > Conditional access**.</span></span>
3. <span data-ttu-id="6e043-156">Na folha **acesso condicional – políticas** , clique em **política de linha de base: exigir MFA para administradores (visualização)**.</span><span class="sxs-lookup"><span data-stu-id="6e043-156">On the **Conditional access – Policies** blade, click **Baseline policy: Require MFA for admins (preview)**.</span></span>
4. <span data-ttu-id="6e043-157">Nas **políticas de linha de base...**</span><span class="sxs-lookup"><span data-stu-id="6e043-157">On the **Baseline policies…**</span></span> <span data-ttu-id="6e043-158">lâmina, clique em **usar política imediatamente _GT_ salvar**.</span><span class="sxs-lookup"><span data-stu-id="6e043-158">blade, click **Use policy immediately > Save**.</span></span>

<span data-ttu-id="6e043-159">Essa segunda política bloqueia o acesso à autenticação de conta de administrador global quando o risco de entrada é médio ou alto.</span><span class="sxs-lookup"><span data-stu-id="6e043-159">This second policy blocks access to global administrator account authentication when the sign-in risk is medium or high.</span></span>

1. <span data-ttu-id="6e043-160">Na folha **acesso condicional – políticas** , clique em **nova política**.</span><span class="sxs-lookup"><span data-stu-id="6e043-160">On the **Conditional access – Policies** blade, click **New policy**.</span></span>
2. <span data-ttu-id="6e043-161">Na **nova** folha, digite **administradores globais** em **nome**.</span><span class="sxs-lookup"><span data-stu-id="6e043-161">On the **New** blade, type **Global administrators** in **Name**.</span></span>
3. <span data-ttu-id="6e043-162">Na seção **atribuições** , clique em **usuários e grupos**.</span><span class="sxs-lookup"><span data-stu-id="6e043-162">In the **Assignments** section, click **Users and groups**.</span></span>
4. <span data-ttu-id="6e043-163">Na guia **incluir** da folha **usuários e grupos** , clique em **Selecionar usuários e grupos _GT_ usuários e grupos > selecionar**.</span><span class="sxs-lookup"><span data-stu-id="6e043-163">On the **Include** tab of the **Users and groups** blade, click **Select users and groups > Users and groups > Select**.</span></span>
5. <span data-ttu-id="6e043-164">Na folha **selecionar** , clique em **GlobalAdmins _GT_ selecionar > concluído**.</span><span class="sxs-lookup"><span data-stu-id="6e043-164">On the **Select** blade, click the **GlobalAdmins > Select > Done**.</span></span>
6. <span data-ttu-id="6e043-165">Na seção **atribuições** , clique em **condições**.</span><span class="sxs-lookup"><span data-stu-id="6e043-165">In the **Assignments** section, click **Conditions**.</span></span>
7. <span data-ttu-id="6e043-166">Na folha **condições** , clique em **risco de entrada**, clique em **Sim** para **Configurar**, clique **em alta** e **média**e, em seguida, clique em **selecionar** e **concluir**.</span><span class="sxs-lookup"><span data-stu-id="6e043-166">On the **Conditions** blade, click **Sign-in risk**, click **Yes** for **Configure**, click **High** and **Medium**, and then click **Select** and **Done**.</span></span>
8. <span data-ttu-id="6e043-167">Na seção **controles de acesso** da **nova** folha, clique em **conceder**.</span><span class="sxs-lookup"><span data-stu-id="6e043-167">In the **Access controls** section of the **New** blade, click **Grant**.</span></span>
9. <span data-ttu-id="6e043-168">Na folha **conceder** , clique em **bloquear acesso**e clique em **selecionar**.</span><span class="sxs-lookup"><span data-stu-id="6e043-168">On the **Grant** blade, click **Block access**, and then click **Select**.</span></span>
10. <span data-ttu-id="6e043-169">Na **nova** folha, clique em **ativado** para **habilitar a política**e clique em **criar**.</span><span class="sxs-lookup"><span data-stu-id="6e043-169">On the **New** blade, click **On** for **Enable policy**, and then click **Create**.</span></span>
11. <span data-ttu-id="6e043-170">Feche as guias **portal do Azure** e **centro de administração do Microsoft 365** .</span><span class="sxs-lookup"><span data-stu-id="6e043-170">Close the **Azure portal** and **Microsoft 365 admin center** tabs.</span></span>

<span data-ttu-id="6e043-171">Para testar a primeira política, saia e entre com a conta DedicatedAdmin.</span><span class="sxs-lookup"><span data-stu-id="6e043-171">To test the first policy, sign out and sign in with the DedicatedAdmin account.</span></span> <span data-ttu-id="6e043-172">Você deve ser solicitado a configurar o MFA na conta de usuário.</span><span class="sxs-lookup"><span data-stu-id="6e043-172">You should be prompted to configure MFA on the user account.</span></span> <span data-ttu-id="6e043-173">Isso demonstra que a primeira política está sendo aplicada.</span><span class="sxs-lookup"><span data-stu-id="6e043-173">This demonstrates that the first policy is being applied.</span></span>

<span data-ttu-id="6e043-174">Consulte a etapa [proteger contas de administrador global](identity-designate-protect-admin-accounts.md#identity-global-admin) na fase de identidade para obter informações e links para proteger suas contas de administrador global em produção.</span><span class="sxs-lookup"><span data-stu-id="6e043-174">See the [Protect global administrator accounts](identity-designate-protect-admin-accounts.md#identity-global-admin) step in the Identity phase for information and links to protect your global administrator accounts in production.</span></span>

## <a name="next-step"></a><span data-ttu-id="6e043-175">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="6e043-175">Next step</span></span>

<span data-ttu-id="6e043-176">Explorar recursos e funcionalidades adicionais de [identidade](m365-enterprise-test-lab-guides.md#identity) no ambiente de teste.</span><span class="sxs-lookup"><span data-stu-id="6e043-176">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="6e043-177">Confira também</span><span class="sxs-lookup"><span data-stu-id="6e043-177">See also</span></span>

[<span data-ttu-id="6e043-178">Fase 2: Identidade</span><span class="sxs-lookup"><span data-stu-id="6e043-178">Phase 2: Identity</span></span>](identity-infrastructure.md)

[<span data-ttu-id="6e043-179">Guias do Laboratório de Teste do Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="6e043-179">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="6e043-180">Implantação do Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="6e043-180">Microsoft 365 Enterprise deployment</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="6e043-181">Documentação do Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="6e043-181">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
