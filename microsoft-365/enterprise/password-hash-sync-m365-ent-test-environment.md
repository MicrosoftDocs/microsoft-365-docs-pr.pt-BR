---
title: Sincronização de hash de senha para ambiente de teste do Microsoft 365
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 05/26/2020
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
- seo-marvel-apr2020
ms.assetid: ''
description: 'Resumo: configurar e demonstrar a sincronização de hash de senha e a entrada para o ambiente de teste do Microsoft 365.'
ms.openlocfilehash: 3c20d1997be2ff47f0b449cbba3afb1e6edcd59a
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487453"
---
# <a name="password-hash-synchronization-for-your-microsoft-365-test-environment"></a><span data-ttu-id="48d11-103">Sincronização de hash de senha para ambiente de teste do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="48d11-103">Password hash synchronization for your Microsoft 365 test environment</span></span>

<span data-ttu-id="48d11-104">*Este Guia de Laboratório de Teste pode ser usado para ambientes de teste do Microsoft 365 para empresas e do Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="48d11-104">*This Test Lab Guide can be used for both Microsoft 365 for enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="48d11-105">Muitas organizações usam o Azure AD Connect e a sincronização de hash de senha para sincronizar o conjunto de contas na floresta local dos Serviços de domínio Active Directory (AD DS) local com o conjunto de contas no locatário do Azure AD da assinatura do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="48d11-105">Many organizations use Azure AD Connect and password hash synchronization to synchronize the set of accounts in their on-premises Active Directory Domain Services (AD DS) forest to the set of accounts in the Azure AD tenant of their Microsoft 365 subscription.</span></span> 

<span data-ttu-id="48d11-106">Este artigo descreve como você pode adicionar a sincronização de hash de senha ao seu ambiente de teste do Microsoft 365, o que resulta nesta configuração:</span><span class="sxs-lookup"><span data-stu-id="48d11-106">This article describes how you can add password hash synchronization to your Microsoft 365 test environment, which results in this configuration:</span></span>
  
![Empresa simulada com ambiente de teste de sincronização de hash de senha](../media/password-hash-sync-m365-ent-test-environment/Phase3.png)
  
<span data-ttu-id="48d11-108">A configuração desse ambiente de teste envolve três fases:</span><span class="sxs-lookup"><span data-stu-id="48d11-108">Setting up this test environment involves three phases:</span></span>
- [<span data-ttu-id="48d11-109">Fase 1 – Criar o ambiente de teste corporativo simulado do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="48d11-109">Phase 1: Create the Microsoft 365 simulated enterprise test environment</span></span>](#phase-1-create-the-microsoft-365-simulated-enterprise-test-environment)
- [<span data-ttu-id="48d11-110">Fase 2 – Criar e registrar o domínio testlab</span><span class="sxs-lookup"><span data-stu-id="48d11-110">Phase 2: Create and register the testlab domain</span></span>](#phase-2-create-and-register-the-testlab-domain)
- [<span data-ttu-id="48d11-111">Fase 3 – Instalar o Azure AD Connect na APP1</span><span class="sxs-lookup"><span data-stu-id="48d11-111">Phase 3: Install Azure AD Connect on APP1</span></span>](#phase-3-install-azure-ad-connect-on-app1)
    
> [!TIP]
> <span data-ttu-id="48d11-112">Para ver um mapa visual de todos os artigos da pilha do Guia de Laboratório de Teste do Microsoft 365 para empresas, vá para a Pilha de Guias de Laboratório de Teste do [Microsoft 365](../downloads/Microsoft365EnterpriseTLGStack.pdf)para empresas.</span><span class="sxs-lookup"><span data-stu-id="48d11-112">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>
  
## <a name="phase-1-create-the-microsoft-365-simulated-enterprise-test-environment"></a><span data-ttu-id="48d11-113">Fase 1 – Criar o ambiente de teste corporativo simulado do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="48d11-113">Phase 1: Create the Microsoft 365 simulated enterprise test environment</span></span>

<span data-ttu-id="48d11-114">Siga as instruções na [configuração base corporativa simulada do Microsoft 365.](simulated-ent-base-configuration-microsoft-365-enterprise.md)</span><span class="sxs-lookup"><span data-stu-id="48d11-114">Follow the instructions in [simulated enterprise base configuration for Microsoft 365](simulated-ent-base-configuration-microsoft-365-enterprise.md).</span></span> <span data-ttu-id="48d11-115">A configuração resultante tem esta aparência:</span><span class="sxs-lookup"><span data-stu-id="48d11-115">Your resulting configuration looks like this:</span></span>
  
![A configuração base corporativa simulada](../media/password-hash-sync-m365-ent-test-environment/Phase1.png)
  
<span data-ttu-id="48d11-117">Esta configuração consiste em:</span><span class="sxs-lookup"><span data-stu-id="48d11-117">This configuration consists of:</span></span>
  
- <span data-ttu-id="48d11-118">Uma assinatura de avaliação ou assinatura paga do Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="48d11-118">A Microsoft 365 E5 trial or paid subscription.</span></span>
- <span data-ttu-id="48d11-119">Uma intranet de organização simplificada conectada à Internet, que consiste nas máquinas virtuais DC1, APP1 e CLIENT1 em uma rede virtual do Azure.</span><span class="sxs-lookup"><span data-stu-id="48d11-119">A simplified organization intranet connected to the internet, consisting of the DC1, APP1, and CLIENT1 virtual machines in an Azure virtual network.</span></span> <span data-ttu-id="48d11-120">DC1 é um controlador de domínio para testlab.<*seu nome* de domínio público> domínio do AD DS.</span><span class="sxs-lookup"><span data-stu-id="48d11-120">DC1 is a domain controller for the testlab.<*your public domain name*> AD DS domain.</span></span>

## <a name="phase-2-create-and-register-the-testlab-domain"></a><span data-ttu-id="48d11-121">Fase 2 – Criar e registrar o domínio testlab</span><span class="sxs-lookup"><span data-stu-id="48d11-121">Phase 2: Create and register the testlab domain</span></span>

<span data-ttu-id="48d11-122">Nesta fase, adicione um domínio DNS público e adicione-o à sua assinatura.</span><span class="sxs-lookup"><span data-stu-id="48d11-122">In this phase, add a public DNS domain, and then add it to your subscription.</span></span>

<span data-ttu-id="48d11-123">Primeiro, trabalhe com seu provedor de registro DNS público para criar um novo nome de domínio DNS público baseado no seu nome de domínio atual e, em seguida, adicione-o à sua assinatura.</span><span class="sxs-lookup"><span data-stu-id="48d11-123">First, work with your public DNS registration provider to create a new public DNS domain name that's based on your current domain name, and then add it to your subscription.</span></span> <span data-ttu-id="48d11-124">Recomendamos usar o nome **testlab.<*seu domínio público.\* >*\*</span><span class="sxs-lookup"><span data-stu-id="48d11-124">We recommend using the name **testlab.<*your public domain*>**.</span></span> <span data-ttu-id="48d11-125">Por exemplo, se seu nome de domínio público for **<span>contoso</span>.com,** adicione o nome de domínio público: **<span>testlab</span>.contoso.com**.</span><span class="sxs-lookup"><span data-stu-id="48d11-125">For example, if your public domain name is **<span>contoso</span>.com**, add the public domain name: **<span>testlab</span>.contoso.com**.</span></span>
  
<span data-ttu-id="48d11-126">Em seguida, adicione **o  > testlab.<** seu domínio público à sua assinatura paga ou de avaliação do Microsoft 365, passando pelo processo de registro de domínio.</span><span class="sxs-lookup"><span data-stu-id="48d11-126">Next, add the **testlab.<*your public domain*>** domain to your Microsoft 365 trial or paid subscription by going through the domain registration process.</span></span> <span data-ttu-id="48d11-127">Isso consiste em adicionar registros DNS adicionais ao **testlab.<*seu domínio\* >*\* público.</span><span class="sxs-lookup"><span data-stu-id="48d11-127">This consists of adding additional DNS records to the **testlab.<*your public domain*>** domain.</span></span> <span data-ttu-id="48d11-128">Para saber mais, confira [Adicionar um domínio ao Microsoft 365.](../admin/setup/add-domain.md)</span><span class="sxs-lookup"><span data-stu-id="48d11-128">For more information, see [Add a domain to Microsoft 365](../admin/setup/add-domain.md).</span></span>

<span data-ttu-id="48d11-129">A configuração resultante tem esta aparência:</span><span class="sxs-lookup"><span data-stu-id="48d11-129">Your resulting configuration looks like this:</span></span>
  
![O registro do seu nome de domínio testlab](../media/password-hash-sync-m365-ent-test-environment/Phase2.png)
  
<span data-ttu-id="48d11-131">Esta configuração consiste em:</span><span class="sxs-lookup"><span data-stu-id="48d11-131">This configuration consists of:</span></span>

- <span data-ttu-id="48d11-132">Uma assinatura paga ou de avaliação do Microsoft 365 E5 com o domínio DNS testlab.<seu nome de domínio *público*> registrado.</span><span class="sxs-lookup"><span data-stu-id="48d11-132">A Microsoft 365 E5 trial or paid subscription with the DNS domain testlab.<*your public domain name*> registered.</span></span>
- <span data-ttu-id="48d11-133">Uma intranet de organização simplificada conectada à Internet, que consiste nas máquinas virtuais DC1, APP1 e CLIENT1 em uma sub-rede de uma rede virtual do Azure.</span><span class="sxs-lookup"><span data-stu-id="48d11-133">A simplified organization intranet connected to the internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span>

<span data-ttu-id="48d11-134">Observe como o testlab.<*seu nome* de domínio público> agora:</span><span class="sxs-lookup"><span data-stu-id="48d11-134">Notice how the testlab.<*your public domain name*> is now:</span></span>

- <span data-ttu-id="48d11-135">Compatível com registros DNS públicos.</span><span class="sxs-lookup"><span data-stu-id="48d11-135">Supported by public DNS records.</span></span>
- <span data-ttu-id="48d11-136">Registrado nas assinaturas do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="48d11-136">Registered in your Microsoft 365 subscriptions.</span></span>
- <span data-ttu-id="48d11-137">O domínio AD DS na sua intranet simulada.</span><span class="sxs-lookup"><span data-stu-id="48d11-137">The AD DS domain on your simulated intranet.</span></span>
     
## <a name="phase-3-install-azure-ad-connect-on-app1"></a><span data-ttu-id="48d11-138">Fase 3 – Instalar o Azure AD Connect na APP1</span><span class="sxs-lookup"><span data-stu-id="48d11-138">Phase 3: Install Azure AD Connect on APP1</span></span>

<span data-ttu-id="48d11-139">Nesta fase, instale e configure a ferramenta Azure AD Connect no APP1 e verifique se ela funciona.</span><span class="sxs-lookup"><span data-stu-id="48d11-139">In this phase, install and configure the Azure AD Connect tool on APP1, and then verify that it works.</span></span>
  
<span data-ttu-id="48d11-140">Primeiro, instale e configure o Azure AD Connect no APP1.</span><span class="sxs-lookup"><span data-stu-id="48d11-140">First, install and configure Azure AD Connect on APP1.</span></span>

1. <span data-ttu-id="48d11-141">No [Portal do Azure](https://portal.azure.com), entre com a conta de administrador global e conecte-se à APP1 com a conta \\Usuário1 do TestLab.</span><span class="sxs-lookup"><span data-stu-id="48d11-141">From the [Azure portal](https://portal.azure.com), sign in with your global administrator account, and then connect to APP1 with the TESTLAB\\User1 account.</span></span>
    
2. <span data-ttu-id="48d11-142">Na área de trabalho da APP1, abra um prompt de comando do Windows PowerShell em nível de administrador e execute esses comandos para desativar a Segurança avançada do Internet Explorer:</span><span class="sxs-lookup"><span data-stu-id="48d11-142">From the desktop of APP1, open an administrator-level Windows PowerShell command prompt, and then run these commands to disable Internet Explorer Enhanced Security:</span></span>
    
   ```powershell
   Set-ItemProperty -Path "HKLM:\SOFTWARE\Microsoft\Active Setup\Installed Components\{A509B1A7-37EF-4b3f-8CFC-4F3A74704073}" -Name "IsInstalled" -Value 0
   Set-ItemProperty -Path "HKLM:\SOFTWARE\Microsoft\Active Setup\Installed Components\{A509B1A8-37EF-4b3f-8CFC-4F3A74704073}" -Name "IsInstalled" -Value 0
   Stop-Process -Name Explorer -Force
   ```

3. <span data-ttu-id="48d11-143">Na barra de tarefas, selecione **Internet Explorer** e vá para [https://aka.ms/aadconnect](https://aka.ms/aadconnect) .</span><span class="sxs-lookup"><span data-stu-id="48d11-143">From the taskbar, select **Internet Explorer** and go to [https://aka.ms/aadconnect](https://aka.ms/aadconnect).</span></span>
    
4. <span data-ttu-id="48d11-144">Na página do Microsoft Azure Active Directory Connect, selecione **Baixar** e **Executar.**</span><span class="sxs-lookup"><span data-stu-id="48d11-144">On the Microsoft Azure Active Directory Connect page, select **Download**, and then select **Run**.</span></span>
    
5. <span data-ttu-id="48d11-145">On the **Welcome to Azure AD Connect** page, select I **agree**, and then select **Continue**.</span><span class="sxs-lookup"><span data-stu-id="48d11-145">On the **Welcome to Azure AD Connect** page, select **I agree**, and then select **Continue**.</span></span>
    
6. <span data-ttu-id="48d11-146">Na página **Configurações Expressas,** selecione **Usar configurações expressas.**</span><span class="sxs-lookup"><span data-stu-id="48d11-146">On the **Express Settings** page, select **Use express settings**.</span></span>
    
7. <span data-ttu-id="48d11-147">Na página **Conectar-se ao Azure AD,** insira o nome da sua conta de administrador global em Nome de **Usuário,** insira sua senha em **Senha** e selecione **Próximo.**</span><span class="sxs-lookup"><span data-stu-id="48d11-147">On the **Connect to Azure AD** page, enter your global administrator account name in **Username,** enter its password in **Password**, and then select **Next**.</span></span>
    
8. <span data-ttu-id="48d11-148">Na página **Conectar-se ao AD DS,** insira **TestLab \\ User1** em **Username,** insira sua senha em **Password** e selecione **Next**.</span><span class="sxs-lookup"><span data-stu-id="48d11-148">On the **Connect to AD DS** page, enter **TESTLAB\\User1** in **Username,** enter its password in **Password**, and then select **Next**.</span></span>
    
9. <span data-ttu-id="48d11-149">Na página **Pronto para configurar,** selecione **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="48d11-149">On the **Ready to configure** page, select **Install**.</span></span>
    
10. <span data-ttu-id="48d11-150">Na página **Configuração completa,** selecione **Sair**.</span><span class="sxs-lookup"><span data-stu-id="48d11-150">On the **Configuration complete** page, select **Exit**.</span></span>
    
11. <span data-ttu-id="48d11-151">No Internet Explorer, vá para o centro de administração do Microsoft 365 ([https://portal.microsoft.com](https://portal.microsoft.com)).</span><span class="sxs-lookup"><span data-stu-id="48d11-151">In Internet Explorer, go to the Microsoft 365 admin center ([https://portal.microsoft.com](https://portal.microsoft.com)).</span></span>
    
12. <span data-ttu-id="48d11-152">No painel de navegação esquerdo, selecione **Usuários > Usuários ativos.**</span><span class="sxs-lookup"><span data-stu-id="48d11-152">In the left navigation pane, select **Users > Active users**.</span></span>
    
    <span data-ttu-id="48d11-153">Observe a conta denominada **Usuario1**.</span><span class="sxs-lookup"><span data-stu-id="48d11-153">Note the account named **User1**.</span></span> <span data-ttu-id="48d11-154">Essa conta fica no domínio TESTLAB do AD DS e é uma prova de que a sincronização de diretórios funcionou.</span><span class="sxs-lookup"><span data-stu-id="48d11-154">This account is from the TESTLAB AD DS domain and is proof that directory synchronization has worked.</span></span>
    
13. <span data-ttu-id="48d11-155">Selecione a **conta Usuário1** e, em seguida, selecione **Licenças e aplicativos.**</span><span class="sxs-lookup"><span data-stu-id="48d11-155">Select the **User1** account, and then select **Licenses and apps**.</span></span>
    
14. <span data-ttu-id="48d11-156">Em **licenças de produto,** selecione seu local (se necessário), desabilite a licença do **Office 365 E5** e habilita a licença do **Microsoft 365 E5.**</span><span class="sxs-lookup"><span data-stu-id="48d11-156">In **Product licenses**, select your location (if needed), disable the **Office 365 E5** license, and then enable the **Microsoft 365 E5** license.</span></span> 

15. <span data-ttu-id="48d11-157">Selecione **Salvar** na parte inferior da página e, em seguida, clique em **Fechar.**</span><span class="sxs-lookup"><span data-stu-id="48d11-157">Select **Save** at the bottom of the page, and then select **Close**.</span></span>
    
<span data-ttu-id="48d11-158">Em seguida, teste a capacidade de entrar em sua assinatura com o **user1@testlab.< >** nome de domínio da conta Usuário1:</span><span class="sxs-lookup"><span data-stu-id="48d11-158">Next, test the ability to sign in to your subscription with the **user1@testlab.<*your domain name*>** user name of the User1 account:</span></span>

1. <span data-ttu-id="48d11-159">Na APP1, saia e entre novamente, mas desta vez especifique uma conta diferente.</span><span class="sxs-lookup"><span data-stu-id="48d11-159">From APP1, sign out, and then sign in again, this time specifying a different account.</span></span>

2. <span data-ttu-id="48d11-160">Quando solicitado a indicar um nome de usuário e uma senha, **especifique user1@testlab.< >** seu nome de domínio e a senha de Usuário1.</span><span class="sxs-lookup"><span data-stu-id="48d11-160">When prompted for a user name and password, specify **user1@testlab.<*your domain name*>** and the User1 password.</span></span> <span data-ttu-id="48d11-161">Você deve conseguir entrar como Usuario1.</span><span class="sxs-lookup"><span data-stu-id="48d11-161">You should successfully sign in as User1.</span></span>
 
<span data-ttu-id="48d11-162">Observe que, embora o Usuário1 tenha permissões de administrador de domínio para o domínio TESTLAB do AD DS, ele não é um administrador global.</span><span class="sxs-lookup"><span data-stu-id="48d11-162">Notice that although User1 has domain administrator permissions for the TESTLAB AD DS domain, it is not a global administrator.</span></span> <span data-ttu-id="48d11-163">Portanto, o ícone **Administrador** não estará disponível como opção.</span><span class="sxs-lookup"><span data-stu-id="48d11-163">Therefore, you will not see the **Admin** icon as an option.</span></span> 

<span data-ttu-id="48d11-164">A configuração resultante tem esta aparência:</span><span class="sxs-lookup"><span data-stu-id="48d11-164">Your resulting configuration looks like this:</span></span>

![Empresa simulada com ambiente de teste de sincronização de hash de senha](../media/password-hash-sync-m365-ent-test-environment/Phase3.png)

<span data-ttu-id="48d11-166">Esta configuração consiste em:</span><span class="sxs-lookup"><span data-stu-id="48d11-166">This configuration consists of:</span></span> 
  
- <span data-ttu-id="48d11-167">Assinaturas pagas ou de avaliação do Microsoft 365 E5 ou Office 365 E5 com o domínio DNS TESTLAB.<seu nome de *domínio*> registrado.</span><span class="sxs-lookup"><span data-stu-id="48d11-167">Microsoft 365 E5 or Office 365 E5 trial or paid subscriptions with the DNS domain TESTLAB.<*your domain name*> registered.</span></span>
- <span data-ttu-id="48d11-168">Uma intranet de organização simplificada conectada à Internet, que consiste nas máquinas virtuais DC1, APP1 e CLIENT1 em uma sub-rede de uma rede virtual do Azure.</span><span class="sxs-lookup"><span data-stu-id="48d11-168">A simplified organization intranet connected to the internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span> <span data-ttu-id="48d11-169">O Azure AD Connect é executado no APP1 para sincronizar periodicamente o domínio TESTLAB do AD DS com o locatário do Azure AD da sua assinatura do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="48d11-169">Azure AD Connect runs on APP1 to periodically synchronize the TESTLAB AD DS domain to the Azure AD tenant of your Microsoft 365 subscription.</span></span>
- <span data-ttu-id="48d11-170">A conta Usuario1 no domínio TESTLAB do AD DS foi sincronizada com o locatário do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="48d11-170">The User1 account in the TESTLAB  AD DS domain has been synchronized with the Azure AD tenant.</span></span>

## <a name="next-step"></a><span data-ttu-id="48d11-171">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="48d11-171">Next step</span></span>

<span data-ttu-id="48d11-172">Explorar recursos e funcionalidades adicionais de [identidade](m365-enterprise-test-lab-guides.md#identity) no ambiente de teste.</span><span class="sxs-lookup"><span data-stu-id="48d11-172">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="48d11-173">Confira também</span><span class="sxs-lookup"><span data-stu-id="48d11-173">See also</span></span>

[<span data-ttu-id="48d11-174">Guias do Laboratório de Teste do Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="48d11-174">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="48d11-175">Visão geral do Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="48d11-175">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="48d11-176">Documentação do Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="48d11-176">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
