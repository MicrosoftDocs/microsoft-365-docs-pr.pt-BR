---
title: Autenticação multifator para seu ambiente de teste do Microsoft 365 Enterprise
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/21/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom:
- TLG
- Ent_TLGs
description: Configurar a autenticação multifator usando mensagens de texto enviadas a um telefone inteligente no seu ambiente de teste do Microsoft 365 Enterprise.
ms.openlocfilehash: 8e202936451030718c0c86601c2c621c50f78e1a
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32291136"
---
# <a name="multi-factor-authentication-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="b9e53-103">Autenticação multifator para seu ambiente de teste do Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="b9e53-103">Multi-factor authentication for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="b9e53-104">Para obter um nível adicional de segurança para entrar no Office 365 ou qualquer serviço ou aplicativo que usa o locatário do Azure AD para sua organização, você pode habilitar a autenticação multifator do Azure, que requer mais do que apenas um nome de usuário e senha para verificar um Count.</span><span class="sxs-lookup"><span data-stu-id="b9e53-104">For an additional level of security for signing in to Office 365 or any service or application that uses the Azure AD tenant for your organization, you can enable Azure multi-factor authentication, which requires more than just a username and password to verify an account.</span></span> <span data-ttu-id="b9e53-105">Com a autenticação multifator, os usuários precisam confirmar uma chamada telefônica, digitar um código de verificação enviado em uma mensagem de texto ou especificar uma senha de aplicativo em seus telefones inteligentes após inserir corretamente suas senhas.</span><span class="sxs-lookup"><span data-stu-id="b9e53-105">With multi-factor authentication, users are required to acknowledge a phone call, type a verification code sent in a text message, or specify an app password on their smart phones after correctly entering their passwords.</span></span> <span data-ttu-id="b9e53-106">O acesso só será possível depois que esse segundo fator de autenticação for atendido.</span><span class="sxs-lookup"><span data-stu-id="b9e53-106">They can sign in only after this second authentication factor has been satisfied.</span></span> 
  
<span data-ttu-id="b9e53-107">Este artigo descreve como habilitar e testar a autenticação baseada em mensagem de texto para uma conta específica.</span><span class="sxs-lookup"><span data-stu-id="b9e53-107">This article describes how to enable and test text message-based authentication for a specific account.</span></span>
  
<span data-ttu-id="b9e53-108">Há duas fases para configurar a autenticação multifator para uma conta no seu ambiente de teste do Microsoft 365 Enterprise:</span><span class="sxs-lookup"><span data-stu-id="b9e53-108">There are two phases to setting up multi-factor authentication for an account in your Microsoft 365 Enterprise test environment:</span></span>
  
1. <span data-ttu-id="b9e53-109">Crie o ambiente de teste do Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="b9e53-109">Create the Microsoft 365 Enterprise test environment.</span></span>
    
2. <span data-ttu-id="b9e53-110">Habilite e teste a autenticação multifator para a conta do usuário 2.</span><span class="sxs-lookup"><span data-stu-id="b9e53-110">Enable and test multi-factor authentication for the User 2 account.</span></span>

![Guias de laboratório de teste da Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="b9e53-112">Clique [aqui](https://aka.ms/m365etlgstack) para ver um mapa visual de todos os artigos da pilha do Guia de Laboratório de Teste do Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="b9e53-112">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="b9e53-113">Fase 1: criar seu ambiente de teste do Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="b9e53-113">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="b9e53-114">Se você só quiser testar a autenticação multifator de forma leve com os requisitos mínimos, siga as instruções em [configuração básica leve](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="b9e53-114">If you just want to test multi-factor authentication in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="b9e53-115">Se você quiser testar a autenticação multifator em uma empresa simulada, siga as instruções em [autenticação de passagem](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="b9e53-115">If you want to test multi-factor authentication in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="b9e53-116">Testar a autenticação multifator não requer o ambiente de teste corporativo simulado, que inclui uma intranet simulada conectada à Internet e a sincronização de diretórios para uma floresta dos serviços de domínio Active Directory (AD DS).</span><span class="sxs-lookup"><span data-stu-id="b9e53-116">Testing multi-factor authentication does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for a Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="b9e53-117">É fornecida aqui como uma opção para que você possa testar a autenticação multifator e experimentá-la em um ambiente que representa uma organização típica.</span><span class="sxs-lookup"><span data-stu-id="b9e53-117">It is provided here as an option so that you can test multi-factor authentication and experiment with it in an environment that represents a typical organization.</span></span> 
  
## <a name="phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account"></a><span data-ttu-id="b9e53-118">Fase 2: habilitar e testar a autenticação multifator para a conta do usuário 2</span><span class="sxs-lookup"><span data-stu-id="b9e53-118">Phase 2: Enable and test multi-factor authentication for the User 2 account</span></span>

<span data-ttu-id="b9e53-119">Habilite a autenticação multifator para a conta do usuário 2 com estas etapas:</span><span class="sxs-lookup"><span data-stu-id="b9e53-119">Enable multi-factor authentication for the User 2 account with these steps:</span></span>
  
1. <span data-ttu-id="b9e53-120">Abra uma instância separada e privada do navegador, vá para o portal do Office ([https://office.com](https://office.com)) e entre com sua conta de administrador global.</span><span class="sxs-lookup"><span data-stu-id="b9e53-120">Open a separate, private instance of your browser, go to the Office portal ([https://office.com](https://office.com)), and then sign in with your global administrator account.</span></span>
    
2. <span data-ttu-id="b9e53-121">Na página principal do portal, clique em **Admin**.</span><span class="sxs-lookup"><span data-stu-id="b9e53-121">From the main portal page, click **Admin**.</span></span>
    
3. <span data-ttu-id="b9e53-122">Na navegação à esquerda, clique em **Usuários > Usuários ativos**.</span><span class="sxs-lookup"><span data-stu-id="b9e53-122">In the left navigation, click **Users > Active users**.</span></span>
    
4. <span data-ttu-id="b9e53-123">No painel usuários ativos, clique em **mais > configuração de autenticação**multifator.</span><span class="sxs-lookup"><span data-stu-id="b9e53-123">In the Active users pane, click **More > Multi-factor authentication setup**.</span></span>
    
5. <span data-ttu-id="b9e53-124">Na lista, selecione a conta do **usuário 2** .</span><span class="sxs-lookup"><span data-stu-id="b9e53-124">In the list, select the **User 2** account.</span></span>
    
6. <span data-ttu-id="b9e53-125">Na seção **usuário 2** , em **etapas rápidas**, clique em **habilitar**.</span><span class="sxs-lookup"><span data-stu-id="b9e53-125">In the **User 2** section, under **Quick steps**, click **Enable**.</span></span>
    
7. <span data-ttu-id="b9e53-126">Na caixa de diálogo **sobre como habilitar a autenticação** multifator, clique em **habilitar autenticação**multifator.</span><span class="sxs-lookup"><span data-stu-id="b9e53-126">In the **About enabling multi-factor auth** dialog box, click **Enable multi-factor auth**.</span></span>
    
8. <span data-ttu-id="b9e53-127">Na caixa de diálogo **atualizações com êxito** , clique em **fechar**.</span><span class="sxs-lookup"><span data-stu-id="b9e53-127">In the **Updates successful** dialog box, click **Close**.</span></span>
    
9. <span data-ttu-id="b9e53-128">Na guia **Microsoft Office Home** , clique no ícone da conta de usuário no canto superior direito e clique em \*\*\*\* sair.</span><span class="sxs-lookup"><span data-stu-id="b9e53-128">On the **Microsoft Office Home** tab, click the user account icon in the upper right, and then click **Sign out**.</span></span>
    
10. <span data-ttu-id="b9e53-129">Feche a instância do navegador.</span><span class="sxs-lookup"><span data-stu-id="b9e53-129">Close your browser instance.</span></span>
   
<span data-ttu-id="b9e53-130">Conclua a configuração da conta do usuário 2 para usar uma mensagem de texto para validação e testá-la com estas etapas:</span><span class="sxs-lookup"><span data-stu-id="b9e53-130">Complete the configuration for the User 2 account to use a text message for validation and test it with these steps:</span></span>
  
1. <span data-ttu-id="b9e53-131">Abra uma nova instância privada do navegador.</span><span class="sxs-lookup"><span data-stu-id="b9e53-131">Open a new, private instance of your browser.</span></span>
    
2. <span data-ttu-id="b9e53-132">Vá para o portal do Office[https://office.com](https://office.com)() e entre com a conta do usuário 2 (Usuário2\<@ Organization name>. onmicrosoft. com) e a senha.</span><span class="sxs-lookup"><span data-stu-id="b9e53-132">Go to the Office portal ([https://office.com](https://office.com)) and sign in with the User 2 account (user2@\<organization name>.onmicrosoft.com) and password.</span></span>
    
3. <span data-ttu-id="b9e53-133">Após entrar, você será solicitado a configurar a conta para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="b9e53-133">After signing in, you are prompted to set up the account for more information.</span></span> <span data-ttu-id="b9e53-134">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="b9e53-134">Click **Next**.</span></span>
    
4. <span data-ttu-id="b9e53-135">Na página **verificação de segurança adicional** :</span><span class="sxs-lookup"><span data-stu-id="b9e53-135">On the **Additional security verification** page:</span></span>
    
   - <span data-ttu-id="b9e53-136">Selecione seu país ou região.</span><span class="sxs-lookup"><span data-stu-id="b9e53-136">Select your country or region.</span></span>
    
   - <span data-ttu-id="b9e53-137">Digite o número de telefone do telefone inteligente que receberá mensagens de texto.</span><span class="sxs-lookup"><span data-stu-id="b9e53-137">Type phone number of the smart phone that will receive text messages.</span></span>
    
   - <span data-ttu-id="b9e53-138">Em **método**, clique em **enviar um código por mensagem de texto**.</span><span class="sxs-lookup"><span data-stu-id="b9e53-138">In **Method**, click **Send me a code by text message**.</span></span>
    
5. <span data-ttu-id="b9e53-139">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="b9e53-139">Click **Next**.</span></span>
    
6. <span data-ttu-id="b9e53-140">Insira o código de verificação da mensagem de texto recebida no telefone inteligente e clique em **verificar**.</span><span class="sxs-lookup"><span data-stu-id="b9e53-140">Enter the verification code from the text message received on your smart phone, and then click **Verify**.</span></span>
    
7. <span data-ttu-id="b9e53-141">Na página **etapa 3: manter seus aplicativos existentes** , registre a senha do aplicativo exibida para a conta do usuário 2 em um local seguro e clique em **concluído**.</span><span class="sxs-lookup"><span data-stu-id="b9e53-141">On the **Step 3: Keep your existing applications** page, record the displayed app password for the User 2 account in a secure location, and then click **Done**.</span></span>
    
8. <span data-ttu-id="b9e53-142">Se esta é a primeira vez que você entrou com a conta de usuário 2, você é solicitado a alterar a senha.</span><span class="sxs-lookup"><span data-stu-id="b9e53-142">If this is the first time you signed in with the User 2 account, you are prompted to change the password.</span></span> <span data-ttu-id="b9e53-143">Digite a senha original e uma nova senha duas vezes e clique em **Atualizar senha e entrar**.</span><span class="sxs-lookup"><span data-stu-id="b9e53-143">Type the original password and a new password twice, and then click **Update password and sign in**.</span></span> <span data-ttu-id="b9e53-144">Registre a nova senha em um local seguro.</span><span class="sxs-lookup"><span data-stu-id="b9e53-144">Record the new password in a secure location.</span></span>
    
    <span data-ttu-id="b9e53-145">Você deve ver o portal do Office para o usuário 2 na guia **Microsoft Office Home** do navegador.</span><span class="sxs-lookup"><span data-stu-id="b9e53-145">You should see the Office portal for User 2 on the **Microsoft Office Home** tab of your browser.</span></span>


<span data-ttu-id="b9e53-146">Consulte a etapa [Configurar a autenticação](identity-multi-factor-authentication.md#identity-mfa) multifator na fase Identity para obter informações e links para implantar a autenticação multifator em produção.</span><span class="sxs-lookup"><span data-stu-id="b9e53-146">See the [Set up multi-factor authentication](identity-multi-factor-authentication.md#identity-mfa) step in the Identity phase for information and links to deploy multi-factor authentication in production.</span></span>
    
## <a name="next-step"></a><span data-ttu-id="b9e53-147">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="b9e53-147">Next step</span></span>

<span data-ttu-id="b9e53-148">Explorar recursos e funcionalidades adicionais de [identidade](m365-enterprise-test-lab-guides.md#identity) no ambiente de teste.</span><span class="sxs-lookup"><span data-stu-id="b9e53-148">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="b9e53-149">Confira também</span><span class="sxs-lookup"><span data-stu-id="b9e53-149">See also</span></span>

[<span data-ttu-id="b9e53-150">Fase 2: Identidade</span><span class="sxs-lookup"><span data-stu-id="b9e53-150">Phase 2: Identity</span></span>](identity-infrastructure.md)

[<span data-ttu-id="b9e53-151">Guias do Laboratório de Teste do Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="b9e53-151">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="b9e53-152">Implantação do Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="b9e53-152">Microsoft 365 Enterprise deployment</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="b9e53-153">Documentação do Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="b9e53-153">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
