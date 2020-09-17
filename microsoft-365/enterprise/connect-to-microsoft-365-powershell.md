---
title: Conecte-se ao Microsoft 365 com o PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/17/2020
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- LIL_Placement
- O365ITProTrain
- Ent_Office_Other
ms.assetid: 5ebc0e21-b72d-46d8-96fa-00643b18eaec
description: Conecte-se ao seu locatário do Microsoft 365 usando o PowerShell para Microsoft 365 para executar tarefas do centro de administração a partir da linha de comando.
ms.openlocfilehash: 9b4cdbe9fcdea48df456e75095f8d269ab84696f
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/17/2020
ms.locfileid: "47950551"
---
# <a name="connect-to-microsoft-365-with-powershell"></a><span data-ttu-id="f566e-103">Conecte-se ao Microsoft 365 com o PowerShell</span><span class="sxs-lookup"><span data-stu-id="f566e-103">Connect to Microsoft 365 with PowerShell</span></span>

<span data-ttu-id="f566e-104">*Esse artigo se aplica ao Microsoft 365 Enterprise e ao Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="f566e-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="f566e-105">O PowerShell para Microsoft 365 permite gerenciar suas configurações do Microsoft 365 a partir da linha de comando.</span><span class="sxs-lookup"><span data-stu-id="f566e-105">PowerShell for Microsoft 365 lets you manage your Microsoft 365 settings from the command line.</span></span> <span data-ttu-id="f566e-106">A conexão com o PowerShell é um processo simples em que você instala o software necessário e então se conecta à sua organização do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f566e-106">Connecting to PowerShell is a simple process where you install the required software and then connect to your Microsoft 365 organization.</span></span> 

<span data-ttu-id="f566e-107">Existem duas versões do módulo do PowerShell usadas para se conectar ao Microsoft 365 e administrar contas de usuários, grupos e licenças:</span><span class="sxs-lookup"><span data-stu-id="f566e-107">There are two versions of the PowerShell module that you use to connect to Microsoft 365 and administer user accounts, groups, and licenses:</span></span>

- <span data-ttu-id="f566e-108">O Azure Active Directory PowerShell para Graph (inclui **AzureAD** no nome dos cmdlets)</span><span class="sxs-lookup"><span data-stu-id="f566e-108">Azure Active Directory PowerShell for Graph (cmdlets include **AzureAD** in their name)</span></span>
- <span data-ttu-id="f566e-109">O Módulo Microsoft Azure Active Directory para Windows PowerShell (inclui **MSol** no nome dos cmdlets)</span><span class="sxs-lookup"><span data-stu-id="f566e-109">Microsoft Azure Active Directory Module for Windows PowerShell (cmdlets include **MSol** in their name)</span></span> 

<span data-ttu-id="f566e-110">A partir da data deste artigo, o Azure Active Directory PowerShell para o módulo do Graph não substituiu completamente a funcionalidade dos cmdlets do Módulo Microsoft Azure Active Directory para o módulo do Windows PowerShell para a administração de usuários, grupos e licenças.</span><span class="sxs-lookup"><span data-stu-id="f566e-110">As of the date of this article, the Azure Active Directory PowerShell for Graph module does not completely replace the functionality in the cmdlets of Microsoft Azure Active Directory Module for Windows PowerShell module for user, group, and license administration.</span></span> <span data-ttu-id="f566e-111">Em alguns casos, você precisa usar ambas as versões.</span><span class="sxs-lookup"><span data-stu-id="f566e-111">In some cases, you need to use both versions.</span></span> <span data-ttu-id="f566e-112">As duas versões podem ser instaladas com segurança no mesmo computador.</span><span class="sxs-lookup"><span data-stu-id="f566e-112">You can safely install both versions on the same computer.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="f566e-113">O que você precisa saber antes de começar?</span><span class="sxs-lookup"><span data-stu-id="f566e-113">What do you need to know before you begin?</span></span>

<span data-ttu-id="f566e-114">Você pode usar as seguintes versões do Windows:</span><span class="sxs-lookup"><span data-stu-id="f566e-114">You can use the following versions of Windows:</span></span>
    
  - <span data-ttu-id="f566e-115">Windows 10, Windows 8.1, Windows 8 ou Windows 7 Service Pack 1 (SP1)</span><span class="sxs-lookup"><span data-stu-id="f566e-115">Windows 10, Windows 8.1, Windows 8, or Windows 7 Service Pack 1 (SP1)</span></span> 
    
  - <span data-ttu-id="f566e-116">Windows Server 2019, Windows Server 2016, Windows Server 2012 R2, Windows Server 2012, or Windows Server 2008 R2 SP1</span><span class="sxs-lookup"><span data-stu-id="f566e-116">Windows Server 2019, Windows Server 2016, Windows Server 2012 R2, Windows Server 2012, or Windows Server 2008 R2 SP1</span></span>

    > [!NOTE]
    > <span data-ttu-id="f566e-117">Para o módulo do PowerShell do Azure Active Directory para Graph, você deve usar o PowerShell versão 5.1 ou posterior.</span><span class="sxs-lookup"><span data-stu-id="f566e-117">For the Azure Active Directory PowerShell for Graph module, you must use PowerShell version 5.1 or later.</span></span> <span data-ttu-id="f566e-118">Para o módulo do PowerShell do Azure Active Directory para módulo do Windows PowerShell, você deve usar o PowerShell versão 5.1 ou posterior até o PowerShell versão 6.</span><span class="sxs-lookup"><span data-stu-id="f566e-118">For the Microsoft Azure Active Directory Module for Windows PowerShell module, you must use PowerShell version 5.1 or later up to PowerShell version 6.</span></span> <span data-ttu-id="f566e-119">Você não pode usar o PowerShell versão 7.</span><span class="sxs-lookup"><span data-stu-id="f566e-119">You cannot use PowerShell version 7.</span></span> <span data-ttu-id="f566e-120">Para Windows 8.1, Windows 8, Windows 7 Service Pack 1 (SP1), Windows Server 2012 R2, Windows Server 2012, e Windows Server 2008 R2 SP1, baixe e instale o [Windows Management Framework 5.1](https://www.microsoft.com/download/details.aspx?id=54616).</span><span class="sxs-lookup"><span data-stu-id="f566e-120">For Windows 8.1, Windows 8, Windows 7 Service Pack 1 (SP1), Windows Server 2012 R2, Windows Server 2012, and Windows Server 2008 R2 SP1, download and install the [Windows Management Framework 5.1](https://www.microsoft.com/download/details.aspx?id=54616).</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="f566e-p104">Use uma versão de 64 bits do Windows, pois o suporte para a versão de 32 bits do Módulo Microsoft Azure Active Directory para Windows PowerShell foi descontinuada em outubro de 2014.</span><span class="sxs-lookup"><span data-stu-id="f566e-p104">Use a 64-bit version of Windows. Support for the 32-bit version the Microsoft Azure Active Directory Module for Windows PowerShell was discontinued in October of 2014.</span></span>
    
<span data-ttu-id="f566e-123">Esses procedimentos são destinados aos usuários que são membros de uma função de administrador do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f566e-123">These procedures are intended for users who are members of a Microsoft 365 admin role.</span></span> <span data-ttu-id="f566e-124">Para obter mais informações, confira [Sobre funções de administrador](https://go.microsoft.com/fwlink/p/?LinkId=532367).</span><span class="sxs-lookup"><span data-stu-id="f566e-124">For more information, see [About admin roles](https://go.microsoft.com/fwlink/p/?LinkId=532367).</span></span>


## <a name="connect-with-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="f566e-125">Conecte-se ao Azure Active Directory PowerShell para o módulo do Graph.</span><span class="sxs-lookup"><span data-stu-id="f566e-125">Connect with the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="f566e-126">Os comandos no módulo do PowerShell do Azure Active Directory para Graph têm o **AzureAD** no nome do cmdlet.</span><span class="sxs-lookup"><span data-stu-id="f566e-126">Commands in the Azure Active Directory PowerShell for Graph module have **AzureAD** in their cmdlet name.</span></span> <span data-ttu-id="f566e-127">Você pode instalar o módulo do [PowerShell do Azure Active Directory para Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) ou o [Azure PowerShell](https://docs.microsoft.com/powershell/azure/install-az-ps).</span><span class="sxs-lookup"><span data-stu-id="f566e-127">You can install the [Azure Active Directory PowerShell for Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) module or [Azure PowerShell](https://docs.microsoft.com/powershell/azure/install-az-ps).</span></span>

<span data-ttu-id="f566e-128">Para os procedimentos que exigem os novos cmdlets no Azure Active Directory do PowerShell para o módulo do Graph, use estas etapas para instalar o módulo e se conectar à sua assinatura do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f566e-128">For procedures that require the new cmdlets in the Azure Active Directory PowerShell for Graph module, use these steps to install the module and connect to your Microsoft 365 subscription.</span></span>

> [!Note]
> <span data-ttu-id="f566e-129">Confira o [Azure Active Directory PowerShell para o módulo do Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) para obter mais informações sobre o suporte a diferentes versões do Microsoft Windows.</span><span class="sxs-lookup"><span data-stu-id="f566e-129">See [Azure Active Directory PowerShell for Graph module](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) for information about the support for different versions of Microsoft Windows.</span></span>

### <a name="step-1-install-required-software"></a><span data-ttu-id="f566e-130">Etapa 1: instalar o software necessário</span><span class="sxs-lookup"><span data-stu-id="f566e-130">Step 1: Install required software</span></span>

<span data-ttu-id="f566e-p107">Essas etapas precisam ser executadas apenas uma vez em seu computador e não toda vez em que você se conectar. No entanto, você provavelmente precisará instalar a versão mais recente do software periodicamente.</span><span class="sxs-lookup"><span data-stu-id="f566e-p107">These steps are required once on your computer, not every time you connect. However, you'll likely need to install newer versions of the software periodically.</span></span>
  
1. <span data-ttu-id="f566e-133">Abra um prompt de comando elevado do Windows PowerShell (execute o Windows PowerShell como administrador).</span><span class="sxs-lookup"><span data-stu-id="f566e-133">Open an elevated Windows PowerShell command prompt (run Windows PowerShell as an administrator).</span></span>
    
2. <span data-ttu-id="f566e-134">Na janela de comando do **Administrador: Windows PowerShell**, execute este comando:</span><span class="sxs-lookup"><span data-stu-id="f566e-134">In the **Administrator: Windows PowerShell** command window, run this command:</span></span>
    
  ```powershell
  Install-Module -Name AzureAD
  ```

<span data-ttu-id="f566e-135">Se solicitado a instalar um módulo de um repositório não confiável, digite **Y** e pressione Enter.</span><span class="sxs-lookup"><span data-stu-id="f566e-135">If prompted about installing a module from an untrusted repository, type **Y** and press ENTER.</span></span>

### <a name="step-2-connect-to-azure-ad-for-your-microsoft-365-subscription"></a><span data-ttu-id="f566e-136">Etapa 2: Conectar-se ao Azure AD da sua assinatura do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="f566e-136">Step 2: Connect to Azure AD for your Microsoft 365 subscription</span></span>

<span data-ttu-id="f566e-137">Para se conectar ao Azure AD da sua assinatura do Microsoft 365 com um nome de usuário e senha, ou com a autenticação multifator (MFA), execute um destes comandos de um prompt de comando do Windows PowerShell (não é necessário ter privilégios elevados).</span><span class="sxs-lookup"><span data-stu-id="f566e-137">To connect to Azure AD for your Microsoft 365 subscription with an account name and password or with multi-factor authentication (MFA), run one of these commands from a Windows PowerShell command prompt (it does not have to be elevated).</span></span>

| <span data-ttu-id="f566e-138">Nuvem do Office 365</span><span class="sxs-lookup"><span data-stu-id="f566e-138">Office 365 cloud</span></span> | <span data-ttu-id="f566e-139">Comando</span><span class="sxs-lookup"><span data-stu-id="f566e-139">Command</span></span> |
|:-------|:-----|
| <span data-ttu-id="f566e-140">Office 365 no Mundo (+GCC)</span><span class="sxs-lookup"><span data-stu-id="f566e-140">Office 365 Worldwide (+GCC)</span></span> | `Connect-AzureAD` |
| <span data-ttu-id="f566e-141">Office 365 operado pela 21 Vianet</span><span class="sxs-lookup"><span data-stu-id="f566e-141">Office 365 operated by 21 Vianet</span></span> | `Connect-AzureAD -AzureEnvironmentName AzureChinaCloud` |
| <span data-ttu-id="f566e-142">Office 365 Germany</span><span class="sxs-lookup"><span data-stu-id="f566e-142">Office 365 Germany</span></span> | `Connect-AzureAD -AzureEnvironmentName AzureGermanyCloud` |
| <span data-ttu-id="f566e-143">Office 365 U.S. Government DoD e Office 365 U.S. Government GCC High</span><span class="sxs-lookup"><span data-stu-id="f566e-143">Office 365 U.S. Government DoD and Office 365 U.S. Government GCC High</span></span> | `Connect-AzureAD -AzureEnvironmentName AzureUSGovernment` |
|||

<span data-ttu-id="f566e-144">Na caixa de diálogo **Entrar na sua conta**, digite seu nome de usuário e senha de uma conta corporativa ou de estudante do Microsoft 365, e então clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="f566e-144">In the **Sign into your account** dialog box, type your Microsoft 365 work or school account user name and password, and then click **OK**.</span></span>

<span data-ttu-id="f566e-145">Se você estiver usando uma MFA, siga as instruções das caixas de diálogo adicionais para fornecer mais informações de autenticação, como um código de verificação.</span><span class="sxs-lookup"><span data-stu-id="f566e-145">If you are using MFA, follow the instructions in the additional dialog boxes to provide more authentication information, such as a verification code.</span></span>

<span data-ttu-id="f566e-146">Depois de se conectar, você pode usar os cmdlets do [módulo do Azure Active Directory PowerShell para Graph](https://docs.microsoft.com/powershell/azuread/v2/azureactivedirectory).</span><span class="sxs-lookup"><span data-stu-id="f566e-146">After connecting, you can use the cmdlets for the [Azure Active Directory PowerShell for Graph module](https://docs.microsoft.com/powershell/azuread/v2/azureactivedirectory).</span></span>
  

## <a name="connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="f566e-147">Conecte com o Módulo Microsoft Azure Active Directory para Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f566e-147">Connect with the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="f566e-148">Os comandos no Módulo Microsoft Azure Active Directory para Windows PowerShell têm **Msol** no nome do cmdlet.</span><span class="sxs-lookup"><span data-stu-id="f566e-148">Commands in the Microsoft Azure Active Directory Module for Windows PowerShell have **Msol** in their cmdlet name.</span></span>

<span data-ttu-id="f566e-149">O PowerShell versão 7 e posterior não oferece suporte ao Módulo do Microsoft Azure Active Directory para módulo do Windows PowerShell e cmdlets com **Msol** no nome.</span><span class="sxs-lookup"><span data-stu-id="f566e-149">PowerShell version 7 and later do not support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="f566e-150">Para o PowerShell versão 7 e posterior, você deve usar o módulo do PowerShell do Azure Active Directory para Graph ou o Azure PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f566e-150">For PowerShell version 7 and later, you must use the Azure Active Directory PowerShell for Graph module or Azure PowerShell.</span></span>

<span data-ttu-id="f566e-151">O PowerShell Core não é compatível com o módulo do Microsoft Azure Active Directory para módulo e cmdlets do Windows PowerShell com **MSol** no nome.</span><span class="sxs-lookup"><span data-stu-id="f566e-151">PowerShell Core does not support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="f566e-152">Para continuar usando esses cmdlets, você deve executá-los a partir do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f566e-152">To continue using these cmdlets, you must run them from Windows PowerShell.</span></span> 
    
### <a name="step-1-install-required-software"></a><span data-ttu-id="f566e-153">Etapa 1: instalar o software necessário</span><span class="sxs-lookup"><span data-stu-id="f566e-153">Step 1: Install required software</span></span>

<span data-ttu-id="f566e-p110">Essas etapas precisam ser executadas apenas uma vez em seu computador e não toda vez em que você se conectar. No entanto, você provavelmente precisará instalar a versão mais recente do software periodicamente.</span><span class="sxs-lookup"><span data-stu-id="f566e-p110">These steps are required once on your computer, not every time you connect. However, you'll likely need to install newer versions of the software periodically.</span></span>
  
1.  <span data-ttu-id="f566e-156">Se você não estiver usando o Windows 10, instale a versão de 64 bits do Assistente de Conexão do Microsoft Online Services: [Assistente de Conexão do Microsoft Online Services para RTW de Profissionais de TI](https://go.microsoft.com/fwlink/p/?LinkId=286152).</span><span class="sxs-lookup"><span data-stu-id="f566e-156">If you are not running Windows 10, install the 64-bit version of the Microsoft Online Services Sign-in Assistant: [Microsoft Online Services Sign-in Assistant for IT Professionals RTW](https://go.microsoft.com/fwlink/p/?LinkId=286152).</span></span>
    
2. <span data-ttu-id="f566e-157">Instale o Módulo Microsoft Azure Active Directory para Windows PowerShell seguindo estas etapas:</span><span class="sxs-lookup"><span data-stu-id="f566e-157">Install the Microsoft Azure Active Directory Module for Windows PowerShell with these steps:</span></span>
    
  - <span data-ttu-id="f566e-158">Abra um prompt de comando privilegiado do Windows PowerShell (execute o Windows PowerShell como administrador).</span><span class="sxs-lookup"><span data-stu-id="f566e-158">Open an elevated Windows PowerShell command prompt (run Windows PowerShell as an administrator).</span></span>
  - <span data-ttu-id="f566e-159">Execute o comando **Install-Module MSOnline**.</span><span class="sxs-lookup"><span data-stu-id="f566e-159">Run the **Install-Module MSOnline** command.</span></span>
  - <span data-ttu-id="f566e-160">Se solicitado a instalar o provedor de NuGet, digite **Y** e pressione Enter.</span><span class="sxs-lookup"><span data-stu-id="f566e-160">If prompted to install the NuGet provider, type **Y** and press ENTER.</span></span>
  - <span data-ttu-id="f566e-161">Se solicitado a instalar o módulo de PSGallery, digite **Y** e pressione Enter.</span><span class="sxs-lookup"><span data-stu-id="f566e-161">If prompted to install the module from PSGallery, type **Y** and press ENTER.</span></span>
    
### <a name="step-2-connect-to-azure-ad-for-your-microsoft-365-subscription"></a><span data-ttu-id="f566e-162">Etapa 2: Conectar-se ao Azure AD da sua assinatura do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="f566e-162">Step 2: Connect to Azure AD for your Microsoft 365 subscription</span></span>

<span data-ttu-id="f566e-163">Para se conectar ao Azure AD da sua assinatura do Microsoft 365 com um nome de usuário e senha, ou com a autenticação multifator (MFA), execute um destes comandos de um prompt de comando do Windows PowerShell (não é necessário ter privilégios elevados).</span><span class="sxs-lookup"><span data-stu-id="f566e-163">To connect to Azure AD for your Microsoft 365 subscription with an account name and password or with multi-factor authentication (MFA), run one of these commands from a Windows PowerShell command prompt (it does not have to be elevated).</span></span>

| <span data-ttu-id="f566e-164">Nuvem do Office 365</span><span class="sxs-lookup"><span data-stu-id="f566e-164">Office 365 cloud</span></span> | <span data-ttu-id="f566e-165">Comando</span><span class="sxs-lookup"><span data-stu-id="f566e-165">Command</span></span> |
|:-------|:-----|
| <span data-ttu-id="f566e-166">Office 365 no Mundo (+GCC)</span><span class="sxs-lookup"><span data-stu-id="f566e-166">Office 365 Worldwide (+GCC)</span></span> | `Connect-MsolService` |
| <span data-ttu-id="f566e-167">Office 365 operado pela 21 Vianet</span><span class="sxs-lookup"><span data-stu-id="f566e-167">Office 365 operated by 21 Vianet</span></span> | `Connect-MsolService -AzureEnvironment AzureChinaCloud` |
| <span data-ttu-id="f566e-168">Office 365 Germany</span><span class="sxs-lookup"><span data-stu-id="f566e-168">Office 365 Germany</span></span> | `Connect-MsolService -AzureEnvironment AzureGermanyCloud` |
| <span data-ttu-id="f566e-169">Office 365 U.S. Government DoD e Office 365 U.S. Government GCC High</span><span class="sxs-lookup"><span data-stu-id="f566e-169">Office 365 U.S. Government DoD and Office 365 U.S. Government GCC High</span></span> | `Connect-MsolService -AzureEnvironment USGovernment` |
|||

<span data-ttu-id="f566e-170">Na caixa de diálogo **Entrar na sua conta**, digite seu nome de usuário e senha de uma conta corporativa ou de estudante do Microsoft 365, e então clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="f566e-170">In the **Sign into your account** dialog box, type your Microsoft 365 work or school account user name and password, and then click **OK**.</span></span>

<span data-ttu-id="f566e-171">Se você estiver usando uma MFA, siga as instruções das caixas de diálogo adicionais para fornecer mais informações de autenticação, como um código de verificação.</span><span class="sxs-lookup"><span data-stu-id="f566e-171">If you are using MFA, follow the instructions in the additional dialog boxes to provide more authentication information, such as a verification code.</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="f566e-172">Como saber se funcionou?</span><span class="sxs-lookup"><span data-stu-id="f566e-172">How do you know this worked?</span></span>

<span data-ttu-id="f566e-173">Se nenhum erro aparecer, você se conectou com êxito.</span><span class="sxs-lookup"><span data-stu-id="f566e-173">If you don't receive any errors, you connected successfully.</span></span> <span data-ttu-id="f566e-174">Um teste rápido é executar um cmdlet do Microsoft 365, por exemplo, **Get-MsolUser**, e ver os resultados.</span><span class="sxs-lookup"><span data-stu-id="f566e-174">A quick test is to run a Microsoft 365 cmdlet—for example, **Get-MsolUser** —and see the results.</span></span>
  
<span data-ttu-id="f566e-175">Caso você receba erros, verifique os seguintes requisitos:</span><span class="sxs-lookup"><span data-stu-id="f566e-175">If you receive errors, check the following requirements:</span></span>
  
- <span data-ttu-id="f566e-176">**Senha incorreta é um problema comum**.</span><span class="sxs-lookup"><span data-stu-id="f566e-176">**A common problem is an incorrect password**.</span></span> <span data-ttu-id="f566e-177">Execute a Etapa 2 novamente.</span><span class="sxs-lookup"><span data-stu-id="f566e-177">Run Step 2 again.</span></span> <span data-ttu-id="f566e-178">e preste muita atenção ao nome de usuário e à senha inseridos.</span><span class="sxs-lookup"><span data-stu-id="f566e-178">and pay close attention to the user name and password you enter.</span></span>
    
- <span data-ttu-id="f566e-179">**O Módulo Microsoft Azure Active Directory para Windows PowerShell requer que o recurso do Microsoft .NET Framework 3.5.* x* esteja habilitado em seu computador**. É provável que seu computador tenha uma versão mais recente instalada (por exemplo, 4 ou 4.5.* x*), mas a compatibilidade com versões anteriores do .NET Framework pode ser habilitada ou desabilitada.</span><span class="sxs-lookup"><span data-stu-id="f566e-179">**The Microsoft Azure Active Directory Module for Windows PowerShell requires that the Microsoft .NET Framework 3.5.* x* feature is enabled on your computer**. It's likely that your computer has a newer version installed (for example, 4 or 4.5.* x*), but backwards compatibility with older versions of the .NET Framework can be enabled or disabled.</span></span> <span data-ttu-id="f566e-180">Para mais informações, confira os seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="f566e-180">For more information, see the following topics:</span></span>
    
  - <span data-ttu-id="f566e-181">Para Windows Server 2012 ou Windows Server 2012 R2, confira [Habilitar o .NET Framework 3.5 usando o Assistente de Adição de Funções e Recursos](https://go.microsoft.com/fwlink/p/?LinkId=532368)</span><span class="sxs-lookup"><span data-stu-id="f566e-181">For Windows Server 2012 or Windows Server 2012 R2, see [Enable .NET Framework 3.5 by using the Add Roles and Features Wizard](https://go.microsoft.com/fwlink/p/?LinkId=532368)</span></span>
    
  - <span data-ttu-id="f566e-182">Para Windows 7 ou Windows Server 2008 R2, confira [Não é possível abrir o Módulo Azure Active Directory para Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=532370)</span><span class="sxs-lookup"><span data-stu-id="f566e-182">For Windows 7 or Windows Server 2008 R2, see [You can't open the Azure Active Directory Module for Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=532370)</span></span>

  - <span data-ttu-id="f566e-183">Para Windows 10, Windows 8.1 e Windows 8, confira [Instalar o .NET Framework 3.5 no Windows 10, Windows 8.1 e Windows 8](https://docs.microsoft.com/dotnet/framework/install/dotnet-35-windows-10)</span><span class="sxs-lookup"><span data-stu-id="f566e-183">For Windows 10, Windows 8.1, and Windows 8, see [Install the .NET Framework 3.5 on Windows 10, Windows 8.1, and Windows 8](https://docs.microsoft.com/dotnet/framework/install/dotnet-35-windows-10)</span></span>

  
- <span data-ttu-id="f566e-184">**Sua versão do Módulo Microsoft Azure Active Directory para Windows PowerShell pode estar desatualizada.**</span><span class="sxs-lookup"><span data-stu-id="f566e-184">**Your version of the Microsoft Azure Active Directory Module for Windows PowerShell might be out of date.**</span></span> <span data-ttu-id="f566e-185">Para verificar, execute o seguinte comando no PowerShell para o Microsoft 365 ou no Módulo Microsoft Azure Active Directory para Windows PowerShell :</span><span class="sxs-lookup"><span data-stu-id="f566e-185">To check, run the following command in PowerShell for Microsoft 365 or the Microsoft Azure Active Directory Module for Windows PowerShell:</span></span>
    
  ```powershell
  (Get-Item C:\Windows\System32\WindowsPowerShell\v1.0\Modules\MSOnline\Microsoft.Online.Administration.Automation.PSModule.dll).VersionInfo.FileVersion
  ```

    <span data-ttu-id="f566e-186">Se o número da versão retornado for menor que o valor 1.0.8070.2, desinstale o Módulo Microsoft Azure Active Directory para Windows PowerShell e volte a Etapa 1 para instalar.</span><span class="sxs-lookup"><span data-stu-id="f566e-186">If the version number returned is lower than the value 1.0.8070.2, uninstall the Microsoft Azure Active Directory Module for Windows PowerShell and install from Step 1 above.</span></span>

- <span data-ttu-id="f566e-187">**Se você receber um erro de conexão, confira este tópico:** ["Connect-MsolService: ocorreu exceção do tipo"](https://go.microsoft.com/fwlink/p/?LinkId=532377).</span><span class="sxs-lookup"><span data-stu-id="f566e-187">**If you receive a connection error, see this topic:** ["Connect-MsolService: Exception of type was thrown" error](https://go.microsoft.com/fwlink/p/?LinkId=532377).</span></span>
    
- <span data-ttu-id="f566e-188">**Se você receber a mensagem de erro "Get-Item : Não é possível encontrar o caminho", use este comando:**</span><span class="sxs-lookup"><span data-stu-id="f566e-188">**If you receive a "Get-Item : Cannot find path" error, use this command:**</span></span> 

```powershell
  (dir "C:\Program Files\WindowsPowerShell\Modules\MSOnline").Name
```

## <a name="see-also"></a><span data-ttu-id="f566e-189">Confira também</span><span class="sxs-lookup"><span data-stu-id="f566e-189">See also</span></span>

- [<span data-ttu-id="f566e-190">Gerenciar o Microsoft 365 com o PowerShell</span><span class="sxs-lookup"><span data-stu-id="f566e-190">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
- [<span data-ttu-id="f566e-191">Introdução ao PowerShell para o Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="f566e-191">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
- [<span data-ttu-id="f566e-192">Conectar-se a todos os serviços do Microsoft 365 usando uma única janela do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f566e-192">Connect to all Microsoft 365 services in a single Windows PowerShell window</span></span>](connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window.md)
