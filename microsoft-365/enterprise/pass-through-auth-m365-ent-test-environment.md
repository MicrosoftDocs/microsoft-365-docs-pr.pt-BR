---
title: Autenticação de passagem para seu ambiente de teste do Microsoft 365
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
- TLG
- Ent_TLGs
ms.assetid: ''
description: 'Resumo: configure a autenticação de passagem para seu ambiente de teste do Microsoft 365.'
ms.openlocfilehash: 4f9941b017f00b40a6ae7e893211131cae51c611
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42066414"
---
# <a name="pass-through-authentication-for-your-microsoft-365-test-environment"></a><span data-ttu-id="cd7d2-103">Autenticação de passagem para seu ambiente de teste do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="cd7d2-103">Pass-through authentication for your Microsoft 365 test environment</span></span>

<span data-ttu-id="cd7d2-104">*Este Guia de Laboratório de Testes pode ser usado para ambientes de teste corporativo do Microsoft 365 Enterprise e do Office 365.*</span><span class="sxs-lookup"><span data-stu-id="cd7d2-104">*This Test Lab Guide can be used for both Microsoft 365 Enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="cd7d2-105">As organizações que desejem usar diretamente a própria infraestrutura do Active Directory Domain Services (AD DS) local para a autenticação em serviços e aplicativos baseados na nuvem da Microsoft podem usar a autenticação de passagem.</span><span class="sxs-lookup"><span data-stu-id="cd7d2-105">Organizations that want to directly use their on-premises Active Directory Domain Services (AD DS) infrastructure for authentication to Microsoft cloud-based services and applications can use pass-through authentication.</span></span> <span data-ttu-id="cd7d2-106">Este artigo descreve como configurar seu ambiente de teste do Microsoft 365 para autenticação de passagem, resultando na seguinte configuração:</span><span class="sxs-lookup"><span data-stu-id="cd7d2-106">This article describes how you can configure your Microsoft 365 test environment for pass-through authentication, resulting in the following configuration:</span></span>
  
![A empresa simulada com ambiente de teste de autenticação de passagem](../media/pass-through-auth-m365-ent-test-environment/Phase2.png)
  
<span data-ttu-id="cd7d2-108">Há duas fases para configurar esse ambiente de teste:</span><span class="sxs-lookup"><span data-stu-id="cd7d2-108">There are two phases to setting up this test environment:</span></span>

1.  <span data-ttu-id="cd7d2-109">Criar o ambiente de teste de empresa simulada do Microsoft 365 com sincronização de hash de senha.</span><span class="sxs-lookup"><span data-stu-id="cd7d2-109">Create the Microsoft 365 simulated enterprise test environment with password hash synchronization.</span></span>
2.  <span data-ttu-id="cd7d2-110">Configurar o Azure AD Connect no APP1 para autenticação de passagem.</span><span class="sxs-lookup"><span data-stu-id="cd7d2-110">Configure Azure AD Connect on APP1 for pass-through authentication.</span></span>
    
![Guias de laboratório de teste da Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="cd7d2-112">Clique [aqui](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) para ver um mapa visual de todos os artigos da pilha do Guia de Laboratório de Teste do Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="cd7d2-112">Click [here](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a><span data-ttu-id="cd7d2-113">Fase 1: configurar a sincronização de hash de senha do ambiente de teste do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="cd7d2-113">Phase 1: Configure password hash synchronization for your Microsoft 365 test environment</span></span>

<span data-ttu-id="cd7d2-p102">Siga as instruções em [sincronização de hash de senha para o Microsoft 365](password-hash-sync-m365-ent-test-environment.md). Aqui está a configuração resultante.</span><span class="sxs-lookup"><span data-stu-id="cd7d2-p102">Follow the instructions in [password hash synchronization for Microsoft 365](password-hash-sync-m365-ent-test-environment.md). Here is your resulting configuration.</span></span>
  
![Empresa simulada com ambiente de teste de sincronização de hash de senha](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
<span data-ttu-id="cd7d2-117">Esta configuração consiste em:</span><span class="sxs-lookup"><span data-stu-id="cd7d2-117">This configuration consists of:</span></span> 
  
- <span data-ttu-id="cd7d2-118">Assinaturas de avaliação ou pagas do Microsoft 365 E5 ou Office 365 E5.</span><span class="sxs-lookup"><span data-stu-id="cd7d2-118">Microsoft 365 E5 or Office 365 E5 trial or paid subscriptions.</span></span>
- <span data-ttu-id="cd7d2-119">Uma intranet de organização simplificada conectado à Internet, que consiste em máquinas virtuais do DC1 APP1 e CLIENT1 em uma sub-rede de uma rede virtual do Azure.</span><span class="sxs-lookup"><span data-stu-id="cd7d2-119">A simplified organization intranet connected to the Internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span> <span data-ttu-id="cd7d2-120">O Azure AD Connect é executado periodicamente no APP1 para sincronizar o domínio TESTLAB do AD DS com o locatário do Azure AD de sua assinatura do Microsoft 365 ou Office 365.</span><span class="sxs-lookup"><span data-stu-id="cd7d2-120">Azure AD Connect runs on APP1 to synchronize the TESTLAB AD DS domain to the Azure AD tenant of your Microsoft 365 or Office 365 subscription periodically.</span></span>

## <a name="phase-2-configure-azure-ad-connect-on-app1-for-pass-through-authentication"></a><span data-ttu-id="cd7d2-121">Fase 2: configurar o Azure AD Connect no APP1 para autenticação de passagem</span><span class="sxs-lookup"><span data-stu-id="cd7d2-121">Phase 2: Configure Azure AD Connect on APP1 for pass-through authentication</span></span>

<span data-ttu-id="cd7d2-122">Nesta fase, você configura o Azure AD Connect no APP1 para usar autenticação de passagem e verifica se ela funciona.</span><span class="sxs-lookup"><span data-stu-id="cd7d2-122">In this phase, you configure Azure AD Connect on APP1 to use pass-through authentication, and then verify that it works.</span></span>

### <a name="configure-azure-ad-connect-on-app1"></a><span data-ttu-id="cd7d2-123">Configurar o Azure AD Connect no APP1</span><span class="sxs-lookup"><span data-stu-id="cd7d2-123">Configure Azure AD Connect on APP1</span></span>

1.  <span data-ttu-id="cd7d2-124">No [Portal do Azure](https://portal.azure.com), entre com a conta de administrador global e conecte-se ao APP1 com a conta TESTLAB\Usuário1.</span><span class="sxs-lookup"><span data-stu-id="cd7d2-124">From the [Azure portal](https://portal.azure.com), sign in with your global administrator account, and then connect to APP1 with the TESTLAB\User1 account.</span></span>

2.  <span data-ttu-id="cd7d2-125">Na área de trabalho do APP1, execute o Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="cd7d2-125">From the desktop of APP1, run Azure AD Connect.</span></span>

3.  <span data-ttu-id="cd7d2-126">Na **Página inicial**, clique em **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="cd7d2-126">On the **Welcome page**, click **Configure**.</span></span>

4.  <span data-ttu-id="cd7d2-127">Na página Tarefas adicionais, clique em **Alterar entrada do usuário** e em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="cd7d2-127">On the Additional tasks page, click **Change user sign-in**, and then click **Next**.</span></span>

5.  <span data-ttu-id="cd7d2-128">Na página **Conectar ao Azure AD**, digite suas credenciais de conta de administrador global e clique em **Próxima**.</span><span class="sxs-lookup"><span data-stu-id="cd7d2-128">On the **Connect to Azure AD** page, type your global administrator account credentials, and then click **Next**.</span></span>

6.  <span data-ttu-id="cd7d2-129">Na página **Entrada de usuário**, clique em **Autenticação de passagem**e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="cd7d2-129">On the **User sign-in** page, click **Pass-through authentication**, and then click **Next**.</span></span>

7.  <span data-ttu-id="cd7d2-130">Na página **Pronto para configurar**, clique em **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="cd7d2-130">On the **Ready to configure** page, click **Configure**.</span></span>

8.  <span data-ttu-id="cd7d2-131">Na página **Configuração concluída**, clique em **Sair**.</span><span class="sxs-lookup"><span data-stu-id="cd7d2-131">On the **Configuration complete** page, click **Exit**.</span></span>

9.  <span data-ttu-id="cd7d2-p104">No portal do Azure, no painel esquerdo, clique em **Azure Active Directory > Azure AD Connect Health**. Verifique se o recurso **Autenticação de passagem** aparece como **Habilitado**.</span><span class="sxs-lookup"><span data-stu-id="cd7d2-p104">From the Azure portal, in the left pane, click **Azure Active Directory > Azure AD Connect**. Verify that the **Pass-through authentication** feature appears as **Enabled**.</span></span>

10. <span data-ttu-id="cd7d2-p105">Clique em **Autenticação de passagem**. O painel **Autenticação de passagem** lista os servidores onde estão instalados os Agentes de Autenticação. Você verá APP1 na lista. Feche o painel **Autenticação de passagem**.</span><span class="sxs-lookup"><span data-stu-id="cd7d2-p105">Click **Pass-through authentication**. The **Pass-through authentication** pane lists the servers where your Authentication Agents are installed. You should see APP1 in the list. Close the **Pass-through authentication** pane.</span></span>

<span data-ttu-id="cd7d2-138">Em seguida, teste a capacidade de entrar em sua assinatura com a conta <strong>usuario1@testlab.</strong>\<seu domínio público> nome de usuário da conta Usuário1.</span><span class="sxs-lookup"><span data-stu-id="cd7d2-138">Next, test the ability to sign in to your subscription with the <strong>user1@testlab.</strong>\<your public domain> user name of the User1 account.</span></span>

1. <span data-ttu-id="cd7d2-139">No APP1, saia e entre novamente, mas desta vez especifique uma conta diferente.</span><span class="sxs-lookup"><span data-stu-id="cd7d2-139">From APP1, sign out, and then sign in again, this time specifying a different account.</span></span>

2. <span data-ttu-id="cd7d2-140">Quando solicitado a fornecer o nome de usuário e a senha, especifique <strong>usuario1@testlab.</strong>\<seu domínio público> e a senha de Usuario1.</span><span class="sxs-lookup"><span data-stu-id="cd7d2-140">When prompted for a user name and password, specify <strong>user1@testlab.</strong>\<your public domain> and the User1 password.</span></span> <span data-ttu-id="cd7d2-141">Você deve conseguir entrar como Usuario1.</span><span class="sxs-lookup"><span data-stu-id="cd7d2-141">You should successfully sign in as User1.</span></span>

<span data-ttu-id="cd7d2-142">Observe que, embora o Usuário1 tenha permissões de administrador de domínio para o domínio TESTLAB do AD DS, ele não é um administrador global.</span><span class="sxs-lookup"><span data-stu-id="cd7d2-142">Notice that although User1 has domain administrator permissions for the TESTLAB AD DS domain, it is not a global administrator.</span></span> <span data-ttu-id="cd7d2-143">Portanto, o ícone **Administrador** não estará disponível como opção.</span><span class="sxs-lookup"><span data-stu-id="cd7d2-143">Therefore, you will not see the **Admin** icon as an option.</span></span>

<span data-ttu-id="cd7d2-144">Esta é a configuração resultante:</span><span class="sxs-lookup"><span data-stu-id="cd7d2-144">Here is your resulting configuration:</span></span>

![A empresa simulada com ambiente de teste de autenticação de passagem](../media/pass-through-auth-m365-ent-test-environment/Phase2.png)
 
<span data-ttu-id="cd7d2-146">Esta configuração consiste em:</span><span class="sxs-lookup"><span data-stu-id="cd7d2-146">This configuration consists of:</span></span>

- <span data-ttu-id="cd7d2-147">Assinaturas pagas ou de avaliação do Microsoft 365 E5 ou do Office 365 E5 com o domínio DNS testlab.\<seu nome de domínio> registrado.</span><span class="sxs-lookup"><span data-stu-id="cd7d2-147">Microsoft 365 E5 or Office 365 E5 trial or paid subscriptions with the DNS domain testlab.\<your domain name> registered.</span></span>
- <span data-ttu-id="cd7d2-p108">Uma intranet de organização simplificada conectada à Internet, composta pelas máquinas virtuais DC1, APP1 e CLIENT1, em uma sub-rede de uma Rede Virtual do Microsoft Azure. Um Agente de Autenticação é executado no APP1 para processar as solicitações de autenticação de passagem do locatário do Azure AD nas assinaturas do Microsoft 365 ou do Office 365. </span><span class="sxs-lookup"><span data-stu-id="cd7d2-p108">A simplified organization intranet connected to the Internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network. An Authentication Agent runs on APP1 to handle pass-through authentication requests from the Azure AD tenant of your Microsoft 365 or Office 365 subscription.</span></span>

## <a name="next-step"></a><span data-ttu-id="cd7d2-150">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="cd7d2-150">Next step</span></span>

<span data-ttu-id="cd7d2-151">Explorar recursos e funcionalidades adicionais de [identidade](m365-enterprise-test-lab-guides.md#identity) no ambiente de teste.</span><span class="sxs-lookup"><span data-stu-id="cd7d2-151">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="cd7d2-152">Confira também</span><span class="sxs-lookup"><span data-stu-id="cd7d2-152">See also</span></span>

[<span data-ttu-id="cd7d2-153">Guias do Laboratório de Teste do Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="cd7d2-153">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="cd7d2-154">Implantar o Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="cd7d2-154">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="cd7d2-155">Documentação do Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="cd7d2-155">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
