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
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom:
- TLGS
- Ent_TLGs
ms.assetid: ''
description: 'Resumo: configure e teste o Logon único Contínuo do Azure AD para o ambiente de teste do Microsoft 365.'
ms.openlocfilehash: d2b17acb2b57e379fe204e3ea4402b3f00ef7d6c
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42083800"
---
# <a name="azure-ad-seamless-single-sign-on-for-your-microsoft-365-test-environment"></a><span data-ttu-id="cd6b5-103">O Logon único Contínuo do Azure AD para o ambiente de teste do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="cd6b5-103">Azure AD Seamless Single Sign-on for your Microsoft 365 test environment</span></span>

<span data-ttu-id="cd6b5-104">*Este Guia de Laboratório de Testes pode ser usado para ambientes de teste corporativo do Microsoft 365 Enterprise e do Office 365.*</span><span class="sxs-lookup"><span data-stu-id="cd6b5-104">*This Test Lab Guide can be used for both Microsoft 365 Enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="cd6b5-p101">O Logon Único (SSO) Contínuo do Azure AD dá acesso automático de usuários quando eles estão em seus computadores ou dispositivos conectados à rede da sua organização. O SSO Contínuo do Azure AD fornece aos usuários acesso fácil às aplicativos baseados na nuvem sem precisar de componentes locais adicionais.</span><span class="sxs-lookup"><span data-stu-id="cd6b5-p101">Azure AD Seamless Single Sign-On (SSO) automatically signs in users when they are on their PCs or devices that are connected to their organization network. Azure AD Seamless SSO provides users with easy access to cloud-based applications without needing any additional on-premises components.</span></span>

<span data-ttu-id="cd6b5-107">Este artigo descreve como você pode configurar seu ambiente de teste do Microsoft 365 para o SSO Contínuo do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="cd6b5-107">This article describes how you can configure your Microsoft 365 test environment for Azure AD Seamless SSO.</span></span>

<span data-ttu-id="cd6b5-108">Há duas etapas para fazer a configuração:</span><span class="sxs-lookup"><span data-stu-id="cd6b5-108">There are two phases to setting this up:</span></span>

1.  <span data-ttu-id="cd6b5-109">Criar o ambiente de teste de empresa simulada do Microsoft 365 com sincronização de hash de senha.</span><span class="sxs-lookup"><span data-stu-id="cd6b5-109">Create the Microsoft 365 simulated enterprise test environment with password hash synchronization.</span></span>
2.  <span data-ttu-id="cd6b5-110">Configurar o Azure Active Directory Connect no APP1 para o SSO Contínuo do Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="cd6b5-110">Configure Azure AD Connect on APP1 for Azure AD Seamless SSO.</span></span>
    
![Guias de laboratório de teste da Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="cd6b5-112">Clique [aqui](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) para ver um mapa visual de todos os artigos da pilha do Guia de Laboratório de Teste do Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="cd6b5-112">Click [here](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a><span data-ttu-id="cd6b5-113">Fase 1: configurar a sincronização de hash de senha do ambiente de teste do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="cd6b5-113">Phase 1: Configure password hash synchronization for your Microsoft 365 test environment</span></span>

<span data-ttu-id="cd6b5-p102">Siga as instruções em [sincronização de hash de senha para o Microsoft 365](password-hash-sync-m365-ent-test-environment.md). Aqui está a configuração resultante.</span><span class="sxs-lookup"><span data-stu-id="cd6b5-p102">Follow the instructions in [password hash synchronization for Microsoft 365](password-hash-sync-m365-ent-test-environment.md). Here is your resulting configuration.</span></span>
  
![Empresa simulada com ambiente de teste de sincronização de hash de senha](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
<span data-ttu-id="cd6b5-117">Esta configuração consiste em:</span><span class="sxs-lookup"><span data-stu-id="cd6b5-117">This configuration consists of:</span></span> 
  
- <span data-ttu-id="cd6b5-118">Assinaturas de avaliação ou pagas do Microsoft 365 E5 ou Office 365 E5.</span><span class="sxs-lookup"><span data-stu-id="cd6b5-118">Microsoft 365 E5 or Office 365 E5 trial or paid subscriptions.</span></span>
- <span data-ttu-id="cd6b5-119">Uma intranet de organização simplificada conectado à Internet, que consiste em máquinas virtuais do DC1 APP1 e CLIENT1 em uma sub-rede de uma rede virtual do Azure.</span><span class="sxs-lookup"><span data-stu-id="cd6b5-119">A simplified organization intranet connected to the Internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span> 
- <span data-ttu-id="cd6b5-120">O Azure AD Connect é executado no APP1 para sincronizar periodicamente o domínio TESTLAB do Active Directory Domain Services (AD DS) com o locatário do Azure AD de sua assinatura do Microsoft 365 ou do Office 365.</span><span class="sxs-lookup"><span data-stu-id="cd6b5-120">Azure AD Connect runs on APP1 to synchronize the TESTLAB Active Directory Domain Services (AD DS) domain to the Azure AD tenant of your Microsoft 365 or Office 365 subscription periodically.</span></span>

## <a name="phase-2-configure-azure-ad-connect-on-app1-for-azure-ad-seamless-sso"></a><span data-ttu-id="cd6b5-121">Fase 2: configure o Azure Active Directory Connect no APP1 para o SSO Contínuo do Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="cd6b5-121">Phase 2: Configure Azure AD Connect on APP1 for Azure AD Seamless SSO</span></span>

<span data-ttu-id="cd6b5-122">Nesta fase, você configura o Azure AD Connect no APP1 para SSO Contínuo do Azure AD e, em seguida, verifica se isso funciona.</span><span class="sxs-lookup"><span data-stu-id="cd6b5-122">In this phase, you configure Azure AD Connect on APP1 for Azure AD Seamless SSO, and then verify that it works.</span></span>

### <a name="configure-azure-ad-connect-on-app1"></a><span data-ttu-id="cd6b5-123">Configurar o Azure AD Connect no APP1</span><span class="sxs-lookup"><span data-stu-id="cd6b5-123">Configure Azure AD Connect on APP1</span></span>

1. <span data-ttu-id="cd6b5-124">No [Portal do Azure](https://portal.azure.com), entre com a conta de administrador global e conecte-se ao APP1 com a conta TESTLAB\Usuário1.</span><span class="sxs-lookup"><span data-stu-id="cd6b5-124">From the [Azure portal](https://portal.azure.com), sign in with your global administrator account, and then connect to APP1 with the TESTLAB\User1 account.</span></span>

2. <span data-ttu-id="cd6b5-125">Na área de trabalho do APP1, execute o Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="cd6b5-125">From the desktop of APP1, run Azure AD Connect.</span></span>

3. <span data-ttu-id="cd6b5-126">Na **Página inicial**, clique em **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="cd6b5-126">On the **Welcome page**, click **Configure**.</span></span>

4. <span data-ttu-id="cd6b5-127">Na página **Tarefas Adicionais**, clique em **Alterar entrada do usuário** e em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="cd6b5-127">On the **Additional tasks** page, click **Change user sign-in**, and then click **Next**.</span></span>

5. <span data-ttu-id="cd6b5-128">Na página **Conectar ao Azure AD**, digite suas credenciais de conta de administrador global e clique em **Próxima**.</span><span class="sxs-lookup"><span data-stu-id="cd6b5-128">On the **Connect to Azure AD** page, type your global administrator account credentials, and then click **Next**.</span></span>

6. <span data-ttu-id="cd6b5-129">Na página **Entrada do usuário**, selecione **Habilitar logon único** e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="cd6b5-129">On the **User sign-in** page, select **Enable single sign-on**, and then click **Next**.</span></span>

7. <span data-ttu-id="cd6b5-130">Na página **Habilitar o logon único**, clique em **Inserir credenciais**.</span><span class="sxs-lookup"><span data-stu-id="cd6b5-130">On the **Enable single sign-on** page, click **Enter credentials**.</span></span>

8. <span data-ttu-id="cd6b5-p103">Na caixa de diálogo **Segurança do Windows**, digite **usuário1** e a senha da conta do Usuário1 e clique em **OK**. Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="cd6b5-p103">In the **Windows Security** dialog box, type **user1** and the password of the user1 account, and then click **OK**. Click **Next**.</span></span>

9. <span data-ttu-id="cd6b5-133">Na página **Pronto para Configurar**, clique em **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="cd6b5-133">On the **Ready to Configure** page, click **Configure**.</span></span>

10. <span data-ttu-id="cd6b5-134">Na página **Configuração concluída**, clique em **Sair**.</span><span class="sxs-lookup"><span data-stu-id="cd6b5-134">On the **Configuration complete** page, click **Exit**.</span></span>

11. <span data-ttu-id="cd6b5-p104">No portal do Azure, no painel esquerdo, clique em **Azure Active Directory > Azure AD Connect Health**. Verifique se o recurso **Logon único Contínuo** aparece como **Habilitado**.</span><span class="sxs-lookup"><span data-stu-id="cd6b5-p104">From the Azure portal, in the left pane, click **Azure Active Directory > Azure AD Connect**. Verify that the **Seamless single sign-on** feature appears as **Enabled**.</span></span>

<span data-ttu-id="cd6b5-137">Em seguida, teste a capacidade de entrar em sua assinatura com a conta <strong>usuario1@testlab.</strong>\<seu domínio público> nome de usuário da conta Usuário1.</span><span class="sxs-lookup"><span data-stu-id="cd6b5-137">Next, test the ability to sign in to your subscription with the <strong>user1@testlab.</strong>\<your public domain> user name of the User1 account.</span></span>

1. <span data-ttu-id="cd6b5-138">Do Internet Explorer para APP1, clique no ícone de configurações e, em seguida, clique em **Opções da Internet**.</span><span class="sxs-lookup"><span data-stu-id="cd6b5-138">From Internet Explorer on APP1, click the settings icon, and then click **Internet Options**.</span></span>
 
2. <span data-ttu-id="cd6b5-139">Em **Opções da Internet**, clique na guia **Segurança**.</span><span class="sxs-lookup"><span data-stu-id="cd6b5-139">In **Internet Options**, click the **Security** tab.</span></span>

3. <span data-ttu-id="cd6b5-140">Clique em **Intranet local** e, em seguida, clique em **Sites**.</span><span class="sxs-lookup"><span data-stu-id="cd6b5-140">Click **Local intranet**, and then click **Sites**.</span></span>

4. <span data-ttu-id="cd6b5-141">Na **Intranet Local**, clique em **Avançado**.</span><span class="sxs-lookup"><span data-stu-id="cd6b5-141">In **Local intranet**, click **Advanced**.</span></span>

5. <span data-ttu-id="cd6b5-142">Em **Adicionar este site à zona**, digite **https<span>://</span>autologon.microsoftazuread-sso.com**, clique em **Adicionar > Fechar > OK > OK**.</span><span class="sxs-lookup"><span data-stu-id="cd6b5-142">In **Add this website to the zone**, type **https<span>://</span>autologon.microsoftazuread-sso.com**, click **Add > Close > OK > OK**.</span></span>

6. <span data-ttu-id="cd6b5-143">Saia e entre novamente, mas desta vez especifique uma conta diferente.</span><span class="sxs-lookup"><span data-stu-id="cd6b5-143">Sign out, and then sign in again, this time specifying a different account.</span></span>

7. <span data-ttu-id="cd6b5-144">Quando solicitado a fazer login, especifique <strong>usuário1@testlab.</strong>\<o nome de seu domínio público> e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="cd6b5-144">When prompted to sign in, specify <strong>user1@testlab.</strong>\<your public domain> name, and then click **Next**.</span></span> <span data-ttu-id="cd6b5-145">Você deve conseguir entrar como Usuário1 sem que uma senha seja solicitada.</span><span class="sxs-lookup"><span data-stu-id="cd6b5-145">You should successfully sign in as User1 without being prompted for a password.</span></span> <span data-ttu-id="cd6b5-146">Isso prova que o SSO de conexão remota do Azure AD está funcionando.</span><span class="sxs-lookup"><span data-stu-id="cd6b5-146">This proves that Azure AD Seamless SSO is working.</span></span>

<span data-ttu-id="cd6b5-147">Observe que, embora o Usuário1 tenha permissões de administrador de domínio para o domínio TESTLAB do AD DS, ele não é um administrador global do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="cd6b5-147">Notice that although User1 has domain administrator permissions for the TESTLAB AD DS domain, it is not a global administrator for Azure AD.</span></span> <span data-ttu-id="cd6b5-148">Portanto, o ícone **Administrador** não estará disponível como opção.</span><span class="sxs-lookup"><span data-stu-id="cd6b5-148">Therefore, you will not see the **Admin** icon as an option.</span></span>

<span data-ttu-id="cd6b5-149">Esta é a configuração resultante:</span><span class="sxs-lookup"><span data-stu-id="cd6b5-149">Here is your resulting configuration:</span></span>

![A empresa simulada com ambiente de teste de autenticação de passagem](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)

 
<span data-ttu-id="cd6b5-151">Esta configuração consiste em:</span><span class="sxs-lookup"><span data-stu-id="cd6b5-151">This configuration consists of:</span></span>

- <span data-ttu-id="cd6b5-152">Assinaturas de avaliação ou pagas do Microsoft 365 E5 ou do Office 365 E5 com o domínio DNS testlab.\<seu nome de domínio> registrado.</span><span class="sxs-lookup"><span data-stu-id="cd6b5-152">Microsoft 365 E5 or Office 365 E5 trial or paid subscriptions with the DNS domain testlab.\<your domain name> registered.</span></span>
- <span data-ttu-id="cd6b5-153">Uma intranet de organização simplificada conectado à Internet, que consiste em máquinas virtuais do DC1 APP1 e CLIENT1 em uma sub-rede de uma rede virtual do Azure.</span><span class="sxs-lookup"><span data-stu-id="cd6b5-153">A simplified organization intranet connected to the Internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span> 
- <span data-ttu-id="cd6b5-154">O Azure AD Connect é executado no APP1 para sincronizar a lista de contas e grupos de locatário do Azure AD de sua assinatura do Microsoft 365 ou do Office 365 para o domínio TESTLAB AD DS.</span><span class="sxs-lookup"><span data-stu-id="cd6b5-154">Azure AD Connect runs on APP1 to synchronize the list of accounts and groups from the Azure AD tenant of your Microsoft 365 or Office 365 subscription to the TESTLAB AD DS domain.</span></span> 
- <span data-ttu-id="cd6b5-155">O SSO Contínuo do Azure AD está habilitado para que os computadores na intranet simulada possam entrar para usar recursos de nuvem do Microsoft 365 sem especificar uma senha de conta de usuário.</span><span class="sxs-lookup"><span data-stu-id="cd6b5-155">Azure AD Seamless SSO is enabled so that computers on the simulated intranet can sign in to Microsoft 365 cloud resources without specifing a user account password.</span></span>

<span data-ttu-id="cd6b5-156">Confira a etapa [Simplificar entrada do usuário](identity-secure-your-passwords.md#identity-sso) na fase de identidade para informações e links para configurar o Logon único Contínuo do Azure AD em produção.</span><span class="sxs-lookup"><span data-stu-id="cd6b5-156">See the [Simplify user sign-in](identity-secure-your-passwords.md#identity-sso) step in the Identity phase for information and links to configure Azure AD Seamless SSO in production.</span></span>

## <a name="next-step"></a><span data-ttu-id="cd6b5-157">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="cd6b5-157">Next step</span></span>

<span data-ttu-id="cd6b5-158">Explorar recursos e funcionalidades adicionais de [identidade](m365-enterprise-test-lab-guides.md#identity) no ambiente de teste.</span><span class="sxs-lookup"><span data-stu-id="cd6b5-158">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="cd6b5-159">Confira também</span><span class="sxs-lookup"><span data-stu-id="cd6b5-159">See also</span></span>

[<span data-ttu-id="cd6b5-160">Guias do Laboratório de Teste do Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="cd6b5-160">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="cd6b5-161">Implantar o Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="cd6b5-161">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="cd6b5-162">Documentação do Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="cd6b5-162">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)


