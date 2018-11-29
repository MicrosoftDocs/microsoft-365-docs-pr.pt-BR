---
title: Sincronização de hash de senha para ambiente de teste do Microsoft 365
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
description: 'Resumo: configurar e demonstrar a sincronização de hash de senha e a entrada para o ambiente de teste do Microsoft 365.'
ms.openlocfilehash: 3cee2b69ce34647627cb2b72f9e0f59a6fba17e9
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/28/2018
ms.locfileid: "26865253"
---
# <a name="password-hash-synchronization-for-your-microsoft-365-test-environment"></a><span data-ttu-id="bda1a-103">Sincronização de hash de senha para ambiente de teste do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="bda1a-103">Password hash synchronization for your Microsoft 365 test environment</span></span>

<span data-ttu-id="bda1a-p101">Muitas organizações usam o Azure AD Connect e a sincronização de hash de senha para sincronizar o conjunto de contas na floresta local do Windows Server Active Directory (AD) com o conjunto de contas no locatário do Azure AD, nas assinaturas do Office 365 e do EMS E5. Este artigo descreve como adicionar a sincronização de hash de senha ao ambiente de teste do Microsoft 365, resultando na seguinte configuração:</span><span class="sxs-lookup"><span data-stu-id="bda1a-p101">Many organizations use Azure AD Connect and password hash synchronization to synchronize the set of accounts in their on-premises Windows Server Active Directory (AD) forest to the set of accounts in the Azure AD tenant of their Office 365 and EMS E5 subscriptions. This article describes how you can add password hash synchronization to your Microsoft 365 test environment, resulting in the following configuration:</span></span>
  
![Empresa simulada com ambiente de teste de sincronização de hash de senha](media/password-hash-sync-m365-ent-test-environment/Phase3.png)
  
<span data-ttu-id="bda1a-107">Há duas fases para configurar esse ambiente de teste:</span><span class="sxs-lookup"><span data-stu-id="bda1a-107">There are two phases to setting up this test environment:</span></span>
  
1. <span data-ttu-id="bda1a-108">Crie o ambiente de teste corporativo simulado do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="bda1a-108">Create the Microsoft 365 simulated enterprise test environment.</span></span>
2. <span data-ttu-id="bda1a-109">Instale e configure o Azure AD Connect na APP1.</span><span class="sxs-lookup"><span data-stu-id="bda1a-109">Install and configure Azure AD Connect on APP1.</span></span>
    
> [!TIP]
> <span data-ttu-id="bda1a-110">Clique [aqui](https://aka.ms/m365etlgstack) para ver um mapa visual de todos os artigos da pilha do Guia de Laboratório de Teste do Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="bda1a-110">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-create-the-microsoft-365-simulated-enterprise-test-environment"></a><span data-ttu-id="bda1a-111">Fase 1 – Criar o ambiente de teste corporativo simulado do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="bda1a-111">Phase 1: Create the Microsoft 365 simulated enterprise test environment</span></span>

<span data-ttu-id="bda1a-p102">Siga as instruções da [configuração base corporativa simulada do Microsoft 365](simulated-ent-base-configuration-microsoft-365-enterprise.md). Aqui está a configuração resultante.</span><span class="sxs-lookup"><span data-stu-id="bda1a-p102">Follow the instructions in [simulated enterprise base configuration for Microsoft 365](simulated-ent-base-configuration-microsoft-365-enterprise.md). Here is your resulting configuration.</span></span>
  
![A configuração base corporativa simulada](media/password-hash-sync-m365-ent-test-environment/Phase1.png)
  
<span data-ttu-id="bda1a-115">Esta configuração consiste em:</span><span class="sxs-lookup"><span data-stu-id="bda1a-115">This configuration consists of:</span></span> 
  
- <span data-ttu-id="bda1a-116">Assinaturas permanentes ou de avaliação do Office 365 E5 e EMS E5.</span><span class="sxs-lookup"><span data-stu-id="bda1a-116">Office 365 E5 and EMS E5 trial or permanent subscriptions.</span></span>
- <span data-ttu-id="bda1a-p103">Uma intranet de organização simplificada conectada à Internet, composta pelas máquinas virtuais DC1, APP1 e CLIENT1, em uma Rede Virtual do Microsoft Azure. O DC1 é um controlador de domínio do domínio testlab.\<nome de domínio público> do Windows Server Active Directory.</span><span class="sxs-lookup"><span data-stu-id="bda1a-p103">A simplified organization intranet connected to the Internet, consisting of the DC1, APP1, and CLIENT1 virtual machines in an Azure virtual network. DC1 is a domain controller for the testlab.\<your public domain name> Windows Server AD domain.</span></span>

## <a name="phase-2-create-and-register-the-testlab-domain"></a><span data-ttu-id="bda1a-119">Fase 2 – Criar e registrar o domínio testlab</span><span class="sxs-lookup"><span data-stu-id="bda1a-119">Phase 2: Create and register the testlab domain</span></span>

<span data-ttu-id="bda1a-120">Nesta fase, você adiciona um domínio DNS público e o adiciona-o à assinatura.</span><span class="sxs-lookup"><span data-stu-id="bda1a-120">In this phase you add a public DNS domain and add it to your subscription.</span></span>

<span data-ttu-id="bda1a-p104">Primeiro, trabalhe com um provedor de registro DNS público para criar um nome de domínio DNS público com base em um nome de domínio atual e adicioná-lo à assinatura do Office 365. Recomendamos usar o nome **testlab.**\<domínio público>. Por exemplo, se o nome de domínio público for <span>**contoso</span>.com**, adicione o nome de domínio público **<span>testlab</span>.contoso.com**.</span><span class="sxs-lookup"><span data-stu-id="bda1a-p104">First, work with your public DNS registration provider to create a new public DNS domain name based on your current domain name and add it to your Office 365 subscription. We recommend using the name **testlab.**\<your public domain>. For example, if your public domain name is <span>**contoso</span>.com**, add the public domain name **<span>testlab</span>.contoso.com**.</span></span>
  
<span data-ttu-id="bda1a-p105">Em seguida, adicione o domínio **testlab.**\<domínio público> à assinatura permanente ou de avaliação do Office 365, passando pelo processo de registro de domínio. Isso consiste em adicionar outros registros DNS ao domínio **testlab.**\<domínio público>. Para saber mais, confira o artigo [Adicionar um domínio e usuários ao Office 365](https://support.office.com/article/Add-users-and-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).</span><span class="sxs-lookup"><span data-stu-id="bda1a-p105">Next, you add the **testlab.**\<your public domain> domain to your Office 365 trial or permanent subscription by going through the domain registration process. This consists of adding additional DNS records to the **testlab.**\<your public domain> domain. For more information, see [Add users and domain to Office 365](https://support.office.com/article/Add-users-and-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).</span></span> 

<span data-ttu-id="bda1a-127">Esta é a configuração resultante.</span><span class="sxs-lookup"><span data-stu-id="bda1a-127">Here is your resulting configuration.</span></span>
  
![O registro do seu nome de domínio testlab](media/password-hash-sync-m365-ent-test-environment/Phase2.png)
  
<span data-ttu-id="bda1a-129">Esta configuração consiste em:</span><span class="sxs-lookup"><span data-stu-id="bda1a-129">This configuration consists of:</span></span>

- <span data-ttu-id="bda1a-130">Assinaturas permanentes ou de avaliação do Office 365 E5 e EMS E5 com o domínio DNS TestLab.\<seu nome de domínio> registrado.</span><span class="sxs-lookup"><span data-stu-id="bda1a-130">Office 365 E5 and EMS E5 trial or permanent subscriptions with the DNS domain testlab.\<your public domain name> registered.</span></span>
- <span data-ttu-id="bda1a-131">Uma intranet de organização simplificada conectado à Internet, que consiste em máquinas virtuais DC1 APP1 e CLIENT1 em uma sub-rede de uma rede virtual do Azure.</span><span class="sxs-lookup"><span data-stu-id="bda1a-131">A simplified organization intranet connected to the Internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span>

<span data-ttu-id="bda1a-132">Veja como o testlab.\<seu nome de domínio público> está agora:</span><span class="sxs-lookup"><span data-stu-id="bda1a-132">Notice how the testlab.\<your public domain name> is now:</span></span>

- <span data-ttu-id="bda1a-133">Compatível com registros DNS públicos.</span><span class="sxs-lookup"><span data-stu-id="bda1a-133">Supported by public DNS records.</span></span>
- <span data-ttu-id="bda1a-134">Registrado nas assinaturas do Office 365 e do EMS.</span><span class="sxs-lookup"><span data-stu-id="bda1a-134">Registered in your Office 365 and EMS subscriptions.</span></span>
- <span data-ttu-id="bda1a-135">O domínio do Windows Server Active Directory na intranet simulada.</span><span class="sxs-lookup"><span data-stu-id="bda1a-135">The Windows Server AD domain on your simulated intranet.</span></span>
     
## <a name="phase-3-install-azure-ad-connect-on-app1"></a><span data-ttu-id="bda1a-136">Fase 3 – Instalar o Azure AD Connect na APP1</span><span class="sxs-lookup"><span data-stu-id="bda1a-136">Phase 3: Install Azure AD Connect on APP1</span></span>

<span data-ttu-id="bda1a-137">Nesta fase, instale e configure a ferramenta Azure AD Connect na APP1 e verifique se ela funciona.</span><span class="sxs-lookup"><span data-stu-id="bda1a-137">In this phase, you install and configure the Azure AD Connect tool on APP1, and then verify that it works.</span></span>
  
<span data-ttu-id="bda1a-138">Primeiro, instale e configure o Azure AD Connect na APP1.</span><span class="sxs-lookup"><span data-stu-id="bda1a-138">First, you install and configure Azure AD Connect on APP1.</span></span>

1. <span data-ttu-id="bda1a-139">No [Portal do Azure](https://portal.azure.com), entre com a conta de administrador global e conecte-se à APP1 com a conta \\Usuário1 do TestLab.</span><span class="sxs-lookup"><span data-stu-id="bda1a-139">From the [Azure portal](https://portal.azure.com), sign in with your global administrator account, and then connect to APP1 with the TESTLAB\\User1 account.</span></span>
    
2. <span data-ttu-id="bda1a-140">Na área de trabalho da APP1, abra um prompt de comando do nível de administrador do Windows PowerShell e execute estes comandos:</span><span class="sxs-lookup"><span data-stu-id="bda1a-140">From the desktop of APP1, open an administrator-level Windows PowerShell command prompt, and then run these commands:</span></span>
    
   ```
   Set-ItemProperty -Path "HKLM:\SOFTWARE\Microsoft\Active Setup\Installed Components\{A509B1A7-37EF-4b3f-8CFC-4F3A74704073}" -Name "IsInstalled" -Value 0
   Set-ItemProperty -Path "HKLM:\SOFTWARE\Microsoft\Active Setup\Installed Components\{A509B1A8-37EF-4b3f-8CFC-4F3A74704073}" -Name "IsInstalled" -Value 0
   Stop-Process -Name Explorer -Force
   ```

3. <span data-ttu-id="bda1a-141">Na barra de tarefas, clique em **Internet Explorer** e acesse [https://aka.ms/aadconnect](https://aka.ms/aadconnect).</span><span class="sxs-lookup"><span data-stu-id="bda1a-141">From the task bar, click **Internet Explorer** and go to [https://aka.ms/aadconnect](https://aka.ms/aadconnect).</span></span>
    
4. <span data-ttu-id="bda1a-142">Na página do Microsoft Azure Active Directory Connect, clique em **Baixar** e, em seguida, clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="bda1a-142">On the Microsoft Azure Active Directory Connect page, click **Download**, and then click **Run**.</span></span>
    
5. <span data-ttu-id="bda1a-143">Na página **Bem-vindo ao Azure AD Connect**, clique em **Concordo** e, em seguida, **Continuar**.</span><span class="sxs-lookup"><span data-stu-id="bda1a-143">On the **Welcome to Azure AD Connect** page, click **I agree**, and then click **Continue**.</span></span>
    
6. <span data-ttu-id="bda1a-144">Na página **Configurações Expressas**, clique em **Usar configurações expressas**.</span><span class="sxs-lookup"><span data-stu-id="bda1a-144">On the **Express Settings** page, click **Use express settings**.</span></span>
    
7. <span data-ttu-id="bda1a-145">Na página **Conectar-se ao Azure AD**, digite o nome da conta de administrador global do Office 365 em **Nome de usuário**, digite a sua senha em **Senha** e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="bda1a-145">On the **Connect to Azure AD** page, type your Office 365 global administrator account name in **Username,** type its password in **Password**, and then click **Next**.</span></span>
    
8. <span data-ttu-id="bda1a-146">Na página **Conectar-se ao AD DS**, digite **TestLab\\Usuário1** no campo **Nome de usuário**, digite a senha no campo **Senha** e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="bda1a-146">On the **Connect to AD DS** page, type **TESTLAB\\User1** in **Username,** type its password in **Password**, and then click **Next**.</span></span>
    
9. <span data-ttu-id="bda1a-147">Na página **Pronto para configurar**, clique em **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="bda1a-147">On the **Ready to configure** page, click **Install**.</span></span>
    
10. <span data-ttu-id="bda1a-148">Na página **Configuração concluída**, clique em **Sair**.</span><span class="sxs-lookup"><span data-stu-id="bda1a-148">On the **Configuration complete** page, click **Exit**.</span></span>
    
11. <span data-ttu-id="bda1a-149">No Internet Explorer, vá para o portal do Office 365 ([https://portal.office.com](https://portal.office.com)).</span><span class="sxs-lookup"><span data-stu-id="bda1a-149">In Internet Explorer, go to the Office 365 portal ([https://portal.office.com](https://portal.office.com)).</span></span>
    
12. <span data-ttu-id="bda1a-150">Na página principal do portal, clique em **Admin**.</span><span class="sxs-lookup"><span data-stu-id="bda1a-150">From the main portal page, click **Admin**.</span></span>
    
13. <span data-ttu-id="bda1a-151">Na navegação à esquerda, clique em **Usuários > Usuários ativos**.</span><span class="sxs-lookup"><span data-stu-id="bda1a-151">In the left navigation, click **Users > Active users**.</span></span>
    
    <span data-ttu-id="bda1a-p106">Observe a conta denominada **Usuário1**. Essa conta fica no domínio TestLab do Windows Server Active Directory e é prova de que a sincronização de diretórios funcionou.</span><span class="sxs-lookup"><span data-stu-id="bda1a-p106">Note the account named **User1**. This account is from the TESTLAB Windows Server AD domain and is proof that directory synchronization has worked.</span></span>
    
14. <span data-ttu-id="bda1a-p107">Clique na conta **Usuário1**. Para licenças de produto, clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="bda1a-p107">Click the **User1** account. For product licenses, click **Edit**.</span></span>
    
15. <span data-ttu-id="bda1a-p108">Em **Licenças de produto**, selecione o país/região e clique no controle **Desativado** da licença do **Office 365 Enterprise E5** (mudando-o para **Ativado**). Faça o mesmo procedimento para a licença do **Enterprise Mobility + Security E5**.</span><span class="sxs-lookup"><span data-stu-id="bda1a-p108">In **Product licenses**, select your scountry, and then click the **Off** control for **Office 365 Enterprise E5** (switching it to **On**). Do the same for the **Enterprise Mobility + Security E5** license.</span></span> 

16. <span data-ttu-id="bda1a-158">Clique em **Salvar**, no final da página, e clique em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="bda1a-158">Click **Save** at the bottom of the page, and then click **Close**.</span></span>
    
<span data-ttu-id="bda1a-159">Em seguida, teste a capacidade de entrar na assinatura do Office 365 com a conta <strong>usuario1@testlab.</strong>\<seu nome de domínio > nome de usuário da conta Usuário1.</span><span class="sxs-lookup"><span data-stu-id="bda1a-159">Next, you test the ability to sign in to your Office 365 subscription with the <strong>user1@testlab.</strong>\<your domain name> user name of the User1 account.</span></span>

1. <span data-ttu-id="bda1a-160">No APP1, encerre o Office 365 e entre novamente, mas desta vez especifique uma conta diferente.</span><span class="sxs-lookup"><span data-stu-id="bda1a-160">From APP1, sign out of Office 365, and then sign in again, this time specifying a different account.</span></span>

2. <span data-ttu-id="bda1a-p109">Quando solicitado a fornecer o nome de usuário e a senha, especifique <strong>usuario1@testlab.</strong>\<seu nome de domínio público> e a senha de Usuário1. Você deve entrar como Usuário1.</span><span class="sxs-lookup"><span data-stu-id="bda1a-p109">When prompted for a user name and password, specify <strong>user1@testlab.</strong>\<your domain name> and the User1 password. You should successfully sign in as User1.</span></span> 
 
<span data-ttu-id="bda1a-p110">Embora o Usuário1 tenha permissões de administrador de domínio para o domínio do Windows Server Active Directory do TestLab, ele não é um administrador global do Office 365. Portanto, o ícone **Administrador** não estará disponível como opção.</span><span class="sxs-lookup"><span data-stu-id="bda1a-p110">Notice that although User1 has domain administrator permissions for the TESTLAB Windows Server AD domain, it is not an Office 365 global administrator. Therefore, you will not see the **Admin** icon as an option.</span></span> 

<span data-ttu-id="bda1a-165">Esta é a configuração resultante.</span><span class="sxs-lookup"><span data-stu-id="bda1a-165">Here is your resulting configuration.</span></span>

![Empresa simulada com ambiente de teste de sincronização de hash de senha](media/password-hash-sync-m365-ent-test-environment/Phase3.png)

<span data-ttu-id="bda1a-167">Esta configuração consiste em:</span><span class="sxs-lookup"><span data-stu-id="bda1a-167">This configuration consists of:</span></span> 
  
- <span data-ttu-id="bda1a-168">Assinaturas permanentes ou de avaliação do Office 365 E5 e EMS E5 com o domínio DNS TestLab.\<seu nome de domínio> registrado.</span><span class="sxs-lookup"><span data-stu-id="bda1a-168">Office 365 E5 and EMS E5 trial or permanent subscriptions with the DNS domain TESTLAB.\<your domain name> registered.</span></span>
- <span data-ttu-id="bda1a-p111">Uma intranet de organização simplificada conectada à Internet, composta pelas máquinas virtuais DC1, APP1 e CLIENT1, em uma sub-rede de uma Rede Virtual do Microsoft Azure. O Azure AD Connect Health é executado na APP1 para sincronizar periodicamente o domínio do Dev/Test Lab do Windows Server Active Directory com o locatário do Microsoft Azure AD, nas assinaturas do Office 365 e do EMS E5.</span><span class="sxs-lookup"><span data-stu-id="bda1a-p111">A simplified organization intranet connected to the Internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network. Azure AD Connect runs on APP1 to synchronize the TESTLAB Windows Server AD domain to the Azure AD tenant of your Office 365 and EMS E5 subscriptions periodically.</span></span>
- <span data-ttu-id="bda1a-171">A conta Usuário1 no domínio TESTLAB do Windows Server AD foi sincronizada com o locatário do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="bda1a-171">The User1 account in the TESTLAB  Windows Server AD domain has been synchronized with the Azure AD tenant.</span></span>

## <a name="next-step"></a><span data-ttu-id="bda1a-172">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="bda1a-172">Next step</span></span>

<span data-ttu-id="bda1a-173">Explorar recursos e funcionalidades adicionais de [identidade](m365-enterprise-test-lab-guides.md#identity) no ambiente de teste.</span><span class="sxs-lookup"><span data-stu-id="bda1a-173">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="bda1a-174">Confira também</span><span class="sxs-lookup"><span data-stu-id="bda1a-174">See also</span></span>

[<span data-ttu-id="bda1a-175">Guias do Laboratório de Teste do Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="bda1a-175">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="bda1a-176">Implantar o Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="bda1a-176">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="bda1a-177">Documentação do Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="bda1a-177">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)


