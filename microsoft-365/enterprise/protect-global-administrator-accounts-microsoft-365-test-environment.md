---
title: Proteger contas de administrador global no seu ambiente de teste do Microsoft 365 Enterprise
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/21/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
ms.custom:
- TLG
- Ent_TLGs
description: Use estas etapas para proteger contas de administrador global no seu ambiente de teste do Microsoft 365 Enterprise.
ms.openlocfilehash: 233e2178b060df4950c340e034d5f51216fac8fb
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/28/2018
ms.locfileid: "26864702"
---
# <a name="protect-global-administrator-accounts-in-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="96e4d-103">Proteger contas de administrador global no seu ambiente de teste do Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="96e4d-103">Protect global administrator accounts in your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="96e4d-p101">Você pode evitar ataques digitais em sua organização, garantindo que suas contas de administrador mais seguras possível. Este artigo descreve como usar políticas de acesso condicional de segurança de aplicativo de nuvem do Office 365 e o Azure AD para proteger as contas de administrador global.</span><span class="sxs-lookup"><span data-stu-id="96e4d-p101">You can prevent digital attacks on your organization by ensuring that your administrator accounts are as secure as possible. This article describes how to use Office 365 Cloud App Security and Azure AD conditional access policies to protect global administrator accounts.</span></span>

<span data-ttu-id="96e4d-106">Há duas fases a proteger contas de administrador global no seu ambiente de teste do Microsoft 365 Enterprise:</span><span class="sxs-lookup"><span data-stu-id="96e4d-106">There are two phases to protecting global administrator accounts in your Microsoft 365 Enterprise test environment:</span></span>

1.  <span data-ttu-id="96e4d-107">Crie o ambiente de teste do Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="96e4d-107">Create the Microsoft 365 Enterprise test environment.</span></span>
2.  <span data-ttu-id="96e4d-108">Protege a sua conta de administrador global dedicado.</span><span class="sxs-lookup"><span data-stu-id="96e4d-108">Protect your dedicated global administrator account.</span></span>

![Guias de Laboratório de Teste do Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="96e4d-110">Clique [aqui](https://aka.ms/m365etlgstack) para ver um mapa visual de todos os artigos da pilha do Guia de Laboratório de Teste do Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="96e4d-110">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  

## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="96e4d-111">Fase 1: Criar o seu ambiente de teste do Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="96e4d-111">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="96e4d-112">Se você deseja testar a proteção da conta de administrador global de forma leve com os requisitos mínimos, siga as instruções na [configuração base leve](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="96e4d-112">If you just want to test global administrator account protection in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="96e4d-113">Se você deseja testar a proteção da conta de administrador global em uma empresa simulada, siga as instruções na [autenticação de passagem](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="96e4d-113">If you want to test global administrator account protection in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="96e4d-p102">Testando a conta de administrador global proteção não requer que o ambiente de teste simulado enterprise, que inclui uma intranet simulada conectado à Internet e a sincronização de diretório para uma floresta do Windows Server AD. Ele é fornecido aqui como uma opção para que você possa testar a proteção da conta de administrador global e experimentar em um ambiente que representa uma organização típica.</span><span class="sxs-lookup"><span data-stu-id="96e4d-p102">Testing global administrator account protection does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for a Windows Server AD forest. It is provided here as an option so that you can test global administrator account protection and experiment with it in an environment that represents a typical organization.</span></span> 
  
## <a name="phase-2-configure-cloud-app-security-and-conditional-access-policies"></a><span data-ttu-id="96e4d-116">Fase 2: Configurar a segurança de aplicativo de nuvem e políticas de acesso condicional</span><span class="sxs-lookup"><span data-stu-id="96e4d-116">Phase 2: Configure Cloud App Security and conditional access policies</span></span>

<span data-ttu-id="96e4d-117">Primeiro, crie uma política de segurança de aplicativo de nuvem do Office 365 para monitorar a atividade da conta de administrador global e enviar alertas para o endereço de email da sua conta de administrador global.</span><span class="sxs-lookup"><span data-stu-id="96e4d-117">First, create an Office 365 Cloud App Security policy to monitor global administrator account activity and send alerts to the email address of your global administrator account.</span></span> 

1. <span data-ttu-id="96e4d-118">Entrar no portal do Office 365 em [http://portal.office.com](http://portal.office.com) usando sua conta de administrador global.</span><span class="sxs-lookup"><span data-stu-id="96e4d-118">Sign in to the Office 365 portal at [http://portal.office.com](http://portal.office.com) using your global administrator account.</span></span>
2. <span data-ttu-id="96e4d-p103">Clique no lado do **Admin** . Na guia do **Centro de administração do Office** , clique em **centrais de Admin > segurança e conformidade**.</span><span class="sxs-lookup"><span data-stu-id="96e4d-p103">Click the **Admin** tile. On the **Office Admin center** tab, click **Admin centers > Security & Compliance**.</span></span>
3. <span data-ttu-id="96e4d-121">No painel de navegação à esquerda, clique em **alertas > Gerenciar avançadas alertas**.</span><span class="sxs-lookup"><span data-stu-id="96e4d-121">In the left navigation pane, click **Alerts > Manage advanced alerts**.</span></span>
4. <span data-ttu-id="96e4d-122">Na página **Gerenciar alertas de avançadas** , clique em **Ativar de segurança de aplicativo de nuvem do Office 365**e, em seguida, clique em **Ir para segurança de aplicativo de nuvem do Office 365**.</span><span class="sxs-lookup"><span data-stu-id="96e4d-122">On the **Manage advanced alerts** page, click **Turn on Office 365 Cloud App Security**, and then click **Go to Office 365 Cloud App Security**.</span></span>
5. <span data-ttu-id="96e4d-123">Na guia nova **painel** , clique em **controle > políticas**.</span><span class="sxs-lookup"><span data-stu-id="96e4d-123">On the new **Dashboard** tab, click **Control > Policies**.</span></span>
6. <span data-ttu-id="96e4d-124">Na página **política** , clique em **Criar política**e clique em **política de atividade**.</span><span class="sxs-lookup"><span data-stu-id="96e4d-124">On the **Policy** page, click **Create policy**, and then click **Activity policy**.</span></span>
7. <span data-ttu-id="96e4d-125">Em **nome da política**, digite **atividades administrativas**.</span><span class="sxs-lookup"><span data-stu-id="96e4d-125">In **Policy name**, type **Administrative activity**.</span></span>
8. <span data-ttu-id="96e4d-126">Em **Severidade da política**, clique em **Alta**.</span><span class="sxs-lookup"><span data-stu-id="96e4d-126">In **Policy severity**, click **High**.</span></span>
9. <span data-ttu-id="96e4d-127">Em **categoria**, clique em **contas privilegiadas**.</span><span class="sxs-lookup"><span data-stu-id="96e4d-127">In **Category**, click **Privileged accounts**.</span></span>
10. <span data-ttu-id="96e4d-128">Em **criar filtros para a política**, em **atividades correspondência das ações a seguir**, clique em **atividades administrativas**.</span><span class="sxs-lookup"><span data-stu-id="96e4d-128">In **Create filters for the policy**, in **Activities matching all of the following**, click **Administrative activity**.</span></span>
11. <span data-ttu-id="96e4d-p104">Em **Alertas**, clique em **Enviar alerta como email**. Em **Para**, digite o endereço de email da conta de administrador global.</span><span class="sxs-lookup"><span data-stu-id="96e4d-p104">In **Alerts**, click **Send alert as email**. In **To**, type the email address of your global administrator account.</span></span>
12. <span data-ttu-id="96e4d-131">Na parte inferior da página, clique em **Criar**.</span><span class="sxs-lookup"><span data-stu-id="96e4d-131">At the bottom of the page, click **Create**.</span></span>
13. <span data-ttu-id="96e4d-132">Feche a guia do **painel** .</span><span class="sxs-lookup"><span data-stu-id="96e4d-132">Close the **Dashboard** tab.</span></span>
    
<span data-ttu-id="96e4d-133">Em seguida, crie uma nova conta de usuário como um administrador global dedicado.</span><span class="sxs-lookup"><span data-stu-id="96e4d-133">Next, create a new user account as a dedicated global administrator.</span></span>

1. <span data-ttu-id="96e4d-134">Na guia do **Centro de administração do Office** , em **usuários ativos**, clique em **Adicionar um usuário**.</span><span class="sxs-lookup"><span data-stu-id="96e4d-134">On the **Office Admin center** tab, under **Active users**, click **Add a user**.</span></span>
2. <span data-ttu-id="96e4d-135">Na página **novo usuário** , digite **DedicatedAdmin** em **nome**, **nome para exibição**e **Username**.</span><span class="sxs-lookup"><span data-stu-id="96e4d-135">On the **New user** page, type **DedicatedAdmin** in **First name**, **Display name**, and **Username**.</span></span>
3. <span data-ttu-id="96e4d-p105">Clique em **senha**, clique em **Deixe-me criar a senha**e, em seguida, digite uma senha forte. Registre a senha para esta nova conta em um local seguro.</span><span class="sxs-lookup"><span data-stu-id="96e4d-p105">Click **Password**, click **Let me create the password**, and then type a strong password. Record the password for this new account in a secure location.</span></span>
4. <span data-ttu-id="96e4d-138">Desmarque **tornar este usuário alterar suas senhas quando eles entrarem pela primeira vez**.</span><span class="sxs-lookup"><span data-stu-id="96e4d-138">Clear **Make this user change their password when they first sign in**.</span></span>
5. <span data-ttu-id="96e4d-139">Clique em **funções**e, em seguida, clique em **Administrador Global**.</span><span class="sxs-lookup"><span data-stu-id="96e4d-139">Click **Roles**, and then click **Global administrator**.</span></span>
6. <span data-ttu-id="96e4d-140">Clique em **licenças do produto**e ative o **Mobility Enterprise + E5 de segurança** e **licenças do Office 365 Enterprise E5** .</span><span class="sxs-lookup"><span data-stu-id="96e4d-140">Click **Product licenses**, and then turn the **Enterprise Mobility + Security E5** and **Office 365 Enterprise E5 licenses** on.</span></span>
7. <span data-ttu-id="96e4d-141">Clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="96e4d-141">Click **Add**.</span></span>
8. <span data-ttu-id="96e4d-142">Em que o **usuário foi adicionado a página**, desmarque **Enviar senha em email**e clique em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="96e4d-142">On the **User was added page**, clear **Send password in email**, and then click **Close**.</span></span>

<span data-ttu-id="96e4d-143">Em seguida, criar um novo grupo chamado GlobalAdmins e adicione a conta de DedicatedAdmin a ela.</span><span class="sxs-lookup"><span data-stu-id="96e4d-143">Next, create a new group named GlobalAdmins and add the DedicatedAdmin account to it.</span></span>

1. <span data-ttu-id="96e4d-144">Na guia do **Centro de administração do Office** , clique no ícone de grupos no painel de navegação esquerdo e, em seguida, clique em **grupos**.</span><span class="sxs-lookup"><span data-stu-id="96e4d-144">On the **Office Admin center** tab, click the groups icon in the left navigation, and then click **Groups**.</span></span>
2. <span data-ttu-id="96e4d-145">Clique em **Adicionar um grupo**.</span><span class="sxs-lookup"><span data-stu-id="96e4d-145">Click **Add a group**.</span></span>
3. <span data-ttu-id="96e4d-146">Na página **Novo grupo** , digite **GlobalAdmins**.</span><span class="sxs-lookup"><span data-stu-id="96e4d-146">On the **New Group** page, type **GlobalAdmins**.</span></span>
4. <span data-ttu-id="96e4d-147">Clique em click **proprietário selecione** sua conta de administrador global e, em seguida, clique em **Adicionar > fechar**.</span><span class="sxs-lookup"><span data-stu-id="96e4d-147">Click **Select owner** click your global administrator account, and then click **Add > Close**.</span></span>
5. <span data-ttu-id="96e4d-148">Na lista de grupos, clique no grupo de **GlobalAdmins** .</span><span class="sxs-lookup"><span data-stu-id="96e4d-148">In the list of groups, click the **GlobalAdmins** group.</span></span>
6. <span data-ttu-id="96e4d-149">Na página **GlobalAdmins** , clique em **Editar para membro**e, em seguida, clique em **Adicionar membros**.</span><span class="sxs-lookup"><span data-stu-id="96e4d-149">On the **GlobalAdmins** page, click **Edit for Member**, and then click **Add members**.</span></span>
7. <span data-ttu-id="96e4d-150">Na lista, clique na conta de **DedicatedAdmin** e, em seguida, clique em **Salvar > fechar > fechar > Centro de administração**.</span><span class="sxs-lookup"><span data-stu-id="96e4d-150">In the list, click the **DedicatedAdmin** account, and then click **Save > Close > Close > Admin center**.</span></span>

<span data-ttu-id="96e4d-151">Em seguida, crie políticas de acesso condicional para exigir a autenticação multifator para contas de administrador global e negar autenticação, se o risco de entrada for média ou alta.</span><span class="sxs-lookup"><span data-stu-id="96e4d-151">Next, create conditional access policies to require multifactor authentication for global administrator accounts and to deny authentication if the sign-in risk is medium or high.</span></span>

<span data-ttu-id="96e4d-152">Essa diretiva primeira requer que todas as contas de administrador global usam MFA.</span><span class="sxs-lookup"><span data-stu-id="96e4d-152">This first policy requires that all global administrator accounts use MFA.</span></span>

1. <span data-ttu-id="96e4d-153">Em uma nova guia do seu navegador, vá para [https://portal.azure.com](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="96e4d-153">In a new tab of your browser, go to [https://portal.azure.com](https://portal.azure.com).</span></span>
2. <span data-ttu-id="96e4d-154">Clique em **Azure Active Directory > acesso condicional**.</span><span class="sxs-lookup"><span data-stu-id="96e4d-154">Click **Azure Active Directory > Conditional access**.</span></span>
3. <span data-ttu-id="96e4d-155">No blade **acesso condicional – políticas** , clique em **diretiva base: exigem MFA para os administradores (preview)**.</span><span class="sxs-lookup"><span data-stu-id="96e4d-155">On the **Conditional access – Policies** blade, click **Baseline policy: Require MFA for admins (preview)**.</span></span>
4. <span data-ttu-id="96e4d-p106">No blade **… políticas de linha de base** , clique em **usar imediatamente a política > Salvar**.</span><span class="sxs-lookup"><span data-stu-id="96e4d-p106">On the **Baseline policies…** blade, click **Use policy immediately > Save**.</span></span>

<span data-ttu-id="96e4d-158">Essa segunda política bloqueia o acesso à autenticação de conta de administrador global quando o risco de entrada é a média ou alta.</span><span class="sxs-lookup"><span data-stu-id="96e4d-158">This second policy blocks access to global administrator account authentication when the sign-in risk is medium or high.</span></span>

1. <span data-ttu-id="96e4d-159">No blade **acesso condicional – políticas** , clique em **nova diretiva**.</span><span class="sxs-lookup"><span data-stu-id="96e4d-159">On the **Conditional access – Policies** blade, click **New policy**.</span></span>
2. <span data-ttu-id="96e4d-160">No blade **New** , digite **administradores globais** no **nome**.</span><span class="sxs-lookup"><span data-stu-id="96e4d-160">On the **New** blade, type **Global administrators** in **Name**.</span></span>
3. <span data-ttu-id="96e4d-161">Na seção de **atribuições** , clique em **usuários e grupos**.</span><span class="sxs-lookup"><span data-stu-id="96e4d-161">In the **Assignments** section, click **Users and groups**.</span></span>
4. <span data-ttu-id="96e4d-162">Na guia **incluir** do blade **usuários e grupos** , clique em **Selecionar usuários e grupos > usuários e grupos > selecione**.</span><span class="sxs-lookup"><span data-stu-id="96e4d-162">On the **Include** tab of the **Users and groups** blade, click **Select users and groups > Users and groups > Select**.</span></span>
5. <span data-ttu-id="96e4d-163">No blade **Selecionar** , clique no **GlobalAdmins > selecione > feito**.</span><span class="sxs-lookup"><span data-stu-id="96e4d-163">On the **Select** blade, click the **GlobalAdmins > Select > Done**.</span></span>
6. <span data-ttu-id="96e4d-164">Na seção de **atribuições** , clique em **condições**.</span><span class="sxs-lookup"><span data-stu-id="96e4d-164">In the **Assignments** section, click **Conditions**.</span></span>
7. <span data-ttu-id="96e4d-165">No blade **condições** , clique em **entrar risco**, clique em **Sim** para **Configurar**, clique em **alta** e **Médio**e, em seguida, clique em **Selecionar** e **feito**.</span><span class="sxs-lookup"><span data-stu-id="96e4d-165">On the **Conditions** blade, click **Sign-in risk**, click **Yes** for **Configure**, click **High** and **Medium**, and then click **Select** and **Done**.</span></span>
8. <span data-ttu-id="96e4d-166">Na seção de **acessar os controles** do blade **novo** , clique em **conceder**.</span><span class="sxs-lookup"><span data-stu-id="96e4d-166">In the **Access controls** section of the **New** blade, click **Grant**.</span></span>
9. <span data-ttu-id="96e4d-167">No blade **Grant** , clique em **Bloquear acesso**e clique em **Selecionar**.</span><span class="sxs-lookup"><span data-stu-id="96e4d-167">On the **Grant** blade, click **Block access**, and then click **Select**.</span></span>
10. <span data-ttu-id="96e4d-168">No blade **novo** , clique **em** para **Ativar a política**e clique em **criar**.</span><span class="sxs-lookup"><span data-stu-id="96e4d-168">On the **New** blade, click **On** for **Enable policy**, and then click **Create**.</span></span>
11. <span data-ttu-id="96e4d-169">Feche as guias **portal Azure** e o **Centro de administração do Office** .</span><span class="sxs-lookup"><span data-stu-id="96e4d-169">Close the **Azure portal** and **Office Admin center** tabs.</span></span>

<span data-ttu-id="96e4d-p107">Para testar a primeira diretiva, sair e entrar com a conta DedicatedAdmin. Você deve ser solicitado para configurar MFA na conta de usuário. Isso demonstra que a primeira diretiva está sendo aplicada.</span><span class="sxs-lookup"><span data-stu-id="96e4d-p107">To test the first policy, sign out and sign in with the DedicatedAdmin account. You should be prompted to configure MFA on the user account. This demonstrates that the first policy is being applied.</span></span>

<span data-ttu-id="96e4d-173">Consulte a etapa de [proteger contas de administrador global](identity-designate-protect-admin-accounts.md) na fase de identidade para obter informações e links para proteger suas contas de administrador global na produção.</span><span class="sxs-lookup"><span data-stu-id="96e4d-173">See the [Protect global administrator accounts](identity-designate-protect-admin-accounts.md) step in the Identity phase for information and links to protect your global administrator accounts in production.</span></span>

## <a name="next-step"></a><span data-ttu-id="96e4d-174">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="96e4d-174">Next step</span></span>

<span data-ttu-id="96e4d-175">Explorar recursos e funcionalidades adicionais de [identidade](m365-enterprise-test-lab-guides.md#identity) no ambiente de teste.</span><span class="sxs-lookup"><span data-stu-id="96e4d-175">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="96e4d-176">Confira também</span><span class="sxs-lookup"><span data-stu-id="96e4d-176">See also</span></span>

[<span data-ttu-id="96e4d-177">Fase 2: Identidade</span><span class="sxs-lookup"><span data-stu-id="96e4d-177">Phase 2: Identity</span></span>](identity-infrastructure.md)

[<span data-ttu-id="96e4d-178">Guias do Laboratório de Teste do Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="96e4d-178">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="96e4d-179">Implantação do Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="96e4d-179">Microsoft 365 Enterprise deployment</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="96e4d-180">Documentação do Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="96e4d-180">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
