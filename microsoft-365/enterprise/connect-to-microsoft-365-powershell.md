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
description: Conecte-se ao seu locatário do Microsoft 365 usando o Windows PowerShell para Microsoft 365 para fazer as tarefas do centro de administração a partir da linha de comando.
ms.openlocfilehash: 58af42958e9b50ee8e39cbd7bd5aab53812e444c
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919171"
---
# <a name="connect-to-microsoft-365-with-powershell"></a><span data-ttu-id="f4c6b-103">Conecte-se ao Microsoft 365 com o PowerShell</span><span class="sxs-lookup"><span data-stu-id="f4c6b-103">Connect to Microsoft 365 with PowerShell</span></span>

<span data-ttu-id="f4c6b-104">*Esse artigo se aplica ao Microsoft 365 Enterprise e ao Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="f4c6b-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="f4c6b-105">O Windows PowerShell para Microsoft 365 permite que você gerencie suas configurações do Microsoft 365 a partir da linha de comando.</span><span class="sxs-lookup"><span data-stu-id="f4c6b-105">PowerShell for Microsoft 365 enables you to manage your Microsoft 365 settings from the command line.</span></span> <span data-ttu-id="f4c6b-106">Para se conectar ao Windows PowerShell, basta instalar o software necessário e conectar-se à sua organização Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f4c6b-106">To connect to PowerShell, just install the required software and then connect to your Microsoft 365 organization.</span></span>

<span data-ttu-id="f4c6b-107">Existem duas versões do módulo Windows PowerShell que você pode usar para se conectar ao Microsoft 365 e administrar contas de usuário, grupos e licenças:</span><span class="sxs-lookup"><span data-stu-id="f4c6b-107">There are two versions of the PowerShell module that you can use to connect to Microsoft 365 and administer user accounts, groups, and licenses:</span></span>

- <span data-ttu-id="f4c6b-108">O Azure Active Directory Windows PowerShell para Microsoft Graph, cujo nome dos cmdlets inclui *AzureAD*</span><span class="sxs-lookup"><span data-stu-id="f4c6b-108">Azure Active Directory PowerShell for Graph, whose cmdlets include *AzureAD* in their name</span></span>
- <span data-ttu-id="f4c6b-109">O Módulo Microsoft Azure Active Directory para Windows PowerShell, cujo nome dos cmdlets inclui *MSol*</span><span class="sxs-lookup"><span data-stu-id="f4c6b-109">Microsoft Azure Active Directory Module for Windows PowerShell, whose cmdlets include *Msol* in their name</span></span>

<span data-ttu-id="f4c6b-110">Atualmente, o módulo Azure Active Directory Windows PowerShell para Microsoft Graph não substitui completamente a funcionalidade do Módulo Microsoft Azure Active Directory para Windows PowerShell para administração de usuários, grupos e licenças.</span><span class="sxs-lookup"><span data-stu-id="f4c6b-110">Currently, the Azure Active Directory PowerShell for Graph module doesn't completely replace the functionality of the Microsoft Azure Active Directory Module for Windows PowerShell module for user, group, and license administration.</span></span> <span data-ttu-id="f4c6b-111">Em alguns casos, você precisa usar ambas as versões.</span><span class="sxs-lookup"><span data-stu-id="f4c6b-111">In some cases, you need to use both versions.</span></span> <span data-ttu-id="f4c6b-112">As duas versões podem ser instaladas com segurança no mesmo computador.</span><span class="sxs-lookup"><span data-stu-id="f4c6b-112">You can safely install both versions on the same computer.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="f4c6b-113">O que você precisa saber antes de começar?</span><span class="sxs-lookup"><span data-stu-id="f4c6b-113">What do you need to know before you begin?</span></span>


<span data-ttu-id="f4c6b-114">**Sistema operacional**</span><span class="sxs-lookup"><span data-stu-id="f4c6b-114">**Operating system**</span></span>

<span data-ttu-id="f4c6b-115">Use uma versão de 64 bits do Windows.</span><span class="sxs-lookup"><span data-stu-id="f4c6b-115">You must use a 64-bit version of Windows.</span></span> <span data-ttu-id="f4c6b-116">O suporte para a versão de 32 bits do Módulo Microsoft Azure Active Directory para Windows PowerShell terminou em 2014.</span><span class="sxs-lookup"><span data-stu-id="f4c6b-116">Support for the 32-bit version of the Microsoft Azure Active Directory Module for Windows PowerShell ended in 2014.</span></span>

<span data-ttu-id="f4c6b-117">Você pode usar as seguintes versões do Windows:</span><span class="sxs-lookup"><span data-stu-id="f4c6b-117">You can use the following versions of Windows:</span></span>
    
  - <span data-ttu-id="f4c6b-118">Windows 10, Windows 8.1, Windows 8 ou Windows 7 Service Pack 1 (SP1)</span><span class="sxs-lookup"><span data-stu-id="f4c6b-118">Windows 10, Windows 8.1, Windows 8, or Windows 7 Service Pack 1 (SP1)</span></span> 
    
  - <span data-ttu-id="f4c6b-119">Windows Server 2019, Windows Server 2016, Windows Server 2012 R2, Windows Server 2012, or Windows Server 2008 R2 SP1</span><span class="sxs-lookup"><span data-stu-id="f4c6b-119">Windows Server 2019, Windows Server 2016, Windows Server 2012 R2, Windows Server 2012, or Windows Server 2008 R2 SP1</span></span>

>[!Note]
><span data-ttu-id="f4c6b-120">Para Windows 8.1, Windows 8, Windows 7 Service Pack 1 (SP1), Windows Server 2012 R2, Windows Server 2012, e Windows Server 2008 R2 SP1, baixe e instale o [Windows Management Framework 5.1](https://www.microsoft.com/download/details.aspx?id=54616).</span><span class="sxs-lookup"><span data-stu-id="f4c6b-120">For Windows 8.1, Windows 8, Windows 7 Service Pack 1 (SP1), Windows Server 2012 R2, Windows Server 2012, and Windows Server 2008 R2 SP1, download and install the [Windows Management Framework 5.1](https://www.microsoft.com/download/details.aspx?id=54616).</span></span>

<span data-ttu-id="f4c6b-121">**PowerShell**</span><span class="sxs-lookup"><span data-stu-id="f4c6b-121">**PowerShell**</span></span>

- <span data-ttu-id="f4c6b-122">Para o módulo do Windows PowerShell do Azure Active Directory para Graph, você deve usar o Windows PowerShell versão 5.1 ou posterior.</span><span class="sxs-lookup"><span data-stu-id="f4c6b-122">For the Azure Active Directory PowerShell for Graph module, you must use PowerShell version 5.1 or later.</span></span>

- <span data-ttu-id="f4c6b-123">Para o Módulo Microsoft Azure Active Directory para Windows PowerShell, você deve usar o Windows PowerShell versão 5.1 ou posterior, até o Windows PowerShell versão 6.</span><span class="sxs-lookup"><span data-stu-id="f4c6b-123">For the Microsoft Azure Active Directory Module for Windows PowerShell module, you must use PowerShell version 5.1 or later, up to PowerShell version 6.</span></span> <span data-ttu-id="f4c6b-124">Você não pode usar o Windows PowerShell versão 7.</span><span class="sxs-lookup"><span data-stu-id="f4c6b-124">You can't use PowerShell version 7.</span></span>
       
>[!Note]
><span data-ttu-id="f4c6b-125">Esses procedimentos são destinados aos usuários que são membros de uma função de administrador do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f4c6b-125">These procedures are intended for users who are members of a Microsoft 365 admin role.</span></span> <span data-ttu-id="f4c6b-126">Para obter mais informações, confira [Sobre funções de administrador](../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="f4c6b-126">For more information, see [About admin roles](../admin/add-users/about-admin-roles.md).</span></span>


## <a name="connect-with-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="f4c6b-127">Conecte-se ao Azure Active Directory PowerShell para o módulo do Graph.</span><span class="sxs-lookup"><span data-stu-id="f4c6b-127">Connect with the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="f4c6b-128">Os comandos no módulo do PowerShell do Azure Active Directory para Graph têm o *AzureAD* no nome do cmdlet.</span><span class="sxs-lookup"><span data-stu-id="f4c6b-128">Commands in the Azure Active Directory PowerShell for Graph module have *AzureAD* in their cmdlet name.</span></span> <span data-ttu-id="f4c6b-129">Você pode instalar o módulo do [PowerShell do Azure Active Directory para Graph](/powershell/azure/active-directory/install-adv2) ou o [Azure PowerShell](/powershell/azure/install-az-ps).</span><span class="sxs-lookup"><span data-stu-id="f4c6b-129">You can install the [Azure Active Directory PowerShell for Graph](/powershell/azure/active-directory/install-adv2) module or [Azure PowerShell](/powershell/azure/install-az-ps).</span></span>

<span data-ttu-id="f4c6b-130">Para procedimentos que exigem os novos cmdlets no módulo Azure Active Directory Windows PowerShell para Graph, siga estas etapas para instalar o módulo e conectar-se à sua assinatura do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f4c6b-130">For procedures that require the new cmdlets in the Azure Active Directory PowerShell for Graph module, follow these steps to install the module and connect to your Microsoft 365 subscription.</span></span>

> [!Note]
> <span data-ttu-id="f4c6b-131">Confira o [Azure Active Directory PowerShell para o módulo do Graph](/powershell/azure/active-directory/install-adv2) para obter mais informações sobre o suporte a diferentes versões do Microsoft Windows.</span><span class="sxs-lookup"><span data-stu-id="f4c6b-131">For information about support for different versions of Windows, see [Azure Active Directory PowerShell for Graph module](/powershell/azure/active-directory/install-adv2) .</span></span>

### <a name="step-1-install-the-required-software"></a><span data-ttu-id="f4c6b-132">Etapa 1: instalar o software necessário</span><span class="sxs-lookup"><span data-stu-id="f4c6b-132">Step 1: Install the required software</span></span>

<span data-ttu-id="f4c6b-133">Estas etapas são necessárias apenas uma vez em seu computador.</span><span class="sxs-lookup"><span data-stu-id="f4c6b-133">These steps are required only one time on your computer.</span></span> <span data-ttu-id="f4c6b-134">Mas provavelmente você precisará atualizar o software periodicamente.</span><span class="sxs-lookup"><span data-stu-id="f4c6b-134">But you'll likely need to update the software periodically.</span></span>
  
1. <span data-ttu-id="f4c6b-135">Abra uma janela elevada do Prompt de Comando do Windows PowerShell (execute o Windows PowerShell como administrador).</span><span class="sxs-lookup"><span data-stu-id="f4c6b-135">Open an elevated Windows PowerShell Command Prompt window (run Windows PowerShell as an administrator).</span></span>
    
2. <span data-ttu-id="f4c6b-136">Execute este comando:</span><span class="sxs-lookup"><span data-stu-id="f4c6b-136">Run this command:</span></span>
    
    ```powershell
    Install-Module -Name AzureAD
    ```

   <span data-ttu-id="f4c6b-137">Se você for solicitado a instalar um módulo de um repositório não confiável, digite **Y** e pressione Enter.</span><span class="sxs-lookup"><span data-stu-id="f4c6b-137">If you're prompted to install a module from an untrusted repository, type **Y** and press Enter.</span></span>

### <a name="step-2-connect-to-azure-ad-for-your-microsoft-365-subscription"></a><span data-ttu-id="f4c6b-138">Etapa 2: Conectar-se ao Azure AD da sua assinatura do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="f4c6b-138">Step 2: Connect to Azure AD for your Microsoft 365 subscription</span></span>

<span data-ttu-id="f4c6b-139">Para se conectar ao Azure Active Directory (Azure AD) para sua assinatura do Microsoft 365 com um nome de conta e senha ou com autenticação multifator, execute um desses comandos em um prompt de comando do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f4c6b-139">To connect to Azure Active Directory (Azure AD) for your Microsoft 365 subscription with an account name and password or with multi-factor authentication, run one of these commands from a Windows PowerShell command prompt.</span></span> <span data-ttu-id="f4c6b-140">(Não precisa ser elevado.)</span><span class="sxs-lookup"><span data-stu-id="f4c6b-140">(It doesn't have to be elevated.)</span></span>

| <span data-ttu-id="f4c6b-141">Nuvem do Office 365</span><span class="sxs-lookup"><span data-stu-id="f4c6b-141">Office 365 cloud</span></span> | <span data-ttu-id="f4c6b-142">Comando</span><span class="sxs-lookup"><span data-stu-id="f4c6b-142">Command</span></span> |
|:-------|:-----|
| <span data-ttu-id="f4c6b-143">Office 365 no Mundo (+GCC)</span><span class="sxs-lookup"><span data-stu-id="f4c6b-143">Office 365 Worldwide (+GCC)</span></span> | `Connect-AzureAD` |
| <span data-ttu-id="f4c6b-144">Office 365 operado pela 21 Vianet</span><span class="sxs-lookup"><span data-stu-id="f4c6b-144">Office 365 operated by 21 Vianet</span></span> | `Connect-AzureAD -AzureEnvironmentName AzureChinaCloud` |
| <span data-ttu-id="f4c6b-145">Office 365 Germany</span><span class="sxs-lookup"><span data-stu-id="f4c6b-145">Office 365 Germany</span></span> | `Connect-AzureAD -AzureEnvironmentName AzureGermanyCloud` |
| <span data-ttu-id="f4c6b-146">Office 365 U.S. Government DoD e Office 365 U.S. Government GCC High</span><span class="sxs-lookup"><span data-stu-id="f4c6b-146">Office 365 U.S. Government DoD and Office 365 U.S. Government GCC High</span></span> | `Connect-AzureAD -AzureEnvironmentName AzureUSGovernment` |
|||

<span data-ttu-id="f4c6b-147">Na caixa de diálogo **Entrar na sua conta**, digite seu nome de usuário e senha da conta corporativa ou de estudante do Microsoft 365 e selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="f4c6b-147">In the **Sign into your account** dialog box, type your Microsoft 365 work or school account user name and password, and then select **OK**.</span></span>

<span data-ttu-id="f4c6b-148">Se você estiver usando a autenticação multifator, siga as instruções para fornecer informações adicionais de autenticação, como um código de verificação.</span><span class="sxs-lookup"><span data-stu-id="f4c6b-148">If you're using multi-factor authentication, follow the instructions to provide additional authentication information, such as a verification code.</span></span>

<span data-ttu-id="f4c6b-149">Depois de se conectar, você pode usar os cmdlets para o [módulo Azure Active Directory Windows PowerShell para Graph](/powershell/module/azuread).</span><span class="sxs-lookup"><span data-stu-id="f4c6b-149">After you connect, you can use the cmdlets for the [Azure Active Directory PowerShell for Graph module](/powershell/module/azuread).</span></span>

## <a name="connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="f4c6b-150">Conecte com o Módulo Microsoft Azure Active Directory para Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f4c6b-150">Connect with the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

>[!Note]
><span data-ttu-id="f4c6b-151">Os cmdlets no Módulo Microsoft Azure Active Directory para Windows PowerShell têm *Msol* em seus nomes.</span><span class="sxs-lookup"><span data-stu-id="f4c6b-151">Cmdlets in the Microsoft Azure Active Directory Module for Windows PowerShell have *Msol* in their name.</span></span>

<span data-ttu-id="f4c6b-152">O PowerShell versão 7 e posterior não oferece suporte ao Módulo Microsoft Azure Active Directory para Windows PowerShell e cmdlets com *Msol* em seus nomes.</span><span class="sxs-lookup"><span data-stu-id="f4c6b-152">PowerShell version 7 and later don't support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with *Msol* in their name.</span></span> <span data-ttu-id="f4c6b-153">Para o PowerShell versão 7 e posterior, você deve usar o módulo do PowerShell do Azure Active Directory para Graph ou o Azure PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f4c6b-153">For PowerShell version 7 and later, you must use the Azure Active Directory PowerShell for Graph module or Azure PowerShell.</span></span>

<span data-ttu-id="f4c6b-154">O PowerShell Core não oferece suporte ao Módulo Microsoft Azure Active Directory para Windows PowerShell para o módulo do Windows PowerShell e cmdlets com *Msol* em seus nomes.</span><span class="sxs-lookup"><span data-stu-id="f4c6b-154">PowerShell Core doesn't support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with *Msol* in their name.</span></span> <span data-ttu-id="f4c6b-155">Execute esses cmdlets do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f4c6b-155">Run these cmdlets from Windows PowerShell.</span></span>
    
### <a name="step-1-install-the-required-software"></a><span data-ttu-id="f4c6b-156">Etapa 1: instalar o software necessário</span><span class="sxs-lookup"><span data-stu-id="f4c6b-156">Step 1: Install the required software</span></span>

<span data-ttu-id="f4c6b-157">Estas etapas são necessárias apenas uma vez em seu computador.</span><span class="sxs-lookup"><span data-stu-id="f4c6b-157">These steps are required only one time on your computer.</span></span> <span data-ttu-id="f4c6b-158">Mas provavelmente você precisará atualizar o software periodicamente.</span><span class="sxs-lookup"><span data-stu-id="f4c6b-158">But you'll likely need to update the software periodically.</span></span>
  
1.  <span data-ttu-id="f4c6b-159">Se você não estiver executando o Windows 10, instale a versão de 64 bits do Assistente de Conexão do Microsoft Online Services: [Assistente de Conexão do Microsoft Online Services para Profissionais de TI RTW](https://www.microsoft.com/Download/details.aspx?id=28177).</span><span class="sxs-lookup"><span data-stu-id="f4c6b-159">If you're not running Windows 10, install the 64-bit version of the Microsoft Online Services Sign-in Assistant: [Microsoft Online Services Sign-in Assistant for IT Professionals RTW](https://www.microsoft.com/Download/details.aspx?id=28177).</span></span>
    
2. <span data-ttu-id="f4c6b-160">Siga estas etapas para instalar o Módulo Microsoft Azure Active Directory para Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="f4c6b-160">Follow these steps to install the Microsoft Azure Active Directory Module for Windows PowerShell:</span></span>
    
   1. <span data-ttu-id="f4c6b-161">Abra um prompt de comando privilegiado do Windows PowerShell (execute o Windows PowerShell como administrador).</span><span class="sxs-lookup"><span data-stu-id="f4c6b-161">Open an elevated Windows PowerShell command prompt (run Windows PowerShell as an administrator).</span></span>
   1.  <span data-ttu-id="f4c6b-162">Execute o comando **Install-Module MSOnline**.</span><span class="sxs-lookup"><span data-stu-id="f4c6b-162">Run the **Install-Module MSOnline** command.</span></span>
   1. <span data-ttu-id="f4c6b-163">Se você for solicitado a instalar o provedor NuGet, digite **S** e pressione Enter.</span><span class="sxs-lookup"><span data-stu-id="f4c6b-163">If you're prompted to install the NuGet provider, type **Y** and press Enter.</span></span>
   1. <span data-ttu-id="f4c6b-164">Se você for solicitado a instalar o módulo do PSGallery, digite **S** e pressione Enter.</span><span class="sxs-lookup"><span data-stu-id="f4c6b-164">If you're prompted to install the module from PSGallery, type **Y** and press Enter.</span></span>
    
### <a name="step-2-connect-to-azure-ad-for-your-microsoft-365-subscription"></a><span data-ttu-id="f4c6b-165">Etapa 2: Conectar-se ao Azure AD da sua assinatura do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="f4c6b-165">Step 2: Connect to Azure AD for your Microsoft 365 subscription</span></span>

<span data-ttu-id="f4c6b-166">Para se conectar ao Azure AD para sua assinatura do Microsoft 365 com um nome de conta e senha ou com autenticação multifator, execute um desses comandos em um prompt de comando do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f4c6b-166">To connect to Azure AD for your Microsoft 365 subscription with an account name and password or with multi-factor authentication, run one of these commands from a Windows PowerShell command prompt.</span></span> <span data-ttu-id="f4c6b-167">(Não precisa ser elevado.)</span><span class="sxs-lookup"><span data-stu-id="f4c6b-167">(It doesn't have to be elevated.)</span></span>

| <span data-ttu-id="f4c6b-168">Nuvem do Office 365</span><span class="sxs-lookup"><span data-stu-id="f4c6b-168">Office 365 cloud</span></span> | <span data-ttu-id="f4c6b-169">Comando</span><span class="sxs-lookup"><span data-stu-id="f4c6b-169">Command</span></span> |
|:-------|:-----|
| <span data-ttu-id="f4c6b-170">Office 365 no Mundo (+GCC)</span><span class="sxs-lookup"><span data-stu-id="f4c6b-170">Office 365 Worldwide (+GCC)</span></span> | `Connect-MsolService` |
| <span data-ttu-id="f4c6b-171">Office 365 operado pela 21 Vianet</span><span class="sxs-lookup"><span data-stu-id="f4c6b-171">Office 365 operated by 21 Vianet</span></span> | `Connect-MsolService -AzureEnvironment AzureChinaCloud` |
| <span data-ttu-id="f4c6b-172">Office 365 Germany</span><span class="sxs-lookup"><span data-stu-id="f4c6b-172">Office 365 Germany</span></span> | `Connect-MsolService -AzureEnvironment AzureGermanyCloud` |
| <span data-ttu-id="f4c6b-173">Office 365 U.S. Government DoD e Office 365 U.S. Government GCC High</span><span class="sxs-lookup"><span data-stu-id="f4c6b-173">Office 365 U.S. Government DoD and Office 365 U.S. Government GCC High</span></span> | `Connect-MsolService -AzureEnvironment USGovernment` |
|||

<span data-ttu-id="f4c6b-174">Na caixa de diálogo **Entrar na sua conta**, digite seu nome de usuário e senha da conta corporativa ou de estudante do Microsoft 365 e selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="f4c6b-174">In the **Sign into your account** dialog box, type your Microsoft 365 work or school account user name and password, and then select **OK**.</span></span>

<span data-ttu-id="f4c6b-175">Se você estiver usando a autenticação multifator, siga as instruções para fornecer informações adicionais de autenticação, como um código de verificação.</span><span class="sxs-lookup"><span data-stu-id="f4c6b-175">If you're using multi-factor authentication, follow the instructions to provide additional authentication information, such as a verification code.</span></span>

### <a name="how-do-you-know-it-worked"></a><span data-ttu-id="f4c6b-176">Como saber se funcionou?</span><span class="sxs-lookup"><span data-stu-id="f4c6b-176">How do you know it worked?</span></span>

<span data-ttu-id="f4c6b-177">Se você não receber uma mensagem de erro, você se conectou com êxito.</span><span class="sxs-lookup"><span data-stu-id="f4c6b-177">If you don't get an error message, you connected successfully.</span></span> <span data-ttu-id="f4c6b-178">Para um teste rápido, execute um cmdlet do Microsoft 365, como **Get-MsolUser**, e confira os resultados.</span><span class="sxs-lookup"><span data-stu-id="f4c6b-178">For quick test,  run a Microsoft 365 cmdlet, such as  **Get-MsolUser**, and see the results.</span></span>
  
<span data-ttu-id="f4c6b-179">Se você receber uma mensagem de erro, cheque os seguintes problemas:</span><span class="sxs-lookup"><span data-stu-id="f4c6b-179">If you get an error message, check the following issues:</span></span>
  
- <span data-ttu-id="f4c6b-180">**Senha incorreta é um problema comum**.</span><span class="sxs-lookup"><span data-stu-id="f4c6b-180">**A common problem is an incorrect password**.</span></span> <span data-ttu-id="f4c6b-181">Execute a [Etapa 2](#step-2-connect-to-azure-ad-for-your-microsoft-365-subscription) novamente e preste muita atenção ao nome de usuário e senha que você inserir.</span><span class="sxs-lookup"><span data-stu-id="f4c6b-181">Run [Step 2](#step-2-connect-to-azure-ad-for-your-microsoft-365-subscription) again, and pay close attention to the user name and password that you enter.</span></span>
    
- <span data-ttu-id="f4c6b-182">**O Módulo Microsoft Azure Active Directory para Windows PowerShell requer o Microsoft .NET Framework 3.5.* x* está ativado em seu computador **. É provável que seu computador tenha uma versão mais recente instalada (por exemplo, 4 ou 4.5.* x*).</span><span class="sxs-lookup"><span data-stu-id="f4c6b-182">**The Microsoft Azure Active Directory Module for Windows PowerShell requires that Microsoft .NET Framework 3.5.* x* is enabled on your computer**. It's likely that your computer has a newer version installed (for example, 4 or 4.5.* x*).</span></span> <span data-ttu-id="f4c6b-183">Mas a compatibilidade com versões anteriores do .NET Framework pode ser habilitada ou desabilitada.</span><span class="sxs-lookup"><span data-stu-id="f4c6b-183">But backward compatibility with older versions of the .NET Framework can be enabled or disabled.</span></span> <span data-ttu-id="f4c6b-184">Para saber mais, confira os seguintes artigos:</span><span class="sxs-lookup"><span data-stu-id="f4c6b-184">For more information, see the following articles:</span></span>
    
  - <span data-ttu-id="f4c6b-185">Para Windows Server 2012 ou Windows Server 2012 R2, confira [Habilitar o .NET Framework 3.5 usando o Assistente de Adição de Funções e Recursos](/previous-versions/windows/it-pro/windows-8.1-and-8/dn482071(v=win.10)).</span><span class="sxs-lookup"><span data-stu-id="f4c6b-185">For Windows Server 2012 or Windows Server 2012 R2, see [Enable .NET Framework 3.5 by using the Add Roles and Features Wizard](/previous-versions/windows/it-pro/windows-8.1-and-8/dn482071(v=win.10)).</span></span>
    
  - <span data-ttu-id="f4c6b-186">Para Windows 7 ou Windows Server 2008 R2, confira [Não é possível abrir o Módulo Azure Active Directory para Windows PowerShell](/troubleshoot/azure/active-directory/cant-open-aad-module-powershell).</span><span class="sxs-lookup"><span data-stu-id="f4c6b-186">For Windows 7 or Windows Server 2008 R2, see [You can't open the Azure Active Directory Module for Windows PowerShell](/troubleshoot/azure/active-directory/cant-open-aad-module-powershell).</span></span>

  - <span data-ttu-id="f4c6b-187">Para Windows 10, Windows 8.1 e Windows 8, confira [Instalar o .NET Framework 3.5 no Windows 10, Windows 8.1 e Windows 8](/dotnet/framework/install/dotnet-35-windows-10)</span><span class="sxs-lookup"><span data-stu-id="f4c6b-187">For Windows 10, Windows 8.1, and Windows 8, see [Install the .NET Framework 3.5 on Windows 10, Windows 8.1, and Windows 8](/dotnet/framework/install/dotnet-35-windows-10).</span></span>

  
- <span data-ttu-id="f4c6b-188">**Sua versão do Módulo Microsoft Azure Active Directory para Windows PowerShell pode estar desatualizada.**</span><span class="sxs-lookup"><span data-stu-id="f4c6b-188">**Your version of the Microsoft Azure Active Directory Module for Windows PowerShell might be out of date.**</span></span> <span data-ttu-id="f4c6b-189">Para verificar, execute o seguinte comando no PowerShell para o Microsoft 365 ou no Módulo Microsoft Azure Active Directory para Windows PowerShell :</span><span class="sxs-lookup"><span data-stu-id="f4c6b-189">To check, run the following command in PowerShell for Microsoft 365 or the Microsoft Azure Active Directory Module for Windows PowerShell:</span></span>
    
  ```powershell
  (Get-Item C:\Windows\System32\WindowsPowerShell\v1.0\Modules\MSOnline\Microsoft.Online.Administration.Automation.PSModule.dll).VersionInfo.FileVersion
  ```

    <span data-ttu-id="f4c6b-190">Se o número da versão retornado for inferior a *1.0.8070.2*, desinstale o Módulo Microsoft Azure Active Directory para Windows PowerShell e instale a partir da [Etapa 1](#step-1-install-the-required-software), acima.</span><span class="sxs-lookup"><span data-stu-id="f4c6b-190">If the version number returned is lower than *1.0.8070.2*, uninstall the Microsoft Azure Active Directory Module for Windows PowerShell and install from [Step 1](#step-1-install-the-required-software), above.</span></span>

- <span data-ttu-id="f4c6b-191">**Se você receber uma mensagem de erro de conexão**, confira [o erro "Connect-MsolService: Exceção de tipo lançada"](/office365/troubleshoot/active-directory/connect-msoservice-throw-exception).</span><span class="sxs-lookup"><span data-stu-id="f4c6b-191">**If you get a connection error message**, see ["Connect-MsolService: Exception of type was thrown" error](/office365/troubleshoot/active-directory/connect-msoservice-throw-exception).</span></span>
    
- <span data-ttu-id="f4c6b-192">**Se você receber uma mensagem de erro "Get-Item: Não é possível encontrar o caminho"**, execute este comando:</span><span class="sxs-lookup"><span data-stu-id="f4c6b-192">**If you get a "Get-Item: Cannot find path" error message**, run this command:</span></span>


   ```powershell
     (dir "C:\Program Files\WindowsPowerShell\Modules\MSOnline").Name
   ```

## <a name="see-also"></a><span data-ttu-id="f4c6b-193">Confira também</span><span class="sxs-lookup"><span data-stu-id="f4c6b-193">See also</span></span>

- [<span data-ttu-id="f4c6b-194">Gerenciar o Microsoft 365 com o PowerShell</span><span class="sxs-lookup"><span data-stu-id="f4c6b-194">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
- [<span data-ttu-id="f4c6b-195">Introdução ao Windows PowerShell para o Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="f4c6b-195">Get started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
- [<span data-ttu-id="f4c6b-196">Conectar-se a todos os serviços do Microsoft 365 usando uma única janela do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f4c6b-196">Connect to all Microsoft 365 services in a single Windows PowerShell window</span></span>](connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window.md)