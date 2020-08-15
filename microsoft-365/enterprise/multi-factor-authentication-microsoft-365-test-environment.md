---
title: Microsoft 365 para a autenticação multifator do ambiente de teste corporativo
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
- seo-marvel-apr2020
description: Configurar a autenticação multifator usando mensagens de texto enviadas a um telefone inteligente no seu ambiente de teste do Microsoft 365 for Enterprise.
ms.openlocfilehash: 4ed50d37e0f4e73d5d1fc62e295df374c61b9786
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46686269"
---
# <a name="multi-factor-authentication-for-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="a5bf6-103">Autenticação multifator para seu ambiente de teste do Microsoft 365 for Enterprise</span><span class="sxs-lookup"><span data-stu-id="a5bf6-103">Multi-factor authentication for your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="a5bf6-104">*Este guia de laboratório de teste pode ser usado para ambientes de teste corporativos do Microsoft 365 para Enterprise e Office 365.*</span><span class="sxs-lookup"><span data-stu-id="a5bf6-104">*This Test Lab Guide can be used for both Microsoft 365 for enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="a5bf6-105">Para obter um nível adicional de segurança para entrar no Microsoft 365 ou qualquer serviço ou aplicativo que usa o locatário do Azure AD para sua assinatura, você pode habilitar a autenticação multifator do Azure, que requer mais do que apenas um nome de usuário e senha para verificar uma conta.</span><span class="sxs-lookup"><span data-stu-id="a5bf6-105">For an additional level of security for signing in to Microsoft 365 or any service or application that uses the Azure AD tenant for your subscription, you can enable Azure multi-factor authentication, which requires more than just a username and password to verify an account.</span></span> 

<span data-ttu-id="a5bf6-106">Com a autenticação multifator, os usuários precisam confirmar uma chamada telefônica, digitar um código de verificação enviado em uma mensagem de texto ou verificar a autenticação com um aplicativo em seus dispositivos inteligentes após a inserção correta de suas senhas.</span><span class="sxs-lookup"><span data-stu-id="a5bf6-106">With multi-factor authentication, users are required to acknowledge a phone call, type a verification code sent in a text message, or verify the authentication with an app on their smart phones after correctly entering their passwords.</span></span> <span data-ttu-id="a5bf6-107">O acesso só será possível depois que esse segundo fator de autenticação for atendido.</span><span class="sxs-lookup"><span data-stu-id="a5bf6-107">They can sign in only after this second authentication factor has been satisfied.</span></span> 
  
<span data-ttu-id="a5bf6-108">Este artigo descreve como habilitar e testar a autenticação baseada em mensagem de texto para uma conta de usuário específica.</span><span class="sxs-lookup"><span data-stu-id="a5bf6-108">This article describes how to enable and test text message-based authentication for a specific user account.</span></span>
  
<span data-ttu-id="a5bf6-109">Há duas fases para configurar a autenticação multifator para uma conta no ambiente de teste do Microsoft 365 for Enterprise:</span><span class="sxs-lookup"><span data-stu-id="a5bf6-109">There are two phases to setting up multi-factor authentication for an account in your Microsoft 365 for enterprise test environment:</span></span>
  
1. <span data-ttu-id="a5bf6-110">Crie o ambiente de teste do Microsoft 365 for Enterprise.</span><span class="sxs-lookup"><span data-stu-id="a5bf6-110">Create the Microsoft 365 for enterprise test environment.</span></span>
    
2. <span data-ttu-id="a5bf6-111">Habilite e teste a autenticação multifator para a conta do usuário 2.</span><span class="sxs-lookup"><span data-stu-id="a5bf6-111">Enable and test multi-factor authentication for the User 2 account.</span></span>

3. <span data-ttu-id="a5bf6-112">Habilite e teste a autenticação multifator com uma política de acesso condicional (opcional).</span><span class="sxs-lookup"><span data-stu-id="a5bf6-112">Enable and test multi-factor authentication with a conditional access policy (optional).</span></span>

![Guias de Laboratório de Teste do Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="a5bf6-114">Vá para o [conjunto de guias de laboratório de teste](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) de um mapa Visual para todos os artigos da pilha do guia do laboratório de teste do Microsoft 365 for Enterprise.</span><span class="sxs-lookup"><span data-stu-id="a5bf6-114">Go to [Test Lab Guide Stack](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="a5bf6-115">Fase 1: desenvolver seu ambiente de teste do Microsoft 365 for Enterprise</span><span class="sxs-lookup"><span data-stu-id="a5bf6-115">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="a5bf6-116">Se você só quiser testar a autenticação multifator de forma leve com os requisitos mínimos, siga as instruções em [configuração básica leve](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="a5bf6-116">If you just want to test multi-factor authentication in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="a5bf6-117">Se você quiser testar a autenticação multifator em uma empresa simulada, siga as instruções em [autenticação de passagem](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="a5bf6-117">If you want to test multi-factor authentication in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="a5bf6-118">Testar a autenticação multifator não requer o ambiente de teste corporativo simulado, que inclui uma intranet simulada conectada à Internet e a sincronização de diretórios para uma floresta dos serviços de domínio Active Directory (AD DS).</span><span class="sxs-lookup"><span data-stu-id="a5bf6-118">Testing multi-factor authentication does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="a5bf6-119">É fornecida aqui como uma opção para que você possa testar a autenticação multifator e experimentá-la em um ambiente que representa uma organização típica.</span><span class="sxs-lookup"><span data-stu-id="a5bf6-119">It is provided here as an option so that you can test multi-factor authentication and experiment with it in an environment that represents a typical organization.</span></span> 
  
## <a name="phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account"></a><span data-ttu-id="a5bf6-120">Fase 2: habilitar e testar a autenticação multifator para a conta do usuário 2</span><span class="sxs-lookup"><span data-stu-id="a5bf6-120">Phase 2: Enable and test multi-factor authentication for the User 2 account</span></span>

<span data-ttu-id="a5bf6-121">Habilite a autenticação multifator para a conta do usuário 2 com estas etapas:</span><span class="sxs-lookup"><span data-stu-id="a5bf6-121">Enable multi-factor authentication for the User 2 account with these steps:</span></span>
  
1. <span data-ttu-id="a5bf6-122">Abra uma instância separada e privada do navegador, vá para o centro de administração do Microsoft 365 ( [https://portal.microsoft.com](https://portal.microsoft.com) ) e entre com sua conta de administrador global.</span><span class="sxs-lookup"><span data-stu-id="a5bf6-122">Open a separate, private instance of your browser, go to the Microsoft 365 admin center ([https://portal.microsoft.com](https://portal.microsoft.com)), and then sign in with your global administrator account.</span></span>
    
2. <span data-ttu-id="a5bf6-123">Na navegação à esquerda, clique em **Usuários > Usuários ativos**.</span><span class="sxs-lookup"><span data-stu-id="a5bf6-123">In the left navigation, click **Users > Active users**.</span></span>
    
3. <span data-ttu-id="a5bf6-124">No painel usuários ativos, clique em **autenticação multifator**.</span><span class="sxs-lookup"><span data-stu-id="a5bf6-124">In the Active users pane, click **Multi-factor authentication**.</span></span>
    
4. <span data-ttu-id="a5bf6-125">Na lista, selecione a conta do **usuário 2** .</span><span class="sxs-lookup"><span data-stu-id="a5bf6-125">In the list, select the **User 2** account.</span></span>
    
5. <span data-ttu-id="a5bf6-126">Na seção **usuário 2** , em **etapas rápidas**, clique em **habilitar**.</span><span class="sxs-lookup"><span data-stu-id="a5bf6-126">In the **User 2** section, under **Quick steps**, click **Enable**.</span></span>
    
6. <span data-ttu-id="a5bf6-127">Na caixa de diálogo **sobre como habilitar a autenticação multifator** , clique em **habilitar autenticação multifator**.</span><span class="sxs-lookup"><span data-stu-id="a5bf6-127">In the **About enabling multi-factor auth** dialog box, click **Enable multi-factor auth**.</span></span>
    
7. <span data-ttu-id="a5bf6-128">Na caixa de diálogo **atualizações com êxito** , clique em **fechar**.</span><span class="sxs-lookup"><span data-stu-id="a5bf6-128">In the **Updates successful** dialog box, click **Close**.</span></span>
    
8. <span data-ttu-id="a5bf6-129">Na guia **centro de administração do Microsoft 365** **, clique no**ícone da conta de usuário no canto superior direito e clique em sair.</span><span class="sxs-lookup"><span data-stu-id="a5bf6-129">On the **Microsoft 365 admin center** tab, click the user account icon in the upper right, and then click **Sign out**.</span></span>
    
9. <span data-ttu-id="a5bf6-130">Feche a instância do navegador.</span><span class="sxs-lookup"><span data-stu-id="a5bf6-130">Close your browser instance.</span></span>
   
<span data-ttu-id="a5bf6-131">Conclua a configuração da conta do usuário 2 para usar uma mensagem de texto para validação e testá-la com estas etapas:</span><span class="sxs-lookup"><span data-stu-id="a5bf6-131">Complete the configuration for the User 2 account to use a text message for validation and test it with these steps:</span></span>
  
1. <span data-ttu-id="a5bf6-132">Abra uma nova instância privada do navegador.</span><span class="sxs-lookup"><span data-stu-id="a5bf6-132">Open a new, private instance of your browser.</span></span>
    
2. <span data-ttu-id="a5bf6-133">Vá para o [centro de administração do Microsoft 365](https://admin.microsoft.com) e entre com o nome da conta e a senha do usuário 2.</span><span class="sxs-lookup"><span data-stu-id="a5bf6-133">Go to the [Microsoft 365 admin center](https://admin.microsoft.com) and sign in with the User 2 account name and password.</span></span>
    
3. <span data-ttu-id="a5bf6-134">Após entrar, você será solicitado a configurar a conta para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="a5bf6-134">After signing in, you are prompted to set up the account for more information.</span></span> <span data-ttu-id="a5bf6-135">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="a5bf6-135">Click **Next**.</span></span>
    
4. <span data-ttu-id="a5bf6-136">Na página **verificação de segurança adicional** :</span><span class="sxs-lookup"><span data-stu-id="a5bf6-136">On the **Additional security verification** page:</span></span>
    
   - <span data-ttu-id="a5bf6-137">Selecione seu país ou região.</span><span class="sxs-lookup"><span data-stu-id="a5bf6-137">Select your country or region.</span></span>
    
   - <span data-ttu-id="a5bf6-138">Digite o número de telefone do telefone inteligente que receberá mensagens de texto.</span><span class="sxs-lookup"><span data-stu-id="a5bf6-138">Type phone number of the smart phone that will receive text messages.</span></span>
    
   - <span data-ttu-id="a5bf6-139">Em **método**, clique em **enviar um código por mensagem de texto**.</span><span class="sxs-lookup"><span data-stu-id="a5bf6-139">In **Method**, click **Send me a code by text message**.</span></span>
    
5. <span data-ttu-id="a5bf6-140">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="a5bf6-140">Click **Next**.</span></span>
    
6. <span data-ttu-id="a5bf6-141">Insira o código de verificação da mensagem de texto recebida no telefone inteligente e clique em **verificar**.</span><span class="sxs-lookup"><span data-stu-id="a5bf6-141">Enter the verification code from the text message received on your smart phone, and then click **Verify**.</span></span>
    
7. <span data-ttu-id="a5bf6-142">Na página **etapa 3: manter seus aplicativos existentes** , clique em **concluído**.</span><span class="sxs-lookup"><span data-stu-id="a5bf6-142">On the **Step 3: Keep your existing applications** page, click **Done**.</span></span>
    
8. <span data-ttu-id="a5bf6-143">Se esta é a primeira vez que você entrou com a conta de usuário 2, você é solicitado a alterar a senha.</span><span class="sxs-lookup"><span data-stu-id="a5bf6-143">If this is the first time you signed in with the User 2 account, you are prompted to change the password.</span></span> <span data-ttu-id="a5bf6-144">Digite a senha original e uma nova senha duas vezes e clique em **Atualizar senha e entrar**.</span><span class="sxs-lookup"><span data-stu-id="a5bf6-144">Type the original password and a new password twice, and then click **Update password and sign in**.</span></span> <span data-ttu-id="a5bf6-145">Registre a nova senha em um local seguro.</span><span class="sxs-lookup"><span data-stu-id="a5bf6-145">Record the new password in a secure location.</span></span>
    
    <span data-ttu-id="a5bf6-146">Você deve ver o portal do Office para o usuário 2 na guia **Microsoft Office Home** do navegador.</span><span class="sxs-lookup"><span data-stu-id="a5bf6-146">You should see the Office portal for User 2 on the **Microsoft Office Home** tab of your browser.</span></span>

## <a name="phase-3-enable-and-test-multi-factor-authentication-with-a-conditional-access-policy"></a><span data-ttu-id="a5bf6-147">Fase 3: habilitar e testar a autenticação multifator com uma política de acesso condicional</span><span class="sxs-lookup"><span data-stu-id="a5bf6-147">Phase 3: Enable and test multi-factor authentication with a conditional access policy</span></span>

<span data-ttu-id="a5bf6-148">*Esta fase só pode ser usada para um ambiente de teste do Microsoft 365 for Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="a5bf6-148">*This phase can only be used for a Microsoft 365 for enterprise test environment.*</span></span>

<span data-ttu-id="a5bf6-149">Nesta fase, habilite a autenticação multifator para a conta do usuário 3 usando um grupo e uma política de acesso condicional.</span><span class="sxs-lookup"><span data-stu-id="a5bf6-149">In this phase you enable multi-factor authentication for the User 3 account using a group and a conditional access policy.</span></span>

<span data-ttu-id="a5bf6-150">Em seguida, crie um novo grupo chamado MFAUsers e adicione a ele 3 conta de usuário.</span><span class="sxs-lookup"><span data-stu-id="a5bf6-150">Next, create a new group named MFAUsers and add the User 3 account to it.</span></span>

1. <span data-ttu-id="a5bf6-151">Na guia **centro de administração do Microsoft 365** , clique em **grupos** na navegação à esquerda e, em seguida, clique em **grupos**.</span><span class="sxs-lookup"><span data-stu-id="a5bf6-151">On the **Microsoft 365 admin center** tab, click **Groups** in the left navigation, and then click **Groups**.</span></span>
2. <span data-ttu-id="a5bf6-152">Clique em **Adicionar um grupo**.</span><span class="sxs-lookup"><span data-stu-id="a5bf6-152">Click **Add a group**.</span></span>
3. <span data-ttu-id="a5bf6-153">No painel **escolher um tipo de grupo** , selecione **segurança**e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="a5bf6-153">In the **Choose a group type** pane, select **Security**, and then click **Next**.</span></span>
4. <span data-ttu-id="a5bf6-154">No painel **Configurar o básico** , clique em **Criar grupo**e, em seguida, clique em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="a5bf6-154">In the **Set up the basics** pane, click **Create group**, and then click **Close**.</span></span>
5. <span data-ttu-id="a5bf6-155">No painel **revisar e concluir a adição de grupo** , digite **MFAUsers**e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="a5bf6-155">In the **Review and finish adding group** pane, type **MFAUsers**, and then click **Next**.</span></span>
6. <span data-ttu-id="a5bf6-156">Na lista de grupos, clique no grupo **MFAUsers** .</span><span class="sxs-lookup"><span data-stu-id="a5bf6-156">In the list of groups, click the **MFAUsers** group.</span></span>
7. <span data-ttu-id="a5bf6-157">No painel **MFAUsers** , clique em **Membros**e, em seguida, clique em **Exibir todos e gerenciar Membros**.</span><span class="sxs-lookup"><span data-stu-id="a5bf6-157">In the **MFAUsers** pane, click **Members**, and then click **View all and manage members**.</span></span>
8. <span data-ttu-id="a5bf6-158">No painel **MFAUsers** , clique em **adicionar membros**, selecione a conta do **usuário 3** e, em seguida, clique em **salvar > fechar > fechar**.</span><span class="sxs-lookup"><span data-stu-id="a5bf6-158">In the **MFAUsers** pane, click **Add members**, select the **User 3** account, and then click **Save > Close > Close**.</span></span>

<span data-ttu-id="a5bf6-159">Em seguida, crie uma política de acesso condicional para exigir a autenticação multifator para os membros do grupo MFAUsers.</span><span class="sxs-lookup"><span data-stu-id="a5bf6-159">Next, create a conditional access policy to require multifactor authentication for members of the MFAUsers group.</span></span>

1. <span data-ttu-id="a5bf6-160">Em uma nova guia do navegador, vá para [https://portal.azure.com](https://portal.azure.com) .</span><span class="sxs-lookup"><span data-stu-id="a5bf6-160">In a new tab of your browser, go to [https://portal.azure.com](https://portal.azure.com).</span></span>
2. <span data-ttu-id="a5bf6-161">Clique em **Azure Active Directory > segurança > acesso condicional**.</span><span class="sxs-lookup"><span data-stu-id="a5bf6-161">Click **Azure Active Directory > Security > Conditional Access**.</span></span>
3. <span data-ttu-id="a5bf6-162">No painel **acesso condicional – políticas** , clique em **nova política**.</span><span class="sxs-lookup"><span data-stu-id="a5bf6-162">In the **Conditional access – Policies** pane, click **New policy**.</span></span>
4. <span data-ttu-id="a5bf6-163">No painel **novo** , digite **MFA para contas de usuário** em **nome**.</span><span class="sxs-lookup"><span data-stu-id="a5bf6-163">In the **New** pane, type **MFA for user accounts** in **Name**.</span></span>
5. <span data-ttu-id="a5bf6-164">Na seção **atribuições** , clique em **usuários e grupos**.</span><span class="sxs-lookup"><span data-stu-id="a5bf6-164">In the **Assignments** section, click **Users and groups**.</span></span>
6. <span data-ttu-id="a5bf6-165">Na guia **incluir** do painel **usuários e grupos** , clique em **Selecionar usuários e grupos > usuários e grupos > selecionar**.</span><span class="sxs-lookup"><span data-stu-id="a5bf6-165">On the **Include** tab of the **Users and groups** pane, click **Select users and groups > Users and groups > Select**.</span></span>
7. <span data-ttu-id="a5bf6-166">No painel **selecionar** , clique no grupo **MFAUsers** e, em seguida, clique em **selecionar > concluído**.</span><span class="sxs-lookup"><span data-stu-id="a5bf6-166">In the **Select** pane, click the **MFAUsers** group, and then click **Select > Done**.</span></span>
8. <span data-ttu-id="a5bf6-167">Na seção **controles de acesso** do painel **novo** , clique em **conceder**.</span><span class="sxs-lookup"><span data-stu-id="a5bf6-167">In the **Access controls** section of the **New** pane, click **Grant**.</span></span>
9. <span data-ttu-id="a5bf6-168">No painel **conceder** , clique em **exigir autenticação multifator**e clique em **selecionar**.</span><span class="sxs-lookup"><span data-stu-id="a5bf6-168">In the **Grant** pane, click **Require multi-factor authentication**, and then click **Select**.</span></span>
10. <span data-ttu-id="a5bf6-169">No painel **novo** , **clique em ativar** para **habilitar a política**e clique em **criar**.</span><span class="sxs-lookup"><span data-stu-id="a5bf6-169">In the **New** pane, click **On** for **Enable policy**, and then click **Create**.</span></span>
11. <span data-ttu-id="a5bf6-170">Feche as guias **portal do Azure** e **centro de administração do Microsoft 365** .</span><span class="sxs-lookup"><span data-stu-id="a5bf6-170">Close the **Azure portal** and **Microsoft 365 admin center** tabs.</span></span>

<span data-ttu-id="a5bf6-171">Para testar esta política, saia e entre com a conta do usuário 3.</span><span class="sxs-lookup"><span data-stu-id="a5bf6-171">To test this policy, sign out and sign in with the User 3 account.</span></span> <span data-ttu-id="a5bf6-172">Você deve ser solicitado a configurar a MFA.</span><span class="sxs-lookup"><span data-stu-id="a5bf6-172">You should be prompted to configure MFA.</span></span> <span data-ttu-id="a5bf6-173">Isso demonstra que a política MFAUsers está sendo aplicada.</span><span class="sxs-lookup"><span data-stu-id="a5bf6-173">This demonstrates that the MFAUsers policy is being applied.</span></span>

## <a name="next-step"></a><span data-ttu-id="a5bf6-174">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="a5bf6-174">Next step</span></span>

<span data-ttu-id="a5bf6-175">Explorar recursos e funcionalidades adicionais de [identidade](m365-enterprise-test-lab-guides.md#identity) no ambiente de teste.</span><span class="sxs-lookup"><span data-stu-id="a5bf6-175">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="a5bf6-176">Confira também</span><span class="sxs-lookup"><span data-stu-id="a5bf6-176">See also</span></span>

[<span data-ttu-id="a5bf6-177">Roteiro de identidade</span><span class="sxs-lookup"><span data-stu-id="a5bf6-177">Identity roadmap</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="a5bf6-178">Guias do Laboratório de Teste do Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="a5bf6-178">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="a5bf6-179">Visão geral do Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="a5bf6-179">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="a5bf6-180">Documentação da Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="a5bf6-180">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
