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
localization_priority: Normal
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom:
- TLGS
- Ent_TLGs
ms.assetid: ''
description: 'Resumo: configurar e testar a redefinição de senha do ambiente de teste do Microsoft 365.'
ms.openlocfilehash: efcaaf9ed1873c0908bb0e64644b8e10de280a01
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50921487"
---
# <a name="password-reset-for-your-microsoft-365-test-environment"></a><span data-ttu-id="f6efa-103">Redefinição de senha do ambiente de teste do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="f6efa-103">Password reset for your Microsoft 365 test environment</span></span>

<span data-ttu-id="f6efa-104">*Este Guia de Laboratório de Teste só pode ser usado para Microsoft 365 ambientes de teste corporativos.*</span><span class="sxs-lookup"><span data-stu-id="f6efa-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="f6efa-105">A redefinição de senha de autoatendimento (SSPR) do Azure Active Directory (Azure AD) permite que os usuários redefinam ou desbloqueiem suas senhas ou contas.</span><span class="sxs-lookup"><span data-stu-id="f6efa-105">Azure Active Directory (Azure AD) self-service password reset (SSPR) allows users to reset or unlock their passwords or accounts.</span></span>

<span data-ttu-id="f6efa-106">Este artigo descreve como configurar e testar redefinições de senha em seu ambiente Microsoft 365 teste.</span><span class="sxs-lookup"><span data-stu-id="f6efa-106">This article describes how to configure and test password resets in your Microsoft 365 test environment.</span></span>

<span data-ttu-id="f6efa-107">A configuração do SSPR envolve três fases:</span><span class="sxs-lookup"><span data-stu-id="f6efa-107">Setting up SSPR involves three phases:</span></span>
- [<span data-ttu-id="f6efa-108">Fase 1: configurar a sincronização de hash de senha do ambiente de teste do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="f6efa-108">Phase 1: Configure password hash synchronization for your Microsoft 365 test environment</span></span>](#phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment)
- [<span data-ttu-id="f6efa-109">Fase 2: Ativar o write-back de senha</span><span class="sxs-lookup"><span data-stu-id="f6efa-109">Phase 2: Enable password writeback</span></span>](#phase-2-enable-password-writeback)
- [<span data-ttu-id="f6efa-110">Fase 3: Configurar e testar a redefinição de senha</span><span class="sxs-lookup"><span data-stu-id="f6efa-110">Phase 3: Configure and test password reset</span></span>](#phase-3-configure-and-test-password-reset)
    
![Guias de Laboratório de Teste do Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="f6efa-112">Para um mapa visual de todos os artigos na pilha Microsoft 365 guia do laboratório de teste empresarial, vá para o Microsoft 365 para a pilha de guias de laboratório [de teste corporativos.](../downloads/Microsoft365EnterpriseTLGStack.pdf)</span><span class="sxs-lookup"><span data-stu-id="f6efa-112">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>

## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a><span data-ttu-id="f6efa-113">Fase 1: configurar a sincronização de hash de senha do ambiente de teste do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="f6efa-113">Phase 1: Configure password hash synchronization for your Microsoft 365 test environment</span></span>

<span data-ttu-id="f6efa-114">Primeiro, siga as instruções na [sincronização de hash de senha](password-hash-sync-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="f6efa-114">First, follow the instructions in [password hash synchronization](password-hash-sync-m365-ent-test-environment.md).</span></span> 

<span data-ttu-id="f6efa-115">Sua configuração resultante tem esta aparência:</span><span class="sxs-lookup"><span data-stu-id="f6efa-115">Your resulting configuration looks like this:</span></span>
  
![Empresa simulada com ambiente de teste de sincronização de hash de senha](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
<span data-ttu-id="f6efa-117">Esta configuração consiste em:</span><span class="sxs-lookup"><span data-stu-id="f6efa-117">This configuration consists of:</span></span>
  
- <span data-ttu-id="f6efa-118">Uma assinatura de avaliação ou assinatura paga do Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="f6efa-118">A Microsoft 365 E5 trial or paid subscription.</span></span>
- <span data-ttu-id="f6efa-119">Uma intranet de organização simplificada conectada à Internet, que consiste nas máquinas virtuais DC1, APP1 e CLIENT1 em uma sub-rede de uma rede virtual do Azure.</span><span class="sxs-lookup"><span data-stu-id="f6efa-119">A simplified organization intranet connected to the internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span>
- <span data-ttu-id="f6efa-120">O Azure AD Connect é executado no APP1 para sincronizar o domínio dos Serviços de domínio Active Directory (AD DS) do TESTLAB com o locatário do Azure AD da sua assinatura do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f6efa-120">Azure AD Connect runs on APP1 to synchronize the TESTLAB Active Directory Domain Services (AD DS) domain to the Azure AD tenant of your Microsoft 365 subscription.</span></span>

## <a name="phase-2-enable-password-writeback"></a><span data-ttu-id="f6efa-121">Fase 2: Ativar o write-back de senha</span><span class="sxs-lookup"><span data-stu-id="f6efa-121">Phase 2: Enable password writeback</span></span>

<span data-ttu-id="f6efa-122">Siga as instruções da [Fase 2 do Guia do laboratório de teste de write-back de senha](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain).</span><span class="sxs-lookup"><span data-stu-id="f6efa-122">Follow the instructions in [Phase 2 of the password writeback Test Lab Guide](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain).</span></span>

<span data-ttu-id="f6efa-123">O write-back de senha precisa estar habilitado para que você possa usar a redefinição de senha.</span><span class="sxs-lookup"><span data-stu-id="f6efa-123">You must have password writeback enabled to use password reset.</span></span>
  
## <a name="phase-3-configure-and-test-password-reset"></a><span data-ttu-id="f6efa-124">Fase 3: Configurar e testar a redefinição de senha</span><span class="sxs-lookup"><span data-stu-id="f6efa-124">Phase 3: Configure and test password reset</span></span>

<span data-ttu-id="f6efa-125">Nesta fase, configure a redefinição de senha no locatário do Azure AD por meio da associação ao grupo e verifique se ela funciona.</span><span class="sxs-lookup"><span data-stu-id="f6efa-125">In this phase, configure password reset in the Azure AD tenant through group membership, and then verify that it works.</span></span>

<span data-ttu-id="f6efa-126">Primeiro, habilite a redefinição de senhas para as contas em um grupo específico do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="f6efa-126">First, enable password reset for the accounts in a specific Azure AD group.</span></span>

1. <span data-ttu-id="f6efa-127">Abra o [https://portal.azure.com](https://portal.azure.com) em uma instância privada do navegador e entre com as credenciais da conta de administrador global.</span><span class="sxs-lookup"><span data-stu-id="f6efa-127">From a private instance of your browser, open [https://portal.azure.com](https://portal.azure.com), and then sign in with the credentials of your global administrator account.</span></span>
2. <span data-ttu-id="f6efa-128">No portal do Azure, selecione **Azure Active Directory**  >  **Grupos**  >  **Novo grupo**.</span><span class="sxs-lookup"><span data-stu-id="f6efa-128">In the Azure portal, select **Azure Active Directory** > **Groups** > **New group**.</span></span>
3. <span data-ttu-id="f6efa-129">Defina o **Tipo de grupo** como **Segurança**, **Nome do grupo** como **PWReset** e o **Tipo de associação** como **Atribuído**.</span><span class="sxs-lookup"><span data-stu-id="f6efa-129">Set the **Group type** to **Security**, **Group name** to **PWReset**, and the **Membership type** to **Assigned**.</span></span>
4. <span data-ttu-id="f6efa-130">Selecione **Membros,** encontre e selecione **Usuário 3,** selecione **Selecionar** e selecione **Criar**.</span><span class="sxs-lookup"><span data-stu-id="f6efa-130">Select **Members**, find and select **User 3**, select **Select**, and then select **Create**.</span></span>
5. <span data-ttu-id="f6efa-131">Feche o painel de **Grupos**.</span><span class="sxs-lookup"><span data-stu-id="f6efa-131">Close the **Groups** pane.</span></span>
6. <span data-ttu-id="f6efa-132">No painel Azure Active Directory, selecione **Redefinição de senha** na navegação à esquerda.</span><span class="sxs-lookup"><span data-stu-id="f6efa-132">In the Azure Active Directory pane, select **Password reset** in the left navigation.</span></span>
7. <span data-ttu-id="f6efa-133">No painel **Redefinição de senha-Propriedades**, vá até a opção **Redefinição da Senha de Autoatendimento Habilitada** e escolha **Selecionado**.</span><span class="sxs-lookup"><span data-stu-id="f6efa-133">In the **Password reset-Properties** pane, under the option **Self Service Password Reset Enabled**, choose **Selected**.</span></span>
8. <span data-ttu-id="f6efa-134">Selecione **Selecionar grupo,** selecione o **grupo PWReset** e selecione **Selecionar**  >  **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="f6efa-134">Select **Select group**, select the **PWReset** group, and then select **Select** > **Save**.</span></span>
9. <span data-ttu-id="f6efa-135">Feche a instância privada do navegador.</span><span class="sxs-lookup"><span data-stu-id="f6efa-135">Close the private browser instance.</span></span>

<span data-ttu-id="f6efa-136">Em seguida, teste a redefinição de senha para a conta usuário 3.</span><span class="sxs-lookup"><span data-stu-id="f6efa-136">Next, test password reset for the User 3 account.</span></span>

1. <span data-ttu-id="f6efa-137">Abra outra instância privada do navegador e vá para [https://aka.ms/ssprsetup](https://aka.ms/ssprsetup).</span><span class="sxs-lookup"><span data-stu-id="f6efa-137">Open a new private browser instance and browse to [https://aka.ms/ssprsetup](https://aka.ms/ssprsetup).</span></span>
1. <span data-ttu-id="f6efa-138">Entre usando as credenciais da conta do Usuário 3.</span><span class="sxs-lookup"><span data-stu-id="f6efa-138">Sign in with the User 3 account credentials.</span></span>
1. <span data-ttu-id="f6efa-139">Em **Mais informações necessárias,** selecione **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="f6efa-139">In **More information required**, select **Next**.</span></span> 
1. <span data-ttu-id="f6efa-140">Em **Não perca o acesso à sua conta**, defina o telefone de autenticação como seu número de celular e o e-mail de autenticação como sua conta de e-mail pessoal ou profissional.</span><span class="sxs-lookup"><span data-stu-id="f6efa-140">In **Don't lose access to your account**, set the authentication phone to your mobile phone number and the authentication email to your work or personal email account.</span></span>
1. <span data-ttu-id="f6efa-141">Depois que ambos são verificados, selecione **Aparência boa** e, em seguida, feche a instância privada do navegador.</span><span class="sxs-lookup"><span data-stu-id="f6efa-141">After both are verified, select **Looks good**, and then close the private instance of the browser.</span></span>
1. <span data-ttu-id="f6efa-142">Em uma nova instância privada do navegador, vá para [https://aka.ms/sspr](https://aka.ms/sspr) .</span><span class="sxs-lookup"><span data-stu-id="f6efa-142">In a new private browser instance, go to [https://aka.ms/sspr](https://aka.ms/sspr).</span></span>
1. <span data-ttu-id="f6efa-143">Insira o nome da conta Usuário 3, insira os caracteres do CAPTCHA e selecione **Next**.</span><span class="sxs-lookup"><span data-stu-id="f6efa-143">Enter the User 3 account name, enter the characters from the CAPTCHA, and then select **Next**.</span></span>
1. <span data-ttu-id="f6efa-144">Para **a etapa de verificação 1,** selecione Email meu email **alternativo** e selecione **Email**.</span><span class="sxs-lookup"><span data-stu-id="f6efa-144">For **verification step 1**, select **Email my alternate email**, and then select **Email**.</span></span> <span data-ttu-id="f6efa-145">Quando você receber o email, insira o código de verificação e selecione **Next**.</span><span class="sxs-lookup"><span data-stu-id="f6efa-145">When you receive the email, enter the verification code, and then select **Next**.</span></span>
1. <span data-ttu-id="f6efa-146">Em **Voltar para sua conta,** insira uma nova senha para a conta usuário 3 e selecione **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="f6efa-146">In **Get back into your account**, enter a new password for the User 3 account, and then select **Finish**.</span></span> <span data-ttu-id="f6efa-147">Anote a senha alterada da conta do Usuário 3 e armazene-a em um local seguro.</span><span class="sxs-lookup"><span data-stu-id="f6efa-147">Note the changed password of the User 3 account and store it in a safe location.</span></span>
1. <span data-ttu-id="f6efa-148">Em uma guia separada do mesmo navegador, vá para [https://portal.office.com](https://portal.office.com) e entre com o nome da conta do Usuário 3 e sua nova senha.</span><span class="sxs-lookup"><span data-stu-id="f6efa-148">In a separate tab of the same browser, go to [https://portal.office.com](https://portal.office.com), and then sign in with the User 3 account name and its new password.</span></span> <span data-ttu-id="f6efa-149">Você verá a **home page do Microsoft Office**.</span><span class="sxs-lookup"><span data-stu-id="f6efa-149">You should see the **Microsoft Office Home** page.</span></span>

## <a name="next-step"></a><span data-ttu-id="f6efa-150">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="f6efa-150">Next step</span></span>

<span data-ttu-id="f6efa-151">Explorar recursos e funcionalidades adicionais de [identidade](m365-enterprise-test-lab-guides.md#identity) no ambiente de teste.</span><span class="sxs-lookup"><span data-stu-id="f6efa-151">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="f6efa-152">Confira também</span><span class="sxs-lookup"><span data-stu-id="f6efa-152">See also</span></span>

[<span data-ttu-id="f6efa-153">Guias do Laboratório de Teste do Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="f6efa-153">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="f6efa-154">Visão geral do Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="f6efa-154">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="f6efa-155">Documentação do Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="f6efa-155">Microsoft 365 for enterprise documentation</span></span>](/microsoft-365-enterprise/)