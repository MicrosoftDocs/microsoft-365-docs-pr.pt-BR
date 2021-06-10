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
localization_priority: Normal
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom:
- TLG
- Ent_TLGs
ms.assetid: ''
description: 'Resumo: configure a autenticação de passagem para seu ambiente de teste do Microsoft 365.'
ms.openlocfilehash: cdbb6927fb8ca0001e3089c7169ce9046208e8f8
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50921523"
---
# <a name="pass-through-authentication-for-your-microsoft-365-test-environment"></a><span data-ttu-id="6d8d6-103">Autenticação de passagem para seu ambiente de teste do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="6d8d6-103">Pass-through authentication for your Microsoft 365 test environment</span></span>

<span data-ttu-id="6d8d6-104">*Este Guia de Laboratório de Teste pode ser usado para Microsoft 365 ambientes de teste corporativos e Office 365 Enterprise de teste.*</span><span class="sxs-lookup"><span data-stu-id="6d8d6-104">*This Test Lab Guide can be used for both Microsoft 365 for enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="6d8d6-105">As organizações que desejem usar diretamente a própria infraestrutura do Active Directory Domain Services (AD DS) local para a autenticação em serviços e aplicativos baseados na nuvem da Microsoft podem usar a autenticação de passagem.</span><span class="sxs-lookup"><span data-stu-id="6d8d6-105">Organizations that want to directly use their on-premises Active Directory Domain Services (AD DS) infrastructure for authentication to Microsoft cloud-based services and applications can use pass-through authentication.</span></span> <span data-ttu-id="6d8d6-106">Este artigo descreve como configurar seu ambiente de teste do Microsoft 365 para autenticação de passagem, resultando na seguinte configuração:</span><span class="sxs-lookup"><span data-stu-id="6d8d6-106">This article describes how you can configure your Microsoft 365 test environment for pass-through authentication, resulting in the following configuration:</span></span>
  
![A empresa simulada com ambiente de teste de autenticação de passagem](../media/pass-through-auth-m365-ent-test-environment/Phase2.png)
  
<span data-ttu-id="6d8d6-108">Há duas fases para configurar esse ambiente de teste:</span><span class="sxs-lookup"><span data-stu-id="6d8d6-108">There are two phases to setting up this test environment:</span></span>

1.    <span data-ttu-id="6d8d6-109">Criar o ambiente de teste de empresa simulada do Microsoft 365 com sincronização de hash de senha.</span><span class="sxs-lookup"><span data-stu-id="6d8d6-109">Create the Microsoft 365 simulated enterprise test environment with password hash synchronization.</span></span>
2.    <span data-ttu-id="6d8d6-110">Configurar o Azure AD Connect no APP1 para autenticação de passagem.</span><span class="sxs-lookup"><span data-stu-id="6d8d6-110">Configure Azure AD Connect on APP1 for pass-through authentication.</span></span>
    
![Guias de laboratório de teste da Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="6d8d6-112">Clique [aqui](../downloads/Microsoft365EnterpriseTLGStack.pdf) para ver um mapa visual de todos os artigos na pilha do Guia de Laboratório de Teste do Microsoft 365 para empresas.</span><span class="sxs-lookup"><span data-stu-id="6d8d6-112">Click [here](../downloads/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a><span data-ttu-id="6d8d6-113">Fase 1: configurar a sincronização de hash de senha do ambiente de teste do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="6d8d6-113">Phase 1: Configure password hash synchronization for your Microsoft 365 test environment</span></span>

<span data-ttu-id="6d8d6-p102">Siga as instruções em [sincronização de hash de senha para o Microsoft 365](password-hash-sync-m365-ent-test-environment.md). Aqui está a configuração resultante.</span><span class="sxs-lookup"><span data-stu-id="6d8d6-p102">Follow the instructions in [password hash synchronization for Microsoft 365](password-hash-sync-m365-ent-test-environment.md). Here is your resulting configuration.</span></span>
  
![Empresa simulada com ambiente de teste de sincronização de hash de senha](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
<span data-ttu-id="6d8d6-117">Esta configuração consiste em:</span><span class="sxs-lookup"><span data-stu-id="6d8d6-117">This configuration consists of:</span></span> 
  
- <span data-ttu-id="6d8d6-118">Microsoft 365 E5 avaliação ou assinatura paga.</span><span class="sxs-lookup"><span data-stu-id="6d8d6-118">Microsoft 365 E5 trial or paid subscription.</span></span>
- <span data-ttu-id="6d8d6-119">Uma intranet de organização simplificada conectado à Internet, que consiste em máquinas virtuais do DC1 APP1 e CLIENT1 em uma sub-rede de uma rede virtual do Azure.</span><span class="sxs-lookup"><span data-stu-id="6d8d6-119">A simplified organization intranet connected to the Internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span> <span data-ttu-id="6d8d6-120">O Azure AD Connect é executado no APP1 para sincronizar o domínio TESTLAB AD DS com o locatário do Azure AD das suas assinaturas do Microsoft 365 periodicamente.</span><span class="sxs-lookup"><span data-stu-id="6d8d6-120">Azure AD Connect runs on APP1 to synchronize the TESTLAB AD DS domain to the Azure AD tenant of your Microsoft 365 subscription periodically.</span></span>

## <a name="phase-2-configure-azure-ad-connect-on-app1-for-pass-through-authentication"></a><span data-ttu-id="6d8d6-121">Fase 2: configurar o Azure AD Connect no APP1 para autenticação de passagem</span><span class="sxs-lookup"><span data-stu-id="6d8d6-121">Phase 2: Configure Azure AD Connect on APP1 for pass-through authentication</span></span>

<span data-ttu-id="6d8d6-122">Nesta fase, você configura o Azure AD Connect no APP1 para usar autenticação de passagem e verifica se ela funciona.</span><span class="sxs-lookup"><span data-stu-id="6d8d6-122">In this phase, you configure Azure AD Connect on APP1 to use pass-through authentication, and then verify that it works.</span></span>

### <a name="configure-azure-ad-connect-on-app1"></a><span data-ttu-id="6d8d6-123">Configurar o Azure AD Connect no APP1</span><span class="sxs-lookup"><span data-stu-id="6d8d6-123">Configure Azure AD Connect on APP1</span></span>

1.    <span data-ttu-id="6d8d6-124">No [Portal do Azure](https://portal.azure.com), entre com a conta de administrador global e conecte-se ao APP1 com a conta TESTLAB\Usuário1.</span><span class="sxs-lookup"><span data-stu-id="6d8d6-124">From the [Azure portal](https://portal.azure.com), sign in with your global administrator account, and then connect to APP1 with the TESTLAB\User1 account.</span></span>

2.    <span data-ttu-id="6d8d6-125">Na área de trabalho do APP1, execute o Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="6d8d6-125">From the desktop of APP1, run Azure AD Connect.</span></span>

3.    <span data-ttu-id="6d8d6-126">Na **Página inicial**, clique em **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="6d8d6-126">On the **Welcome page**, click **Configure**.</span></span>

4.    <span data-ttu-id="6d8d6-127">Na página Tarefas adicionais, clique em **Alterar entrada do usuário** e em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="6d8d6-127">On the Additional tasks page, click **Change user sign-in**, and then click **Next**.</span></span>

5.    <span data-ttu-id="6d8d6-128">Na página **Conectar ao Azure AD**, digite suas credenciais de conta de administrador global e clique em **Próxima**.</span><span class="sxs-lookup"><span data-stu-id="6d8d6-128">On the **Connect to Azure AD** page, type your global administrator account credentials, and then click **Next**.</span></span>

6.    <span data-ttu-id="6d8d6-129">Na página **Entrada de usuário**, clique em **Autenticação de passagem** e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="6d8d6-129">On the **User sign-in** page, click **Pass-through authentication**, and then click **Next**.</span></span>

7.    <span data-ttu-id="6d8d6-130">Na página **Pronto para configurar**, clique em **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="6d8d6-130">On the **Ready to configure** page, click **Configure**.</span></span>

8.    <span data-ttu-id="6d8d6-131">Na página **Configuração concluída**, clique em **Sair**.</span><span class="sxs-lookup"><span data-stu-id="6d8d6-131">On the **Configuration complete** page, click **Exit**.</span></span>

9.    <span data-ttu-id="6d8d6-p104">No portal do Azure, no painel esquerdo, clique em **Azure Active Directory > Azure AD Connect Health**. Verifique se o recurso **Autenticação de passagem** aparece como **Habilitado**.</span><span class="sxs-lookup"><span data-stu-id="6d8d6-p104">From the Azure portal, in the left pane, click **Azure Active Directory > Azure AD Connect**. Verify that the **Pass-through authentication** feature appears as **Enabled**.</span></span>

10.    <span data-ttu-id="6d8d6-p105">Clique em **Autenticação de passagem**. O painel **Autenticação de passagem** lista os servidores onde estão instalados os Agentes de Autenticação. Você verá APP1 na lista. Feche o painel **Autenticação de passagem**.</span><span class="sxs-lookup"><span data-stu-id="6d8d6-p105">Click **Pass-through authentication**. The **Pass-through authentication** pane lists the servers where your Authentication Agents are installed. You should see APP1 in the list. Close the **Pass-through authentication** pane.</span></span>

<span data-ttu-id="6d8d6-138">Em seguida, teste a capacidade de entrar em sua assinatura com o <strong>user1@testlab.</strong>\<your public domain></span><span class="sxs-lookup"><span data-stu-id="6d8d6-138">Next, test the ability to sign in to your subscription with the <strong>user1@testlab.</strong>\<your public domain></span></span> <span data-ttu-id="6d8d6-139">nome de usuário da conta User1.</span><span class="sxs-lookup"><span data-stu-id="6d8d6-139">user name of the User1 account.</span></span>

1. <span data-ttu-id="6d8d6-140">Na APP1, saia e entre novamente, mas desta vez especifique uma conta diferente.</span><span class="sxs-lookup"><span data-stu-id="6d8d6-140">From APP1, sign out, and then sign in again, this time specifying a different account.</span></span>

2. <span data-ttu-id="6d8d6-141">Quando for pedido um nome de usuário e senha, especifique <strong>user1@testlab.</strong>\<your public domain></span><span class="sxs-lookup"><span data-stu-id="6d8d6-141">When prompted for a user name and password, specify <strong>user1@testlab.</strong>\<your public domain></span></span> <span data-ttu-id="6d8d6-142">e a senha do User1.</span><span class="sxs-lookup"><span data-stu-id="6d8d6-142">and the User1 password.</span></span> <span data-ttu-id="6d8d6-143">Você deve conseguir entrar como Usuario1.</span><span class="sxs-lookup"><span data-stu-id="6d8d6-143">You should successfully sign in as User1.</span></span>

<span data-ttu-id="6d8d6-144">Observe que, embora o Usuário1 tenha permissões de administrador de domínio para o domínio TESTLAB do AD DS, ele não é um administrador global.</span><span class="sxs-lookup"><span data-stu-id="6d8d6-144">Notice that although User1 has domain administrator permissions for the TESTLAB AD DS domain, it is not a global administrator.</span></span> <span data-ttu-id="6d8d6-145">Portanto, o ícone **Administrador** não estará disponível como opção.</span><span class="sxs-lookup"><span data-stu-id="6d8d6-145">Therefore, you will not see the **Admin** icon as an option.</span></span>

<span data-ttu-id="6d8d6-146">Esta é a configuração resultante:</span><span class="sxs-lookup"><span data-stu-id="6d8d6-146">Here is your resulting configuration:</span></span>

![A empresa simulada com ambiente de teste de autenticação de passagem](../media/pass-through-auth-m365-ent-test-environment/Phase2.png)
 
<span data-ttu-id="6d8d6-148">Esta configuração consiste em:</span><span class="sxs-lookup"><span data-stu-id="6d8d6-148">This configuration consists of:</span></span>

- <span data-ttu-id="6d8d6-149">Uma Microsoft 365 E5 de avaliação ou assinaturas pagas com o testlab de domínio DNS.\<your domain name></span><span class="sxs-lookup"><span data-stu-id="6d8d6-149">A Microsoft 365 E5 trial or paid subscriptions with the DNS domain testlab.\<your domain name></span></span> <span data-ttu-id="6d8d6-150">registrado.</span><span class="sxs-lookup"><span data-stu-id="6d8d6-150">registered.</span></span>
- <span data-ttu-id="6d8d6-p110">Uma intranet simplificada da organização conectada à Internet, consistindo nas máquinas virtuais DC1, APP1 e CLIENT1 em uma sub-rede de uma rede virtual do Azure. Um Agente de autenticação é executado no APP1 para lidar com solicitações de autenticação de passagem do locatário do Azure AD da sua assinatura do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6d8d6-p110">A simplified organization intranet connected to the Internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network. An Authentication Agent runs on APP1 to handle pass-through authentication requests from the Azure AD tenant of your Microsoft 365 subscription.</span></span>

## <a name="next-step"></a><span data-ttu-id="6d8d6-153">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="6d8d6-153">Next step</span></span>

<span data-ttu-id="6d8d6-154">Explorar recursos e funcionalidades adicionais de [identidade](m365-enterprise-test-lab-guides.md#identity) no ambiente de teste.</span><span class="sxs-lookup"><span data-stu-id="6d8d6-154">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="6d8d6-155">Confira também</span><span class="sxs-lookup"><span data-stu-id="6d8d6-155">See also</span></span>

[<span data-ttu-id="6d8d6-156">Guias do Laboratório de Teste do Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="6d8d6-156">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="6d8d6-157">Visão geral do Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="6d8d6-157">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="6d8d6-158">Documentação do Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="6d8d6-158">Microsoft 365 for enterprise documentation</span></span>](/microsoft-365-enterprise/)