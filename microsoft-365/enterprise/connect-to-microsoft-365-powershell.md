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
ms.openlocfilehash: 70d6aa1373daf2322319d21e385fc1498af3351e
ms.sourcegitcommit: 3b9fab82d63aea41d5f544938868c5d2cbf52d7a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/05/2021
ms.locfileid: "52782796"
---
# <a name="connect-to-microsoft-365-with-powershell"></a><span data-ttu-id="a2906-103">Conecte-se ao Microsoft 365 com o PowerShell</span><span class="sxs-lookup"><span data-stu-id="a2906-103">Connect to Microsoft 365 with PowerShell</span></span>

<span data-ttu-id="a2906-104">*Esse artigo se aplica ao Microsoft 365 Enterprise e ao Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="a2906-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="a2906-105">O Windows PowerShell para Microsoft 365 permite que você gerencie suas configurações do Microsoft 365 a partir da linha de comando.</span><span class="sxs-lookup"><span data-stu-id="a2906-105">PowerShell for Microsoft 365 enables you to manage your Microsoft 365 settings from the command line.</span></span> <span data-ttu-id="a2906-106">Para se conectar ao Windows PowerShell, basta instalar o software necessário e conectar-se à sua organização Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a2906-106">To connect to PowerShell, just install the required software and then connect to your Microsoft 365 organization.</span></span>

<span data-ttu-id="a2906-107">Existem duas versões do módulo Windows PowerShell que você pode usar para se conectar ao Microsoft 365 e administrar contas de usuário, grupos e licenças:</span><span class="sxs-lookup"><span data-stu-id="a2906-107">There are two versions of the PowerShell module that you can use to connect to Microsoft 365 and administer user accounts, groups, and licenses:</span></span>

- <span data-ttu-id="a2906-108">O Azure Active Directory Windows PowerShell para Microsoft Graph, cujo nome dos cmdlets inclui *AzureAD*</span><span class="sxs-lookup"><span data-stu-id="a2906-108">Azure Active Directory PowerShell for Graph, whose cmdlets include *AzureAD* in their name</span></span>
- <span data-ttu-id="a2906-109">O Módulo Microsoft Azure Active Directory para Windows PowerShell, cujo nome dos cmdlets inclui *MSol*</span><span class="sxs-lookup"><span data-stu-id="a2906-109">Microsoft Azure Active Directory Module for Windows PowerShell, whose cmdlets include *Msol* in their name</span></span>

<span data-ttu-id="a2906-110">Atualmente, o módulo Azure Active Directory Windows PowerShell para Microsoft Graph não substitui completamente a funcionalidade do Módulo Microsoft Azure Active Directory para Windows PowerShell para administração de usuários, grupos e licenças.</span><span class="sxs-lookup"><span data-stu-id="a2906-110">Currently, the Azure Active Directory PowerShell for Graph module doesn't completely replace the functionality of the Microsoft Azure Active Directory Module for Windows PowerShell module for user, group, and license administration.</span></span> <span data-ttu-id="a2906-111">Em alguns casos, você precisa usar ambas as versões.</span><span class="sxs-lookup"><span data-stu-id="a2906-111">In some cases, you need to use both versions.</span></span> <span data-ttu-id="a2906-112">As duas versões podem ser instaladas com segurança no mesmo computador.</span><span class="sxs-lookup"><span data-stu-id="a2906-112">You can safely install both versions on the same computer.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="a2906-113">O que você precisa saber antes de começar?</span><span class="sxs-lookup"><span data-stu-id="a2906-113">What do you need to know before you begin?</span></span>


<span data-ttu-id="a2906-114">**Sistema operacional**</span><span class="sxs-lookup"><span data-stu-id="a2906-114">**Operating system**</span></span>

<span data-ttu-id="a2906-p103">Você deve usar uma versão de 64 bits do Windows porque o suporte para a versão de 32 bits do Módulo Microsoft Azure Active Directory para Windows PowerShell foi encerrado em 2014.</span><span class="sxs-lookup"><span data-stu-id="a2906-p103">You must use a 64-bit version of Windows. Support for the 32-bit version of the Microsoft Azure Active Directory Module for Windows PowerShell ended in 2014.</span></span>

<span data-ttu-id="a2906-117">Você pode usar as seguintes versões do Windows:</span><span class="sxs-lookup"><span data-stu-id="a2906-117">You can use the following versions of Windows:</span></span>
    
  - <span data-ttu-id="a2906-118">Windows 10, Windows 8.1, Windows 8 ou Windows 7 Service Pack 1 (SP1)</span><span class="sxs-lookup"><span data-stu-id="a2906-118">Windows 10, Windows 8.1, Windows 8, or Windows 7 Service Pack 1 (SP1)</span></span> 
    
  - <span data-ttu-id="a2906-119">Windows Server 2019, Windows Server 2016, Windows Server 2012 R2, Windows Server 2012, or Windows Server 2008 R2 SP1</span><span class="sxs-lookup"><span data-stu-id="a2906-119">Windows Server 2019, Windows Server 2016, Windows Server 2012 R2, Windows Server 2012, or Windows Server 2008 R2 SP1</span></span>

>[!Note]
><span data-ttu-id="a2906-120">Para Windows 8.1, Windows 8, Windows 7 Service Pack 1 (SP1), Windows Server 2012 R2, Windows Server 2012, e Windows Server 2008 R2 SP1, baixe e instale o [Windows Management Framework 5.1](https://www.microsoft.com/download/details.aspx?id=54616).</span><span class="sxs-lookup"><span data-stu-id="a2906-120">For Windows 8.1, Windows 8, Windows 7 Service Pack 1 (SP1), Windows Server 2012 R2, Windows Server 2012, and Windows Server 2008 R2 SP1, download and install the [Windows Management Framework 5.1](https://www.microsoft.com/download/details.aspx?id=54616).</span></span>

<span data-ttu-id="a2906-121">**PowerShell**</span><span class="sxs-lookup"><span data-stu-id="a2906-121">**PowerShell**</span></span>

- <span data-ttu-id="a2906-122">Para o módulo do Windows PowerShell do Azure Active Directory para Graph, você deve usar o Windows PowerShell versão 5.1 ou posterior.</span><span class="sxs-lookup"><span data-stu-id="a2906-122">For the Azure Active Directory PowerShell for Graph module, you must use PowerShell version 5.1 or later.</span></span>

- <span data-ttu-id="a2906-p104">Para o Módulo Microsoft Azure Active Directory para Windows PowerShell, você deve usar o PowerShell versão 5.1 ou posterior, até o PowerShell versão 6. Você não pode usar o PowerShell versão 7.</span><span class="sxs-lookup"><span data-stu-id="a2906-p104">For the Microsoft Azure Active Directory Module for Windows PowerShell module, you must use PowerShell version 5.1 or later, up to PowerShell version 6. You can't use PowerShell version 7.</span></span>
       
>[!Note]
><span data-ttu-id="a2906-125">Esses procedimentos são destinados aos usuários que são membros de uma função de administrador do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a2906-125">These procedures are intended for users who are members of a Microsoft 365 admin role.</span></span> <span data-ttu-id="a2906-126">Para obter mais informações, confira [Sobre funções de administrador](../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="a2906-126">For more information, see [About admin roles](../admin/add-users/about-admin-roles.md).</span></span>


## <a name="connect-with-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="a2906-127">Conecte-se ao Azure Active Directory PowerShell para o módulo do Graph.</span><span class="sxs-lookup"><span data-stu-id="a2906-127">Connect with the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="a2906-128">Os comandos no módulo do PowerShell do Azure Active Directory para Graph têm o *AzureAD* no nome do cmdlet.</span><span class="sxs-lookup"><span data-stu-id="a2906-128">Commands in the Azure Active Directory PowerShell for Graph module have *AzureAD* in their cmdlet name.</span></span> <span data-ttu-id="a2906-129">Você pode instalar o módulo do [PowerShell do Azure Active Directory para Graph](/powershell/azure/active-directory/install-adv2) ou o [Azure PowerShell](/powershell/azure/install-az-ps).</span><span class="sxs-lookup"><span data-stu-id="a2906-129">You can install the [Azure Active Directory PowerShell for Graph](/powershell/azure/active-directory/install-adv2) module or [Azure PowerShell](/powershell/azure/install-az-ps).</span></span>

<span data-ttu-id="a2906-130">Para procedimentos que exigem os novos cmdlets no módulo Azure Active Directory Windows PowerShell para Graph, siga estas etapas para instalar o módulo e conectar-se à sua assinatura do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a2906-130">For procedures that require the new cmdlets in the Azure Active Directory PowerShell for Graph module, follow these steps to install the module and connect to your Microsoft 365 subscription.</span></span>

> [!Note]
> <span data-ttu-id="a2906-131">Confira o [Azure Active Directory PowerShell para o módulo do Graph](/powershell/azure/active-directory/install-adv2) para obter mais informações sobre o suporte a diferentes versões do Microsoft Windows.</span><span class="sxs-lookup"><span data-stu-id="a2906-131">For information about support for different versions of Windows, see [Azure Active Directory PowerShell for Graph module](/powershell/azure/active-directory/install-adv2) .</span></span>

### <a name="step-1-install-the-required-software"></a><span data-ttu-id="a2906-132">Etapa 1: instalar o software necessário</span><span class="sxs-lookup"><span data-stu-id="a2906-132">Step 1: Install the required software</span></span>

<span data-ttu-id="a2906-133">Estas etapas são necessárias apenas uma vez em seu computador.</span><span class="sxs-lookup"><span data-stu-id="a2906-133">These steps are required only one time on your computer.</span></span> <span data-ttu-id="a2906-134">Mas provavelmente você precisará atualizar o software periodicamente.</span><span class="sxs-lookup"><span data-stu-id="a2906-134">But you'll likely need to update the software periodically.</span></span>
  
1. <span data-ttu-id="a2906-135">Abra uma janela elevada do Prompt de Comando do Windows PowerShell (execute o Windows PowerShell como administrador).</span><span class="sxs-lookup"><span data-stu-id="a2906-135">Open an elevated Windows PowerShell Command Prompt window (run Windows PowerShell as an administrator).</span></span>
    
2. <span data-ttu-id="a2906-136">Execute este comando:</span><span class="sxs-lookup"><span data-stu-id="a2906-136">Run this command:</span></span>
    
    ```powershell
    Install-Module -Name AzureAD
    ```

  <span data-ttu-id="a2906-137">Por padrão, o PowerShell Gallery (PSGallery) não está configurado como um repositório confiável para **PowerShellGet**.</span><span class="sxs-lookup"><span data-stu-id="a2906-137">By default, the PowerShell Gallery (PSGallery) isn't configured as a trusted repository for **PowerShellGet**.</span></span> <span data-ttu-id="a2906-138">Na primeira vez que usar o PSGallery, você verá a seguinte mensagem:</span><span class="sxs-lookup"><span data-stu-id="a2906-138">The first time you use the PSGallery, you'll see the following message:</span></span>

```console
Untrusted repository

You are installing the modules from an untrusted repository. If you trust this repository, change
its InstallationPolicy value by running the `Set-PSRepository` cmdlet.

Are you sure you want to install the modules from 'PSGallery'?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "N"):
```

<span data-ttu-id="a2906-139">Responda **Sim** ou **Sim** para todos para continuar com a instalação.</span><span class="sxs-lookup"><span data-stu-id="a2906-139">Answer **Yes** or **Yes to All** to continue with the installation.</span></span>


### <a name="step-2-connect-to-azure-ad-for-your-microsoft-365-subscription"></a><span data-ttu-id="a2906-140">Etapa 2: Conectar-se ao Azure AD da sua assinatura do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="a2906-140">Step 2: Connect to Azure AD for your Microsoft 365 subscription</span></span>

<span data-ttu-id="a2906-p109">Para se conectar ao Azure Active Directory (Azure AD) da sua assinatura do Microsoft 365 com um nome de usuário e senha, ou com a autenticação multifator (MFA), execute um destes comandos de um prompt de comando do Windows PowerShell (não é necessário ser privilegiado).</span><span class="sxs-lookup"><span data-stu-id="a2906-p109">To connect to Azure Active Directory (Azure AD) for your Microsoft 365 subscription with an account name and password or with multi-factor authentication, run one of these commands from a Windows PowerShell command prompt. (It doesn't have to be elevated.)</span></span>

| <span data-ttu-id="a2906-143">Nuvem do Office 365</span><span class="sxs-lookup"><span data-stu-id="a2906-143">Office 365 cloud</span></span> | <span data-ttu-id="a2906-144">Comando</span><span class="sxs-lookup"><span data-stu-id="a2906-144">Command</span></span> |
|:-------|:-----|
| <span data-ttu-id="a2906-145">Office 365 no Mundo (+GCC)</span><span class="sxs-lookup"><span data-stu-id="a2906-145">Office 365 Worldwide (+GCC)</span></span> | `Connect-AzureAD` |
| <span data-ttu-id="a2906-146">Office 365 operado pela 21 Vianet</span><span class="sxs-lookup"><span data-stu-id="a2906-146">Office 365 operated by 21 Vianet</span></span> | `Connect-AzureAD -AzureEnvironmentName AzureChinaCloud` |
| <span data-ttu-id="a2906-147">Office 365 Germany</span><span class="sxs-lookup"><span data-stu-id="a2906-147">Office 365 Germany</span></span> | `Connect-AzureAD -AzureEnvironmentName AzureGermanyCloud` |
| <span data-ttu-id="a2906-148">Office 365 U.S. Government DoD e Office 365 U.S. Government GCC High</span><span class="sxs-lookup"><span data-stu-id="a2906-148">Office 365 U.S. Government DoD and Office 365 U.S. Government GCC High</span></span> | `Connect-AzureAD -AzureEnvironmentName AzureUSGovernment` |
|||

<span data-ttu-id="a2906-149">Na caixa de diálogo **Entrar na sua conta**, digite seu nome de usuário e senha da conta corporativa ou de estudante do Microsoft 365 e selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="a2906-149">In the **Sign into your account** dialog box, type your Microsoft 365 work or school account user name and password, and then select **OK**.</span></span>

<span data-ttu-id="a2906-150">Se você estiver usando a autenticação multifator, siga as instruções para fornecer informações adicionais de autenticação, como um código de verificação.</span><span class="sxs-lookup"><span data-stu-id="a2906-150">If you're using multi-factor authentication, follow the instructions to provide additional authentication information, such as a verification code.</span></span>

<span data-ttu-id="a2906-151">Depois de se conectar, você pode usar os cmdlets para o [módulo Azure Active Directory Windows PowerShell para Graph](/powershell/module/azuread).</span><span class="sxs-lookup"><span data-stu-id="a2906-151">After you connect, you can use the cmdlets for the [Azure Active Directory PowerShell for Graph module](/powershell/module/azuread).</span></span>

## <a name="connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="a2906-152">Conecte com o Módulo Microsoft Azure Active Directory para Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="a2906-152">Connect with the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

>[!Note]
><span data-ttu-id="a2906-153">Os cmdlets no Módulo Microsoft Azure Active Directory para Windows PowerShell têm *Msol* em seus nomes.</span><span class="sxs-lookup"><span data-stu-id="a2906-153">Cmdlets in the Microsoft Azure Active Directory Module for Windows PowerShell have *Msol* in their name.</span></span>

<span data-ttu-id="a2906-154">O PowerShell versão 7 e posterior não oferece suporte ao Módulo Microsoft Azure Active Directory para Windows PowerShell e cmdlets com *Msol* em seus nomes.</span><span class="sxs-lookup"><span data-stu-id="a2906-154">PowerShell version 7 and later don't support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with *Msol* in their name.</span></span> <span data-ttu-id="a2906-155">Para o PowerShell versão 7 e posterior, você deve usar o módulo do PowerShell do Azure Active Directory para Graph ou o Azure PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a2906-155">For PowerShell version 7 and later, you must use the Azure Active Directory PowerShell for Graph module or Azure PowerShell.</span></span>

<span data-ttu-id="a2906-156">O PowerShell Core não oferece suporte ao Módulo Microsoft Azure Active Directory para Windows PowerShell para o módulo do Windows PowerShell e cmdlets com *Msol* em seus nomes.</span><span class="sxs-lookup"><span data-stu-id="a2906-156">PowerShell Core doesn't support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with *Msol* in their name.</span></span> <span data-ttu-id="a2906-157">Execute esses cmdlets do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a2906-157">Run these cmdlets from Windows PowerShell.</span></span>
    
### <a name="step-1-install-the-required-software"></a><span data-ttu-id="a2906-158">Etapa 1: instalar o software necessário</span><span class="sxs-lookup"><span data-stu-id="a2906-158">Step 1: Install the required software</span></span>

<span data-ttu-id="a2906-159">Estas etapas são necessárias apenas uma vez em seu computador.</span><span class="sxs-lookup"><span data-stu-id="a2906-159">These steps are required only one time on your computer.</span></span> <span data-ttu-id="a2906-160">Mas provavelmente você precisará atualizar o software periodicamente.</span><span class="sxs-lookup"><span data-stu-id="a2906-160">But you'll likely need to update the software periodically.</span></span>
  
1.  <span data-ttu-id="a2906-161">Se você não estiver executando o Windows 10, instale a versão de 64 bits do Assistente de Conexão do Microsoft Online Services: [Assistente de Conexão do Microsoft Online Services para Profissionais de TI RTW](https://download.microsoft.com/download/7/1/E/71EF1D05-A42C-4A1F-8162-96494B5E615C/msoidcli_32bit.msi).</span><span class="sxs-lookup"><span data-stu-id="a2906-161">If you're not running Windows 10, install the 64-bit version of the Microsoft Online Services Sign-in Assistant: [Microsoft Online Services Sign-in Assistant for IT Professionals RTW](https://download.microsoft.com/download/7/1/E/71EF1D05-A42C-4A1F-8162-96494B5E615C/msoidcli_32bit.msi).</span></span>
    
2. <span data-ttu-id="a2906-162">Siga estas etapas para instalar o Módulo Microsoft Azure Active Directory para Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="a2906-162">Follow these steps to install the Microsoft Azure Active Directory Module for Windows PowerShell:</span></span>
    
   1. <span data-ttu-id="a2906-163">Abra um prompt de comando privilegiado do Windows PowerShell (execute o Windows PowerShell como administrador).</span><span class="sxs-lookup"><span data-stu-id="a2906-163">Open an elevated Windows PowerShell command prompt (run Windows PowerShell as an administrator).</span></span>
   1.  <span data-ttu-id="a2906-164">Execute o comando **Install-Module MSOnline**.</span><span class="sxs-lookup"><span data-stu-id="a2906-164">Run the **Install-Module MSOnline** command.</span></span>
   1. <span data-ttu-id="a2906-165">Se você for solicitado a instalar o provedor NuGet, digite **S** e pressione Enter.</span><span class="sxs-lookup"><span data-stu-id="a2906-165">If you're prompted to install the NuGet provider, type **Y** and press Enter.</span></span>
   1. <span data-ttu-id="a2906-166">Se você for solicitado a instalar o módulo do PSGallery, digite **S** e pressione Enter.</span><span class="sxs-lookup"><span data-stu-id="a2906-166">If you're prompted to install the module from PSGallery, type **Y** and press Enter.</span></span>
    
### <a name="step-2-connect-to-azure-ad-for-your-microsoft-365-subscription"></a><span data-ttu-id="a2906-167">Etapa 2: Conectar-se ao Azure AD da sua assinatura do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="a2906-167">Step 2: Connect to Azure AD for your Microsoft 365 subscription</span></span>

<span data-ttu-id="a2906-p113">Para se conectar ao Azure AD da sua assinatura do Microsoft 365 com um nome de usuário e senha, ou com a autenticação multifator (MFA), execute um destes comandos de um prompt de comando do Windows PowerShell (não é necessário ser privilegiado).</span><span class="sxs-lookup"><span data-stu-id="a2906-p113">To connect to Azure AD for your Microsoft 365 subscription with an account name and password or with multi-factor authentication, run one of these commands from a Windows PowerShell command prompt. (It doesn't have to be elevated.)</span></span>

| <span data-ttu-id="a2906-170">Nuvem do Office 365</span><span class="sxs-lookup"><span data-stu-id="a2906-170">Office 365 cloud</span></span> | <span data-ttu-id="a2906-171">Comando</span><span class="sxs-lookup"><span data-stu-id="a2906-171">Command</span></span> |
|:-------|:-----|
| <span data-ttu-id="a2906-172">Office 365 no Mundo (+GCC)</span><span class="sxs-lookup"><span data-stu-id="a2906-172">Office 365 Worldwide (+GCC)</span></span> | `Connect-MsolService` |
| <span data-ttu-id="a2906-173">Office 365 operado pela 21 Vianet</span><span class="sxs-lookup"><span data-stu-id="a2906-173">Office 365 operated by 21 Vianet</span></span> | `Connect-MsolService -AzureEnvironment AzureChinaCloud` |
| <span data-ttu-id="a2906-174">Office 365 Germany</span><span class="sxs-lookup"><span data-stu-id="a2906-174">Office 365 Germany</span></span> | `Connect-MsolService -AzureEnvironment AzureGermanyCloud` |
| <span data-ttu-id="a2906-175">Office 365 U.S. Government DoD e Office 365 U.S. Government GCC High</span><span class="sxs-lookup"><span data-stu-id="a2906-175">Office 365 U.S. Government DoD and Office 365 U.S. Government GCC High</span></span> | `Connect-MsolService -AzureEnvironment USGovernment` |
|||

<span data-ttu-id="a2906-176">Na caixa de diálogo **Entrar na sua conta**, digite seu nome de usuário e senha da conta corporativa ou de estudante do Microsoft 365 e selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="a2906-176">In the **Sign into your account** dialog box, type your Microsoft 365 work or school account user name and password, and then select **OK**.</span></span>

<span data-ttu-id="a2906-177">Se você estiver usando a autenticação multifator, siga as instruções para fornecer informações adicionais de autenticação, como um código de verificação.</span><span class="sxs-lookup"><span data-stu-id="a2906-177">If you're using multi-factor authentication, follow the instructions to provide additional authentication information, such as a verification code.</span></span>

### <a name="how-do-you-know-it-worked"></a><span data-ttu-id="a2906-178">Como saber se funcionou?</span><span class="sxs-lookup"><span data-stu-id="a2906-178">How do you know it worked?</span></span>

<span data-ttu-id="a2906-179">Se você não receber uma mensagem de erro, você se conectou com êxito.</span><span class="sxs-lookup"><span data-stu-id="a2906-179">If you don't get an error message, you connected successfully.</span></span> <span data-ttu-id="a2906-180">Para um teste rápido, execute um cmdlet do Microsoft 365, como **Get-MsolUser**, e confira os resultados.</span><span class="sxs-lookup"><span data-stu-id="a2906-180">For quick test,  run a Microsoft 365 cmdlet, such as  **Get-MsolUser**, and see the results.</span></span>
  
<span data-ttu-id="a2906-181">Se você receber uma mensagem de erro, cheque os seguintes problemas:</span><span class="sxs-lookup"><span data-stu-id="a2906-181">If you get an error message, check the following issues:</span></span>
  
- <span data-ttu-id="a2906-182">**Senha incorreta é um problema comum**.</span><span class="sxs-lookup"><span data-stu-id="a2906-182">**A common problem is an incorrect password**.</span></span> <span data-ttu-id="a2906-183">Execute a [Etapa 2](#step-2-connect-to-azure-ad-for-your-microsoft-365-subscription) novamente e preste muita atenção ao nome de usuário e senha que você inserir.</span><span class="sxs-lookup"><span data-stu-id="a2906-183">Run [Step 2](#step-2-connect-to-azure-ad-for-your-microsoft-365-subscription) again, and pay close attention to the user name and password that you enter.</span></span>
    
- <span data-ttu-id="a2906-184">**O Módulo Microsoft Azure Active Directory para Windows PowerShell requer o Microsoft .NET Framework 3.5.* x* está ativado em seu computador **. É provável que seu computador tenha uma versão mais recente instalada (por exemplo, 4 ou 4.5.* x*).</span><span class="sxs-lookup"><span data-stu-id="a2906-184">**The Microsoft Azure Active Directory Module for Windows PowerShell requires that Microsoft .NET Framework 3.5.* x* is enabled on your computer**. It's likely that your computer has a newer version installed (for example, 4 or 4.5.* x*).</span></span> <span data-ttu-id="a2906-185">Mas a compatibilidade com versões anteriores do .NET Framework pode ser habilitada ou desabilitada.</span><span class="sxs-lookup"><span data-stu-id="a2906-185">But backward compatibility with older versions of the .NET Framework can be enabled or disabled.</span></span> <span data-ttu-id="a2906-186">Para saber mais, confira os seguintes artigos:</span><span class="sxs-lookup"><span data-stu-id="a2906-186">For more information, see the following articles:</span></span>
    
  - <span data-ttu-id="a2906-187">Para Windows Server 2012 ou Windows Server 2012 R2, confira [Habilitar o .NET Framework 3.5 usando o Assistente de Adição de Funções e Recursos](/previous-versions/windows/it-pro/windows-8.1-and-8/dn482071(v=win.10)).</span><span class="sxs-lookup"><span data-stu-id="a2906-187">For Windows Server 2012 or Windows Server 2012 R2, see [Enable .NET Framework 3.5 by using the Add Roles and Features Wizard](/previous-versions/windows/it-pro/windows-8.1-and-8/dn482071(v=win.10)).</span></span>
    
  - <span data-ttu-id="a2906-188">Para Windows 7 ou Windows Server 2008 R2, confira [Não é possível abrir o Módulo Azure Active Directory para Windows PowerShell](/troubleshoot/azure/active-directory/cant-open-aad-module-powershell).</span><span class="sxs-lookup"><span data-stu-id="a2906-188">For Windows 7 or Windows Server 2008 R2, see [You can't open the Azure Active Directory Module for Windows PowerShell](/troubleshoot/azure/active-directory/cant-open-aad-module-powershell).</span></span>

  - <span data-ttu-id="a2906-189">Para Windows 10, Windows 8.1 e Windows 8, confira [Instalar o .NET Framework 3.5 no Windows 10, Windows 8.1 e Windows 8](/dotnet/framework/install/dotnet-35-windows-10)</span><span class="sxs-lookup"><span data-stu-id="a2906-189">For Windows 10, Windows 8.1, and Windows 8, see [Install the .NET Framework 3.5 on Windows 10, Windows 8.1, and Windows 8](/dotnet/framework/install/dotnet-35-windows-10).</span></span>

  
- <span data-ttu-id="a2906-190">**Sua versão do Módulo Microsoft Azure Active Directory para Windows PowerShell pode estar desatualizada.**</span><span class="sxs-lookup"><span data-stu-id="a2906-190">**Your version of the Microsoft Azure Active Directory Module for Windows PowerShell might be out of date.**</span></span> <span data-ttu-id="a2906-191">Para verificar, execute o seguinte comando no PowerShell para o Microsoft 365 ou no Módulo Microsoft Azure Active Directory para Windows PowerShell :</span><span class="sxs-lookup"><span data-stu-id="a2906-191">To check, run the following command in PowerShell for Microsoft 365 or the Microsoft Azure Active Directory Module for Windows PowerShell:</span></span>
    
  ```powershell
  (Get-Item C:\Windows\System32\WindowsPowerShell\v1.0\Modules\MSOnline\Microsoft.Online.Administration.Automation.PSModule.dll).VersionInfo.FileVersion
  ```

    <span data-ttu-id="a2906-192">Se o número da versão retornado for inferior a *1.0.8070.2*, desinstale o Módulo Microsoft Azure Active Directory para Windows PowerShell e instale a partir da [Etapa 1](#step-1-install-the-required-software), acima.</span><span class="sxs-lookup"><span data-stu-id="a2906-192">If the version number returned is lower than *1.0.8070.2*, uninstall the Microsoft Azure Active Directory Module for Windows PowerShell and install from [Step 1](#step-1-install-the-required-software), above.</span></span>

- <span data-ttu-id="a2906-193">**Se você receber uma mensagem de erro de conexão**, confira [o erro "Connect-MsolService: Exceção de tipo lançada"](/office365/troubleshoot/active-directory/connect-msoservice-throw-exception).</span><span class="sxs-lookup"><span data-stu-id="a2906-193">**If you get a connection error message**, see ["Connect-MsolService: Exception of type was thrown" error](/office365/troubleshoot/active-directory/connect-msoservice-throw-exception).</span></span>
    
- <span data-ttu-id="a2906-194">**Se você receber uma mensagem de erro "Get-Item: Não é possível encontrar o caminho"**, execute este comando:</span><span class="sxs-lookup"><span data-stu-id="a2906-194">**If you get a "Get-Item: Cannot find path" error message**, run this command:</span></span>


   ```powershell
     (dir "C:\Program Files\WindowsPowerShell\Modules\MSOnline").Name
   ```

## <a name="see-also"></a><span data-ttu-id="a2906-195">Confira também</span><span class="sxs-lookup"><span data-stu-id="a2906-195">See also</span></span>

- [<span data-ttu-id="a2906-196">Gerenciar o Microsoft 365 com o PowerShell</span><span class="sxs-lookup"><span data-stu-id="a2906-196">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
- [<span data-ttu-id="a2906-197">Introdução ao Windows PowerShell para o Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="a2906-197">Get started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
- [<span data-ttu-id="a2906-198">Conectar-se a todos os serviços do Microsoft 365 usando uma única janela do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="a2906-198">Connect to all Microsoft 365 services in a single Windows PowerShell window</span></span>](connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window.md)
