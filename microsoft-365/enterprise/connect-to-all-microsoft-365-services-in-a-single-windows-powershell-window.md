---
title: Conectar-se a todos os serviços do Microsoft 365 usando uma única janela do PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/26/2020
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
ms.openlocfilehash: af676434017cbe7025baa5e8509e6203a5d59674
ms.sourcegitcommit: 555d756c69ac9031d1fb928f2e1f9750beede066
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/29/2020
ms.locfileid: "47307620"
---
# <a name="connect-to-all-microsoft-365-services-in-a-single-powershell-window"></a><span data-ttu-id="641ba-103">Conectar-se a todos os serviços do Microsoft 365 usando uma única janela do PowerShell</span><span class="sxs-lookup"><span data-stu-id="641ba-103">Connect to all Microsoft 365 services in a single PowerShell window</span></span>

<span data-ttu-id="641ba-104">Quando você usa o PowerShell para gerenciar o Microsoft 365, é possível ter múltiplas sessões diferentes do PowerShell do Windows abertas ao mesmo tempo em janelas diferentes do PowerShell, correspondentes ao gerenciamento das contas de usuário, ao SharePoint Online, ao Exchange Online, ao Skype for Business Online, ao Microsoft Teams e ao Centro de Conformidade &amp; Segurança.</span><span class="sxs-lookup"><span data-stu-id="641ba-104">When you use PowerShell to manage Microsoft 365, it is possible to have multiple PowerShell sessions open at the same time in different PowerShell windows corresponding to managing user accounts, SharePoint Online, Exchange Online, Skype for Business Online, Microsoft Teams, and the Security &amp; Compliance Center.</span></span> 
  
<span data-ttu-id="641ba-105">Essa não é uma forma ideal de gerenciar o Microsoft 365 porque não é possível trocar dados entre essas janelas para o gerenciamento de diversos serviços.</span><span class="sxs-lookup"><span data-stu-id="641ba-105">This is not optimal for managing Microsoft 365 because you can't exchange data among those windows for cross-service management.</span></span> <span data-ttu-id="641ba-106">Este tópico descreve como usar uma única instância do PowerShell a partir da qual você pode gerenciar suas contas do Microsoft 365, do Skype for Business Online, do Exchange Online, do SharePoint Online, do Microsoft Teams e do Centro de Conformidade e &amp; Segurança.</span><span class="sxs-lookup"><span data-stu-id="641ba-106">This topic describes how to use a single instance of PowerShell from which you can manage Microsoft 365 accounts, Skype for Business Online, Exchange Online, SharePoint Online, Microsoft Teams, and the Security &amp; Compliance Center.</span></span>

>[!Note]
><span data-ttu-id="641ba-107">Atualmente este artigo contém apenas os comandos necessários para se conectar com a nuvem mundial (+GCC).</span><span class="sxs-lookup"><span data-stu-id="641ba-107">This article currently only contains the commands to connect to the Worldwide (+GCC) cloud.</span></span> <span data-ttu-id="641ba-108">As observações fornecem links para os artigos que contêm informações sobre como se conectar à outras nuvens do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="641ba-108">Notes provide links to articles with information about connecting to the other Microsoft 365 clouds.</span></span>
>

## <a name="before-you-begin"></a><span data-ttu-id="641ba-109">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="641ba-109">Before you begin</span></span>

<span data-ttu-id="641ba-110">Antes que você possa gerenciar o Microsoft 365 inteiro a partir de uma única instância do PowerShell, considere os seguinte pré-requisitos:</span><span class="sxs-lookup"><span data-stu-id="641ba-110">Before you can manage all of Microsoft 365 from a single instance of PowerShell, consider the following prerequisites:</span></span>
  
- <span data-ttu-id="641ba-111">A conta corporativa ou de estudante do Microsoft 365 que você usa para esses procedimentos precisa ser membro de uma função de administrador do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="641ba-111">The Microsoft 365 work or school account that you use for these procedures needs to be a member of a Microsoft 365 admin role.</span></span> <span data-ttu-id="641ba-112">Para obter mais informações, confira o artigo [Sobre funções de administrador](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles?view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="641ba-112">For more information, see [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles?view=o365-worldwide).</span></span> <span data-ttu-id="641ba-113">Isso é obrigatório para o PowerShell no Microsoft 365, mas não necessariamente para todos os demais serviços do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="641ba-113">This a requirement for PowerShell for Microsoft 365, not necessarily for all other Microsoft 365 services.</span></span>
    
- <span data-ttu-id="641ba-114">Você pode usar as seguintes versões de 64 bits do Windows:</span><span class="sxs-lookup"><span data-stu-id="641ba-114">You can use the following 64-bit versions of Windows:</span></span>
    
  - <span data-ttu-id="641ba-115">Windows 10</span><span class="sxs-lookup"><span data-stu-id="641ba-115">Windows 10</span></span>
    
  - <span data-ttu-id="641ba-116">Windows 8.1 ou Windows 8</span><span class="sxs-lookup"><span data-stu-id="641ba-116">Windows 8.1 or Windows 8</span></span>
    
  - <span data-ttu-id="641ba-117">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="641ba-117">Windows Server 2019</span></span>
    
  - <span data-ttu-id="641ba-118">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="641ba-118">Windows Server 2016</span></span>
    
  - <span data-ttu-id="641ba-119">Windows Server 2012 R2 ou Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="641ba-119">Windows Server 2012 R2 or Windows Server 2012</span></span>
    
  - <span data-ttu-id="641ba-120">Windows 7 Service Pack 1 (SP1)\*</span><span class="sxs-lookup"><span data-stu-id="641ba-120">Windows 7 Service Pack 1 (SP1)\*</span></span>
    
  - <span data-ttu-id="641ba-121">Windows Server 2008 R2 SP1\*</span><span class="sxs-lookup"><span data-stu-id="641ba-121">Windows Server 2008 R2 SP1\*</span></span>
    
    <span data-ttu-id="641ba-122">\*É necessário instalar o Microsoft .NET Framework 4.5.*x* e, em seguida, o Windows Management Framework 3.0 ou o Windows Management Framework 4.0.</span><span class="sxs-lookup"><span data-stu-id="641ba-122">\* You need to install the Microsoft .NET Framework 4.5.*x* and then either the Windows Management Framework 3.0 or the Windows Management Framework 4.0.</span></span> <span data-ttu-id="641ba-123">Para obter mais informações, consulte [Instalar o .NET Framework](https://go.microsoft.com/fwlink/p/?LinkId=257868) e [Windows Management 3.0](https://go.microsoft.com/fwlink/p/?LinkId=272757), ou o [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/p/?LinkId=391344).</span><span class="sxs-lookup"><span data-stu-id="641ba-123">For more information, see [Installing the .NET Framework](https://go.microsoft.com/fwlink/p/?LinkId=257868) and [Windows Management Framework 3.0](https://go.microsoft.com/fwlink/p/?LinkId=272757) or [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/p/?LinkId=391344).</span></span>
    
    <span data-ttu-id="641ba-124">É preciso usar a versão de 64 bits do Windows devido aos requisitos do módulo do Skype for Business Online e de um dos módulos do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="641ba-124">You need to use a 64-bit version of Windows because of the requirements for the Skype for Business Online module and one of the Microsoft 365 modules.</span></span>
    
- <span data-ttu-id="641ba-125">É preciso instalar os módulos necessários para o Azure Active Directory (Azure AD), o Exchange Online, o SharePoint Online, o Skype for Business Online e o Teams:</span><span class="sxs-lookup"><span data-stu-id="641ba-125">You need to install the modules that are required for Azure Active Directory (Azure AD), Exchange Online, SharePoint Online, Skype for Business Online and Teams:</span></span>
    
   - [<span data-ttu-id="641ba-126">Azure Active Directory V2</span><span class="sxs-lookup"><span data-stu-id="641ba-126">Azure Active Directory V2</span></span>](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)
   - [<span data-ttu-id="641ba-127">Shell de Gerenciamento do SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="641ba-127">SharePoint Online Management Shell</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=255251)
   - [<span data-ttu-id="641ba-128">Skype for Business Online, módulo do PowerShell</span><span class="sxs-lookup"><span data-stu-id="641ba-128">Skype for Business Online, PowerShell Module</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=532439)
   - [<span data-ttu-id="641ba-129">PowerShell do Exchange Online V2</span><span class="sxs-lookup"><span data-stu-id="641ba-129">Exchange Online PowerShell V2</span></span>](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell-v2/exchange-online-powershell-v2?view=exchange-ps#install-and-maintain-the-exchange-online-powershell-v2-module)
   - [<span data-ttu-id="641ba-130">Visão Geral do PowerShell do Teams</span><span class="sxs-lookup"><span data-stu-id="641ba-130">Teams PowerShell Overview</span></span>](https://docs.microsoft.com/microsoftteams/teams-powershell-overview)
    
-  <span data-ttu-id="641ba-131">O PowerShell precisa ser configurado para executar os scripts assinados do Skype for Business Online e do Centro de Conformidade e &amp; Segurança.</span><span class="sxs-lookup"><span data-stu-id="641ba-131">PowerShell needs to be configured to run signed scripts for Skype for Business Online and the Security &amp; Compliance Center.</span></span> <span data-ttu-id="641ba-132">Para fazer isso, execute o comando a seguir em uma janela elevada do PowerShell (uma janela do PowerShell que você abre quando seleciona **Executar como administrador**).</span><span class="sxs-lookup"><span data-stu-id="641ba-132">To do this, run the following command in an elevated PowerShell session (a PowerShell window you open by selecting **Run as administrator**).</span></span>
    
   ```powershell
   Set-ExecutionPolicy RemoteSigned
   ```

## <a name="connection-steps-when-using-just-a-password"></a><span data-ttu-id="641ba-133">Etapas de conexão quando estiver usando apenas uma senha</span><span class="sxs-lookup"><span data-stu-id="641ba-133">Connection steps when using just a password</span></span>

<span data-ttu-id="641ba-134">Estas são as etapas para se conectar a todos os serviços em uma única janela do PowerShell quando você estiver usando apenas uma senha para entrar.</span><span class="sxs-lookup"><span data-stu-id="641ba-134">Here are the steps to connect to all the services in a single PowerShell window when you are using just a password for sign-in.</span></span>
  
1. <span data-ttu-id="641ba-135">Abra o PowerShell do Windows.</span><span class="sxs-lookup"><span data-stu-id="641ba-135">Open Windows PowerShell.</span></span>
    
2. <span data-ttu-id="641ba-136">Execute este comando e digite as credenciais da sua conta corporativa ou de estudante do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="641ba-136">Run this command and enter your Microsoft 365 work or school account credentials.</span></span>
    
   ```powershell
   $credential = Get-Credential
   ```

3. <span data-ttu-id="641ba-137">Execute este comando para se conectar ao Azure AD usando o PowerShell do Azure Active Directory para o módulo Gráfico.</span><span class="sxs-lookup"><span data-stu-id="641ba-137">Run this command to connect to Azure AD using the Azure Active Directory PowerShell for Graph module.</span></span>
    
   ```powershell
   Connect-AzureAD -Credential $credential
   ```
  
   <span data-ttu-id="641ba-138">Alternativamente, se você estiver usando o Módulo do Microsoft Azure Active Directory para o módulo PowerShell, execute este comando.</span><span class="sxs-lookup"><span data-stu-id="641ba-138">Alternately, if you are using the Microsoft Azure Active Directory Module for PowerShell module, run this command.</span></span>
      
   ```powershell
   Connect-MsolService -Credential $credential
   ```

   > [!Note]
   > <span data-ttu-id="641ba-139">O PowerShell Core não é compatível com o módulo do Microsoft Azure Active Directory para o módulo e cmdlets do PowerShell com **Msol** no nome.</span><span class="sxs-lookup"><span data-stu-id="641ba-139">PowerShell Core does not support the Microsoft Azure Active Directory Module for PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="641ba-140">Para continuar usando esses cmdlets, você deve executá-los a partir do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="641ba-140">To continue using these cmdlets, you must run them from PowerShell.</span></span>

4. <span data-ttu-id="641ba-141">Execute estes comandos para se conectar ao SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="641ba-141">Run these commands to connect to SharePoint Online.</span></span> <span data-ttu-id="641ba-142">Especifique o nome da organização para o seu domínio.</span><span class="sxs-lookup"><span data-stu-id="641ba-142">Specify the organization name for your domain.</span></span> <span data-ttu-id="641ba-143">Por exemplo, para "litwareinc.onmicrosoft.com" o valor nome da organização é "litwareinc".</span><span class="sxs-lookup"><span data-stu-id="641ba-143">For example, for "litwareinc.onmicrosoft.com", the  organization name value is "litwareinc".</span></span>
    
   ```powershell
   $orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
   Connect-SPOService -Url https://$orgName-admin.sharepoint.com -Credential $userCredential
   ```

5. <span data-ttu-id="641ba-144">Execute estes comandos para se conectar ao Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="641ba-144">Run these commands to connect to Skype for Business Online.</span></span> <span data-ttu-id="641ba-145">Um aviso sobre o aumento do valor de `WSMan NetworkDelayms` é esperado na primeira vez que você se conectar e deve ser ignorado.</span><span class="sxs-lookup"><span data-stu-id="641ba-145">A warning about increasing the `WSMan NetworkDelayms` value is expected the first time you connect and should be ignored.</span></span>
     
   ```powershell
   Import-Module SkypeOnlineConnector
   $sfboSession = New-CsOnlineSession -Credential $credential
   Import-PSSession $sfboSession
   ```

6. <span data-ttu-id="641ba-146">Execute este comando para se conectar ao Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="641ba-146">Run this command to connect to Exchange Online.</span></span>
    
   ```powershell
   Connect-ExchangeOnline -Credential $credential -ShowProgress $true
   ```

   > [!Note]
   > <span data-ttu-id="641ba-147">Para se conectar às nuvens do Exchange Online para Microsoft 365 que não sejam Mundiais, use o parâmetro **-ExchangeEnvironmentName**.</span><span class="sxs-lookup"><span data-stu-id="641ba-147">To connect to Exchange Online for Microsoft 365 clouds other than Worldwide, use the **-ExchangeEnvironmentName** parameter.</span></span> <span data-ttu-id="641ba-148">Confira o artigo [Conectar-se ao ExchangeOnline](https://docs.microsoft.com/powershell/module/exchange/powershell-v2-module/connect-exchangeonline?view=exchange-ps) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="641ba-148">See [Connect-ExchangeOnline](https://docs.microsoft.com/powershell/module/exchange/powershell-v2-module/connect-exchangeonline?view=exchange-ps) for more information.</span></span>

7. <span data-ttu-id="641ba-149">Execute estes comandos para se conectar ao PowerShell do Teams.</span><span class="sxs-lookup"><span data-stu-id="641ba-149">Run these commands to connect to Teams PowerShell.</span></span>
    
   ```powershell
   Import-Module MicrosoftTeams
   Connect-MicrosoftTeams -Credential $credential
   ```
  
   > [!Note]
   > <span data-ttu-id="641ba-150">Para se conectar às nuvens do Microsoft Teams que não sejam Mundiais, confira o artigo [Conectar-se ao MicrosoftTeams](https://docs.microsoft.com/powershell/module/teams/connect-microsoftteams?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="641ba-150">To connect to Microsoft Teams clouds other than Worldwide, see [Connect-MicrosoftTeams](https://docs.microsoft.com/powershell/module/teams/connect-microsoftteams?view=teams-ps).</span></span>

8. <span data-ttu-id="641ba-151">Execute estes comandos para se conectar ao Centro de Conformidade &amp; Segurança.</span><span class="sxs-lookup"><span data-stu-id="641ba-151">Run these commands to connect to the Security &amp; Compliance Center.</span></span>
    
   ```powershell
   $SccSession = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid/ -Credential $credential -Authentication "Basic" -AllowRedirection
   Import-PSSession $SccSession -Prefix cc
   ```

   > [!Note]
   > <span data-ttu-id="641ba-152">Para se conectar às nuvens do Centro de Conformidade &amp; Segurança do Microsoft 365 que não sejam Mundiais, confira o artigo [Conectar-se ao PowerShell do Centro de Conformidade & Segurança](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span><span class="sxs-lookup"><span data-stu-id="641ba-152">To connect to the Security &amp; Compliance Center for Microsoft 365 clouds other than Worldwide, see [Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span></span>

<span data-ttu-id="641ba-153">Aqui estão todos os comandos em um único bloco quando estiver usando o PowerShell do Azure Active Directory para o módulo Gráfico.</span><span class="sxs-lookup"><span data-stu-id="641ba-153">Here are all the commands in a single block when using the Azure Active Directory PowerShell for Graph module.</span></span> <span data-ttu-id="641ba-154">Especifique o nome do seu host de domínio e, em seguida, execute todos eles ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="641ba-154">Specify the name of your domain host, and then run them all at one time.</span></span>
  
```powershell
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
$credential = Get-Credential
Connect-AzureAD -Credential $credential
Import-Module Microsoft.Online.SharePoint.PowerShell -DisableNameChecking
Connect-SPOService -Url https://$orgName-admin.sharepoint.com -credential $credential
Import-Module SkypeOnlineConnector
$sfboSession = New-CsOnlineSession -Credential $credential
Import-PSSession $sfboSession
$SccSession = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid/ -Credential $credential -Authentication "Basic" -AllowRedirection
Import-PSSession $SccSession -Prefix cc
Connect-ExchangeOnline -Credential $credential -ShowProgress $true
Import-Module MicrosoftTeams
Connect-MicrosoftTeams -Credential $credential
```

<span data-ttu-id="641ba-155">Alternativamente, aqui estão todos os comandos em um único bloco se você estiver usando o módulo do Microsoft Azure Active Directory para o módulo PowerShell.</span><span class="sxs-lookup"><span data-stu-id="641ba-155">Alternately, here are all the commands in a single block when using the Microsoft Azure Active Directory Module for PowerShell module.</span></span> <span data-ttu-id="641ba-156">Especifique o nome do seu host de domínio e, em seguida, execute todos eles ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="641ba-156">Specify the name of your domain host, and then run them all at one time.</span></span>
  
```powershell
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
$credential = Get-Credential
Connect-MsolService -Credential $credential
Import-Module Microsoft.Online.SharePoint.PowerShell -DisableNameChecking
Connect-SPOService -Url https://$orgName-admin.sharepoint.com -credential $credential
Import-Module SkypeOnlineConnector
$sfboSession = New-CsOnlineSession -Credential $credential
Import-PSSession $sfboSession
$SccSession = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid/ -Credential $credential -Authentication "Basic" -AllowRedirection
Import-PSSession $SccSession -Prefix cc
Connect-ExchangeOnline -Credential $credential -ShowProgress $true
Import-Module MicrosoftTeams
Connect-MicrosoftTeams -Credential $credential
```

<span data-ttu-id="641ba-157">Quando estiver pronto para fechar a janela do PowerShell, execute este comando para remover as sessões ativas do Skype for Business Online, SharePoint Online, Centro de Conformidade e &amp; Segurança, e Teams:</span><span class="sxs-lookup"><span data-stu-id="641ba-157">When you are ready to close down the PowerShell window, run this command to remove the active sessions to Skype for Business Online, SharePoint Online, the Security &amp; Compliance Center, and Teams:</span></span>
  
```powershell
Remove-PSSession $sfboSession ; Remove-PSSession $SccSession ; Disconnect-SPOService ; Disconnect-MicrosoftTeams 
```

## <a name="connection-steps-when-using-multi-factor-authentication"></a><span data-ttu-id="641ba-158">Etapas de conexão quando estiver usando a autenticação multifator</span><span class="sxs-lookup"><span data-stu-id="641ba-158">Connection steps when using multi-factor authentication</span></span>

<span data-ttu-id="641ba-159">Aqui estão todos os comandos em um único bloco para se conectar ao Azure AD, SharePoint Online, Skype for Business, Exchange Online e Teams usando uma autenticação multifator em uma única janela usando o PowerShell do Azure Active Directory para o módulo Gráfico.</span><span class="sxs-lookup"><span data-stu-id="641ba-159">Here are all the commands in a single block to connect to Azure AD, SharePoint Online, Skype for Business, Exchange Online, and Teams using multi-factor authentication in a single window using the Azure Active Directory PowerShell for Graph module.</span></span> <span data-ttu-id="641ba-160">Especifique o nome do usuário principal (UPN) de uma conta de usuário e o nome do seu host de domínio e, em seguida, execute todos eles de uma só vez.</span><span class="sxs-lookup"><span data-stu-id="641ba-160">Specify the user principal name (UPN) name of a user account and your domain host name, and then run them all at one time.</span></span>

```powershell
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
#Azure Active Directory
Connect-AzureAD
#SharePoint Online
Connect-SPOService -Url https://$orgName-admin.sharepoint.com
#Skype for Business Online
$sfboSession = New-CsOnlineSession -UserName $acctName
Import-PSSession $sfboSession
#Exchange Online
Connect-ExchangeOnline -UserPrincipalName $acctName -ShowProgress $true
#Teams
Import-Module MicrosoftTeams
Connect-MicrosoftTeams
```

<span data-ttu-id="641ba-161">Alternativamente, aqui estão todos os comandos se você estiver usando o Módulo do Microsoft Azure Active Directory para o módulo PowerShell.</span><span class="sxs-lookup"><span data-stu-id="641ba-161">Alternately, here are all the commands when using the Microsoft Azure Active Directory Module for PowerShell module.</span></span>

```powershell
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
#Azure Active Directory
Connect-MsolService
#SharePoint Online
Connect-SPOService -Url https://$orgName-admin.sharepoint.com
#Skype for Business Online
$sfboSession = New-CsOnlineSession -UserName $acctName
Import-PSSession $sfboSession
#Exchange Online
Connect-ExchangeOnline -UserPrincipalName $acctName -ShowProgress $true
#Teams
Import-Module MicrosoftTeams
Connect-MicrosoftTeams
```

<span data-ttu-id="641ba-162">Para se conectar ao Centro de Conformidade &amp; Segurança usando a autenticação multifator, confira o artigo [Conectar-se ao PowerShell do Centro de Conformidade & Segurança usando a autenticação multifator](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/mfa-connect-to-scc-powershell?view=exchange-ps):</span><span class="sxs-lookup"><span data-stu-id="641ba-162">For the Security &amp; Compliance Center, see [Connect to Security & Compliance Center PowerShell using multi-factor authentication](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/mfa-connect-to-scc-powershell?view=exchange-ps) to connect using multi-factor authentication:</span></span>

## <a name="see-also"></a><span data-ttu-id="641ba-163">Confira também</span><span class="sxs-lookup"><span data-stu-id="641ba-163">See also</span></span>

- [<span data-ttu-id="641ba-164">Conectar-se ao Microsoft 365 com o PowerShell</span><span class="sxs-lookup"><span data-stu-id="641ba-164">Connect to Microsoft 365 with PowerShell</span></span>](connect-to-microsoft-365-powershell.md)
- [<span data-ttu-id="641ba-165">Gerenciar o SharePoint Online com o PowerShell</span><span class="sxs-lookup"><span data-stu-id="641ba-165">Manage SharePoint Online with PowerShell</span></span>](manage-sharepoint-online-with-microsoft-365-powershell.md)
- [<span data-ttu-id="641ba-166">Gerenciar contas de usuário, licenças e grupos do Microsoft 365 com o PowerShell</span><span class="sxs-lookup"><span data-stu-id="641ba-166">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
