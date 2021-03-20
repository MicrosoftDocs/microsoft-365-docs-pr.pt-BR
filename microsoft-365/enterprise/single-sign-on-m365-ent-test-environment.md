---
title: O Logon único Contínuo do Azure AD para o ambiente de teste do Microsoft 365
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/21/2019
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
description: 'Resumo: configure e teste o Logon único Contínuo do Azure AD para o ambiente de teste do Microsoft 365.'
ms.openlocfilehash: 7fcbc82cfb35c598358c8160dd06427c2a9c59a2
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50904859"
---
# <a name="azure-ad-seamless-single-sign-on-for-your-microsoft-365-test-environment"></a><span data-ttu-id="90535-103">O Logon único Contínuo do Azure AD para o ambiente de teste do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="90535-103">Azure AD Seamless Single Sign-on for your Microsoft 365 test environment</span></span>

<span data-ttu-id="90535-104">*Este Guia de Laboratório de Teste pode ser usado para ambientes de teste do Microsoft 365 para empresas e office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="90535-104">*This Test Lab Guide can be used for both Microsoft 365 for enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="90535-105">O Azure AD Seamless Single Sign-On (SSO contínuo) conecta automaticamente os usuários quando estão em seus PCs ou dispositivos conectados à rede da organização.</span><span class="sxs-lookup"><span data-stu-id="90535-105">Azure AD Seamless Single Sign-On (Seamless SSO) automatically signs in users when they are on their PCs or devices that are connected to their organization network.</span></span> <span data-ttu-id="90535-106">O SSO Contínuo do Azure AD fornece aos usuários acesso fácil a aplicativos baseados em nuvem sem precisar de componentes locais adicionais.</span><span class="sxs-lookup"><span data-stu-id="90535-106">Azure AD Seamless SSO provides users with easy access to cloud-based applications without needing any additional on-premises components.</span></span>

<span data-ttu-id="90535-107">Este artigo descreve como configurar seu ambiente de teste do Microsoft 365 para o SSO contínuo do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="90535-107">This article describes how to configure your Microsoft 365 test environment for Azure AD Seamless SSO.</span></span>

<span data-ttu-id="90535-108">Configurar o SSO contínuo do Azure AD envolve duas fases:</span><span class="sxs-lookup"><span data-stu-id="90535-108">Setting up Azure AD Seamless SSO involves two phases:</span></span>
- [<span data-ttu-id="90535-109">Fase 1: configurar a sincronização de hash de senha do ambiente de teste do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="90535-109">Phase 1: Configure password hash synchronization for your Microsoft 365 test environment</span></span>](#phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment)
- [<span data-ttu-id="90535-110">Fase 2: configure o Azure Active Directory Connect no APP1 para o SSO Contínuo do Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="90535-110">Phase 2: Configure Azure AD Connect on APP1 for Azure AD Seamless SSO</span></span>](#phase-2-configure-azure-ad-connect-on-app1-for-azure-ad-seamless-sso)
   
![Guias de Laboratório de Teste do Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="90535-112">Para um mapa visual de todos os artigos na pilha guia de laboratório de teste do Microsoft 365 para empresas, vá para [o Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span><span class="sxs-lookup"><span data-stu-id="90535-112">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>
  
## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a><span data-ttu-id="90535-113">Fase 1: configurar a sincronização de hash de senha do ambiente de teste do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="90535-113">Phase 1: Configure password hash synchronization for your Microsoft 365 test environment</span></span>

<span data-ttu-id="90535-114">Siga as instruções na [sincronização de hash de senha para o Microsoft 365](password-hash-sync-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="90535-114">Follow the instructions in [password hash synchronization for Microsoft 365](password-hash-sync-m365-ent-test-environment.md).</span></span> 

<span data-ttu-id="90535-115">Sua configuração resultante tem esta aparência:</span><span class="sxs-lookup"><span data-stu-id="90535-115">Your resulting configuration looks like this:</span></span>
  
![Empresa simulada com ambiente de teste de sincronização de hash de senha](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
<span data-ttu-id="90535-117">Esta configuração consiste em:</span><span class="sxs-lookup"><span data-stu-id="90535-117">This configuration consists of:</span></span>
  
- <span data-ttu-id="90535-118">Uma assinatura de avaliação ou assinatura paga do Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="90535-118">A Microsoft 365 E5 trial or paid subscription.</span></span>
- <span data-ttu-id="90535-119">Uma intranet de organização simplificada conectada à Internet, que consiste nas máquinas virtuais DC1, APP1 e CLIENT1 em uma sub-rede de uma rede virtual do Azure.</span><span class="sxs-lookup"><span data-stu-id="90535-119">A simplified organization intranet connected to the internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span>
- <span data-ttu-id="90535-120">O Azure AD Connect é executado no APP1 para sincronizar periodicamente o domínio testlab active directory domain Services (AD DS) com o locatário do Azure AD da sua assinatura do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="90535-120">Azure AD Connect runs on APP1 to periodically synchronize the TESTLAB Active Directory Domain Services (AD DS) domain to the Azure AD tenant of your Microsoft 365 subscription.</span></span>

## <a name="phase-2-configure-azure-ad-connect-on-app1-for-azure-ad-seamless-sso"></a><span data-ttu-id="90535-121">Fase 2: configure o Azure Active Directory Connect no APP1 para o SSO Contínuo do Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="90535-121">Phase 2: Configure Azure AD Connect on APP1 for Azure AD Seamless SSO</span></span>

<span data-ttu-id="90535-122">Nesta fase, configure o Azure AD Connect no APP1 para o SSO contínuo do Azure AD e verifique se ele funciona.</span><span class="sxs-lookup"><span data-stu-id="90535-122">In this phase, configure Azure AD Connect on APP1 for Azure AD Seamless SSO, and then verify that it works.</span></span>

### <a name="configure-azure-ad-connect-on-app1"></a><span data-ttu-id="90535-123">Configurar o Azure AD Connect no APP1</span><span class="sxs-lookup"><span data-stu-id="90535-123">Configure Azure AD Connect on APP1</span></span>

1. <span data-ttu-id="90535-124">No [Portal do Azure](https://portal.azure.com), entre com a conta de administrador global e conecte-se ao APP1 com a conta TESTLAB\Usuário1.</span><span class="sxs-lookup"><span data-stu-id="90535-124">From the [Azure portal](https://portal.azure.com), sign in with your global administrator account, and then connect to APP1 with the TESTLAB\User1 account.</span></span>

2. <span data-ttu-id="90535-125">Na área de trabalho APP1, execute o Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="90535-125">From the APP1 desktop, run Azure AD Connect.</span></span>

3. <span data-ttu-id="90535-126">Na página **Bem-vindo,** selecione **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="90535-126">On the **Welcome page**, select **Configure**.</span></span>

4. <span data-ttu-id="90535-127">Na página **Tarefas adicionais,** selecione **Alterar a login do** usuário e selecione **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="90535-127">On the **Additional tasks** page, select **Change user sign-in**, and then select **Next**.</span></span>

5. <span data-ttu-id="90535-128">Na página **Conectar-se ao Azure AD,** insira suas credenciais de conta de administrador global e selecione **Next**.</span><span class="sxs-lookup"><span data-stu-id="90535-128">On the **Connect to Azure AD** page, enter your global administrator account credentials, and then select **Next**.</span></span>

6. <span data-ttu-id="90535-129">Na página **Login do** usuário, selecione Habilitar **logom único** e selecione **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="90535-129">On the **User sign-in** page, select **Enable single sign-on**, and then select **Next**.</span></span>

7. <span data-ttu-id="90535-130">Na página **Habilitar entrada** única, selecione **Inserir credenciais**.</span><span class="sxs-lookup"><span data-stu-id="90535-130">On the **Enable single sign-on** page, select **Enter credentials**.</span></span>

8. <span data-ttu-id="90535-131">Na caixa de diálogo Segurança do **Windows,** insira **user1** e a senha da conta user1, selecione **OK** e selecione **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="90535-131">In the **Windows Security** dialog box, enter **user1** and the password of the user1 account, select **OK**, and then select **Next**.</span></span>

9. <span data-ttu-id="90535-132">Na página **Pronto para Configurar,** selecione **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="90535-132">On the **Ready to Configure** page, select **Configure**.</span></span>

10. <span data-ttu-id="90535-133">Na página **Configuração completa,** selecione **Sair**.</span><span class="sxs-lookup"><span data-stu-id="90535-133">On the **Configuration complete** page, select **Exit**.</span></span>

11. <span data-ttu-id="90535-134">No portal do Azure, no painel esquerdo, selecione **Azure Active Directory**  >  **Azure AD Connect**.</span><span class="sxs-lookup"><span data-stu-id="90535-134">From the Azure portal, in the left pane, select **Azure Active Directory** > **Azure AD Connect**.</span></span> <span data-ttu-id="90535-135">Verifique se o **recurso de logom único** contínuo aparece como **Habilitado**.</span><span class="sxs-lookup"><span data-stu-id="90535-135">Verify that the **Seamless single sign-on** feature appears as **Enabled**.</span></span>

<span data-ttu-id="90535-136">Em seguida, teste a capacidade de entrar em sua assinatura com o <strong>user1@testlab.</strong>\<*your public domain*></span><span class="sxs-lookup"><span data-stu-id="90535-136">Next, test the ability to sign in to your subscription with the <strong>user1@testlab.</strong>\<*your public domain*></span></span> <span data-ttu-id="90535-137">nome de usuário da conta User1.</span><span class="sxs-lookup"><span data-stu-id="90535-137">user name of the User1 account.</span></span>

1. <span data-ttu-id="90535-138">No Internet Explorer no APP1, selecione o ícone de configurações e selecione **Opções da Internet**.</span><span class="sxs-lookup"><span data-stu-id="90535-138">From Internet Explorer on APP1, select the settings icon, and then select **Internet Options**.</span></span>
 
2. <span data-ttu-id="90535-139">Em **Opções da Internet,** selecione a **guia** Segurança.</span><span class="sxs-lookup"><span data-stu-id="90535-139">In **Internet Options**, select the **Security** tab.</span></span>

3. <span data-ttu-id="90535-140">Selecione **Intranet Local** e, em seguida, selecione **Sites**.</span><span class="sxs-lookup"><span data-stu-id="90535-140">Select **Local intranet**, and then select **Sites**.</span></span>

4. <span data-ttu-id="90535-141">Na **intranet local,** selecione **Avançado**.</span><span class="sxs-lookup"><span data-stu-id="90535-141">In **Local intranet**, select **Advanced**.</span></span>

5. <span data-ttu-id="90535-142">Em **Adicionar este site à zona**, insira **https <span>://</span>autologon.microsoftazuread-sso.com**, selecione Adicionar   >  **Fechar**  >  **OK**  >  **OK**.</span><span class="sxs-lookup"><span data-stu-id="90535-142">In **Add this website to the zone**, enter **https <span>://</span>autologon.microsoftazuread-sso.com**, select **Add** > **Close** > **OK** > **OK**.</span></span>

6. <span data-ttu-id="90535-143">Saia e entre novamente, mas desta vez especifique uma conta diferente.</span><span class="sxs-lookup"><span data-stu-id="90535-143">Sign out, and then sign in again, this time specifying a different account.</span></span>

7. <span data-ttu-id="90535-144">Quando solicitado a entrar, especifique <strong>user1@testlab.</strong>\<*your public domain*></span><span class="sxs-lookup"><span data-stu-id="90535-144">When prompted to sign in, specify <strong>user1@testlab.</strong>\<*your public domain*></span></span> <span data-ttu-id="90535-145">name e, em seguida, selecione **Next**.</span><span class="sxs-lookup"><span data-stu-id="90535-145">name, and then select **Next**.</span></span> <span data-ttu-id="90535-146">Você deve conseguir entrar como Usuário1 sem que uma senha seja solicitada.</span><span class="sxs-lookup"><span data-stu-id="90535-146">You should successfully sign in as User1 without being prompted for a password.</span></span> <span data-ttu-id="90535-147">Isso prova que o SSO de conexão remota do Azure AD está funcionando.</span><span class="sxs-lookup"><span data-stu-id="90535-147">This proves that Azure AD Seamless SSO is working.</span></span>

<span data-ttu-id="90535-148">Observe que, embora o Usuário1 tenha permissões de administrador de domínio para o domínio TESTLAB do AD DS, ele não é um administrador global do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="90535-148">Notice that although User1 has domain administrator permissions for the TESTLAB AD DS domain, it is not a global administrator for Azure AD.</span></span> <span data-ttu-id="90535-149">Portanto, o ícone **Administrador** não estará disponível como opção.</span><span class="sxs-lookup"><span data-stu-id="90535-149">Therefore, you will not see the **Admin** icon as an option.</span></span>

<span data-ttu-id="90535-150">Esta é a configuração resultante:</span><span class="sxs-lookup"><span data-stu-id="90535-150">Here is your resulting configuration:</span></span>

![A empresa simulada com ambiente de teste de autenticação de passagem](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)

<span data-ttu-id="90535-152">Esta configuração consiste em:</span><span class="sxs-lookup"><span data-stu-id="90535-152">This configuration consists of:</span></span>

- <span data-ttu-id="90535-153">Uma avaliação do Microsoft 365 E5 ou assinaturas pagas com o testlab de domínio DNS.\<*your domain name*></span><span class="sxs-lookup"><span data-stu-id="90535-153">A Microsoft 365 E5 trial or paid subscriptions with the DNS domain testlab.\<*your domain name*></span></span> <span data-ttu-id="90535-154">registrado.</span><span class="sxs-lookup"><span data-stu-id="90535-154">registered.</span></span>
- <span data-ttu-id="90535-155">Uma intranet de organização simplificada conectada à Internet, que consiste nas máquinas virtuais DC1, APP1 e CLIENT1 em uma sub-rede de uma rede virtual do Azure.</span><span class="sxs-lookup"><span data-stu-id="90535-155">A simplified organization intranet connected to the internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span>
- <span data-ttu-id="90535-156">O Azure AD Connect é executado no APP1 para sincronizar a lista de contas e grupos do locatário do Azure AD da sua assinatura do Microsoft 365 para o domínio TESTLAB AD DS.</span><span class="sxs-lookup"><span data-stu-id="90535-156">Azure AD Connect runs on APP1 to synchronize the list of accounts and groups from the Azure AD tenant of your Microsoft 365 subscription to the TESTLAB AD DS domain.</span></span>
- <span data-ttu-id="90535-157">O SSO Contínuo do Azure AD está habilitado para que os computadores na intranet simulada possam entrar nos recursos de nuvem do Microsoft 365 sem especificar uma senha de conta de usuário.</span><span class="sxs-lookup"><span data-stu-id="90535-157">Azure AD Seamless SSO is enabled so that computers on the simulated intranet can sign in to Microsoft 365 cloud resources without specifying a user account password.</span></span>

## <a name="next-step"></a><span data-ttu-id="90535-158">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="90535-158">Next step</span></span>

<span data-ttu-id="90535-159">Explorar recursos e funcionalidades adicionais de [identidade](m365-enterprise-test-lab-guides.md#identity) no ambiente de teste.</span><span class="sxs-lookup"><span data-stu-id="90535-159">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="90535-160">Confira também</span><span class="sxs-lookup"><span data-stu-id="90535-160">See also</span></span>

[<span data-ttu-id="90535-161">Guias do Laboratório de Teste do Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="90535-161">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="90535-162">Visão geral do Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="90535-162">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="90535-163">Documentação do Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="90535-163">Microsoft 365 for enterprise documentation</span></span>](/microsoft-365-enterprise/)