---
title: Sincronização de hash de senha para ambiente de teste do Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/13/2018
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
description: 'Resumo: configurar e demonstrar a sincronização de hash de senha e a entrada para o ambiente de teste do Microsoft 365.'
ms.openlocfilehash: 0c6f7ec4afdfaaca0c84ed33ea0c1b1f248a82f5
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/15/2019
ms.locfileid: "34073171"
---
# <a name="password-hash-synchronization-for-your-microsoft-365-test-environment"></a><span data-ttu-id="e960f-103">Sincronização de hash de senha para ambiente de teste do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e960f-103">Password hash synchronization for your Microsoft 365 test environment</span></span>

<span data-ttu-id="e960f-104">Muitas organizações usam o Azure AD Connect e a sincronização de hash de senha para sincronizar o conjunto de contas na própria floresta do Active Directory Domain Services (AD DS) local com o conjunto de contas no locatário do Azure AD de suas assinaturas do Office 365 e EMS E5.</span><span class="sxs-lookup"><span data-stu-id="e960f-104">Many organizations use Azure AD Connect and password hash synchronization to synchronize the set of accounts in their on-premises Active Directory Domain Services (AD DS) forest to the set of accounts in the Azure AD tenant of their Office 365 and EMS E5 subscriptions.</span></span> <span data-ttu-id="e960f-105">Este artigo descreve como adicionar a sincronização de hash de senha a seu ambiente de teste do Microsoft 365, resultando na seguinte configuração:</span><span class="sxs-lookup"><span data-stu-id="e960f-105">This article describes how you can add password hash synchronization to your Microsoft 365 test environment, resulting in the following configuration:</span></span>
  
![Empresa simulada com ambiente de teste de sincronização de hash de senha](media/password-hash-sync-m365-ent-test-environment/Phase3.png)
  
<span data-ttu-id="e960f-107">Há duas fases para configurar esse ambiente de teste:</span><span class="sxs-lookup"><span data-stu-id="e960f-107">There are two phases to setting up this test environment:</span></span>
  
1. <span data-ttu-id="e960f-108">Crie o ambiente de teste corporativo simulado do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e960f-108">Create the Microsoft 365 simulated enterprise test environment.</span></span>
2. <span data-ttu-id="e960f-109">Instale e configure o Azure AD Connect na APP1.</span><span class="sxs-lookup"><span data-stu-id="e960f-109">Install and configure Azure AD Connect on APP1.</span></span>
    
> [!TIP]
> <span data-ttu-id="e960f-110">Clique [aqui](https://aka.ms/m365etlgstack) para ver um mapa visual de todos os artigos da pilha do Guia de Laboratório de Teste do Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="e960f-110">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-create-the-microsoft-365-simulated-enterprise-test-environment"></a><span data-ttu-id="e960f-111">Fase 1 – Criar o ambiente de teste corporativo simulado do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e960f-111">Phase 1: Create the Microsoft 365 simulated enterprise test environment</span></span>

<span data-ttu-id="e960f-p102">Siga as instruções da [configuração base corporativa simulada do Microsoft 365](simulated-ent-base-configuration-microsoft-365-enterprise.md). Aqui está a configuração resultante.</span><span class="sxs-lookup"><span data-stu-id="e960f-p102">Follow the instructions in [simulated enterprise base configuration for Microsoft 365](simulated-ent-base-configuration-microsoft-365-enterprise.md). Here is your resulting configuration.</span></span>
  
![A configuração base corporativa simulada](media/password-hash-sync-m365-ent-test-environment/Phase1.png)
  
<span data-ttu-id="e960f-115">Esta configuração consiste em:</span><span class="sxs-lookup"><span data-stu-id="e960f-115">This configuration consists of:</span></span> 
  
- <span data-ttu-id="e960f-116">Assinaturas pagas ou de avaliação do Office 365 E5 e EMS E5.</span><span class="sxs-lookup"><span data-stu-id="e960f-116">Office 365 E5 and EMS E5 trial or paid subscriptions.</span></span>
- <span data-ttu-id="e960f-117">Uma intranet de organização simplificada conectada à Internet, que consiste em máquinas virtuais do DC1, APP1 e CLIENT1 em uma rede virtual do Azure.</span><span class="sxs-lookup"><span data-stu-id="e960f-117">A simplified organization intranet connected to the Internet, consisting of the DC1, APP1, and CLIENT1 virtual machines in an Azure virtual network.</span></span> <span data-ttu-id="e960f-118">O DC1 é um controlador de domínio para o testlab.\<seu nome de domínio público> domínio do AD DS.</span><span class="sxs-lookup"><span data-stu-id="e960f-118">DC1 is a domain controller for the testlab.\<your public domain name> Active Directory Domain Services (AD DS) domain.</span></span>

## <a name="phase-2-create-and-register-the-testlab-domain"></a><span data-ttu-id="e960f-119">Fase 2 – Criar e registrar o domínio testlab</span><span class="sxs-lookup"><span data-stu-id="e960f-119">Phase 2: Create and register the testlab domain</span></span>

<span data-ttu-id="e960f-120">Nesta fase, você adiciona um domínio DNS público e o adiciona-o à assinatura.</span><span class="sxs-lookup"><span data-stu-id="e960f-120">In this phase you add a public DNS domain and add it to your subscription.</span></span>

<span data-ttu-id="e960f-p104">Primeiro, trabalhe com um provedor de registro DNS público para criar um nome de domínio DNS público com base em um nome de domínio atual e adicioná-lo à assinatura do Office 365. Recomendamos usar o nome **testlab.**\<domínio público>. Por exemplo, se o nome de domínio público for <span>**contoso</span>.com**, adicione o nome de domínio público **<span>testlab</span>.contoso.com**.</span><span class="sxs-lookup"><span data-stu-id="e960f-p104">First, work with your public DNS registration provider to create a new public DNS domain name based on your current domain name and add it to your Office 365 subscription. We recommend using the name **testlab.**\<your public domain>. For example, if your public domain name is <span>**contoso</span>.com**, add the public domain name **<span>testlab</span>.contoso.com**.</span></span>
  
<span data-ttu-id="e960f-124">Em seguida, adicione o **testlab.**\<seu domínio público> domínio da sua assinatura de avaliação ou paga do Office 365 por meio do processo de registro de domínio.</span><span class="sxs-lookup"><span data-stu-id="e960f-124">Next, you add the **testlab.**\<your public domain> domain to your Office 365 trial or paid subscription by going through the domain registration process.</span></span> <span data-ttu-id="e960f-125">Isso consiste em adicionar outros registros DNS ao **testlab.**\<seu domínio público> domínio.</span><span class="sxs-lookup"><span data-stu-id="e960f-125">This consists of adding additional DNS records to the **testlab.**\<your public domain> domain.</span></span> <span data-ttu-id="e960f-126">Confira mais informações em [Adicionar usuários e domínio ao Office 365](https://support.office.com/article/Add-users-and-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).</span><span class="sxs-lookup"><span data-stu-id="e960f-126">For more information, see [Add users and domain to Office 365](https://support.office.com/article/Add-users-and-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).</span></span> 

<span data-ttu-id="e960f-127">Esta é a configuração resultante.</span><span class="sxs-lookup"><span data-stu-id="e960f-127">Here is your resulting configuration.</span></span>
  
![O registro do seu nome de domínio testlab](media/password-hash-sync-m365-ent-test-environment/Phase2.png)
  
<span data-ttu-id="e960f-129">Esta configuração consiste em:</span><span class="sxs-lookup"><span data-stu-id="e960f-129">This configuration consists of:</span></span>

- <span data-ttu-id="e960f-130">Assinaturas pagas ou de avaliação do Office 365 E5 e EMS E5 com o domínio DNS testlab.\<seu nome de domínio público> registrado.</span><span class="sxs-lookup"><span data-stu-id="e960f-130">Office 365 E5 and EMS E5 trial or paid subscriptions with the DNS domain testlab.\<your public domain name> registered.</span></span>
- <span data-ttu-id="e960f-131">Uma intranet de organização simplificada conectado à Internet, que consiste em máquinas virtuais do DC1 APP1 e CLIENT1 em uma sub-rede de uma rede virtual do Azure.</span><span class="sxs-lookup"><span data-stu-id="e960f-131">A simplified organization intranet connected to the Internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span>

<span data-ttu-id="e960f-132">Veja como o testlab.\<seu nome de domínio público> está agora:</span><span class="sxs-lookup"><span data-stu-id="e960f-132">Notice how the testlab.\<your public domain name> is now:</span></span>

- <span data-ttu-id="e960f-133">Compatível com registros DNS públicos.</span><span class="sxs-lookup"><span data-stu-id="e960f-133">Supported by public DNS records.</span></span>
- <span data-ttu-id="e960f-134">Registrado nas assinaturas do Office 365 e do EMS.</span><span class="sxs-lookup"><span data-stu-id="e960f-134">Registered in your Office 365 and EMS subscriptions.</span></span>
- <span data-ttu-id="e960f-135">O domínio AD DS na sua intranet simulada.</span><span class="sxs-lookup"><span data-stu-id="e960f-135">The AD DS domain on your simulated intranet.</span></span>
     
## <a name="phase-3-install-azure-ad-connect-on-app1"></a><span data-ttu-id="e960f-136">Fase 3 – Instalar o Azure AD Connect na APP1</span><span class="sxs-lookup"><span data-stu-id="e960f-136">Phase 3: Install Azure AD Connect on APP1</span></span>

<span data-ttu-id="e960f-137">Nesta fase, instale e configure a ferramenta Azure AD Connect na APP1 e verifique se ela funciona.</span><span class="sxs-lookup"><span data-stu-id="e960f-137">In this phase, you install and configure the Azure AD Connect tool on APP1, and then verify that it works.</span></span>
  
<span data-ttu-id="e960f-138">Primeiro, instale e configure o Azure AD Connect na APP1.</span><span class="sxs-lookup"><span data-stu-id="e960f-138">First, you install and configure Azure AD Connect on APP1.</span></span>

1. <span data-ttu-id="e960f-139">No [Portal do Azure](https://portal.azure.com), entre com a conta de administrador global e conecte-se à APP1 com a conta \\Usuário1 do TestLab.</span><span class="sxs-lookup"><span data-stu-id="e960f-139">From the [Azure portal](https://portal.azure.com), sign in with your global administrator account, and then connect to APP1 with the TESTLAB\\User1 account.</span></span>
    
2. <span data-ttu-id="e960f-140">Na área de trabalho da APP1, abra um prompt de comando do nível de administrador do Windows PowerShell e execute estes comandos:</span><span class="sxs-lookup"><span data-stu-id="e960f-140">From the desktop of APP1, open an administrator-level Windows PowerShell command prompt, and then run these commands:</span></span>
    
   ```
   Set-ItemProperty -Path "HKLM:\SOFTWARE\Microsoft\Active Setup\Installed Components\{A509B1A7-37EF-4b3f-8CFC-4F3A74704073}" -Name "IsInstalled" -Value 0
   Set-ItemProperty -Path "HKLM:\SOFTWARE\Microsoft\Active Setup\Installed Components\{A509B1A8-37EF-4b3f-8CFC-4F3A74704073}" -Name "IsInstalled" -Value 0
   Stop-Process -Name Explorer -Force
   ```

3. <span data-ttu-id="e960f-141">Na barra de tarefas, clique em **Internet Explorer** e acesse [https://aka.ms/aadconnect](https://aka.ms/aadconnect).</span><span class="sxs-lookup"><span data-stu-id="e960f-141">From the task bar, click **Internet Explorer** and go to [https://aka.ms/aadconnect](https://aka.ms/aadconnect).</span></span>
    
4. <span data-ttu-id="e960f-142">Na página do Microsoft Azure Active Directory Connect, clique em **Baixar** e, em seguida, clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="e960f-142">On the Microsoft Azure Active Directory Connect page, click **Download**, and then click **Run**.</span></span>
    
5. <span data-ttu-id="e960f-143">Na página **Bem-vindo ao Azure AD Connect**, clique em **Concordo** e, em seguida, **Continuar**.</span><span class="sxs-lookup"><span data-stu-id="e960f-143">On the **Welcome to Azure AD Connect** page, click **I agree**, and then click **Continue**.</span></span>
    
6. <span data-ttu-id="e960f-144">Na página **Configurações Expressas**, clique em **Usar configurações expressas**.</span><span class="sxs-lookup"><span data-stu-id="e960f-144">On the **Express Settings** page, click **Use express settings**.</span></span>
    
7. <span data-ttu-id="e960f-145">Na página **Conectar-se ao Azure AD**, digite o nome da conta de administrador global do Office 365 em **Nome de usuário**, digite a sua senha em **Senha** e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="e960f-145">On the **Connect to Azure AD** page, type your Office 365 global administrator account name in **Username,** type its password in **Password**, and then click **Next**.</span></span>
    
8. <span data-ttu-id="e960f-146">Na página **Conectar-se ao AD DS**, digite **TestLab\\Usuário1** no campo **Nome de usuário**, digite a senha no campo **Senha** e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="e960f-146">On the **Connect to AD DS** page, type **TESTLAB\\User1** in **Username,** type its password in **Password**, and then click **Next**.</span></span>
    
9. <span data-ttu-id="e960f-147">Na página **Pronto para configurar**, clique em **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="e960f-147">On the **Ready to configure** page, click **Install**.</span></span>
    
10. <span data-ttu-id="e960f-148">Na página **Configuração concluída**, clique em **Sair**.</span><span class="sxs-lookup"><span data-stu-id="e960f-148">On the **Configuration complete** page, click **Exit**.</span></span>
    
11. <span data-ttu-id="e960f-149">No Internet Explorer, vá para o centro de administração do Microsoft 365 ([https://portal.microsoft.com](https://portal.microsoft.com)).</span><span class="sxs-lookup"><span data-stu-id="e960f-149">In Internet Explorer, go to the Microsoft 365 admin center ([https://portal.microsoft.com](https://portal.microsoft.com)).</span></span>
    
12. <span data-ttu-id="e960f-150">Na navegação à esquerda, clique em **Usuários > Usuários ativos**.</span><span class="sxs-lookup"><span data-stu-id="e960f-150">In the left navigation, click **Users > Active users**.</span></span>
    
    <span data-ttu-id="e960f-151">Observe a conta denominada **Usuario1**.</span><span class="sxs-lookup"><span data-stu-id="e960f-151">Note the account named **User1**.</span></span> <span data-ttu-id="e960f-152">Essa conta fica no domínio TESTLAB do AD DS e é uma prova de que a sincronização de diretórios funcionou.</span><span class="sxs-lookup"><span data-stu-id="e960f-152">This account is from the TESTLAB AD DS domain and is proof that directory synchronization has worked.</span></span>
    
13. <span data-ttu-id="e960f-p107">Clique na conta **Usuário1**. Para licenças de produto, clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="e960f-p107">Click the **User1** account. For product licenses, click **Edit**.</span></span>
    
14. <span data-ttu-id="e960f-p108">Em **Licenças de produto**, selecione o país/região e clique no controle **Desativado** da licença do **Office 365 Enterprise E5** (mudando-o para **Ativado**). Faça o mesmo procedimento para a licença do **Enterprise Mobility + Security E5**.</span><span class="sxs-lookup"><span data-stu-id="e960f-p108">In **Product licenses**, select your scountry, and then click the **Off** control for **Office 365 Enterprise E5** (switching it to **On**). Do the same for the **Enterprise Mobility + Security E5** license.</span></span> 

15. <span data-ttu-id="e960f-157">Clique em **Salvar**, no final da página, e clique em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="e960f-157">Click **Save** at the bottom of the page, and then click **Close**.</span></span>
    
<span data-ttu-id="e960f-158">Em seguida, teste a capacidade de entrar na assinatura do Office 365 com a conta <strong>usuario1@testlab.</strong>\<seu nome de domínio > nome de usuário da conta Usuário1.</span><span class="sxs-lookup"><span data-stu-id="e960f-158">Next, you test the ability to sign in to your Office 365 subscription with the <strong>user1@testlab.</strong>\<your domain name> user name of the User1 account.</span></span>

1. <span data-ttu-id="e960f-159">No APP1, encerre o Office 365 e entre novamente, mas desta vez especifique uma conta diferente.</span><span class="sxs-lookup"><span data-stu-id="e960f-159">From APP1, sign out of Office 365, and then sign in again, this time specifying a different account.</span></span>

2. <span data-ttu-id="e960f-p109">Quando solicitado a fornecer o nome de usuário e a senha, especifique <strong>usuario1@testlab.</strong>\<seu nome de domínio público> e a senha de Usuário1. Você deve entrar como Usuário1.</span><span class="sxs-lookup"><span data-stu-id="e960f-p109">When prompted for a user name and password, specify <strong>user1@testlab.</strong>\<your domain name> and the User1 password. You should successfully sign in as User1.</span></span> 
 
<span data-ttu-id="e960f-162">Observe que, embora o Usuario1 tenha permissões de administrador de domínio para o domínio TESTLAB do AD DS, ele não é um administrador global do Office 365.</span><span class="sxs-lookup"><span data-stu-id="e960f-162">Notice that although User1 has domain administrator permissions for the TESTLAB AD DS domain, it is not an Office 365 global administrator.</span></span> <span data-ttu-id="e960f-163">Portanto, o ícone **Administrador** não estará disponível como opção.</span><span class="sxs-lookup"><span data-stu-id="e960f-163">Therefore, you will not see the **Admin** icon as an option.</span></span> 

<span data-ttu-id="e960f-164">Esta é a configuração resultante.</span><span class="sxs-lookup"><span data-stu-id="e960f-164">Here is your resulting configuration.</span></span>

![Empresa simulada com ambiente de teste de sincronização de hash de senha](media/password-hash-sync-m365-ent-test-environment/Phase3.png)

<span data-ttu-id="e960f-166">Esta configuração consiste em:</span><span class="sxs-lookup"><span data-stu-id="e960f-166">This configuration consists of:</span></span> 
  
- <span data-ttu-id="e960f-167">Assinaturas pagas ou de avaliação do Office 365 E5 e EMS E5 com o domínio DNS TESTLAB.\<seu nome de domínio> registrado.</span><span class="sxs-lookup"><span data-stu-id="e960f-167">Office 365 E5 and EMS E5 trial or paid subscriptions with the DNS domain TESTLAB.\<your domain name> registered.</span></span>
- <span data-ttu-id="e960f-168">Uma intranet de organização simplificada conectado à Internet, que consiste em máquinas virtuais do DC1 APP1 e CLIENT1 em uma sub-rede de uma rede virtual do Azure.</span><span class="sxs-lookup"><span data-stu-id="e960f-168">A simplified organization intranet connected to the Internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span> <span data-ttu-id="e960f-169">O Azure AD Connect é executado periodicamente no APP1 para sincronizar o domínio TESTLAB do AD DS com o locatário do Azure AD de suas assinaturas do Office 365 e EMS E5.</span><span class="sxs-lookup"><span data-stu-id="e960f-169">Azure AD Connect runs on APP1 to synchronize the TESTLAB AD DS domain to the Azure AD tenant of your Office 365 and EMS E5 subscriptions periodically.</span></span>
- <span data-ttu-id="e960f-170">A conta Usuario1 no domínio TESTLAB do AD DS foi sincronizada com o locatário do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="e960f-170">The User1 account in the TESTLAB  AD DS domain has been synchronized with the Azure AD tenant.</span></span>

## <a name="next-step"></a><span data-ttu-id="e960f-171">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="e960f-171">Next step</span></span>

<span data-ttu-id="e960f-172">Explorar recursos e funcionalidades adicionais de [identidade](m365-enterprise-test-lab-guides.md#identity) no ambiente de teste.</span><span class="sxs-lookup"><span data-stu-id="e960f-172">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="e960f-173">Confira também</span><span class="sxs-lookup"><span data-stu-id="e960f-173">See also</span></span>

[<span data-ttu-id="e960f-174">Guias do Laboratório de Teste do Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="e960f-174">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="e960f-175">Implantar o Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="e960f-175">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="e960f-176">Documentação do Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="e960f-176">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)


