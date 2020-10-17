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
ms.openlocfilehash: f98f82de50feb2a9f92d1ecc4775c5307b314a72
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487595"
---
# <a name="azure-ad-seamless-single-sign-on-for-your-microsoft-365-test-environment"></a><span data-ttu-id="70901-103">O Logon único Contínuo do Azure AD para o ambiente de teste do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="70901-103">Azure AD Seamless Single Sign-on for your Microsoft 365 test environment</span></span>

<span data-ttu-id="70901-104">*Este guia de laboratório de teste pode ser usado para ambientes de teste corporativos do Microsoft 365 para Enterprise e Office 365.*</span><span class="sxs-lookup"><span data-stu-id="70901-104">*This Test Lab Guide can be used for both Microsoft 365 for enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="70901-p101">O Sign-On único do Azure Active Directory (SSO sem problemas) entra automaticamente nos usuários quando eles estão em seus computadores ou dispositivos conectados à rede da organização. O SSO direto do Azure AD fornece aos usuários acesso fácil aos aplicativos baseados na nuvem sem precisar de nenhum componente adicional no local.</span><span class="sxs-lookup"><span data-stu-id="70901-p101">Azure AD Seamless Single Sign-On (Seamless SSO) automatically signs in users when they are on their PCs or devices that are connected to their organization network. Azure AD Seamless SSO provides users with easy access to cloud-based applications without needing any additional on-premises components.</span></span>

<span data-ttu-id="70901-107">Este artigo descreve como configurar seu ambiente de teste do Microsoft 365 para SSO direto do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="70901-107">This article describes how to configure your Microsoft 365 test environment for Azure AD Seamless SSO.</span></span>

<span data-ttu-id="70901-108">Configurar o SSO contínuo do Azure AD envolve duas fases:</span><span class="sxs-lookup"><span data-stu-id="70901-108">Setting up Azure AD Seamless SSO involves two phases:</span></span>
- [<span data-ttu-id="70901-109">Fase 1: configurar a sincronização de hash de senha do ambiente de teste do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="70901-109">Phase 1: Configure password hash synchronization for your Microsoft 365 test environment</span></span>](#phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment)
- [<span data-ttu-id="70901-110">Fase 2: configure o Azure Active Directory Connect no APP1 para o SSO Contínuo do Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="70901-110">Phase 2: Configure Azure AD Connect on APP1 for Azure AD Seamless SSO</span></span>](#phase-2-configure-azure-ad-connect-on-app1-for-azure-ad-seamless-sso)
   
![Guias de laboratório de teste da Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="70901-112">Para obter um mapa Visual para todos os artigos da pilha do guia do laboratório de teste do Microsoft 365 for Enterprise, vá para a [pilha do guia do laboratório de teste da microsoft 365 para empresas](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span><span class="sxs-lookup"><span data-stu-id="70901-112">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>
  
## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a><span data-ttu-id="70901-113">Fase 1: configurar a sincronização de hash de senha do ambiente de teste do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="70901-113">Phase 1: Configure password hash synchronization for your Microsoft 365 test environment</span></span>

<span data-ttu-id="70901-114">Siga as instruções em [sincronização de hash de senha para o Microsoft 365](password-hash-sync-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="70901-114">Follow the instructions in [password hash synchronization for Microsoft 365](password-hash-sync-m365-ent-test-environment.md).</span></span> 

<span data-ttu-id="70901-115">A configuração resultante tem a seguinte aparência:</span><span class="sxs-lookup"><span data-stu-id="70901-115">Your resulting configuration looks like this:</span></span>
  
![Empresa simulada com ambiente de teste de sincronização de hash de senha](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
<span data-ttu-id="70901-117">Esta configuração consiste em:</span><span class="sxs-lookup"><span data-stu-id="70901-117">This configuration consists of:</span></span>
  
- <span data-ttu-id="70901-118">Uma assinatura de avaliação ou assinatura paga do Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="70901-118">A Microsoft 365 E5 trial or paid subscription.</span></span>
- <span data-ttu-id="70901-119">Uma intranet de organização simplificada conectada à Internet, consistindo nas máquinas virtuais DC1, APP1 e CLIENT1 em uma sub-rede de uma rede virtual do Azure.</span><span class="sxs-lookup"><span data-stu-id="70901-119">A simplified organization intranet connected to the internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span>
- <span data-ttu-id="70901-120">O Azure AD Connect é executado no APP1 para sincronizar periodicamente o domínio do AD DS (serviços de domínio Active Directory) do TESTLAB para o locatário do Azure AD da sua assinatura do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="70901-120">Azure AD Connect runs on APP1 to periodically synchronize the TESTLAB Active Directory Domain Services (AD DS) domain to the Azure AD tenant of your Microsoft 365 subscription.</span></span>

## <a name="phase-2-configure-azure-ad-connect-on-app1-for-azure-ad-seamless-sso"></a><span data-ttu-id="70901-121">Fase 2: configure o Azure Active Directory Connect no APP1 para o SSO Contínuo do Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="70901-121">Phase 2: Configure Azure AD Connect on APP1 for Azure AD Seamless SSO</span></span>

<span data-ttu-id="70901-122">Nesta fase, configure o Azure AD Connect no APP1 para o SSO contínuo do Azure AD e, em seguida, verifique se ele funciona.</span><span class="sxs-lookup"><span data-stu-id="70901-122">In this phase, configure Azure AD Connect on APP1 for Azure AD Seamless SSO, and then verify that it works.</span></span>

### <a name="configure-azure-ad-connect-on-app1"></a><span data-ttu-id="70901-123">Configurar o Azure AD Connect no APP1</span><span class="sxs-lookup"><span data-stu-id="70901-123">Configure Azure AD Connect on APP1</span></span>

1. <span data-ttu-id="70901-124">No [Portal do Azure](https://portal.azure.com), entre com a conta de administrador global e conecte-se ao APP1 com a conta TESTLAB\Usuário1.</span><span class="sxs-lookup"><span data-stu-id="70901-124">From the [Azure portal](https://portal.azure.com), sign in with your global administrator account, and then connect to APP1 with the TESTLAB\User1 account.</span></span>

2. <span data-ttu-id="70901-125">Na área de trabalho do APP1, execute o Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="70901-125">From the APP1 desktop, run Azure AD Connect.</span></span>

3. <span data-ttu-id="70901-126">Na **página de boas-vindas**, selecione **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="70901-126">On the **Welcome page**, select **Configure**.</span></span>

4. <span data-ttu-id="70901-127">Na página **tarefas adicionais** , selecione **alterar entrada do usuário**e, em seguida, selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="70901-127">On the **Additional tasks** page, select **Change user sign-in**, and then select **Next**.</span></span>

5. <span data-ttu-id="70901-128">Na página **conectar ao Azure ad** , insira as credenciais de sua conta de administrador global e selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="70901-128">On the **Connect to Azure AD** page, enter your global administrator account credentials, and then select **Next**.</span></span>

6. <span data-ttu-id="70901-129">Na página **entrada do usuário** , selecione **habilitar logon único**e, em seguida, selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="70901-129">On the **User sign-in** page, select **Enable single sign-on**, and then select **Next**.</span></span>

7. <span data-ttu-id="70901-130">Na página **habilitar logon único** , selecione **Inserir credenciais**.</span><span class="sxs-lookup"><span data-stu-id="70901-130">On the **Enable single sign-on** page, select **Enter credentials**.</span></span>

8. <span data-ttu-id="70901-131">Na caixa de diálogo **segurança do Windows** , digite **Usuário1** e a senha da conta Usuário1, selecione **OK**e, em seguida, selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="70901-131">In the **Windows Security** dialog box, enter **user1** and the password of the user1 account, select **OK**, and then select **Next**.</span></span>

9. <span data-ttu-id="70901-132">Na página **pronto para configurar** , selecione **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="70901-132">On the **Ready to Configure** page, select **Configure**.</span></span>

10. <span data-ttu-id="70901-133">Na página **configuração concluída** , selecione **sair**.</span><span class="sxs-lookup"><span data-stu-id="70901-133">On the **Configuration complete** page, select **Exit**.</span></span>

11. <span data-ttu-id="70901-134">No portal do Azure, no painel esquerdo, selecione **Azure Active Directory**  >  **Azure ad Connect**.</span><span class="sxs-lookup"><span data-stu-id="70901-134">From the Azure portal, in the left pane, select **Azure Active Directory** > **Azure AD Connect**.</span></span> <span data-ttu-id="70901-135">Verifique se o recurso de **logon único contínuo** aparece como **habilitado**.</span><span class="sxs-lookup"><span data-stu-id="70901-135">Verify that the **Seamless single sign-on** feature appears as **Enabled**.</span></span>

<span data-ttu-id="70901-136">Em seguida, teste a capacidade de entrar em sua assinatura com o <strong>user1@testlab.</strong>\<*your public domain*></span><span class="sxs-lookup"><span data-stu-id="70901-136">Next, test the ability to sign in to your subscription with the <strong>user1@testlab.</strong>\<*your public domain*></span></span> <span data-ttu-id="70901-137">nome de usuário da conta User1.</span><span class="sxs-lookup"><span data-stu-id="70901-137">user name of the User1 account.</span></span>

1. <span data-ttu-id="70901-138">No Internet Explorer no APP1, selecione o ícone configurações e, em seguida, selecione **Opções da Internet**.</span><span class="sxs-lookup"><span data-stu-id="70901-138">From Internet Explorer on APP1, select the settings icon, and then select **Internet Options**.</span></span>
 
2. <span data-ttu-id="70901-139">Em **Opções da Internet**, selecione a guia **segurança** .</span><span class="sxs-lookup"><span data-stu-id="70901-139">In **Internet Options**, select the **Security** tab.</span></span>

3. <span data-ttu-id="70901-140">Selecione **intranet local**e, em seguida, selecione **sites**.</span><span class="sxs-lookup"><span data-stu-id="70901-140">Select **Local intranet**, and then select **Sites**.</span></span>

4. <span data-ttu-id="70901-141">Em **intranet local**, selecione **avançado**.</span><span class="sxs-lookup"><span data-stu-id="70901-141">In **Local intranet**, select **Advanced**.</span></span>

5. <span data-ttu-id="70901-142">Em **Adicionar este site à zona**, digite **https<span>://</span>AutoLogon.microsoftazuread-SSO.com**, selecione **Adicionar**  >  **fechar**  >  **OK**  >  **OK**.</span><span class="sxs-lookup"><span data-stu-id="70901-142">In **Add this website to the zone**, enter **https<span>://</span>autologon.microsoftazuread-sso.com**, select **Add** > **Close** > **OK** > **OK**.</span></span>

6. <span data-ttu-id="70901-143">Saia e entre novamente, mas desta vez especifique uma conta diferente.</span><span class="sxs-lookup"><span data-stu-id="70901-143">Sign out, and then sign in again, this time specifying a different account.</span></span>

7. <span data-ttu-id="70901-144">Quando solicitado a entrar, especifique <strong>user1@testlab.</strong>\<*your public domain*></span><span class="sxs-lookup"><span data-stu-id="70901-144">When prompted to sign in, specify <strong>user1@testlab.</strong>\<*your public domain*></span></span> <span data-ttu-id="70901-145">nome e, em seguida, selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="70901-145">name, and then select **Next**.</span></span> <span data-ttu-id="70901-146">Você deve conseguir entrar como Usuário1 sem que uma senha seja solicitada.</span><span class="sxs-lookup"><span data-stu-id="70901-146">You should successfully sign in as User1 without being prompted for a password.</span></span> <span data-ttu-id="70901-147">Isso prova que o SSO de conexão remota do Azure AD está funcionando.</span><span class="sxs-lookup"><span data-stu-id="70901-147">This proves that Azure AD Seamless SSO is working.</span></span>

<span data-ttu-id="70901-148">Observe que, embora o Usuário1 tenha permissões de administrador de domínio para o domínio TESTLAB do AD DS, ele não é um administrador global do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="70901-148">Notice that although User1 has domain administrator permissions for the TESTLAB AD DS domain, it is not a global administrator for Azure AD.</span></span> <span data-ttu-id="70901-149">Portanto, o ícone **Administrador** não estará disponível como opção.</span><span class="sxs-lookup"><span data-stu-id="70901-149">Therefore, you will not see the **Admin** icon as an option.</span></span>

<span data-ttu-id="70901-150">Esta é a configuração resultante:</span><span class="sxs-lookup"><span data-stu-id="70901-150">Here is your resulting configuration:</span></span>

![A empresa simulada com ambiente de teste de autenticação de passagem](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)

<span data-ttu-id="70901-152">Esta configuração consiste em:</span><span class="sxs-lookup"><span data-stu-id="70901-152">This configuration consists of:</span></span>

- <span data-ttu-id="70901-153">Uma assinatura paga ou de avaliação do Microsoft 365 E5 com o domínio DNS testlab.\<*your domain name*></span><span class="sxs-lookup"><span data-stu-id="70901-153">A Microsoft 365 E5 trial or paid subscriptions with the DNS domain testlab.\<*your domain name*></span></span> <span data-ttu-id="70901-154">registrado.</span><span class="sxs-lookup"><span data-stu-id="70901-154">registered.</span></span>
- <span data-ttu-id="70901-155">Uma intranet de organização simplificada conectada à Internet, consistindo nas máquinas virtuais DC1, APP1 e CLIENT1 em uma sub-rede de uma rede virtual do Azure.</span><span class="sxs-lookup"><span data-stu-id="70901-155">A simplified organization intranet connected to the internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span>
- <span data-ttu-id="70901-156">O Azure AD Connect é executado no APP1 para sincronizar a lista de contas e grupos do locatário do Azure AD da sua assinatura do Microsoft 365 para o domínio TESTLAB AD DS.</span><span class="sxs-lookup"><span data-stu-id="70901-156">Azure AD Connect runs on APP1 to synchronize the list of accounts and groups from the Azure AD tenant of your Microsoft 365 subscription to the TESTLAB AD DS domain.</span></span>
- <span data-ttu-id="70901-157">O SSO direto do Azure Active Directory está habilitado para que os computadores na intranet simulada possam entrar no Microsoft 365 Cloud Resources sem especificar uma senha de conta de usuário.</span><span class="sxs-lookup"><span data-stu-id="70901-157">Azure AD Seamless SSO is enabled so that computers on the simulated intranet can sign in to Microsoft 365 cloud resources without specifying a user account password.</span></span>

## <a name="next-step"></a><span data-ttu-id="70901-158">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="70901-158">Next step</span></span>

<span data-ttu-id="70901-159">Explorar recursos e funcionalidades adicionais de [identidade](m365-enterprise-test-lab-guides.md#identity) no ambiente de teste.</span><span class="sxs-lookup"><span data-stu-id="70901-159">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="70901-160">Confira também</span><span class="sxs-lookup"><span data-stu-id="70901-160">See also</span></span>

[<span data-ttu-id="70901-161">Guias do Laboratório de Teste do Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="70901-161">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="70901-162">Visão geral do Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="70901-162">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="70901-163">Documentação da Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="70901-163">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
