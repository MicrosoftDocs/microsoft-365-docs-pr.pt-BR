---
title: Redefinição de senha do ambiente de teste do Microsoft 365
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/13/2019
audience: ITPro
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
ms.openlocfilehash: c8d5ed0c7feac98afd3230a305f4ab1f850ca7f8
ms.sourcegitcommit: 93e6bf1b541e22129f8c443051375d0ef1374150
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/13/2020
ms.locfileid: "42633169"
---
# <a name="password-reset-for-your-microsoft-365-test-environment"></a><span data-ttu-id="a9627-103">Redefinição de senha do ambiente de teste do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="a9627-103">Password reset for your Microsoft 365 test environment</span></span>

<span data-ttu-id="a9627-104">*Este Guia de Laboratório de Testes pode ser usado apenas em ambientes de teste do Microsoft 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="a9627-104">*This Test Lab Guide can only be used for Microsoft 365 Enterprise test environments.*</span></span>

<span data-ttu-id="a9627-105">A redefinição de senha de autoatendimento (SSPR) do Azure Active Directory (Azure AD) permite que os usuários redefinam ou desbloqueiem suas senhas ou contas.</span><span class="sxs-lookup"><span data-stu-id="a9627-105">Azure Active Directory (Azure AD) self-service password reset (SSPR) allows users to reset or unlock their passwords or accounts.</span></span> 

<span data-ttu-id="a9627-106">Este artigo descreve como você pode configurar e testar redefinições de senha em seu ambiente de teste do Microsoft 365 em três fases:</span><span class="sxs-lookup"><span data-stu-id="a9627-106">This article describes how you can configure and test password resets in your Microsoft 365 test environment in three phases:</span></span>

1.  <span data-ttu-id="a9627-107">Criar o ambiente de teste do Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="a9627-107">Create the Microsoft 365 Enterprise test environment.</span></span>
2.  <span data-ttu-id="a9627-108">Ativar write-back de senha.</span><span class="sxs-lookup"><span data-stu-id="a9627-108">Enable password writeback.</span></span>
3.  <span data-ttu-id="a9627-109">Configure e teste a redefinição de senha da conta do Usuário 3.</span><span class="sxs-lookup"><span data-stu-id="a9627-109">Configure and test password reset for the User 3 account.</span></span>
    
![Guias do Laboratório de Teste do Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="a9627-111">Clique [aqui](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) para ver um mapa visual de todos os artigos da pilha do Guia de Laboratório de Teste do Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="a9627-111">Click [here](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>

## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a><span data-ttu-id="a9627-112">Fase 1: configurar a sincronização de hash de senha do ambiente de teste do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="a9627-112">Phase 1: Configure password hash synchronization for your Microsoft 365 test environment</span></span>

<span data-ttu-id="a9627-p101">Primeiro, siga as instruções em [sincronização de hash de senha](password-hash-sync-m365-ent-test-environment.md). Aqui está sua configuração resultante.</span><span class="sxs-lookup"><span data-stu-id="a9627-p101">First, follow the instructions in [password hash synchronization](password-hash-sync-m365-ent-test-environment.md). Here is your resulting configuration.</span></span>
  
![Empresa simulada com ambiente de teste de sincronização de hash de senha](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
<span data-ttu-id="a9627-116">Esta configuração consiste em:</span><span class="sxs-lookup"><span data-stu-id="a9627-116">This configuration consists of:</span></span> 
  
- <span data-ttu-id="a9627-117">Assinaturas de avaliação ou pagas do Microsoft 365 E5 ou Office 365 E5.</span><span class="sxs-lookup"><span data-stu-id="a9627-117">Microsoft 365 E5 or Office 365 E5 trial or paid subscriptions.</span></span>
- <span data-ttu-id="a9627-118">Uma intranet de organização simplificada conectado à Internet, que consiste em máquinas virtuais do DC1 APP1 e CLIENT1 em uma sub-rede de uma rede virtual do Azure.</span><span class="sxs-lookup"><span data-stu-id="a9627-118">A simplified organization intranet connected to the Internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span> 
- <span data-ttu-id="a9627-119">O Azure AD Connect é executado no APP1 para sincronizar o domínio TESTLAB do Active Directory Domain Services (AD DS) com o locatário do Azure AD de assinatura do Microsoft 365 ou do Office 365.</span><span class="sxs-lookup"><span data-stu-id="a9627-119">Azure AD Connect runs on APP1 to synchronize the TESTLAB Active Directory Domain Services (AD DS) domain to the Azure AD tenant of your Microsoft 365 or Office 365 subscription.</span></span>

## <a name="phase-2-enable-password-writeback"></a><span data-ttu-id="a9627-120">Fase 2: Ativar o write-back de senha</span><span class="sxs-lookup"><span data-stu-id="a9627-120">Phase 2: Enable password writeback</span></span>

<span data-ttu-id="a9627-121">Siga as instruções da [Fase 2 do Guia do laboratório de teste de write-back de senha](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain).</span><span class="sxs-lookup"><span data-stu-id="a9627-121">Follow the instructions in [Phase 2 of the password writeback Test Lab Guide](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain).</span></span>

<span data-ttu-id="a9627-122">O write-back de senha precisa estar habilitado para que você possa usar a redefinição de senha.</span><span class="sxs-lookup"><span data-stu-id="a9627-122">You must have password writeback enabled to use password reset.</span></span>
  
## <a name="phase-3-configure-and-test-password-reset"></a><span data-ttu-id="a9627-123">Fase 3: Configurar e testar a redefinição de senha</span><span class="sxs-lookup"><span data-stu-id="a9627-123">Phase 3: Configure and test password reset</span></span>

<span data-ttu-id="a9627-124">Nesta fase, você configura a redefinição de senhas no locatário do Microsoft Azure AD por meio de uma associação de grupo, e verifica se ela funciona.</span><span class="sxs-lookup"><span data-stu-id="a9627-124">In this phase, you configure password reset in the Azure AD tenant through group membership, and then verify that it works.</span></span>

<span data-ttu-id="a9627-125">Primeiro, habilite a redefinição de senhas para as contas em um grupo específico do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="a9627-125">First, enable password reset for the accounts in a specific Azure AD group.</span></span>

1. <span data-ttu-id="a9627-126">Abra o [https://portal.azure.com](https://portal.azure.com) em uma instância privada do navegador e entre com as credenciais da conta de administrador global.</span><span class="sxs-lookup"><span data-stu-id="a9627-126">From a private instance of your browser, open [https://portal.azure.com](https://portal.azure.com), and then sign in with the credentials of your global administrator account.</span></span>
2. <span data-ttu-id="a9627-127">No Portal do Azure, clique em **Azure Active Directory > Grupos > Novo grupo**.</span><span class="sxs-lookup"><span data-stu-id="a9627-127">In the Azure portal, click **Azure Active Directory > Groups > New group**.</span></span>
3. <span data-ttu-id="a9627-128">Defina o **Tipo de grupo** como **Segurança**, **Nome do grupo** como **PWReset** e o**Tipo de associação** como **Atribuído**.</span><span class="sxs-lookup"><span data-stu-id="a9627-128">Set the **Group type** to **Security**, **Group name** to **PWReset**, and the **Membership type** to **Assigned**.</span></span> 
4. <span data-ttu-id="a9627-129">Clique em **Membros**, localize e selecione **Usuário 3**, em seguida, clique em **Selecionar**e, logo depois, clique em **Criar**.</span><span class="sxs-lookup"><span data-stu-id="a9627-129">Click **Members**, find and select **User 3**, and then click **Select**, and then click **Create**.</span></span>
5. <span data-ttu-id="a9627-130">Feche o painel de **Grupos**.</span><span class="sxs-lookup"><span data-stu-id="a9627-130">Close the **Groups** pane.</span></span>
6. <span data-ttu-id="a9627-131">No painel de Azure Active Directory, clique em**Redefinição de senha**na barra de navegação à esquerda.</span><span class="sxs-lookup"><span data-stu-id="a9627-131">In the Azure Active Directory pane, click **Password reset** in the left navigation.</span></span>
7. <span data-ttu-id="a9627-132">No painel **Redefinição de senha-Propriedades**, vá até a opção **Redefinição da Senha de Autoatendimento Habilitada** e escolha **Selecionado**.</span><span class="sxs-lookup"><span data-stu-id="a9627-132">In the **Password reset-Properties** pane, under the option **Self Service Password Reset Enabled**, choose **Selected**.</span></span>
8. <span data-ttu-id="a9627-133">Clique **Selecionar grupo**, selecione o grupo **PWReset** e, em seguida, clique em **Selecionar > Salvar**.</span><span class="sxs-lookup"><span data-stu-id="a9627-133">Click **Select group**, select the **PWReset** group, and then click **Select > Save**.</span></span>
9. <span data-ttu-id="a9627-134">Feche a instância privada do navegador.</span><span class="sxs-lookup"><span data-stu-id="a9627-134">Close the private browser instance.</span></span>

<span data-ttu-id="a9627-135">Em seguida, teste a redefinição de senha para a conta do Usuário 3.</span><span class="sxs-lookup"><span data-stu-id="a9627-135">Next, you test password reset for the User 3 account.</span></span>

1. <span data-ttu-id="a9627-136">Abra outra instância privada do navegador e vá para [https://aka.ms/ssprsetup](https://aka.ms/ssprsetup).</span><span class="sxs-lookup"><span data-stu-id="a9627-136">Open a new private browser instance and browse to [https://aka.ms/ssprsetup](https://aka.ms/ssprsetup).</span></span>
2. <span data-ttu-id="a9627-137">Entre usando as credenciais da conta do Usuário 3.</span><span class="sxs-lookup"><span data-stu-id="a9627-137">Sign in with the User 3 account credentials.</span></span>
3. <span data-ttu-id="a9627-138">Em **Mais informações**, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="a9627-138">In **More information required**, click **Next**.</span></span> 
5. <span data-ttu-id="a9627-139">Em **Não perca o acesso à sua conta**, defina o telefone de autenticação com um número de celular e o email de autenticação com uma conta de email pessoal ou de trabalho.</span><span class="sxs-lookup"><span data-stu-id="a9627-139">In **Don’t lose access to your account**, set the authentication phone to your mobile phone number and the authentication email to your work or personal email account.</span></span>
7. <span data-ttu-id="a9627-140">Depois de verificar ambos, clique em **Parece bom** e feche a instância privada do navegador.</span><span class="sxs-lookup"><span data-stu-id="a9627-140">After both are verified, click **Looks good** and close the private instance of the browser.</span></span>
8. <span data-ttu-id="a9627-141">Abra uma nova instância privada do navegador e vá para [https://aka.ms/sspr](https://aka.ms/sspr).</span><span class="sxs-lookup"><span data-stu-id="a9627-141">Open a new private browser instance and go to [https://aka.ms/sspr](https://aka.ms/sspr).</span></span>
9. <span data-ttu-id="a9627-142">Digite o nome da conta do Usuário 3, digite os caracteres do CAPTCHA e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="a9627-142">Type the User 3 account name, type the characters from the CAPTCHA, and then click **Next**.</span></span>
10. <span data-ttu-id="a9627-p102">Na **etapa de verificação 1**, clique em **Inserir o meu email alternativo** e em **Enviar email**. Quando receber o email, digite o código de verificação e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="a9627-p102">For **verification step 1**, click **Email my alternate email**, and then click **Email**. When you receive the email, type the verification code, and then click **Next**.</span></span>
11. <span data-ttu-id="a9627-145">No **Retornar à sua conta**, digite uma nova senha para a conta do Usuário 3 e clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="a9627-145">In **Get back into your account**, type a new password for the User 3 account, and then click **Finish**.</span></span> <span data-ttu-id="a9627-146">Anote a senha alterada da conta do Usuário 3 e armazene-a em um local seguro.</span><span class="sxs-lookup"><span data-stu-id="a9627-146">Note the changed password of the User 3 account and store it in a safe location.</span></span>
12. <span data-ttu-id="a9627-147">Em uma guia separada do mesmo navegador, vá para [https://portal.office.com](https://portal.office.com) e entre com o nome da conta do Usuário 3 e sua nova senha.</span><span class="sxs-lookup"><span data-stu-id="a9627-147">In a separate tab of the same browser, go to [https://portal.office.com](https://portal.office.com), and then sign in with the User 3 account name and its new password.</span></span> <span data-ttu-id="a9627-148">Você verá a **home page do Microsoft Office**.</span><span class="sxs-lookup"><span data-stu-id="a9627-148">You should see the **Microsoft Office Home** page.</span></span>

<span data-ttu-id="a9627-149">Confira informações e links para configurar a redefinição de senhas em produção na etapa [Simplificar a redefinição de senhas](identity-secure-your-passwords.md#identity-pw-reset), na fase Identidade.</span><span class="sxs-lookup"><span data-stu-id="a9627-149">See the [Simplify password resets](identity-secure-your-passwords.md#identity-pw-reset) step in the Identity phase for information and links to configure password resets in production.</span></span>

## <a name="next-step"></a><span data-ttu-id="a9627-150">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="a9627-150">Next step</span></span>

<span data-ttu-id="a9627-151">Explorar recursos e funcionalidades adicionais de [identidade](m365-enterprise-test-lab-guides.md#identity) no ambiente de teste.</span><span class="sxs-lookup"><span data-stu-id="a9627-151">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="a9627-152">Confira também</span><span class="sxs-lookup"><span data-stu-id="a9627-152">See also</span></span>

[<span data-ttu-id="a9627-153">Guias do Laboratório de Teste do Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="a9627-153">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="a9627-154">Implantar o Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="a9627-154">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="a9627-155">Documentação do Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="a9627-155">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
