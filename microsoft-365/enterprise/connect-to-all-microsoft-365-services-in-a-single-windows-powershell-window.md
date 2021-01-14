---
title: Conectar-se a todos os serviços do Microsoft 365 usando uma única janela do PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/10/2020
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- LIL_Placement
- Ent_Office_Other
- O365ITProTrain
- httpsfix
ms.assetid: 53d3eef6-4a16-4fb9-903c-816d5d98d7e8
description: 'Resumo: conectar-se a todos os serviços do Microsoft 365 usando uma única janela do PowerShell.'
ms.openlocfilehash: 4266b4f216b4c9df48f0c19d1d2123269eb32cae
ms.sourcegitcommit: 00d231bf0100e843a5a93161695e87ceff9e1349
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/13/2021
ms.locfileid: "49849583"
---
# <a name="connect-to-all-microsoft-365-services-in-a-single-powershell-window"></a><span data-ttu-id="4fe96-103">Conectar-se a todos os serviços do Microsoft 365 usando uma única janela do PowerShell</span><span class="sxs-lookup"><span data-stu-id="4fe96-103">Connect to all Microsoft 365 services in a single PowerShell window</span></span>

<span data-ttu-id="4fe96-104">Ao usar o Windows PowerShell para gerenciar o Microsoft 365, você pode ter várias sessões do PowerShell abertas ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="4fe96-104">When you use PowerShell to manage Microsoft 365, you can have multiple PowerShell sessions open at the same time.</span></span> <span data-ttu-id="4fe96-105">Você pode ter diferentes janelas do PowerShell para gerenciar contas de usuário, Microsoft Office SharePoint Online, Exchange Online, Skype for Business Online, Microsoft Teams e o &amp; Centro de Conformidade de Segurança.</span><span class="sxs-lookup"><span data-stu-id="4fe96-105">You might have different PowerShell windows to manage user accounts, SharePoint Online, Exchange Online, Skype for Business Online, Microsoft Teams, and the Security &amp; Compliance center.</span></span>
  
<span data-ttu-id="4fe96-106">Este cenário não é ideal para gerenciar o Microsoft 365, porque você não pode trocar dados entre essas janelas para gerenciamento entre serviços.</span><span class="sxs-lookup"><span data-stu-id="4fe96-106">This scenario isn't optimal for managing Microsoft 365, because you can't exchange data among those windows for cross-service management.</span></span> <span data-ttu-id="4fe96-107">Este artigo descreve como usar uma única instância do Windows PowerShell para gerenciar contas do Microsoft 365, Skype for Business Online, Exchange Online, Microsoft Office SharePoint Online, Microsoft Teams e o &amp; Centro de Conformidade de Segurança.</span><span class="sxs-lookup"><span data-stu-id="4fe96-107">This article describes how to use a single instance of PowerShell to manage Microsoft 365 accounts, Skype for Business Online, Exchange Online, SharePoint Online, Microsoft Teams, and the Security &amp; Compliance Center.</span></span>

>[!Note]
><span data-ttu-id="4fe96-108">Atualmente este artigo contém apenas os comandos necessários para se conectar com a nuvem mundial (+GCC).</span><span class="sxs-lookup"><span data-stu-id="4fe96-108">This article currently only contains the commands to connect to the Worldwide (+GCC) cloud.</span></span> <span data-ttu-id="4fe96-109">As notas fornecem links para artigos sobre conexão com outras nuvens do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4fe96-109">Notes provide links to articles about connecting to the other Microsoft 365 clouds.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="4fe96-110">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="4fe96-110">Before you begin</span></span>

<span data-ttu-id="4fe96-111">Antes que você possa gerenciar o Microsoft 365 inteiro a partir de uma única instância do PowerShell, considere os seguinte pré-requisitos:</span><span class="sxs-lookup"><span data-stu-id="4fe96-111">Before you can manage all of Microsoft 365 from a single instance of PowerShell, consider the following prerequisites:</span></span>
  
- <span data-ttu-id="4fe96-112">A conta corporativa ou de estudante do Microsoft 365 que você usa deve ser membro de uma função de administrador do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4fe96-112">The Microsoft 365 work or school account that you use must be a member of a Microsoft 365 admin role.</span></span> <span data-ttu-id="4fe96-113">Para obter mais informações, confira o artigo [Sobre funções de administrador](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="4fe96-113">For more information, see [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span> <span data-ttu-id="4fe96-114">Este é um requisito do Windows PowerShell para Microsoft 365, mas não necessariamente para todos os outros serviços do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4fe96-114">This is a requirement for PowerShell for Microsoft 365, but not necessarily for all other Microsoft 365 services.</span></span>
    
- <span data-ttu-id="4fe96-115">Você pode usar as seguintes versões de 64 bits do Windows:</span><span class="sxs-lookup"><span data-stu-id="4fe96-115">You can use the following 64-bit versions of Windows:</span></span>
    
  - <span data-ttu-id="4fe96-116">Windows 10</span><span class="sxs-lookup"><span data-stu-id="4fe96-116">Windows 10</span></span>
    
  - <span data-ttu-id="4fe96-117">Windows 8.1 ou Windows 8</span><span class="sxs-lookup"><span data-stu-id="4fe96-117">Windows 8.1 or Windows 8</span></span>
    
  - <span data-ttu-id="4fe96-118">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="4fe96-118">Windows Server 2019</span></span>
    
  - <span data-ttu-id="4fe96-119">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="4fe96-119">Windows Server 2016</span></span>
    
  - <span data-ttu-id="4fe96-120">Windows Server 2012 R2 ou Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="4fe96-120">Windows Server 2012 R2 or Windows Server 2012</span></span>
    
  - <span data-ttu-id="4fe96-121">Windows 7 Service Pack 1 (SP1)\*</span><span class="sxs-lookup"><span data-stu-id="4fe96-121">Windows 7 Service Pack 1 (SP1)\*</span></span>
    
  - <span data-ttu-id="4fe96-122">Windows Server 2008 R2 SP1\*</span><span class="sxs-lookup"><span data-stu-id="4fe96-122">Windows Server 2008 R2 SP1\*</span></span>
    
    <span data-ttu-id="4fe96-123">\* É necessário instalar o Microsoft .NET Framework 4.5. *x* e o Windows Management Framework 3.0 ou 4.0.</span><span class="sxs-lookup"><span data-stu-id="4fe96-123">\* You need to install Microsoft .NET Framework 4.5.*x* and then Windows Management Framework 3.0 or 4.0.</span></span> <span data-ttu-id="4fe96-124">Para obter mais informações, confira [Windows Management Framework](https://docs.microsoft.com/powershell/scripting/windows-powershell/wmf/overview?view=powershell-7).</span><span class="sxs-lookup"><span data-stu-id="4fe96-124">For more information, see [Windows Management Framework](https://docs.microsoft.com/powershell/scripting/windows-powershell/wmf/overview?view=powershell-7).</span></span>
    
    <span data-ttu-id="4fe96-125">É preciso usar a versão de 64 bits do Windows devido aos requisitos do módulo do Skype for Business Online e de um dos módulos do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4fe96-125">You need to use a 64-bit version of Windows because of the requirements for the Skype for Business Online module and one of the Microsoft 365 modules.</span></span>
    
- <span data-ttu-id="4fe96-126">É preciso instalar os módulos necessários para o Azure Active Directory (Azure AD), o Exchange Online, o SharePoint Online, o Skype for Business Online e o Teams:</span><span class="sxs-lookup"><span data-stu-id="4fe96-126">You need to install the modules that are required for Azure Active Directory (Azure AD), Exchange Online, SharePoint Online, Skype for Business Online and Teams:</span></span>
    
  - [<span data-ttu-id="4fe96-127">Azure Active Directory V2</span><span class="sxs-lookup"><span data-stu-id="4fe96-127">Azure Active Directory V2</span></span>](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)
  - [<span data-ttu-id="4fe96-128">Shell de Gerenciamento do SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="4fe96-128">SharePoint Online Management Shell</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=255251)
  - [<span data-ttu-id="4fe96-129">Skype for Business Online, módulo do PowerShell</span><span class="sxs-lookup"><span data-stu-id="4fe96-129">Skype for Business Online, PowerShell Module</span></span>](https://docs.microsoft.com/microsoftteams/teams-powershell-overview)
  - [<span data-ttu-id="4fe96-130">PowerShell do Exchange Online V2</span><span class="sxs-lookup"><span data-stu-id="4fe96-130">Exchange Online PowerShell V2</span></span>](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell-v2#install-and-maintain-the-exchange-online-powershell-v2-module)
  - [<span data-ttu-id="4fe96-131">Visão Geral do PowerShell do Teams</span><span class="sxs-lookup"><span data-stu-id="4fe96-131">Teams PowerShell Overview</span></span>](https://docs.microsoft.com/microsoftteams/teams-powershell-overview)
    
-  <span data-ttu-id="4fe96-132">O Windows PowerShell deve ser configurado para executar scripts assinados para o Cliente Skype® for Business Online e o &amp; Centro de Conformidade de Segurança.</span><span class="sxs-lookup"><span data-stu-id="4fe96-132">PowerShell must be configured to run signed scripts for Skype for Business Online and the Security &amp; Compliance Center.</span></span> <span data-ttu-id="4fe96-133">Execute o seguinte comando em uma sessão Windows PowerShell elevada (uma sessão PowerShell que você **Executa como administrador**).</span><span class="sxs-lookup"><span data-stu-id="4fe96-133">Run the following command in an elevated PowerShell session (a PowerShell session that you **Run as administrator**).</span></span>
    
   ```powershell
   Set-ExecutionPolicy RemoteSigned
   ```

## <a name="exchange-online-and-security-amp-compliance-center-with-the-exchange-online-powershell-v2-module"></a><span data-ttu-id="4fe96-134">O Exchange Online e o &amp; Centro de Conformidade de Segurança com o módulo do Windows PowerShell V2 do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="4fe96-134">Exchange Online and Security &amp; Compliance Center with the Exchange Online PowerShell V2 module</span></span>

<span data-ttu-id="4fe96-135">Os procedimentos neste artigo usam o módulo Exchange Online Windows PowerShell V2 para ambos se conectarem ao Exchange Online e ao &amp; Centro de Conformidade de Segurança.</span><span class="sxs-lookup"><span data-stu-id="4fe96-135">The procedures in this article use the Exchange Online PowerShell V2 module to connect to both Exchange Online and the Security &amp; Compliance Center.</span></span> <span data-ttu-id="4fe96-136">Mas atualmente você não pode se conectar a ambos *na mesma janela do Windows PowerShell*.</span><span class="sxs-lookup"><span data-stu-id="4fe96-136">But currently you can't connect to both *in the same PowerShell window*.</span></span> <span data-ttu-id="4fe96-137">Portanto, você deve escolher se conectar a um ou outro ao configurar uma janela do PowerShell para vários serviços do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4fe96-137">So you have to choose to connect to one or the other when you configure a PowerShell window for multiple Microsoft 365 services.</span></span>

## <a name="connection-steps-when-using-just-a-password"></a><span data-ttu-id="4fe96-138">Etapas de conexão quando estiver usando apenas uma senha</span><span class="sxs-lookup"><span data-stu-id="4fe96-138">Connection steps when using just a password</span></span>

<span data-ttu-id="4fe96-139">Siga estas etapas para se conectar a todos os serviços em uma única janela do PowerShell quando estiver usando apenas uma senha para entrar.</span><span class="sxs-lookup"><span data-stu-id="4fe96-139">Follow these steps to connect to all the services in a single PowerShell window when you're using just a password for sign-in.</span></span>
  
1. <span data-ttu-id="4fe96-140">Abra o PowerShell do Windows.</span><span class="sxs-lookup"><span data-stu-id="4fe96-140">Open Windows PowerShell.</span></span>
    
2. <span data-ttu-id="4fe96-141">Execute este comando e digite as credenciais da sua conta corporativa ou de estudante do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4fe96-141">Run this command and enter your Microsoft 365 work or school account credentials.</span></span>
    
   ```powershell
   $credential = Get-Credential
   ```

3. <span data-ttu-id="4fe96-142">Execute este comando para se conectar ao Azure AD usando o módulo Azure Active Directory Windows PowerShell para Graph.</span><span class="sxs-lookup"><span data-stu-id="4fe96-142">Run this command to connect to Azure AD by using the Azure Active Directory PowerShell for Graph module.</span></span>
    
   ```powershell
   Connect-AzureAD -Credential $credential
   ```
  
   <span data-ttu-id="4fe96-143">Ou se você estiver usando o Módulo Microsoft Azure Active Directory para Windows PowerShell, execute este comando.</span><span class="sxs-lookup"><span data-stu-id="4fe96-143">Or if you're using the Microsoft Azure Active Directory Module for Windows PowerShell module, run this command.</span></span>
      
   ```powershell
   Connect-MsolService -Credential $credential
   ```

   > [!Note]
   > <span data-ttu-id="4fe96-144">O PowerShell Core não oferece suporte ao Módulo Microsoft Azure Active Directory para Windows PowerShell para o módulo do Windows PowerShell e cmdlets com *Msol* em seus nomes.</span><span class="sxs-lookup"><span data-stu-id="4fe96-144">PowerShell Core doesn't support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with *Msol* in their name.</span></span> <span data-ttu-id="4fe96-145">Você deve executar esses cmdlets do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4fe96-145">You must run these cmdlets from PowerShell.</span></span>

4. <span data-ttu-id="4fe96-146">Execute estes comandos para se conectar ao SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="4fe96-146">Run these commands to connect to SharePoint Online.</span></span> <span data-ttu-id="4fe96-147">Especifique o nome da organização para o seu domínio.</span><span class="sxs-lookup"><span data-stu-id="4fe96-147">Specify the organization name for your domain.</span></span> <span data-ttu-id="4fe96-148">Por exemplo, para "litwareinc\.onmicrosoft.com", o valor do nome da organização é "litwareinc".</span><span class="sxs-lookup"><span data-stu-id="4fe96-148">For example, for "litwareinc\.onmicrosoft.com", the  organization name value is "litwareinc".</span></span>
    
   ```powershell
   $orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
   Connect-SPOService -Url https://$orgName-admin.sharepoint.com -Credential $Credential
   ```

5. <span data-ttu-id="4fe96-149">Execute esses comandos para se conectar ao Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="4fe96-149">Run these commands to connect to Skype for Business Online.</span></span> <span data-ttu-id="4fe96-150">Um aviso sobre o aumento do valor de `WSMan NetworkDelayms` aparecerá na primeira vez que você se conectar.</span><span class="sxs-lookup"><span data-stu-id="4fe96-150">A warning about increasing the `WSMan NetworkDelayms` value will appear the first time that you connect.</span></span> <span data-ttu-id="4fe96-151">Ignore isto.</span><span class="sxs-lookup"><span data-stu-id="4fe96-151">Ignore it.</span></span>
     
   > [!Note]
   > <span data-ttu-id="4fe96-152">O Conector Skype for Business Online atualmente faz parte do módulo mais recente do PowerShell do Teams.</span><span class="sxs-lookup"><span data-stu-id="4fe96-152">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span> <span data-ttu-id="4fe96-153">Se você estiver usando o último lançamento público do PowerShell Teams, você não precisa instalar o Conector do Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="4fe96-153">If you're using the latest Teams PowerShell public release, you don't need to install the Skype for Business Online Connector.</span></span>
   
   ```powershell
   Import-Module MicrosoftTeams
   $sfboSession = New-CsOnlineSession -Credential $credential
   Import-PSSession $sfboSession
   ```

6. <span data-ttu-id="4fe96-154">Execute este comando para se conectar ao Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="4fe96-154">Run this command to connect to Exchange Online.</span></span>
    
   ```powershell
   Import-Module ExchangeOnlineManagement
   Connect-ExchangeOnline -Credential $credential -ShowProgress $true
   ```

   > [!Note]
   > <span data-ttu-id="4fe96-155">Para se conectar às nuvens do Exchange Online para Microsoft 365 que não sejam Mundiais, confira[Conectar ao PowerShell do Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="4fe96-155">To connect to Exchange Online for Microsoft 365 clouds other than Worldwide, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

   <span data-ttu-id="4fe96-156">Como alternativa, execute estes comandos para se conectar ao &amp; Centro de Conformidade de Segurança.</span><span class="sxs-lookup"><span data-stu-id="4fe96-156">Alternatively, run these commands to connect to the Security &amp; Compliance Center.</span></span>
    
   ```powershell
   $acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
   Import-Module ExchangeOnlineManagement
   Connect-IPPSSession -UserPrincipalName $acctName
   ```

   > [!Note]
   > <span data-ttu-id="4fe96-157">Para se conectar às nuvens do Centro de Conformidade &amp; e Segurança do Microsoft 365 que não sejam Mundiais, confira o artigo [Conectar-se ao PowerShell do Centro de Conformidade e Segurança](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span><span class="sxs-lookup"><span data-stu-id="4fe96-157">To connect to the Security &amp; Compliance Center for Microsoft 365 clouds other than Worldwide, see [Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span></span>

   <span data-ttu-id="4fe96-158">Execute estes comandos para se conectar ao PowerShell do Teams.</span><span class="sxs-lookup"><span data-stu-id="4fe96-158">Run these commands to connect to Teams PowerShell.</span></span>
    
   ```powershell
   Import-Module MicrosoftTeams
   Connect-MicrosoftTeams -Credential $credential
   ```
  
   > [!Note]
   > <span data-ttu-id="4fe96-159">Para se conectar a nuvens do Microsoft Teams que não sejam *Worldwide*, confira [Connect-MicrosoftTeams](https://docs.microsoft.com/powershell/module/teams/connect-microsoftteams).</span><span class="sxs-lookup"><span data-stu-id="4fe96-159">To connect to Microsoft Teams clouds other than *Worldwide*, see [Connect-MicrosoftTeams](https://docs.microsoft.com/powershell/module/teams/connect-microsoftteams).</span></span>


### <a name="azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="4fe96-160">Módulo do Azure Active Directory Windows PowerShell para Graph</span><span class="sxs-lookup"><span data-stu-id="4fe96-160">Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="4fe96-161">Aqui estão os comandos para todos os serviços *exceto &amp; Centro de Conformidade de Segurança* em um único bloco quando você usa o Azure Active Directory Windows PowerShell para módulo Graph.</span><span class="sxs-lookup"><span data-stu-id="4fe96-161">Here are the commands for all the services *except Security &amp; Compliance Center* in a single block when you use the Azure Active Directory PowerShell for Graph module.</span></span> <span data-ttu-id="4fe96-162">Especifique o nome do host de domínio e execute-os todos ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="4fe96-162">Specify the name of your domain host and run them all at the same time.</span></span>
  
```powershell
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
$credential = Get-Credential
Connect-AzureAD -Credential $credential
Import-Module Microsoft.Online.SharePoint.PowerShell -DisableNameChecking
Connect-SPOService -Url https://$orgName-admin.sharepoint.com -credential $credential
Import-Module MicrosoftTeams
$sfboSession = New-CsOnlineSession -Credential $credential
Import-PSSession $sfboSession
Import-Module ExchangeOnlineManagement
Connect-ExchangeOnline -Credential $credential -ShowProgress $true
Import-Module MicrosoftTeams
Connect-MicrosoftTeams -Credential $credential
```

<span data-ttu-id="4fe96-163">Aqui estão os comandos para todos os serviços *exceto Exchange Online* em um único bloco quando você usa o Azure Active Directory Windows PowerShell para o módulo Graph.</span><span class="sxs-lookup"><span data-stu-id="4fe96-163">Here are the commands for all the services *except Exchange Online* in a single block when you use the Azure Active Directory PowerShell for Graph module.</span></span> <span data-ttu-id="4fe96-164">Especifique o nome do host de domínio e o UPN para a entrada e execute-os todos ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="4fe96-164">Specify the name of your domain host and the UPN for the sign-in and run them all at the same time.</span></span>
  
```powershell
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$credential = Get-Credential -UserName $acctName
Connect-AzureAD -Credential $credential
Import-Module Microsoft.Online.SharePoint.PowerShell -DisableNameChecking
Connect-SPOService -Url https://$orgName-admin.sharepoint.com -credential $credential
Import-Module MicrosoftTeams
$sfboSession = New-CsOnlineSession -Credential $credential
Import-PSSession $sfboSession
Import-Module ExchangeOnlineManagement
Connect-IPPSSession -UserPrincipalName $acctName
Import-Module MicrosoftTeams
Connect-MicrosoftTeams -Credential $credential
```

### <a name="microsoft-azure-active-directory-module-for-windows-powershell-module"></a><span data-ttu-id="4fe96-165">Módulo Microsoft Azure Active Directory para Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="4fe96-165">Microsoft Azure Active Directory Module for Windows PowerShell module</span></span>

<span data-ttu-id="4fe96-166">Aqui estão os comandos para todos os serviços *exceto &amp; Centro de Conformidade de Segurança* em um único bloco quando você usa o Módulo Microsoft Azure Active Directory para Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4fe96-166">Here are the commands for all the services *except Security &amp; Compliance Center* in a single block when you use the Microsoft Azure Active Directory Module for Windows PowerShell module.</span></span> <span data-ttu-id="4fe96-167">Especifique o nome do host de domínio e execute-os todos de uma vez.</span><span class="sxs-lookup"><span data-stu-id="4fe96-167">Specify the name of your domain host and run them all at one time.</span></span>
  
```powershell
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
$credential = Get-Credential
Connect-MsolService -Credential $credential
Import-Module Microsoft.Online.SharePoint.PowerShell -DisableNameChecking
Connect-SPOService -Url https://$orgName-admin.sharepoint.com -credential $credential
Import-Module MicrosoftTeams
$sfboSession = New-CsOnlineSession -Credential $credential
Import-PSSession $sfboSession
Import-Module ExchangeOnlineManagement
Connect-ExchangeOnline -Credential $credential -ShowProgress $true
Import-Module MicrosoftTeams
Connect-MicrosoftTeams -Credential $credential
```

<span data-ttu-id="4fe96-168">Aqui estão os comandos para todos os serviços *exceto Exchange Online* em um único bloco quando você usa o Módulo Microsoft Azure Active Directory para Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4fe96-168">Here are the commands for all the services *except Exchange Online* in a single block when you use the Microsoft Azure Active Directory Module for Windows PowerShell module.</span></span> <span data-ttu-id="4fe96-169">Especifique o nome do host de domínio e o UPN para a entrada e execute-os todos de uma vez.</span><span class="sxs-lookup"><span data-stu-id="4fe96-169">Specify the name of your domain host and the UPN for the sign-in and run them all at one time.</span></span>
  
```powershell
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$credential = Get-Credential -UserName $acctName
Connect-AzureAD -Credential $credential
Import-Module Microsoft.Online.SharePoint.PowerShell -DisableNameChecking
Connect-SPOService -Url https://$orgName-admin.sharepoint.com -credential $credential
Import-Module MicrosoftTeams
$sfboSession = New-CsOnlineSession -Credential $credential
Import-PSSession $sfboSession
Import-Module ExchangeOnlineManagement
Connect-IPPSSession -UserPrincipalName $acctName
Import-Module MicrosoftTeams
Connect-MicrosoftTeams -Credential $credential
```
## <a name="connection-steps-when-using-multi-factor-authentication"></a><span data-ttu-id="4fe96-170">Etapas de conexão quando estiver usando a autenticação multifator</span><span class="sxs-lookup"><span data-stu-id="4fe96-170">Connection steps when using multi-factor authentication</span></span>

### <a name="azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="4fe96-171">Use o Windows PowerShell do Azure Active Directory para o módulo do Graph</span><span class="sxs-lookup"><span data-stu-id="4fe96-171">Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="4fe96-172">Aqui estão todos os comandos em um único bloco para se conectar a vários serviços do Microsoft 365 *exceto &amp; Centro de Conformidade de Segurança* quando você usa a autenticação multifator com o Azure Active Directory Windows PowerShell para módulo Graph.</span><span class="sxs-lookup"><span data-stu-id="4fe96-172">Here are all the commands in a single block to connect to multiple Microsoft 365 services *except Security &amp; Compliance Center* when you use multi-factor authentication with the Azure Active Directory PowerShell for Graph module.</span></span>

```powershell
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
#Azure Active Directory
Connect-AzureAD
#SharePoint Online
Connect-SPOService -Url https://$orgName-admin.sharepoint.com
#Skype for Business Online
Import-Module MicrosoftTeams
$sfboSession = New-CsOnlineSession
Import-PSSession $sfboSession
#Exchange Online
Import-Module ExchangeOnlineManagement
Connect-ExchangeOnline -UserPrincipalName $acctName -ShowProgress $true
#Teams
Import-Module MicrosoftTeams
Connect-MicrosoftTeams
```
<span data-ttu-id="4fe96-173">Aqui estão todos os comandos em um único bloco para conectar a vários serviços Microsoft 365 *exceto Exchange Online* com autenticação multifator quando você usa o Azure Active Directory Windows PowerShell para módulo Graph.</span><span class="sxs-lookup"><span data-stu-id="4fe96-173">Here are all the commands in a single block to connect to multiple Microsoft 365 services *except Exchange Online* with multi-factor authentication when you use the Azure Active Directory PowerShell for Graph module.</span></span>

```powershell
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
#Azure Active Directory
Connect-AzureAD
#SharePoint Online
Connect-SPOService -Url https://$orgName-admin.sharepoint.com
#Skype for Business Online
Import-Module MicrosoftTeams
$sfboSession = New-CsOnlineSession
Import-PSSession $sfboSession
#Security & Compliance Center
Import-Module ExchangeOnlineManagement
Connect-IPPSSession -UserPrincipalName $acctName
#Teams
Import-Module MicrosoftTeams
Connect-MicrosoftTeams
```
### <a name="microsoft-azure-active-directory-module-for-windows-powershell-module"></a><span data-ttu-id="4fe96-174">Módulo Microsoft Azure Active Directory para Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="4fe96-174">Microsoft Azure Active Directory Module for Windows PowerShell module</span></span>

<span data-ttu-id="4fe96-175">Aqui estão todos os comandos em um único bloco para se conectar a vários serviços do Microsoft 365 *exceto &amp; Centro de Conformidade de Segurança* quando você usa autenticação multifator com o Módulo Microsoft Azure Active Directory para Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4fe96-175">Here are all the commands in a single block to connect to multiple Microsoft 365 services *except Security &amp; Compliance Center* when you use multi-factor authentication with the Microsoft Azure Active Directory Module for Windows PowerShell module.</span></span>

```powershell
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
#Azure Active Directory
Connect-MsolService
#SharePoint Online
Connect-SPOService -Url https://$orgName-admin.sharepoint.com
#Skype for Business Online
Import-Module MicrosoftTeams
$sfboSession = New-CsOnlineSession
Import-PSSession $sfboSession
#Exchange Online
Import-Module ExchangeOnlineManagement
Connect-ExchangeOnline -UserPrincipalName $acctName -ShowProgress $true
#Teams
Import-Module MicrosoftTeams
Connect-MicrosoftTeams
```
<span data-ttu-id="4fe96-176">Aqui estão todos os comandos em um único bloco para se conectar a vários serviços Microsoft 365 *exceto Exchange Online* quando você usa autenticação multifator com o Módulo Microsoft Azure Active Directory para Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4fe96-176">Here are all the commands in a single block to connect to multiple Microsoft 365 services *except Exchange Online* when you use multi-factor authentication with the Microsoft Azure Active Directory Module for Windows PowerShell module.</span></span>

```powershell
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
#Azure Active Directory
Connect-MsolService
#SharePoint Online
Connect-SPOService -Url https://$orgName-admin.sharepoint.com
#Skype for Business Online
Import-Module MicrosoftTeams
$sfboSession = New-CsOnlineSession
Import-PSSession $sfboSession
#Security & Compliance Center
Import-Module ExchangeOnlineManagement
Connect-IPPSSession -UserPrincipalName $acctName
#Teams
Import-Module MicrosoftTeams
Connect-MicrosoftTeams
```

## <a name="close-the-powershell-window"></a><span data-ttu-id="4fe96-177">Fechar a janela do PowerShell</span><span class="sxs-lookup"><span data-stu-id="4fe96-177">Close the PowerShell window</span></span>

<span data-ttu-id="4fe96-178">Para fechar a janela do PowerShell, execute este comando para remover as sessões ativas do Skype for Business Online, Microsoft Office SharePoint Online e Teams:</span><span class="sxs-lookup"><span data-stu-id="4fe96-178">To close down the PowerShell window, run this command to remove the active sessions to Skype for Business Online, SharePoint Online, and Teams:</span></span>
  
```powershell
Remove-PSSession $sfboSession ; Disconnect-SPOService ; Disconnect-MicrosoftTeams 
```

## <a name="see-also"></a><span data-ttu-id="4fe96-179">Confira também</span><span class="sxs-lookup"><span data-stu-id="4fe96-179">See also</span></span>

- [<span data-ttu-id="4fe96-180">Conectar-se ao Microsoft 365 com o PowerShell</span><span class="sxs-lookup"><span data-stu-id="4fe96-180">Connect to Microsoft 365 with PowerShell</span></span>](connect-to-microsoft-365-powershell.md)
- [<span data-ttu-id="4fe96-181">Gerenciar o SharePoint Online com o PowerShell</span><span class="sxs-lookup"><span data-stu-id="4fe96-181">Manage SharePoint Online with PowerShell</span></span>](manage-sharepoint-online-with-microsoft-365-powershell.md)
- [<span data-ttu-id="4fe96-182">Gerenciar contas de usuário, licenças e grupos do Microsoft 365 com o PowerShell</span><span class="sxs-lookup"><span data-stu-id="4fe96-182">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
