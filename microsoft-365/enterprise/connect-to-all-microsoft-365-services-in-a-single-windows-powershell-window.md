---
title: Conectar-se a todos os serviços do Microsoft 365 usando uma única janela do PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 02/02/2021
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
ms.openlocfilehash: 390e2446737b4b85dfaba64974666fab4938a5dd
ms.sourcegitcommit: 4f40f5be140a23bacff6fd7b85536de14fc7d499
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2021
ms.locfileid: "50084596"
---
# <a name="connect-to-all-microsoft-365-services-in-a-single-powershell-window"></a><span data-ttu-id="f2930-103">Conectar-se a todos os serviços do Microsoft 365 usando uma única janela do PowerShell</span><span class="sxs-lookup"><span data-stu-id="f2930-103">Connect to all Microsoft 365 services in a single PowerShell window</span></span>

<span data-ttu-id="f2930-104">Ao usar o Windows PowerShell para gerenciar o Microsoft 365, você pode ter várias sessões do PowerShell abertas ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="f2930-104">When you use PowerShell to manage Microsoft 365, you can have multiple PowerShell sessions open at the same time.</span></span> <span data-ttu-id="f2930-105">Você pode ter diferentes janelas do PowerShell para gerenciar contas de usuário, Microsoft Office SharePoint Online, Exchange Online, Skype for Business Online, Microsoft Teams e o &amp; Centro de Conformidade de Segurança.</span><span class="sxs-lookup"><span data-stu-id="f2930-105">You might have different PowerShell windows to manage user accounts, SharePoint Online, Exchange Online, Skype for Business Online, Microsoft Teams, and the Security &amp; Compliance center.</span></span>
  
<span data-ttu-id="f2930-106">Este cenário não é ideal para gerenciar o Microsoft 365, porque você não pode trocar dados entre essas janelas para gerenciamento entre serviços.</span><span class="sxs-lookup"><span data-stu-id="f2930-106">This scenario isn't optimal for managing Microsoft 365, because you can't exchange data among those windows for cross-service management.</span></span> <span data-ttu-id="f2930-107">Este artigo descreve como usar uma única instância do Windows PowerShell para gerenciar contas do Microsoft 365, Skype for Business Online, Exchange Online, Microsoft Office SharePoint Online, Microsoft Teams e o &amp; Centro de Conformidade de Segurança.</span><span class="sxs-lookup"><span data-stu-id="f2930-107">This article describes how to use a single instance of PowerShell to manage Microsoft 365 accounts, Skype for Business Online, Exchange Online, SharePoint Online, Microsoft Teams, and the Security &amp; Compliance Center.</span></span>

>[!Note]
><span data-ttu-id="f2930-108">Atualmente este artigo contém apenas os comandos necessários para se conectar com a nuvem mundial (+GCC).</span><span class="sxs-lookup"><span data-stu-id="f2930-108">This article currently only contains the commands to connect to the Worldwide (+GCC) cloud.</span></span> <span data-ttu-id="f2930-109">As notas fornecem links para artigos sobre conexão com outras nuvens do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f2930-109">Notes provide links to articles about connecting to the other Microsoft 365 clouds.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="f2930-110">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="f2930-110">Before you begin</span></span>

<span data-ttu-id="f2930-111">Antes que você possa gerenciar o Microsoft 365 inteiro a partir de uma única instância do PowerShell, considere os seguinte pré-requisitos:</span><span class="sxs-lookup"><span data-stu-id="f2930-111">Before you can manage all of Microsoft 365 from a single instance of PowerShell, consider the following prerequisites:</span></span>
  
- <span data-ttu-id="f2930-112">A conta corporativa ou de estudante do Microsoft 365 que você usa deve ser membro de uma função de administrador do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f2930-112">The Microsoft 365 work or school account that you use must be a member of a Microsoft 365 admin role.</span></span> <span data-ttu-id="f2930-113">Para obter mais informações, confira o artigo [Sobre funções de administrador](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="f2930-113">For more information, see [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span> <span data-ttu-id="f2930-114">Este é um requisito do Windows PowerShell para Microsoft 365, mas não necessariamente para todos os outros serviços do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f2930-114">This is a requirement for PowerShell for Microsoft 365, but not necessarily for all other Microsoft 365 services.</span></span>
    
- <span data-ttu-id="f2930-115">Você pode usar as seguintes versões de 64 bits do Windows:</span><span class="sxs-lookup"><span data-stu-id="f2930-115">You can use the following 64-bit versions of Windows:</span></span>
    
  - <span data-ttu-id="f2930-116">Windows 10</span><span class="sxs-lookup"><span data-stu-id="f2930-116">Windows 10</span></span>
    
  - <span data-ttu-id="f2930-117">Windows 8.1 ou Windows 8</span><span class="sxs-lookup"><span data-stu-id="f2930-117">Windows 8.1 or Windows 8</span></span>
    
  - <span data-ttu-id="f2930-118">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="f2930-118">Windows Server 2019</span></span>
    
  - <span data-ttu-id="f2930-119">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="f2930-119">Windows Server 2016</span></span>
    
  - <span data-ttu-id="f2930-120">Windows Server 2012 R2 ou Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="f2930-120">Windows Server 2012 R2 or Windows Server 2012</span></span>
    
  - <span data-ttu-id="f2930-121">Windows 7 Service Pack 1 (SP1)\*</span><span class="sxs-lookup"><span data-stu-id="f2930-121">Windows 7 Service Pack 1 (SP1)\*</span></span>
    
  - <span data-ttu-id="f2930-122">Windows Server 2008 R2 SP1\*</span><span class="sxs-lookup"><span data-stu-id="f2930-122">Windows Server 2008 R2 SP1\*</span></span>
    
    <span data-ttu-id="f2930-123">\* É necessário instalar o Microsoft .NET Framework 4.5. *x* e o Windows Management Framework 3.0 ou 4.0.</span><span class="sxs-lookup"><span data-stu-id="f2930-123">\* You need to install Microsoft .NET Framework 4.5.*x* and then Windows Management Framework 3.0 or 4.0.</span></span> <span data-ttu-id="f2930-124">Para obter mais informações, confira [Windows Management Framework](https://docs.microsoft.com/powershell/scripting/windows-powershell/wmf/overview).</span><span class="sxs-lookup"><span data-stu-id="f2930-124">For more information, see [Windows Management Framework](https://docs.microsoft.com/powershell/scripting/windows-powershell/wmf/overview).</span></span>
    
    <span data-ttu-id="f2930-125">É preciso usar a versão de 64 bits do Windows devido aos requisitos do módulo do Skype for Business Online e de um dos módulos do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f2930-125">You need to use a 64-bit version of Windows because of the requirements for the Skype for Business Online module and one of the Microsoft 365 modules.</span></span>
    
- <span data-ttu-id="f2930-126">É preciso instalar os módulos necessários para o Azure Active Directory (Azure AD), o Exchange Online, o SharePoint Online, o Skype for Business Online e o Teams:</span><span class="sxs-lookup"><span data-stu-id="f2930-126">You need to install the modules that are required for Azure Active Directory (Azure AD), Exchange Online, SharePoint Online, Skype for Business Online and Teams:</span></span>
    
  - [<span data-ttu-id="f2930-127">Azure Active Directory V2</span><span class="sxs-lookup"><span data-stu-id="f2930-127">Azure Active Directory V2</span></span>](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)
  - [<span data-ttu-id="f2930-128">Shell de Gerenciamento do SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="f2930-128">SharePoint Online Management Shell</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=255251)
  - [<span data-ttu-id="f2930-129">Skype for Business Online, módulo do PowerShell</span><span class="sxs-lookup"><span data-stu-id="f2930-129">Skype for Business Online, PowerShell Module</span></span>](https://docs.microsoft.com/microsoftteams/teams-powershell-overview)
  - [<span data-ttu-id="f2930-130">PowerShell do Exchange Online V2</span><span class="sxs-lookup"><span data-stu-id="f2930-130">Exchange Online PowerShell V2</span></span>](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell-v2#install-and-maintain-the-exchange-online-powershell-v2-module)
  - [<span data-ttu-id="f2930-131">Visão Geral do PowerShell do Teams</span><span class="sxs-lookup"><span data-stu-id="f2930-131">Teams PowerShell Overview</span></span>](https://docs.microsoft.com/microsoftteams/teams-powershell-overview)
    
-  <span data-ttu-id="f2930-132">O Windows PowerShell deve ser configurado para executar scripts assinados para o Cliente Skype® for Business Online e o &amp; Centro de Conformidade de Segurança.</span><span class="sxs-lookup"><span data-stu-id="f2930-132">PowerShell must be configured to run signed scripts for Skype for Business Online and the Security &amp; Compliance Center.</span></span> <span data-ttu-id="f2930-133">Execute o seguinte comando em uma sessão Windows PowerShell elevada (uma sessão PowerShell que você **Executa como administrador**).</span><span class="sxs-lookup"><span data-stu-id="f2930-133">Run the following command in an elevated PowerShell session (a PowerShell session that you **Run as administrator**).</span></span>
    
   ```powershell
   Set-ExecutionPolicy RemoteSigned
   ```

## <a name="connection-steps-when-using-just-a-password"></a><span data-ttu-id="f2930-134">Etapas de conexão quando estiver usando apenas uma senha</span><span class="sxs-lookup"><span data-stu-id="f2930-134">Connection steps when using just a password</span></span>

<span data-ttu-id="f2930-135">Siga estas etapas para se conectar a todos os serviços em uma única janela do PowerShell quando estiver usando apenas uma senha para entrar.</span><span class="sxs-lookup"><span data-stu-id="f2930-135">Follow these steps to connect to all the services in a single PowerShell window when you're using just a password for sign-in.</span></span>
  
1. <span data-ttu-id="f2930-136">Abra o PowerShell do Windows.</span><span class="sxs-lookup"><span data-stu-id="f2930-136">Open Windows PowerShell.</span></span>
    
2. <span data-ttu-id="f2930-137">Execute este comando e digite as credenciais da sua conta corporativa ou de estudante do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f2930-137">Run this command and enter your Microsoft 365 work or school account credentials.</span></span>
    
   ```powershell
   $credential = Get-Credential
   ```

3. <span data-ttu-id="f2930-138">Execute este comando para se conectar ao Azure AD usando o módulo Azure Active Directory Windows PowerShell para Graph.</span><span class="sxs-lookup"><span data-stu-id="f2930-138">Run this command to connect to Azure AD by using the Azure Active Directory PowerShell for Graph module.</span></span>
    
   ```powershell
   Connect-AzureAD -Credential $credential
   ```
  
   <span data-ttu-id="f2930-139">Ou se você estiver usando o Módulo Microsoft Azure Active Directory para Windows PowerShell, execute este comando.</span><span class="sxs-lookup"><span data-stu-id="f2930-139">Or if you're using the Microsoft Azure Active Directory Module for Windows PowerShell module, run this command.</span></span>
      
   ```powershell
   Connect-MsolService -Credential $credential
   ```

   > [!Note]
   > <span data-ttu-id="f2930-140">O PowerShell Core não oferece suporte ao Módulo Microsoft Azure Active Directory para Windows PowerShell para o módulo do Windows PowerShell e cmdlets com *Msol* em seus nomes.</span><span class="sxs-lookup"><span data-stu-id="f2930-140">PowerShell Core doesn't support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with *Msol* in their name.</span></span> <span data-ttu-id="f2930-141">Você deve executar esses cmdlets do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f2930-141">You must run these cmdlets from PowerShell.</span></span>

4. <span data-ttu-id="f2930-142">Execute estes comandos para se conectar ao SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="f2930-142">Run these commands to connect to SharePoint Online.</span></span> <span data-ttu-id="f2930-143">Especifique o nome da organização para o seu domínio.</span><span class="sxs-lookup"><span data-stu-id="f2930-143">Specify the organization name for your domain.</span></span> <span data-ttu-id="f2930-144">Por exemplo, para "litwareinc\.onmicrosoft.com", o valor do nome da organização é "litwareinc".</span><span class="sxs-lookup"><span data-stu-id="f2930-144">For example, for "litwareinc\.onmicrosoft.com", the  organization name value is "litwareinc".</span></span>
    
   ```powershell
   $orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
   Import-Module Microsoft.Online.SharePoint.PowerShell -DisableNameChecking
   Connect-SPOService -Url https://$orgName-admin.sharepoint.com -Credential $Credential
   ```

5. <span data-ttu-id="f2930-145">Execute esses comandos para se conectar ao Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="f2930-145">Run these commands to connect to Skype for Business Online.</span></span> <span data-ttu-id="f2930-146">Um aviso sobre o aumento do valor de `WSMan NetworkDelayms` aparecerá na primeira vez que você se conectar.</span><span class="sxs-lookup"><span data-stu-id="f2930-146">A warning about increasing the `WSMan NetworkDelayms` value will appear the first time that you connect.</span></span> <span data-ttu-id="f2930-147">Ignore isto.</span><span class="sxs-lookup"><span data-stu-id="f2930-147">Ignore it.</span></span>
     
   > [!Note]
   > <span data-ttu-id="f2930-148">O Conector Skype for Business Online atualmente faz parte do módulo mais recente do PowerShell do Teams.</span><span class="sxs-lookup"><span data-stu-id="f2930-148">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span> <span data-ttu-id="f2930-149">Se você estiver usando o último lançamento público do PowerShell Teams, você não precisa instalar o Conector do Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="f2930-149">If you're using the latest Teams PowerShell public release, you don't need to install the Skype for Business Online Connector.</span></span>
   
   ```powershell
   $sfboSession = New-CsOnlineSession -Credential $credential
   Import-PSSession $sfboSession
   ```

6. <span data-ttu-id="f2930-150">Execute estes comandos para se conectar ao Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="f2930-150">Run these commands to connect to Exchange Online.</span></span>
    
   ```powershell
   Import-Module ExchangeOnlineManagement
   Connect-ExchangeOnline -ShowProgress $true
   ```

   > [!Note]
   > <span data-ttu-id="f2930-151">Para se conectar às nuvens do Exchange Online para Microsoft 365 que não sejam Mundiais, confira[Conectar ao PowerShell do Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="f2930-151">To connect to Exchange Online for Microsoft 365 clouds other than Worldwide, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

7. <span data-ttu-id="f2930-152">Execute estes comandos para se conectar ao Centro de Conformidade &amp; Segurança.</span><span class="sxs-lookup"><span data-stu-id="f2930-152">Run these commands to connect to the Security &amp; Compliance Center.</span></span>
    
   ```powershell
   $acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
   Connect-IPPSSession -UserPrincipalName $acctName
   ```

   > [!Note]
   > <span data-ttu-id="f2930-153">Para se conectar às nuvens do Centro de Conformidade &amp; e Segurança do Microsoft 365 que não sejam Mundiais, confira o artigo [Conectar-se ao PowerShell do Centro de Conformidade e Segurança](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span><span class="sxs-lookup"><span data-stu-id="f2930-153">To connect to the Security &amp; Compliance Center for Microsoft 365 clouds other than Worldwide, see [Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span></span>

8. <span data-ttu-id="f2930-154">Execute estes comandos para se conectar ao PowerShell do Teams.</span><span class="sxs-lookup"><span data-stu-id="f2930-154">Run these commands to connect to Teams PowerShell.</span></span>
    
   ```powershell
   Import-Module MicrosoftTeams
   Connect-MicrosoftTeams
   ```
  
   > [!Note]
   > <span data-ttu-id="f2930-155">Para se conectar a nuvens do Microsoft Teams que não sejam *Worldwide*, confira [Connect-MicrosoftTeams](https://docs.microsoft.com/powershell/module/teams/connect-microsoftteams).</span><span class="sxs-lookup"><span data-stu-id="f2930-155">To connect to Microsoft Teams clouds other than *Worldwide*, see [Connect-MicrosoftTeams](https://docs.microsoft.com/powershell/module/teams/connect-microsoftteams).</span></span>


### <a name="azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="f2930-156">Módulo do Azure Active Directory Windows PowerShell para Graph</span><span class="sxs-lookup"><span data-stu-id="f2930-156">Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="f2930-157">Aqui estão os comandos para todos os serviços em um único bloco quando você usa o módulo do PowerShell para Graph do Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="f2930-157">Here are the commands for all the services in a single block when you use the Azure Active Directory PowerShell for Graph module.</span></span> <span data-ttu-id="f2930-158">Especifique o nome do host de domínio e o UPN para a entrada e execute-os todos ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="f2930-158">Specify the name of your domain host and the UPN for the sign-in and run them all at the same time.</span></span>
  
```powershell
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$credential = Get-Credential -UserName $acctName -Message "Type the account's password."
#Azure Active Directory
Connect-AzureAD -Credential $credential
#SharePoint Online
Import-Module Microsoft.Online.SharePoint.PowerShell -DisableNameChecking
Connect-SPOService -Url https://$orgName-admin.sharepoint.com -credential $credential
#Skype for Business Online
$sfboSession = New-CsOnlineSession -Credential $credential
Import-PSSession $sfboSession
#Exchange Online
Import-Module ExchangeOnlineManagement
Connect-ExchangeOnline -ShowProgress $true
#Security & Compliance Center
Connect-IPPSSession -UserPrincipalName $acctName
#Teams
Import-Module MicrosoftTeams
Connect-MicrosoftTeams
```

### <a name="microsoft-azure-active-directory-module-for-windows-powershell-module"></a><span data-ttu-id="f2930-159">Módulo Microsoft Azure Active Directory para Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f2930-159">Microsoft Azure Active Directory Module for Windows PowerShell module</span></span>

<span data-ttu-id="f2930-160">Aqui estão os comandos para todos os serviços em um único bloco quando você usa o Módulo Microsoft Azure Active Directory para Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f2930-160">Here are the commands for all the services in a single block when you use the Microsoft Azure Active Directory Module for Windows PowerShell module.</span></span> <span data-ttu-id="f2930-161">Especifique o nome do host de domínio e o UPN para a entrada e execute-os todos de uma vez.</span><span class="sxs-lookup"><span data-stu-id="f2930-161">Specify the name of your domain host and the UPN for the sign-in and run them all at one time.</span></span>
  
```powershell
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$credential = Get-Credential -UserName $acctName -Message "Type the account's password."
#Azure Active Directory
Connect-MsolService -Credential $credential
#SharePoint Online
Import-Module Microsoft.Online.SharePoint.PowerShell -DisableNameChecking
Connect-SPOService -Url https://$orgName-admin.sharepoint.com -credential $credential
#Skype for Business Online
$sfboSession = New-CsOnlineSession -Credential $credential
Import-PSSession $sfboSession
#Exchange Online
Import-Module ExchangeOnlineManagement
Connect-ExchangeOnline -ShowProgress $true
#Security & Compliance Center
Connect-IPPSSession -UserPrincipalName $acctName
#Teams
Import-Module MicrosoftTeams
Connect-MicrosoftTeams
```

## <a name="connection-steps-when-using-multi-factor-authentication"></a><span data-ttu-id="f2930-162">Etapas de conexão quando estiver usando a autenticação multifator</span><span class="sxs-lookup"><span data-stu-id="f2930-162">Connection steps when using multi-factor authentication</span></span>

### <a name="azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="f2930-163">Use o Windows PowerShell do Azure Active Directory para o módulo do Graph</span><span class="sxs-lookup"><span data-stu-id="f2930-163">Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="f2930-164">Aqui estão todos os comandos em um único bloco para se conectar a vários serviços do Microsoft 365 ao usar a autenticação multifator com o módulo do PowerShell para Graph do Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="f2930-164">Here are all the commands in a single block to connect to multiple Microsoft 365 services when you use multi-factor authentication with the Azure Active Directory PowerShell for Graph module.</span></span>

```powershell
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
#Azure Active Directory
Connect-AzureAD
#SharePoint Online
Connect-SPOService -Url https://$orgName-admin.sharepoint.com
#Skype for Business Online
$sfboSession = New-CsOnlineSession
Import-PSSession $sfboSession
#Exchange Online
Import-Module ExchangeOnlineManagement
Connect-ExchangeOnline -UserPrincipalName $acctName -ShowProgress $true
#Security & Compliance Center
Connect-IPPSSession -UserPrincipalName $acctName
#Teams
Import-Module MicrosoftTeams
Connect-MicrosoftTeams
```
### <a name="microsoft-azure-active-directory-module-for-windows-powershell-module"></a><span data-ttu-id="f2930-165">Módulo Microsoft Azure Active Directory para Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f2930-165">Microsoft Azure Active Directory Module for Windows PowerShell module</span></span>

<span data-ttu-id="f2930-166">Aqui estão todos os comandos em um único bloco para se conectar a vários serviços do Microsoft 365 ao usar a autenticação multifator com o Módulo do Microsoft Azure Active Directory para Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f2930-166">Here are all the commands in a single block to connect to multiple Microsoft 365 services when you use multi-factor authentication with the Microsoft Azure Active Directory Module for Windows PowerShell module.</span></span>

```powershell
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
#Azure Active Directory
Connect-MsolService
#SharePoint Online
Connect-SPOService -Url https://$orgName-admin.sharepoint.com
#Skype for Business Online
$sfboSession = New-CsOnlineSession
Import-PSSession $sfboSession
#Exchange Online
Import-Module ExchangeOnlineManagement
Connect-ExchangeOnline -UserPrincipalName $acctName -ShowProgress $true
#Security & Compliance Center
Connect-IPPSSession -UserPrincipalName $acctName
#Teams
Import-Module MicrosoftTeams
Connect-MicrosoftTeams
```

## <a name="close-the-powershell-window"></a><span data-ttu-id="f2930-167">Fechar a janela do PowerShell</span><span class="sxs-lookup"><span data-stu-id="f2930-167">Close the PowerShell window</span></span>

<span data-ttu-id="f2930-168">Para fechar a janela do PowerShell, execute este comando para remover as sessões ativas do Skype for Business Online, Microsoft Office SharePoint Online e Teams:</span><span class="sxs-lookup"><span data-stu-id="f2930-168">To close down the PowerShell window, run this command to remove the active sessions to Skype for Business Online, SharePoint Online, and Teams:</span></span>
  
```powershell
Remove-PSSession $sfboSession ; Disconnect-SPOService ; Disconnect-MicrosoftTeams 
```

## <a name="see-also"></a><span data-ttu-id="f2930-169">Confira também</span><span class="sxs-lookup"><span data-stu-id="f2930-169">See also</span></span>

- [<span data-ttu-id="f2930-170">Conectar-se ao Microsoft 365 com o PowerShell</span><span class="sxs-lookup"><span data-stu-id="f2930-170">Connect to Microsoft 365 with PowerShell</span></span>](connect-to-microsoft-365-powershell.md)
- [<span data-ttu-id="f2930-171">Gerenciar o SharePoint Online com o PowerShell</span><span class="sxs-lookup"><span data-stu-id="f2930-171">Manage SharePoint Online with PowerShell</span></span>](manage-sharepoint-online-with-microsoft-365-powershell.md)
- [<span data-ttu-id="f2930-172">Gerenciar contas de usuário, licenças e grupos do Microsoft 365 com o PowerShell</span><span class="sxs-lookup"><span data-stu-id="f2930-172">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
