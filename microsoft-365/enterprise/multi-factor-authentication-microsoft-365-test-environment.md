---
title: Microsoft 365 para autenticação multifatório do ambiente de teste empresarial
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
description: Configure a autenticação multifatório usando mensagens de texto enviadas para um telefone inteligente em seu Microsoft 365 ambiente de teste empresarial.
ms.openlocfilehash: aeb8940a9499909b8c568d1230f9aa45aee07b3d
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50923751"
---
# <a name="multi-factor-authentication-for-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="21bfe-103">Autenticação multifafatório para seu Microsoft 365 para ambiente de teste empresarial</span><span class="sxs-lookup"><span data-stu-id="21bfe-103">Multi-factor authentication for your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="21bfe-104">*Este Guia de Laboratório de Teste pode ser usado para Microsoft 365 ambientes de teste corporativos e Office 365 Enterprise de teste.*</span><span class="sxs-lookup"><span data-stu-id="21bfe-104">*This Test Lab Guide can be used for both Microsoft 365 for enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="21bfe-105">Para obter um nível adicional de segurança para entrar no Microsoft 365 ou qualquer serviço ou aplicativo que use o locatário do Azure AD para sua assinatura, você pode habilitar a autenticação multifabilitar do Azure AD, que exige mais do que apenas um nome de usuário e senha para verificar uma conta.</span><span class="sxs-lookup"><span data-stu-id="21bfe-105">For an additional level of security for signing in to Microsoft 365 or any service or application that uses the Azure AD tenant for your subscription, you can enable Azure AD multi-factor authentication, which requires more than just a username and password to verify an account.</span></span>

<span data-ttu-id="21bfe-106">Com a autenticação multifatório, os usuários são obrigados a reconhecer uma chamada telefônica, digitar um código de verificação enviado em uma mensagem de texto ou verificar a autenticação com um aplicativo em seus telefones inteligentes depois de inserir corretamente suas senhas.</span><span class="sxs-lookup"><span data-stu-id="21bfe-106">With multi-factor authentication, users are required to acknowledge a phone call, type a verification code sent in a text message, or verify the authentication with an app on their smart phones after correctly entering their passwords.</span></span> <span data-ttu-id="21bfe-107">Eles só podem entrar depois que esse segundo fator de autenticação for satisfeito.</span><span class="sxs-lookup"><span data-stu-id="21bfe-107">They can sign in only after this second authentication factor is satisfied.</span></span>
  
<span data-ttu-id="21bfe-108">Este artigo descreve como habilitar e testar a autenticação baseada em mensagens de texto para uma conta de usuário específica.</span><span class="sxs-lookup"><span data-stu-id="21bfe-108">This article describes how to enable and test text message-based authentication for a specific user account.</span></span>
  
<span data-ttu-id="21bfe-109">Configurar a autenticação multifatória para uma conta em sua Microsoft 365 para o ambiente de teste empresarial envolve duas fases e uma terceira fase opcional:</span><span class="sxs-lookup"><span data-stu-id="21bfe-109">Setting up multi-factor authentication for an account in your Microsoft 365 for enterprise test environment involves two phases and a third optional phase:</span></span>
- [<span data-ttu-id="21bfe-110">Fase 1: criar seu Microsoft 365 para ambiente de teste empresarial</span><span class="sxs-lookup"><span data-stu-id="21bfe-110">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [<span data-ttu-id="21bfe-111">Fase 2: Habilitar e testar a autenticação multifatória para a conta do Usuário 2</span><span class="sxs-lookup"><span data-stu-id="21bfe-111">Phase 2: Enable and test multi-factor authentication for the User 2 account</span></span>](#phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account)
- [<span data-ttu-id="21bfe-112">Fase 3: Habilitar e testar a autenticação multifacional com uma política de acesso condicional</span><span class="sxs-lookup"><span data-stu-id="21bfe-112">Phase 3: Enable and test multi-factor authentication with a conditional access policy</span></span>](#phase-3-enable-and-test-multi-factor-authentication-with-a-conditional-access-policy)

![Guias de Laboratório de Teste do Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="21bfe-114">Para um mapa visual de todos os artigos na pilha Microsoft 365 guia do laboratório de teste empresarial, vá para o Microsoft 365 para a pilha de guias de laboratório [de teste corporativos.](../downloads/Microsoft365EnterpriseTLGStack.pdf)</span><span class="sxs-lookup"><span data-stu-id="21bfe-114">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="21bfe-115">Fase 1: criar seu Microsoft 365 para ambiente de teste empresarial</span><span class="sxs-lookup"><span data-stu-id="21bfe-115">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="21bfe-116">Se você quiser apenas testar a autenticação multifa factor de forma leve com os requisitos mínimos, siga as instruções em [Configuração base leve.](lightweight-base-configuration-microsoft-365-enterprise.md)</span><span class="sxs-lookup"><span data-stu-id="21bfe-116">If you just want to test multi-factor authentication in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="21bfe-117">Se você quiser testar a autenticação multifa factor em uma empresa simulada, siga as instruções em [Autenticação passagem](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="21bfe-117">If you want to test multi-factor authentication in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="21bfe-118">Testar a autenticação multifatório não exige o ambiente de teste empresarial simulado, que inclui uma intranet simulada conectada à Internet e a sincronização de diretórios para uma floresta dos Serviços de Domínio do Active Directory (AD DS).</span><span class="sxs-lookup"><span data-stu-id="21bfe-118">Testing multi-factor authentication does not require the simulated enterprise test environment, which includes a simulated intranet connected to the internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="21bfe-119">Ele é fornecido aqui como uma opção para que você possa testar a autenticação multifa factor e experimentá-la em um ambiente que representa uma organização típica.</span><span class="sxs-lookup"><span data-stu-id="21bfe-119">It is provided here as an option so that you can test multi-factor authentication and experiment with it in an environment that represents a typical organization.</span></span>
  
## <a name="phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account"></a><span data-ttu-id="21bfe-120">Fase 2: Habilitar e testar a autenticação multifatória para a conta do Usuário 2</span><span class="sxs-lookup"><span data-stu-id="21bfe-120">Phase 2: Enable and test multi-factor authentication for the User 2 account</span></span>

<span data-ttu-id="21bfe-121">Habilita a autenticação multifabilitar para a conta usuário 2 com estas etapas:</span><span class="sxs-lookup"><span data-stu-id="21bfe-121">Enable multi-factor authentication for the User 2 account with these steps:</span></span>
  
1. <span data-ttu-id="21bfe-122">Abra uma instância separada e privada do navegador, vá para o centro de administração Microsoft 365 ( ), e entre [https://portal.microsoft.com](https://portal.microsoft.com) com sua conta de administrador global.</span><span class="sxs-lookup"><span data-stu-id="21bfe-122">Open a separate, private instance of your browser, go to the Microsoft 365 admin center ([https://portal.microsoft.com](https://portal.microsoft.com)), and then sign in with your global administrator account.</span></span>
    
2. <span data-ttu-id="21bfe-123">Na navegação à esquerda, selecione **Usuários**  >  **Usuários ativos**.</span><span class="sxs-lookup"><span data-stu-id="21bfe-123">In the left navigation, select **Users** > **Active users**.</span></span>
    
3. <span data-ttu-id="21bfe-124">No painel Usuários ativos, selecione **Autenticação multifator**.</span><span class="sxs-lookup"><span data-stu-id="21bfe-124">In the Active users pane, select **Multi-factor authentication**.</span></span>
    
4. <span data-ttu-id="21bfe-125">Na lista, selecione a **conta Usuário 2.**</span><span class="sxs-lookup"><span data-stu-id="21bfe-125">In the list, select the **User 2** account.</span></span>
    
5. <span data-ttu-id="21bfe-126">Na seção **Usuário 2,** em **Etapas rápidas,** selecione **Habilitar**.</span><span class="sxs-lookup"><span data-stu-id="21bfe-126">In the **User 2** section, under **Quick steps**, select **Enable**.</span></span>
    
6. <span data-ttu-id="21bfe-127">Na caixa **de diálogo Sobre como habilitar a autenticação** multi-fator, selecione Habilitar **auth multi-factor**.</span><span class="sxs-lookup"><span data-stu-id="21bfe-127">In the **About enabling multi-factor auth** dialog box, select **Enable multi-factor auth**.</span></span>
    
7. <span data-ttu-id="21bfe-128">Na caixa **de diálogo Atualizações bem-sucedidas,** selecione **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="21bfe-128">In the **Updates successful** dialog box, select **Close**.</span></span>
    
8. <span data-ttu-id="21bfe-129">Na guia **Microsoft 365 centro** de administração, selecione o ícone da conta de usuário no canto superior direito e selecione **Sair**.</span><span class="sxs-lookup"><span data-stu-id="21bfe-129">On the **Microsoft 365 admin center** tab, select the user account icon in the upper right, and then select **Sign out**.</span></span>
    
9. <span data-ttu-id="21bfe-130">Feche a instância do navegador.</span><span class="sxs-lookup"><span data-stu-id="21bfe-130">Close your browser instance.</span></span>
   
<span data-ttu-id="21bfe-131">Conclua a configuração da conta usuário 2 para usar uma mensagem de texto para validação e testá-la com estas etapas:</span><span class="sxs-lookup"><span data-stu-id="21bfe-131">Complete the configuration for the User 2 account to use a text message for validation and test it with these steps:</span></span>
  
1. <span data-ttu-id="21bfe-132">Abra uma nova instância privada do navegador.</span><span class="sxs-lookup"><span data-stu-id="21bfe-132">Open a new, private instance of your browser.</span></span>
    
2. <span data-ttu-id="21bfe-133">Vá para o [Microsoft 365 de administração](https://admin.microsoft.com) e entre com o nome da conta do Usuário 2 e a senha.</span><span class="sxs-lookup"><span data-stu-id="21bfe-133">Go to the [Microsoft 365 admin center](https://admin.microsoft.com) and sign in with the User 2 account name and password.</span></span>
    
3. <span data-ttu-id="21bfe-134">Depois de entrar, você será solicitado a configurar a conta para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="21bfe-134">After signing in, you are prompted to set up the account for more information.</span></span> <span data-ttu-id="21bfe-135">Selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="21bfe-135">Select **Next**.</span></span>
    
4. <span data-ttu-id="21bfe-136">Na página **Verificação de segurança** adicional:</span><span class="sxs-lookup"><span data-stu-id="21bfe-136">On the **Additional security verification** page:</span></span>
    
   - <span data-ttu-id="21bfe-137">Selecione seu país ou região.</span><span class="sxs-lookup"><span data-stu-id="21bfe-137">Select your country or region.</span></span>
    
   - <span data-ttu-id="21bfe-138">Insira o número de telefone do smartphone que receberá mensagens de texto.</span><span class="sxs-lookup"><span data-stu-id="21bfe-138">Enter the phone number of the smart phone that will receive text messages.</span></span>
    
   - <span data-ttu-id="21bfe-139">Em **Método**, selecione **Enviar-me um código por mensagem de texto**.</span><span class="sxs-lookup"><span data-stu-id="21bfe-139">In **Method**, select **Send me a code by text message**.</span></span>
    
5. <span data-ttu-id="21bfe-140">Selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="21bfe-140">Select **Next**.</span></span>
    
6. <span data-ttu-id="21bfe-141">Insira o código de verificação da mensagem de texto recebida em seu smartphone e selecione **Verificar**.</span><span class="sxs-lookup"><span data-stu-id="21bfe-141">Enter the verification code from the text message received on your smart phone, and then select **Verify**.</span></span>
    
7. <span data-ttu-id="21bfe-142">Na Etapa **3: Mantenha seus aplicativos existentes,** selecione **Feito**.</span><span class="sxs-lookup"><span data-stu-id="21bfe-142">On the **Step 3: Keep your existing applications** page, select **Done**.</span></span>
    
8. <span data-ttu-id="21bfe-143">Se essa for a primeira vez que você se inscreveu na conta Usuário 2, será solicitado a alterar a senha.</span><span class="sxs-lookup"><span data-stu-id="21bfe-143">If this is the first time you signed in with the User 2 account, you are prompted to change the password.</span></span> <span data-ttu-id="21bfe-144">Insira a senha original e uma nova senha duas vezes e selecione **Atualizar senha e entre**.</span><span class="sxs-lookup"><span data-stu-id="21bfe-144">Enter the original password and a new password twice, and then select **Update password and sign in**.</span></span> <span data-ttu-id="21bfe-145">Grave a nova senha em um local seguro.</span><span class="sxs-lookup"><span data-stu-id="21bfe-145">Record the new password in a secure location.</span></span>
    
    <span data-ttu-id="21bfe-146">Você deve ver o portal Office para o Usuário 2 na guia **Microsoft Office Home** do navegador.</span><span class="sxs-lookup"><span data-stu-id="21bfe-146">You should see the Office portal for User 2 on the **Microsoft Office Home** tab of your browser.</span></span>

## <a name="phase-3-enable-and-test-multi-factor-authentication-with-a-conditional-access-policy"></a><span data-ttu-id="21bfe-147">Fase 3: Habilitar e testar a autenticação multifacional com uma política de acesso condicional</span><span class="sxs-lookup"><span data-stu-id="21bfe-147">Phase 3: Enable and test multi-factor authentication with a conditional access policy</span></span>

<span data-ttu-id="21bfe-148">*Essa fase só pode ser usada para um Microsoft 365 para ambiente de teste empresarial.*</span><span class="sxs-lookup"><span data-stu-id="21bfe-148">*This phase can only be used for a Microsoft 365 for enterprise test environment.*</span></span>

<span data-ttu-id="21bfe-149">Nesta fase, você habilita a autenticação multifacional para a conta usuário 3 usando um grupo e uma política de acesso condicional.</span><span class="sxs-lookup"><span data-stu-id="21bfe-149">In this phase, you enable multi-factor authentication for the User 3 account using a group and a conditional access policy.</span></span>

<span data-ttu-id="21bfe-150">Em seguida, crie um novo grupo chamado MFAUsers e adicione a conta Usuário 3 a ele.</span><span class="sxs-lookup"><span data-stu-id="21bfe-150">Next, create a new group named MFAUsers and add the User 3 account to it.</span></span>

1. <span data-ttu-id="21bfe-151">Na guia **Microsoft 365 centro de** administração, selecione **Grupos** na navegação à esquerda e selecione **Grupos**.</span><span class="sxs-lookup"><span data-stu-id="21bfe-151">On the **Microsoft 365 admin center** tab, select **Groups** in the left navigation, and then select **Groups**.</span></span>
2. <span data-ttu-id="21bfe-152">Selecione **Adicionar um grupo**.</span><span class="sxs-lookup"><span data-stu-id="21bfe-152">Select **Add a group**.</span></span>
3. <span data-ttu-id="21bfe-153">No painel **Escolher um tipo de** grupo, selecione **Segurança** e, em seguida, selecione **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="21bfe-153">In the **Choose a group type** pane, select **Security**, and then select **Next**.</span></span>
4. <span data-ttu-id="21bfe-154">No painel **Configurar as noções básicas,** selecione **Criar grupo** e selecione **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="21bfe-154">In the **Set up the basics** pane, select **Create group**, and then select **Close**.</span></span>
5. <span data-ttu-id="21bfe-155">No painel **Revisar e concluir a adição de** grupo, insira **MFAUsers** e selecione **Next**.</span><span class="sxs-lookup"><span data-stu-id="21bfe-155">In the **Review and finish adding group** pane, enter **MFAUsers**, and then select **Next**.</span></span>
6. <span data-ttu-id="21bfe-156">Na lista de grupos, selecione o **grupo MFAUsers.**</span><span class="sxs-lookup"><span data-stu-id="21bfe-156">In the list of groups, select the **MFAUsers** group.</span></span>
7. <span data-ttu-id="21bfe-157">No painel **MFAUsers,** selecione **Membros** e selecione **Exibir tudo e gerenciar membros**.</span><span class="sxs-lookup"><span data-stu-id="21bfe-157">In the **MFAUsers** pane, select **Members**, and then select **View all and manage members**.</span></span>
8. <span data-ttu-id="21bfe-158">No painel **MFAUsers,** selecione **Adicionar** membros, selecione a conta Usuário **3** e selecione **Salvar**  >  **Fechar**  >  **Fechar.**</span><span class="sxs-lookup"><span data-stu-id="21bfe-158">In the **MFAUsers** pane, select **Add members**, select the **User 3** account, and then select **Save** > **Close** > **Close**.</span></span>

<span data-ttu-id="21bfe-159">Em seguida, crie uma política de acesso condicional para exigir autenticação multifator para membros do grupo MFAUsers.</span><span class="sxs-lookup"><span data-stu-id="21bfe-159">Next, create a conditional access policy to require multifactor authentication for members of the MFAUsers group.</span></span>

1. <span data-ttu-id="21bfe-160">Em uma nova guia do navegador, vá para [https://portal.azure.com](https://portal.azure.com) .</span><span class="sxs-lookup"><span data-stu-id="21bfe-160">In a new tab of your browser, go to [https://portal.azure.com](https://portal.azure.com).</span></span>
2. <span data-ttu-id="21bfe-161">Selecione **Azure Active Directory**  >  **Acesso Condicional** de  >  **Segurança.**</span><span class="sxs-lookup"><span data-stu-id="21bfe-161">Select **Azure Active Directory** > **Security** > **Conditional Access**.</span></span>
3. <span data-ttu-id="21bfe-162">No painel **Acesso Condicional – Políticas,** selecione **Nova política**.</span><span class="sxs-lookup"><span data-stu-id="21bfe-162">In the **Conditional access – Policies** pane, select **New policy**.</span></span>
4. <span data-ttu-id="21bfe-163">No painel **Novo,** insira **MFA para contas de usuário** na **caixa** Nome.</span><span class="sxs-lookup"><span data-stu-id="21bfe-163">In the **New** pane, enter **MFA for user accounts** in the **Name** box.</span></span>
5. <span data-ttu-id="21bfe-164">Na seção **Atribuições,** selecione **Usuários e grupos**.</span><span class="sxs-lookup"><span data-stu-id="21bfe-164">In the **Assignments** section, select **Users and groups**.</span></span>
6. <span data-ttu-id="21bfe-165">Na guia **Incluir** do painel **Usuários e** grupos, selecione Selecionar usuários **e grupos** Usuários e  >  **grupos**  >  **Selecione**.</span><span class="sxs-lookup"><span data-stu-id="21bfe-165">On the **Include** tab of the **Users and groups** pane, select **Select users and groups** > **Users and groups** > **Select**.</span></span>
7. <span data-ttu-id="21bfe-166">No painel **Selecionar,** selecione o grupo **MFAUsers** e selecione **Selecionar**  >  **Feito**.</span><span class="sxs-lookup"><span data-stu-id="21bfe-166">In the **Select** pane, select the **MFAUsers** group, and then select **Select** > **Done**.</span></span>
8. <span data-ttu-id="21bfe-167">Na seção **Controles de** acesso do **painel Novo,** selecione **Conceder**.</span><span class="sxs-lookup"><span data-stu-id="21bfe-167">In the **Access controls** section of the **New** pane, select **Grant**.</span></span>
9. <span data-ttu-id="21bfe-168">No painel **Conceder,** selecione **Exigir autenticação multifator** e selecione **Selecionar**.</span><span class="sxs-lookup"><span data-stu-id="21bfe-168">In the **Grant** pane, select **Require multi-factor authentication**, and then select **Select**.</span></span>
10. <span data-ttu-id="21bfe-169">No painel **Novo,** selecione **Ativar para** **Habilitar política** e selecione **Criar**.</span><span class="sxs-lookup"><span data-stu-id="21bfe-169">In the **New** pane, select **On** for **Enable policy**, and then select **Create**.</span></span>
11. <span data-ttu-id="21bfe-170">Feche o **portal do Azure** e **Microsoft 365 de centro de** administração.</span><span class="sxs-lookup"><span data-stu-id="21bfe-170">Close the **Azure portal** and **Microsoft 365 admin center** tabs.</span></span>

<span data-ttu-id="21bfe-171">Para testar essa política, saia e entre com a conta Usuário 3.</span><span class="sxs-lookup"><span data-stu-id="21bfe-171">To test this policy, sign out and sign in with the User 3 account.</span></span> <span data-ttu-id="21bfe-172">Você deve ser solicitado a configurar o MFA.</span><span class="sxs-lookup"><span data-stu-id="21bfe-172">You should be prompted to configure MFA.</span></span> <span data-ttu-id="21bfe-173">Isso demonstra que a política MFAUsers está sendo aplicada.</span><span class="sxs-lookup"><span data-stu-id="21bfe-173">This demonstrates that the MFAUsers policy is being applied.</span></span>

## <a name="next-step"></a><span data-ttu-id="21bfe-174">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="21bfe-174">Next step</span></span>

<span data-ttu-id="21bfe-175">Explorar recursos e funcionalidades adicionais de [identidade](m365-enterprise-test-lab-guides.md#identity) no ambiente de teste.</span><span class="sxs-lookup"><span data-stu-id="21bfe-175">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="21bfe-176">Confira também</span><span class="sxs-lookup"><span data-stu-id="21bfe-176">See also</span></span>

[<span data-ttu-id="21bfe-177">Roteiro de identidade</span><span class="sxs-lookup"><span data-stu-id="21bfe-177">Identity roadmap</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="21bfe-178">Guias do Laboratório de Teste do Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="21bfe-178">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="21bfe-179">Visão geral do Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="21bfe-179">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="21bfe-180">Documentação do Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="21bfe-180">Microsoft 365 for enterprise documentation</span></span>](/microsoft-365-enterprise/)