---
title: Redefinição de senha do ambiente de teste do Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/19/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom:
- TLGS
- Ent_TLGs
ms.assetid: ''
description: 'Resumo: configurar e testar a redefinição de senha do ambiente de teste do Microsoft 365.'
ms.openlocfilehash: f5fc8d68493464d6b4a6ffdcda64ed9a0d8c7cdd
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32289454"
---
# <a name="password-reset-for-your-microsoft-365-test-environment"></a><span data-ttu-id="f5b26-103">Redefinição de senha do ambiente de teste do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="f5b26-103">Password reset for your Microsoft 365 test environment</span></span>

<span data-ttu-id="f5b26-104">O SSPR (autoatendimento de redefinição de senha) do Microsoft Azure AD permite aos usuários redefinir ou desbloquear as senhas ou contas.</span><span class="sxs-lookup"><span data-stu-id="f5b26-104">Azure AD self-service password reset (SSPR) allows users to reset or unlock their passwords or accounts.</span></span> 

<span data-ttu-id="f5b26-105">Este artigo descreve como configurar e testar a redefinição de senhas no ambiente de teste do Microsoft 365 em duas fases:</span><span class="sxs-lookup"><span data-stu-id="f5b26-105">This article describes how you can configure and test password resets in your Microsoft 365 test environment in two phases:</span></span>

1.  <span data-ttu-id="f5b26-106">Criar o ambiente de teste do Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="f5b26-106">Create the Microsoft 365 simulated enterprise test environment.</span></span>
2.  <span data-ttu-id="f5b26-107">Configurar e testar a redefinição de senha da conta Usuário 2.</span><span class="sxs-lookup"><span data-stu-id="f5b26-107">Configure and test password reset for the User 2 account.</span></span>
    
![Guias de Laboratório de Teste do Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="f5b26-109">Clique [aqui](https://aka.ms/m365etlgstack) para ver um mapa visual de todos os artigos da pilha do Guia de Laboratório de Teste do Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="f5b26-109">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>

## <a name="phase-1-configure-password-hash-synchronization-and-password-writebback-for-your-microsoft-365-test-environment"></a><span data-ttu-id="f5b26-110">Fase 1: Configurar a sincronização e write-back de senha para seu ambiente de teste do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="f5b26-110">Phase 1: Configure password hash synchronization and password reset for your Microsoft 365 test environment</span></span>

<span data-ttu-id="f5b26-p101">Primeiro, siga as instruções em [sincronização de hash de senha](password-hash-sync-m365-ent-test-environment.md). Aqui está sua configuração resultante.</span><span class="sxs-lookup"><span data-stu-id="f5b26-p101">First, follow the instructions in [password hash synchronization](password-hash-sync-m365-ent-test-environment.md). Here is your resulting configuration.</span></span>
  
![Empresa simulada com ambiente de teste de sincronização de hash de senha](media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
<span data-ttu-id="f5b26-114">Esta configuração consiste em:</span><span class="sxs-lookup"><span data-stu-id="f5b26-114">This configuration consists of:</span></span> 
  
- <span data-ttu-id="f5b26-115">Assinaturas pagas ou de avaliação do Office 365 E5 e EMS E5.</span><span class="sxs-lookup"><span data-stu-id="f5b26-115">Office 365 E5 and EMS E5 trial or paid subscriptions.</span></span>
- <span data-ttu-id="f5b26-116">Uma intranet de organização simplificada conectado à Internet, que consiste em máquinas virtuais do DC1 APP1 e CLIENT1 em uma sub-rede de uma rede virtual do Azure.</span><span class="sxs-lookup"><span data-stu-id="f5b26-116">A simplified organization intranet connected to the Internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span> 
- <span data-ttu-id="f5b26-117">Azure AD Connect é executado no APP1 para sincronizar o domínio TESTLAB AD DS ao locatário do Azure AD de suas assinaturas do Office 365 e EMS E5.</span><span class="sxs-lookup"><span data-stu-id="f5b26-117">Azure AD Connect runs on APP1 to synchronize the TESTLAB AD DS domain to the Azure AD tenant of your Office 365 and EMS E5 subscriptions.</span></span>

<span data-ttu-id="f5b26-118">Em seguida, siga as instruções em [Fase 2 do write-back de senha](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain) do Guia de Laboratório de Teste.</span><span class="sxs-lookup"><span data-stu-id="f5b26-118">Next, follow the instructions in [Phase 2 of the password reset](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain) Test Lab Guide.</span></span>

<span data-ttu-id="f5b26-119">O write-back de senha precisa estar habilitado para que você possa usar a redefinição de senha.</span><span class="sxs-lookup"><span data-stu-id="f5b26-119">You must have password reset enabled to use password writeback.</span></span>
  
## <a name="phase-2-configure-and-test-password-reset"></a><span data-ttu-id="f5b26-120">Fase 2: configurar e testar a redefinição de senhas</span><span class="sxs-lookup"><span data-stu-id="f5b26-120">Phase 2: Configure and test password reset</span></span>

<span data-ttu-id="f5b26-121">Nesta fase, você configura a redefinição de senhas no locatário do Microsoft Azure AD por meio de uma associação de grupo, e verifica se ela funciona.</span><span class="sxs-lookup"><span data-stu-id="f5b26-121">In this phase, you configure password reset in the Azure AD tenant through group membership, and then verify that it works.</span></span>

<span data-ttu-id="f5b26-122">Primeiro, habilite a redefinição de senhas para as contas em um grupo específico do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="f5b26-122">First, enable password reset for the accounts in a specific Azure AD group.</span></span>

1. <span data-ttu-id="f5b26-123">Abra o [https://portal.azure.com](https://portal.azure.com) em uma instância privada do navegador e entre com as credenciais da conta de administrador global.</span><span class="sxs-lookup"><span data-stu-id="f5b26-123">From a private instance of your browser, open [https://portal.azure.com](https://portal.azure.com), and then sign in with the credentials of your global administrator account.</span></span>
2. <span data-ttu-id="f5b26-124">No Portal do Azure, clique em **Azure Active Directory > Grupos > Novo grupo**.</span><span class="sxs-lookup"><span data-stu-id="f5b26-124">In the Azure portal, click **Azure Active Directory > Groups > New group**.</span></span>
3. <span data-ttu-id="f5b26-p102">Defina **Tipo de grupo** como **Segurança**, **Nome do grupo** como **PWReset** e **Tipo de associação** como **Atribuído**; em seguida, clique em **Criar**.</span><span class="sxs-lookup"><span data-stu-id="f5b26-p102">Set the **Group type** to **Security**, **Group name** to **PWReset**, and the **Membership type** to **Assigned**. Click **Create**.</span></span>
5. <span data-ttu-id="f5b26-127">Clique no grupo **PWReset** na lista e, em seguida, clique em **Membros**.</span><span class="sxs-lookup"><span data-stu-id="f5b26-127">Click the **PWReset** group in the list, and then click **Members**.</span></span>
6. <span data-ttu-id="f5b26-p103">Clique em **Adicionar membros**, clique em **Usuário 2** e em **Selecionar**. Feche as páginas **PWReset** e **Grupo**.</span><span class="sxs-lookup"><span data-stu-id="f5b26-p103">Click **Add members**, click **User 2**, and then click **Select**. Close the **PWReset** and **Group** pages.</span></span>
7. <span data-ttu-id="f5b26-130">Na página do Azure Active Directory, clique em **Redefinição de senha**.</span><span class="sxs-lookup"><span data-stu-id="f5b26-130">On the Azure Active Directory page, click **Password reset**.</span></span>
8. <span data-ttu-id="f5b26-131">Na página **Propriedades**, vá até a opção **Redefinição da Senha de Autoatendimento Habilitada** e escolha **Selecionado**.</span><span class="sxs-lookup"><span data-stu-id="f5b26-131">From the **Properties** page, under the option **Self Service Password Reset Enabled**, choose **Selected**.</span></span>
9. <span data-ttu-id="f5b26-132">Em **Selecionar grupo**, selecione **PWReset** e clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="f5b26-132">From **Select group**, select **PWReset**, and then click **Save**.</span></span>
10. <span data-ttu-id="f5b26-133">Feche a instância privada do navegador.</span><span class="sxs-lookup"><span data-stu-id="f5b26-133">Close the private browser instance.</span></span>

<span data-ttu-id="f5b26-134">Em seguida, teste a redefinição de senha na conta do Usuário 2.</span><span class="sxs-lookup"><span data-stu-id="f5b26-134">Next, you test password reset for the User 2 account.</span></span>

1. <span data-ttu-id="f5b26-135">Abra outra instância privada do navegador e acesse [https://aka.ms/ssprsetup](https://aka.ms/ssprsetup).</span><span class="sxs-lookup"><span data-stu-id="f5b26-135">Open a new private browser instance and browse to [https://aka.ms/ssprsetup](https://aka.ms/ssprsetup).</span></span>
2. <span data-ttu-id="f5b26-136">Entre com as credenciais da conta do Usuário 2.</span><span class="sxs-lookup"><span data-stu-id="f5b26-136">Sign in with the User 2 account credentials.</span></span>
3. <span data-ttu-id="f5b26-137">Em **Não perca o acesso à sua conta**, defina o telefone de autenticação com um número de celular e o email de autenticação com uma conta de email pessoal ou de trabalho.</span><span class="sxs-lookup"><span data-stu-id="f5b26-137">In **Don’t lose access to your account**, set the authentication phone to your mobile phone number and the authentication email to your work or personal email account.</span></span>
4. <span data-ttu-id="f5b26-138">Depois de verificar ambos, clique em **Parece bom** e feche a instância privada do navegador.</span><span class="sxs-lookup"><span data-stu-id="f5b26-138">After both are verified, click **Looks good** and close the private instance of the browser.</span></span>
5. <span data-ttu-id="f5b26-139">Abra uma nova instância privada do navegador e vá para [https://aka.ms/sspr](https://aka.ms/sspr).</span><span class="sxs-lookup"><span data-stu-id="f5b26-139">Open a new private browser instance and go to [https://aka.ms/sspr](https://aka.ms/sspr).</span></span>
6. <span data-ttu-id="f5b26-140">Entre com as credenciais da conta do Usuário 2, digite os caracteres do CAPTCHA e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="f5b26-140">Sign in with the User 2 account credentials, type the characters from the CAPTCHA, and then click **Next**.</span></span>
8. <span data-ttu-id="f5b26-p104">Na **etapa de verificação 1**, clique em **Inserir o meu email alternativo** e em **Enviar email**. Quando receber o email, digite o código de verificação e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="f5b26-p104">For **verification step 1**, click **Email my alternate email**, and then click **Email**. When you receive the email, type the verification code, and then click **Next**.</span></span>
9. <span data-ttu-id="f5b26-p105">Em **Retornar à sua conta**, digite uma nova senha para a conta do Usuário 2 e clique em **Concluir**. Anote a nova senha da conta do Usuário 2 e guarde-a em um local seguro.</span><span class="sxs-lookup"><span data-stu-id="f5b26-p105">In **Get back into your account**, type a new password for the User 2 account, and then click **Finish**. Note the changed password of the User 2 account and store it in a safe location.</span></span>
10. <span data-ttu-id="f5b26-p106">Em uma guia separada do mesmo navegador, acesse [https://office.com](https://office.com) e entre com o nome da conta do Usuário 2 e a nova senha. Você verá a página do **Office Home**.</span><span class="sxs-lookup"><span data-stu-id="f5b26-p106">In a separate tab of the same browser, go to [https://office.com](https://office.com), and then sign in with the User 2 account name and its new password. You should see the **Office Home** page.</span></span>

<span data-ttu-id="f5b26-147">Confira informações e links para configurar a redefinição de senhas em produção na etapa [Simplificar a redefinição de senhas](identity-password-reset.md#identity-pw-reset), na fase Identidade.</span><span class="sxs-lookup"><span data-stu-id="f5b26-147">See the [Simplify password resets](identity-password-reset.md#identity-pw-reset) step in the Identity phase for information and links to configure password resets in production.</span></span>

## <a name="next-step"></a><span data-ttu-id="f5b26-148">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="f5b26-148">Next step</span></span>

<span data-ttu-id="f5b26-149">Explorar recursos e funcionalidades adicionais de [identidade](m365-enterprise-test-lab-guides.md#identity) no ambiente de teste.</span><span class="sxs-lookup"><span data-stu-id="f5b26-149">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="f5b26-150">Confira também</span><span class="sxs-lookup"><span data-stu-id="f5b26-150">See also</span></span>

[<span data-ttu-id="f5b26-151">Guias do Laboratório de Teste do Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="f5b26-151">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="f5b26-152">Implantar o Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="f5b26-152">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="f5b26-153">Documentação do Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="f5b26-153">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
