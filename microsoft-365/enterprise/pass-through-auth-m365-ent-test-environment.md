---
title: Autenticação de passagem para seu ambiente de teste do Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/13/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom:
- TLG
- Ent_TLGs
ms.assetid: ''
description: 'Resumo: configure a autenticação de passagem para seu ambiente de teste do Microsoft 365.'
ms.openlocfilehash: 26222f04617999104a1ad010eb189a0c01370a6d
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/28/2018
ms.locfileid: "26864873"
---
# <a name="pass-through-authentication-for-your-microsoft-365-test-environment"></a><span data-ttu-id="93d42-103">Autenticação de passagem para seu ambiente de teste do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="93d42-103">Pass-through authentication for your Microsoft 365 test environment</span></span>

<span data-ttu-id="93d42-p101">As organizações que desejem usar diretamente sua infraestrutura local do Windows Server Active Directory (AD) para autenticação em aplicativos e serviços de nuvem da Microsoft podem usar a autenticação de passagem. Este artigo descreve como você pode configurar seu ambiente de teste do Microsoft 365 para autenticação de passagem, resultando na seguinte configuração:</span><span class="sxs-lookup"><span data-stu-id="93d42-p101">Organizations that want to directly use their on-premises Windows Server Active Directory (AD) infrastructure for authentication to Microsoft cloud-based services and applications can use pass-through authentication. This article describes how you can configure your Microsoft 365 test environment for pass-through authentication, resulting in the following configuration:</span></span>
  
![A empresa simulada com ambiente de teste de autenticação de passagem](media/pass-through-auth-m365-ent-test-environment/Phase2.png)
  
<span data-ttu-id="93d42-107">Há duas fases para configurar esse ambiente de teste:</span><span class="sxs-lookup"><span data-stu-id="93d42-107">There are two phases to setting up this test environment:</span></span>

1.  <span data-ttu-id="93d42-108">Crie o ambiente de teste de empresa simulada do Microsoft 365 com sincronização de hash de senha.</span><span class="sxs-lookup"><span data-stu-id="93d42-108">Create the Microsoft 365 simulated enterprise test environment with password hash synchronization.</span></span>
2.  <span data-ttu-id="93d42-109">Configure o Azure AD Connect no APP1 para autenticação de passagem.</span><span class="sxs-lookup"><span data-stu-id="93d42-109">Configure Azure AD Connect on APP1 for pass-through authentication.</span></span>
    
![Guias de laboratório de teste da Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="93d42-111">Clique [aqui](https://aka.ms/m365etlgstack) para ver um mapa visual de todos os artigos da pilha do Guia de Laboratório de Teste do Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="93d42-111">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a><span data-ttu-id="93d42-112">Fase 1: configurar a sincronização de hash de senha do ambiente de teste do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="93d42-112">Phase 1: Configure password hash synchronization for your Microsoft 365 test environment</span></span>

<span data-ttu-id="93d42-p102">Siga as instruções em [sincronização de hash de senha para o Microsoft 365](password-hash-sync-m365-ent-test-environment.md). Aqui está a configuração resultante.</span><span class="sxs-lookup"><span data-stu-id="93d42-p102">Follow the instructions in [password hash synchronization for Microsoft 365](password-hash-sync-m365-ent-test-environment.md). Here is your resulting configuration.</span></span>
  
![Empresa simulada com ambiente de teste de sincronização de hash de senha](media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
<span data-ttu-id="93d42-116">Esta configuração consiste em:</span><span class="sxs-lookup"><span data-stu-id="93d42-116">This configuration consists of:</span></span> 
  
- <span data-ttu-id="93d42-117">Assinaturas permanentes ou de avaliação do Office 365 E5 e EMS E5.</span><span class="sxs-lookup"><span data-stu-id="93d42-117">Office 365 E5 and EMS E5 trial or permanent subscriptions.</span></span>
- <span data-ttu-id="93d42-p103">Uma intranet de organização simplificada conectada à Internet, composta pelas máquinas virtuais DC1, APP1 e CLIENT1, em uma sub-rede de uma Rede Virtual do Microsoft Azure. O Azure AD Connect Health é executado na APP1 para sincronizar periodicamente o domínio do Dev/Test Lab do Windows Server Active Directory com o locatário do Microsoft Azure AD, nas assinaturas do Office 365 e do EMS E5.</span><span class="sxs-lookup"><span data-stu-id="93d42-p103">A simplified organization intranet connected to the Internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network. Azure AD Connect runs on APP1 to synchronize the TESTLAB Windows Server AD domain to the Azure AD tenant of your Office 365 and EMS E5 subscriptions periodically.</span></span>

## <a name="phase-2-configure-azure-ad-connect-on-app1-for-pass-through-authentication"></a><span data-ttu-id="93d42-120">Fase 2: configurar o Azure AD Connect no APP1 para autenticação de passagem</span><span class="sxs-lookup"><span data-stu-id="93d42-120">Phase 2: Configure Azure AD Connect on APP1 for pass-through authentication</span></span>

<span data-ttu-id="93d42-121">Nesta fase, você configura o Azure AD Connect no APP1 para usar autenticação de passagem e verifica se ela funciona.</span><span class="sxs-lookup"><span data-stu-id="93d42-121">In this phase, you configure Azure AD Connect on APP1 to use pass-through authentication, and then verify that it works.</span></span>

### <a name="configure-azure-ad-connect-on-app1"></a><span data-ttu-id="93d42-122">Configurar o Azure AD Connect no APP1</span><span class="sxs-lookup"><span data-stu-id="93d42-122">Configure Azure AD Connect on APP1</span></span>

1.  <span data-ttu-id="93d42-123">No [Portal do Azure](https://portal.azure.com), entre com a conta de administrador global e conecte-se ao APP1 com a conta TESTLAB\Usuário1.</span><span class="sxs-lookup"><span data-stu-id="93d42-123">From the [Azure portal](https://portal.azure.com), sign in with your global administrator account, and then connect to APP1 with the TESTLAB\User1 account.</span></span>

2.  <span data-ttu-id="93d42-124">Na área de trabalho do APP1, execute o Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="93d42-124">From the desktop of APP1, run Azure AD Connect.</span></span>

3.  <span data-ttu-id="93d42-125">Na página **Página inicial**, clique em **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="93d42-125">On the **Welcome page**, click **Configure**.</span></span>

4.  <span data-ttu-id="93d42-126">Na página Tarefas adicionais, clique em **Alterar entrada do usuário** e em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="93d42-126">On the Additional tasks page, click **Change user sign-in**, and then click **Next**.</span></span>

5.  <span data-ttu-id="93d42-127">Na página **Conectar ao Azure AD**, digite suas credenciais de conta de administrador global e clique em **Próxima**.</span><span class="sxs-lookup"><span data-stu-id="93d42-127">On the **Connect to Azure AD** page, type your global administrator account credentials, and then click **Next**.</span></span>

6.  <span data-ttu-id="93d42-128">Na página **Entrada de usuário**, clique em **Autenticação de passagem**e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="93d42-128">On the **User sign-in** page, click **Pass-through authentication**, and then click **Next**.</span></span>

7.  <span data-ttu-id="93d42-129">Na página **Pronto para configurar**, clique em **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="93d42-129">On the **Ready to configure** page, click **Configure**.</span></span>

8.  <span data-ttu-id="93d42-130">Na página **Configuração concluída**, clique em **Sair**.</span><span class="sxs-lookup"><span data-stu-id="93d42-130">On the **Configuration complete** page, click **Exit**.</span></span>

9.  <span data-ttu-id="93d42-p104">No portal do Azure, no painel esquerdo, clique em **Azure Active Directory > Azure AD Connect Health**. Verifique se o recurso **Autenticação de passagem** aparece como **Habilitado**.</span><span class="sxs-lookup"><span data-stu-id="93d42-p104">From the Azure portal, in the left pane, click **Azure Active Directory > Azure AD Connect**. Verify that the **Pass-through authentication** feature appears as **Enabled**.</span></span>

10. <span data-ttu-id="93d42-p105">Clique em **Autenticação de passagem**. O painel **Autenticação de passagem** lista os servidores onde estão instalados os Agentes de Autenticação. Você verá APP1 na lista. Feche o painel **Autenticação de passagem**.</span><span class="sxs-lookup"><span data-stu-id="93d42-p105">Click **Pass-through authentication**. The **Pass-through authentication** pane lists the servers where your Authentication Agents are installed. You should see APP1 in the list. Close the **Pass-through authentication** pane.</span></span>

<span data-ttu-id="93d42-137">Em seguida, teste a capacidade de entrar na assinatura do Office 365 com a conta usuario1@testlab.\<seu domínio público>nome de usuário da conta Usuário1.</span><span class="sxs-lookup"><span data-stu-id="93d42-137">Next, test the ability to sign in to your Office 365 subscription with the user1@testlab.\<your public domain> user name of the User1 account.</span></span>

1. <span data-ttu-id="93d42-138">No APP1, encerre o Office 365 e entre novamente, mas desta vez especifique uma conta diferente.</span><span class="sxs-lookup"><span data-stu-id="93d42-138">From APP1, sign out of Office 365, and then sign in again, this time specifying a different account.</span></span>

2. <span data-ttu-id="93d42-p106">Quando solicitado a fornecer o nome de usuário e a senha, especifique usuario1@testlab.\<seu domínio público> e a senha de Usuário1. Você deve entrar como Usuário1.</span><span class="sxs-lookup"><span data-stu-id="93d42-p106">When prompted for a user name and password, specify user1@testlab.\<your public domain> and the User1 password. You should successfully sign in as User1.</span></span>

<span data-ttu-id="93d42-p107">Embora o Usuário1 tenha permissões de administrador de domínio para o domínio do Windows Server Active Directory do TestLab, ele não é um administrador global do Office 365. Portanto, o ícone **Administrador** não estará disponível como opção.</span><span class="sxs-lookup"><span data-stu-id="93d42-p107">Notice that although User1 has domain administrator permissions for the TESTLAB Windows Server AD domain, it is not an Office 365 global administrator. Therefore, you will not see the **Admin** icon as an option.</span></span>

<span data-ttu-id="93d42-143">Esta é a configuração resultante:</span><span class="sxs-lookup"><span data-stu-id="93d42-143">Here is your resulting configuration:</span></span>

![A empresa simulada com ambiente de teste de autenticação de passagem](media/pass-through-auth-m365-ent-test-environment/Phase2.png)
 
<span data-ttu-id="93d42-145">Esta configuração consiste em:</span><span class="sxs-lookup"><span data-stu-id="93d42-145">This configuration consists of:</span></span>

- <span data-ttu-id="93d42-146">Assinaturas permanentes ou de avaliação do Office 365 E5 e EMS E5 com o domínio DNS TESTLAB.\<seu nome de domínio> registrado.</span><span class="sxs-lookup"><span data-stu-id="93d42-146">Office 365 E5 and EMS E5 trial or permanent subscriptions with the DNS domain TESTLAB.\<your domain name> registered.</span></span>
- <span data-ttu-id="93d42-p108">Uma intranet de organização simplificada conectada à Internet, composta pelas máquinas virtuais DC1, APP1 e CLIENT1, em uma sub-rede de uma Rede Virtual do Microsoft Azure. Um Agente de Autenticação é executado no APP1 para processar as solicitações de autenticação de passagem do locatário do Azure AD nas assinaturas do Office 365 e do EMS E5.</span><span class="sxs-lookup"><span data-stu-id="93d42-p108">A simplified organization intranet connected to the Internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network. An Authentication Agent runs on APP1 to handle pass-through authentication requests from the Azure AD tenant of your Office 365 and EMS E5 subscriptions.</span></span>

## <a name="next-step"></a><span data-ttu-id="93d42-149">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="93d42-149">Next step</span></span>

<span data-ttu-id="93d42-150">Explorar recursos e funcionalidades adicionais de [identidade](m365-enterprise-test-lab-guides.md#identity) no ambiente de teste.</span><span class="sxs-lookup"><span data-stu-id="93d42-150">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="93d42-151">Confira também</span><span class="sxs-lookup"><span data-stu-id="93d42-151">See also</span></span>

[<span data-ttu-id="93d42-152">Guias do Laboratório de Teste do Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="93d42-152">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="93d42-153">Implantar o Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="93d42-153">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="93d42-154">Documentação do Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="93d42-154">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)


