---
title: O Logon único Contínuo do Azure AD para o ambiente de teste do Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/21/2018
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
description: 'Resumo: configure e teste o Logon único Contínuo do Azure AD para o ambiente de teste do Microsoft 365.'
ms.openlocfilehash: c8417d7ff1c4a2b9a753968804d187300b6c6195
ms.sourcegitcommit: 2c2248b03f7753d64490f2f7e56ec644a235b65a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/15/2019
ms.locfileid: "38640592"
---
# <a name="azure-ad-seamless-single-sign-on-for-your-microsoft-365-test-environment"></a><span data-ttu-id="32788-103">O Logon único Contínuo do Azure AD para o ambiente de teste do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="32788-103">Azure AD Seamless Single Sign-on for your Microsoft 365 test environment</span></span>

<span data-ttu-id="32788-p101">O Logon Único (SSO) Contínuo do Azure AD dá acesso automático de usuários quando eles estão em seus computadores ou dispositivos conectados à rede da sua organização. O SSO Contínuo do Azure AD fornece aos usuários acesso fácil às aplicativos baseados na nuvem sem precisar de componentes locais adicionais.</span><span class="sxs-lookup"><span data-stu-id="32788-p101">Azure AD Seamless Single Sign-On (SSO) automatically signs in users when they are on their PCs or devices that are connected to their organization network. Azure AD Seamless SSO provides users with easy access to cloud-based applications without needing any additional on-premises components.</span></span>

<span data-ttu-id="32788-106">Este artigo descreve como você pode configurar seu ambiente de teste do Microsoft 365 para o SSO Contínuo do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="32788-106">This article describes how you can configure your Microsoft 365 test environment for Azure AD Seamless SSO.</span></span>

<span data-ttu-id="32788-107">Há duas etapas para fazer a configuração:</span><span class="sxs-lookup"><span data-stu-id="32788-107">There are two phases to setting this up:</span></span>

1.  <span data-ttu-id="32788-108">Criar o ambiente de teste de empresa simulada do Microsoft 365 com sincronização de hash de senha.</span><span class="sxs-lookup"><span data-stu-id="32788-108">Create the Microsoft 365 simulated enterprise test environment with password hash synchronization.</span></span>
2.  <span data-ttu-id="32788-109">Configurar o Azure Active Directory Connect no APP1 para o SSO Contínuo do Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="32788-109">Configure Azure AD Connect on APP1 for Azure AD Seamless SSO.</span></span>
    
![Guias de laboratório de teste da Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="32788-111">Clique [aqui](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) para ver um mapa visual de todos os artigos da pilha do Guia de Laboratório de Teste do Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="32788-111">Click [here](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a><span data-ttu-id="32788-112">Fase 1: configurar a sincronização de hash de senha do ambiente de teste do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="32788-112">Phase 1: Configure password hash synchronization for your Microsoft 365 test environment</span></span>

<span data-ttu-id="32788-p102">Siga as instruções em [sincronização de hash de senha para o Microsoft 365](password-hash-sync-m365-ent-test-environment.md). Aqui está a configuração resultante.</span><span class="sxs-lookup"><span data-stu-id="32788-p102">Follow the instructions in [password hash synchronization for Microsoft 365](password-hash-sync-m365-ent-test-environment.md). Here is your resulting configuration.</span></span>
  
![Empresa simulada com ambiente de teste de sincronização de hash de senha](media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
<span data-ttu-id="32788-116">Esta configuração consiste em:</span><span class="sxs-lookup"><span data-stu-id="32788-116">This configuration consists of:</span></span> 
  
- <span data-ttu-id="32788-117">Assinaturas pagas ou de avaliação do Office 365 E5 e EMS E5.</span><span class="sxs-lookup"><span data-stu-id="32788-117">Office 365 E5 and EMS E5 trial or paid subscriptions.</span></span>
- <span data-ttu-id="32788-118">Uma intranet de organização simplificada conectado à Internet, que consiste em máquinas virtuais do DC1 APP1 e CLIENT1 em uma sub-rede de uma rede virtual do Azure.</span><span class="sxs-lookup"><span data-stu-id="32788-118">A simplified organization intranet connected to the Internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span> 
- <span data-ttu-id="32788-119">O Azure AD Connect é executado no APP1 para sincronizar periodicamente o domínio TESTLAB do Active Directory Domain Services (AD DS) com o locatário do Azure AD de suas assinaturas do Office 365 e do EMS E5.</span><span class="sxs-lookup"><span data-stu-id="32788-119">Azure AD Connect runs on APP1 to synchronize the TESTLAB Active Directory Domain Services (AD DS) domain to the Azure AD tenant of your Office 365 and EMS E5 subscriptions periodically.</span></span>

## <a name="phase-2-configure-azure-ad-connect-on-app1-for-azure-ad-seamless-sso"></a><span data-ttu-id="32788-120">Fase 2: configure o Azure Active Directory Connect no APP1 para o SSO Contínuo do Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="32788-120">Phase 2: Configure Azure AD Connect on APP1 for Azure AD Seamless SSO</span></span>

<span data-ttu-id="32788-121">Nesta fase, você configura o Azure AD Connect no APP1 para SSO Contínuo do Azure AD e, em seguida, verifica se isso funciona.</span><span class="sxs-lookup"><span data-stu-id="32788-121">In this phase, you configure Azure AD Connect on APP1 for Azure AD Seamless SSO, and then verify that it works.</span></span>

### <a name="configure-azure-ad-connect-on-app1"></a><span data-ttu-id="32788-122">Configurar o Azure AD Connect no APP1</span><span class="sxs-lookup"><span data-stu-id="32788-122">Configure Azure AD Connect on APP1</span></span>

1. <span data-ttu-id="32788-123">No [Portal do Azure](https://portal.azure.com), entre com a conta de administrador global e conecte-se ao APP1 com a conta TESTLAB\Usuário1.</span><span class="sxs-lookup"><span data-stu-id="32788-123">From the [Azure portal](https://portal.azure.com), sign in with your global administrator account, and then connect to APP1 with the TESTLAB\User1 account.</span></span>

2. <span data-ttu-id="32788-124">Na área de trabalho do APP1, execute o Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="32788-124">From the desktop of APP1, run Azure AD Connect.</span></span>

3. <span data-ttu-id="32788-125">Na **Página inicial**, clique em **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="32788-125">On the **Welcome page**, click **Configure**.</span></span>

4. <span data-ttu-id="32788-126">Na página **Tarefas Adicionais**, clique em **Alterar entrada do usuário** e em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="32788-126">On the **Additional tasks** page, click **Change user sign-in**, and then click **Next**.</span></span>

5. <span data-ttu-id="32788-127">Na página **Conectar ao Azure AD**, digite suas credenciais de conta de administrador global e clique em **Próxima**.</span><span class="sxs-lookup"><span data-stu-id="32788-127">On the **Connect to Azure AD** page, type your global administrator account credentials, and then click **Next**.</span></span>

6. <span data-ttu-id="32788-128">Na página **Entrada do usuário**, selecione **Habilitar logon único** e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="32788-128">On the **User sign-in** page, select **Enable single sign-on**, and then click **Next**.</span></span>

7. <span data-ttu-id="32788-129">Na página **Habilitar o logon único**, clique em **Inserir credenciais**.</span><span class="sxs-lookup"><span data-stu-id="32788-129">On the **Enable single sign-on** page, click **Enter credentials**.</span></span>

8. <span data-ttu-id="32788-p103">Na caixa de diálogo **Segurança do Windows**, digite **usuário1** e a senha da conta do Usuário1 e clique em **OK**. Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="32788-p103">In the **Windows Security** dialog box, type **user1** and the password of the user1 account, and then click **OK**. Click **Next**.</span></span>

9. <span data-ttu-id="32788-132">Na página **Pronto para Configurar**, clique em **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="32788-132">On the **Ready to Configure** page, click **Configure**.</span></span>

10. <span data-ttu-id="32788-133">Na página **Configuração concluída**, clique em **Sair**.</span><span class="sxs-lookup"><span data-stu-id="32788-133">On the **Configuration complete** page, click **Exit**.</span></span>

11. <span data-ttu-id="32788-p104">No portal do Azure, no painel esquerdo, clique em **Azure Active Directory > Azure AD Connect Health**. Verifique se o recurso **Logon único Contínuo** aparece como **Habilitado**.</span><span class="sxs-lookup"><span data-stu-id="32788-p104">From the Azure portal, in the left pane, click **Azure Active Directory > Azure AD Connect**. Verify that the **Seamless single sign-on** feature appears as **Enabled**.</span></span>

<span data-ttu-id="32788-136">Em seguida, teste a capacidade de entrar na assinatura do Office 365 com a conta <strong>usuario1@testlab.</strong>\<seu domínio público>nome de usuário da conta Usuário1.</span><span class="sxs-lookup"><span data-stu-id="32788-136">Next, test the ability to sign in to your Office 365 subscription with the <strong>user1@testlab.</strong>\<your public domain> user name of the User1 account.</span></span>

1. <span data-ttu-id="32788-137">Do Internet Explorer para APP1, clique no ícone de configurações e, em seguida, clique em **Opções da Internet**.</span><span class="sxs-lookup"><span data-stu-id="32788-137">From Internet Explorer on APP1, click the settings icon, and then click **Internet Options**.</span></span>
 
2. <span data-ttu-id="32788-138">Em **Opções da Internet**, clique na guia **Segurança**.</span><span class="sxs-lookup"><span data-stu-id="32788-138">In **Internet Options**, click the **Security** tab.</span></span>

3. <span data-ttu-id="32788-139">Clique em **Intranet local** e, em seguida, clique em **Sites**.</span><span class="sxs-lookup"><span data-stu-id="32788-139">Click **Local intranet**, and then click **Sites**.</span></span>

4. <span data-ttu-id="32788-140">Na **Intranet Local**, clique em **Avançado**.</span><span class="sxs-lookup"><span data-stu-id="32788-140">In **Local intranet**, click **Advanced**.</span></span>

5. <span data-ttu-id="32788-141">Em **Adicionar este site à zona**, digite **https<span>://</span>autologon.microsoftazuread-sso.com**, clique em **Adicionar > Fechar > OK > OK**.</span><span class="sxs-lookup"><span data-stu-id="32788-141">In **Add this website to the zone**, type **https<span>://</span>autologon.microsoftazuread-sso.com**, click **Add > Close > OK > OK**.</span></span>

6. <span data-ttu-id="32788-142">Encerre o Office 365 e entre novamente, mas desta vez especifique uma conta diferente.</span><span class="sxs-lookup"><span data-stu-id="32788-142">Sign out of Office 365, and then sign in again, this time specifying a different account.</span></span>

7. <span data-ttu-id="32788-143">Quando solicitado a fazer login, especifique <strong>usuário1@testlab.</strong>\<o nome de seu domínio público> e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="32788-143">When prompted to sign in, specify <strong>user1@testlab.</strong>\<your public domain> name, and then click **Next**.</span></span> <span data-ttu-id="32788-144">Você deve conseguir entrar como Usuário1 sem que uma senha seja solicitada.</span><span class="sxs-lookup"><span data-stu-id="32788-144">You should successfully sign in as User1 without being prompted for a password.</span></span> <span data-ttu-id="32788-145">Isso prova que o SSO de conexão remota do Azure AD está funcionando.</span><span class="sxs-lookup"><span data-stu-id="32788-145">This proves that Azure AD Seamless SSO is working.</span></span>

<span data-ttu-id="32788-146">Observe que, embora o Usuário1 tenha permissões de administrador de domínio para o domínio do AD DS TESTLAB, ele não é um administrador global do Azure AD e do Office 365.</span><span class="sxs-lookup"><span data-stu-id="32788-146">Notice that although User1 has domain administrator permissions for the TESTLAB AD DS domain, it is not a global administrator for Azure AD and Office 365.</span></span> <span data-ttu-id="32788-147">Portanto, o ícone **Administrador** não estará disponível como opção.</span><span class="sxs-lookup"><span data-stu-id="32788-147">Therefore, you will not see the **Admin** icon as an option.</span></span>

<span data-ttu-id="32788-148">Esta é a configuração resultante:</span><span class="sxs-lookup"><span data-stu-id="32788-148">Here is your resulting configuration:</span></span>

![A empresa simulada com ambiente de teste de autenticação de passagem](media/pass-through-auth-m365-ent-test-environment/Phase1.png)

 
<span data-ttu-id="32788-150">Esta configuração consiste em:</span><span class="sxs-lookup"><span data-stu-id="32788-150">This configuration consists of:</span></span>

- <span data-ttu-id="32788-151">Assinaturas pagas ou de avaliação do Office 365 E5 e EMS E5 com o domínio DNS testlab.\<seu nome de domínio> registrado.</span><span class="sxs-lookup"><span data-stu-id="32788-151">Office 365 E5 and EMS E5 trial or paid subscriptions with the DNS domain testlab.\<your domain name> registered.</span></span>
- <span data-ttu-id="32788-152">Uma intranet de organização simplificada conectado à Internet, que consiste em máquinas virtuais do DC1 APP1 e CLIENT1 em uma sub-rede de uma rede virtual do Azure.</span><span class="sxs-lookup"><span data-stu-id="32788-152">A simplified organization intranet connected to the Internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span> 
- <span data-ttu-id="32788-153">O Azure AD Connect é executado no APP1 para sincronizar a lista de contas e grupos de locatário do Azure AD de suas assinaturas do Office 365 e EMS E5 para o domínio TESTLAB AD DS.</span><span class="sxs-lookup"><span data-stu-id="32788-153">Azure AD Connect runs on APP1 to synchronize the list of accounts and groups from the Azure AD tenant of your Office 365 and EMS E5 subscriptions to the TESTLAB AD DS domain.</span></span> 
- <span data-ttu-id="32788-154">O SSO Contínuo do Azure AD está habilitado para que os computadores na intranet simulada possam entrar para usar recursos de nuvem do Microsoft 365 sem especificar uma senha de conta de usuário.</span><span class="sxs-lookup"><span data-stu-id="32788-154">Azure AD Seamless SSO is enabled so that computers on the simulated intranet can sign in to Microsoft 365 cloud resources without specifing a user account password.</span></span>

<span data-ttu-id="32788-155">Confira a etapa [Simplificar entrada do usuário](identity-secure-your-passwords.md#identity-sso) na fase de identidade para informações e links para configurar o Logon único Contínuo do Azure AD em produção.</span><span class="sxs-lookup"><span data-stu-id="32788-155">See the [Simplify user sign-in](identity-secure-your-passwords.md#identity-sso) step in the Identity phase for information and links to configure Azure AD Seamless SSO in production.</span></span>

## <a name="next-step"></a><span data-ttu-id="32788-156">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="32788-156">Next step</span></span>

<span data-ttu-id="32788-157">Explorar recursos e funcionalidades adicionais de [identidade](m365-enterprise-test-lab-guides.md#identity) no ambiente de teste.</span><span class="sxs-lookup"><span data-stu-id="32788-157">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="32788-158">Confira também</span><span class="sxs-lookup"><span data-stu-id="32788-158">See also</span></span>

[<span data-ttu-id="32788-159">Guias do Laboratório de Teste do Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="32788-159">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="32788-160">Implantar o Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="32788-160">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="32788-161">Documentação do Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="32788-161">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)


