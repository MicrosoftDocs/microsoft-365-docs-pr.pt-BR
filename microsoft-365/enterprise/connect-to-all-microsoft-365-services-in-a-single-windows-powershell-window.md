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
ms.openlocfilehash: e4cb3a10d14f6d4c16ef9323d6e5b3c500ebc0c5
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/12/2020
ms.locfileid: "47545969"
---
# <a name="connect-to-all-microsoft-365-services-in-a-single-powershell-window"></a><span data-ttu-id="c497a-103">Conectar-se a todos os serviços do Microsoft 365 usando uma única janela do PowerShell</span><span class="sxs-lookup"><span data-stu-id="c497a-103">Connect to all Microsoft 365 services in a single PowerShell window</span></span>

<span data-ttu-id="c497a-104">Quando você usa o PowerShell para gerenciar o Microsoft 365, é possível ter múltiplas sessões diferentes do PowerShell do Windows abertas ao mesmo tempo em janelas diferentes do PowerShell, correspondentes ao gerenciamento das contas de usuário, ao SharePoint Online, ao Exchange Online, ao Skype for Business Online, ao Microsoft Teams e ao Centro de Conformidade &amp; Segurança.</span><span class="sxs-lookup"><span data-stu-id="c497a-104">When you use PowerShell to manage Microsoft 365, it is possible to have multiple PowerShell sessions open at the same time in different PowerShell windows corresponding to managing user accounts, SharePoint Online, Exchange Online, Skype for Business Online, Microsoft Teams, and the Security &amp; Compliance Center.</span></span> 
  
<span data-ttu-id="c497a-105">Essa não é uma forma ideal de gerenciar o Microsoft 365 porque não é possível trocar dados entre essas janelas para o gerenciamento de diversos serviços.</span><span class="sxs-lookup"><span data-stu-id="c497a-105">This is not optimal for managing Microsoft 365 because you can't exchange data among those windows for cross-service management.</span></span> <span data-ttu-id="c497a-106">Este tópico descreve como usar uma única instância do PowerShell a partir da qual você pode gerenciar suas contas do Microsoft 365, do Skype for Business Online, do Exchange Online, do SharePoint Online, do Microsoft Teams e do Centro de Conformidade e &amp; Segurança.</span><span class="sxs-lookup"><span data-stu-id="c497a-106">This topic describes how to use a single instance of PowerShell from which you can manage Microsoft 365 accounts, Skype for Business Online, Exchange Online, SharePoint Online, Microsoft Teams, and the Security &amp; Compliance Center.</span></span>

>[!Note]
><span data-ttu-id="c497a-107">Atualmente este artigo contém apenas os comandos necessários para se conectar com a nuvem mundial (+GCC).</span><span class="sxs-lookup"><span data-stu-id="c497a-107">This article currently only contains the commands to connect to the Worldwide (+GCC) cloud.</span></span> <span data-ttu-id="c497a-108">As observações fornecem links para os artigos que contêm informações sobre como se conectar à outras nuvens do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c497a-108">Notes provide links to articles with information about connecting to the other Microsoft 365 clouds.</span></span>
>

## <a name="before-you-begin"></a><span data-ttu-id="c497a-109">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="c497a-109">Before you begin</span></span>

<span data-ttu-id="c497a-110">Antes que você possa gerenciar o Microsoft 365 inteiro a partir de uma única instância do PowerShell, considere os seguinte pré-requisitos:</span><span class="sxs-lookup"><span data-stu-id="c497a-110">Before you can manage all of Microsoft 365 from a single instance of PowerShell, consider the following prerequisites:</span></span>
  
- <span data-ttu-id="c497a-111">A conta corporativa ou de estudante do Microsoft 365 que você usa para esses procedimentos precisa ser membro de uma função de administrador do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c497a-111">The Microsoft 365 work or school account that you use for these procedures needs to be a member of a Microsoft 365 admin role.</span></span> <span data-ttu-id="c497a-112">Para obter mais informações, confira o artigo [Sobre funções de administrador](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="c497a-112">For more information, see [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span> <span data-ttu-id="c497a-113">Isso é obrigatório para o PowerShell no Microsoft 365, mas não necessariamente para todos os demais serviços do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c497a-113">This a requirement for PowerShell for Microsoft 365, not necessarily for all other Microsoft 365 services.</span></span>
    
- <span data-ttu-id="c497a-114">Você pode usar as seguintes versões de 64 bits do Windows:</span><span class="sxs-lookup"><span data-stu-id="c497a-114">You can use the following 64-bit versions of Windows:</span></span>
    
  - <span data-ttu-id="c497a-115">Windows 10</span><span class="sxs-lookup"><span data-stu-id="c497a-115">Windows 10</span></span>
    
  - <span data-ttu-id="c497a-116">Windows 8.1 ou Windows 8</span><span class="sxs-lookup"><span data-stu-id="c497a-116">Windows 8.1 or Windows 8</span></span>
    
  - <span data-ttu-id="c497a-117">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="c497a-117">Windows Server 2019</span></span>
    
  - <span data-ttu-id="c497a-118">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="c497a-118">Windows Server 2016</span></span>
    
  - <span data-ttu-id="c497a-119">Windows Server 2012 R2 ou Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="c497a-119">Windows Server 2012 R2 or Windows Server 2012</span></span>
    
  - <span data-ttu-id="c497a-120">Windows 7 Service Pack 1 (SP1)\*</span><span class="sxs-lookup"><span data-stu-id="c497a-120">Windows 7 Service Pack 1 (SP1)\*</span></span>
    
  - <span data-ttu-id="c497a-121">Windows Server 2008 R2 SP1\*</span><span class="sxs-lookup"><span data-stu-id="c497a-121">Windows Server 2008 R2 SP1\*</span></span>
    
    <span data-ttu-id="c497a-122">\*É necessário instalar o Microsoft .NET Framework 4.5.*x* e, em seguida, o Windows Management Framework 3.0 ou o Windows Management Framework 4.0.</span><span class="sxs-lookup"><span data-stu-id="c497a-122">\* You need to install the Microsoft .NET Framework 4.5.*x* and then either the Windows Management Framework 3.0 or the Windows Management Framework 4.0.</span></span> <span data-ttu-id="c497a-123">Para obter mais informações, consulte [Instalar o .NET Framework](https://go.microsoft.com/fwlink/p/?LinkId=257868) e [Windows Management 3.0](https://go.microsoft.com/fwlink/p/?LinkId=272757), ou o [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/p/?LinkId=391344).</span><span class="sxs-lookup"><span data-stu-id="c497a-123">For more information, see [Installing the .NET Framework](https://go.microsoft.com/fwlink/p/?LinkId=257868) and [Windows Management Framework 3.0](https://go.microsoft.com/fwlink/p/?LinkId=272757) or [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/p/?LinkId=391344).</span></span>
    
    <span data-ttu-id="c497a-124">É preciso usar a versão de 64 bits do Windows devido aos requisitos do módulo do Skype for Business Online e de um dos módulos do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c497a-124">You need to use a 64-bit version of Windows because of the requirements for the Skype for Business Online module and one of the Microsoft 365 modules.</span></span>
    
- <span data-ttu-id="c497a-125">É preciso instalar os módulos necessários para o Azure Active Directory (Azure AD), o Exchange Online, o SharePoint Online, o Skype for Business Online e o Teams:</span><span class="sxs-lookup"><span data-stu-id="c497a-125">You need to install the modules that are required for Azure Active Directory (Azure AD), Exchange Online, SharePoint Online, Skype for Business Online and Teams:</span></span>
    
  - [<span data-ttu-id="c497a-126">Azure Active Directory V2</span><span class="sxs-lookup"><span data-stu-id="c497a-126">Azure Active Directory V2</span></span>](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)
  - [<span data-ttu-id="c497a-127">Shell de Gerenciamento do SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="c497a-127">SharePoint Online Management Shell</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=255251)
  - [<span data-ttu-id="c497a-128">Skype for Business Online, módulo do PowerShell</span><span class="sxs-lookup"><span data-stu-id="c497a-128">Skype for Business Online, PowerShell Module</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=532439)
  - [<span data-ttu-id="c497a-129">PowerShell do Exchange Online V2</span><span class="sxs-lookup"><span data-stu-id="c497a-129">Exchange Online PowerShell V2</span></span>](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell-v2#install-and-maintain-the-exchange-online-powershell-v2-module)
  - [<span data-ttu-id="c497a-130">Visão Geral do PowerShell do Teams</span><span class="sxs-lookup"><span data-stu-id="c497a-130">Teams PowerShell Overview</span></span>](https://docs.microsoft.com/microsoftteams/teams-powershell-overview)
    
-  <span data-ttu-id="c497a-131">O PowerShell precisa ser configurado para executar os scripts assinados do Skype for Business Online e do Centro de Conformidade e &amp; Segurança.</span><span class="sxs-lookup"><span data-stu-id="c497a-131">PowerShell needs to be configured to run signed scripts for Skype for Business Online and the Security &amp; Compliance Center.</span></span> <span data-ttu-id="c497a-132">Para fazer isso, execute o comando a seguir em uma janela elevada do PowerShell (uma janela do PowerShell que você abre quando seleciona **Executar como administrador**).</span><span class="sxs-lookup"><span data-stu-id="c497a-132">To do this, run the following command in an elevated PowerShell session (a PowerShell window you open by selecting **Run as administrator**).</span></span>
    
   ```powershell
   Set-ExecutionPolicy RemoteSigned
   ```

## <a name="exchange-online-and-security-amp-compliance-center-with-the-exchange-online-powershell-v2-module"></a><span data-ttu-id="c497a-133">Exchange Online e Centro de Conformidade &amp; e Segurança com o módulo do Windows PowerShell V2 do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="c497a-133">Exchange Online and Security &amp; Compliance Center with the Exchange Online PowerShell V2 module</span></span>

<span data-ttu-id="c497a-134">Este artigo usa o módulo do Microsoft Windows PowerShell V2 do Exchange Online para se conectar ao Centro de Conformidade do Exchange Online e ao Centro de Conformidade &amp; e Segurança.</span><span class="sxs-lookup"><span data-stu-id="c497a-134">This article uses the Exchange Online PowerShell V2 module to connect to both Exchange Online and Security &amp; Compliance Center.</span></span> <span data-ttu-id="c497a-135">No entanto, neste momento você não consegue se conectar ao Exchange Online e ao &amp; Centro de Conformidade **e Segurança na mesma janela do Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="c497a-135">However, at this time you cannot connect to both Exchange Online and the Security &amp; Compliance Center **in the same PowerShell window**.</span></span>

<span data-ttu-id="c497a-136">Portanto, você deve escolher uma conexão com o Exchange Online *ou* o Centro de Conformidade &amp; e Segurança ao configurar uma janela do PowerShell para vários serviços do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c497a-136">Therefore, you must choose a connection with either Exchange Online *or* the Security &amp; Compliance Center when configuring a PowerShell window for multiple Microsoft 365 services.</span></span>

## <a name="connection-steps-when-using-just-a-password"></a><span data-ttu-id="c497a-137">Etapas de conexão quando estiver usando apenas uma senha</span><span class="sxs-lookup"><span data-stu-id="c497a-137">Connection steps when using just a password</span></span>

<span data-ttu-id="c497a-138">Estas são as etapas para se conectar a todos os serviços em uma única janela do PowerShell quando você estiver usando apenas uma senha para entrar.</span><span class="sxs-lookup"><span data-stu-id="c497a-138">Here are the steps to connect to all the services in a single PowerShell window when you are using just a password for sign-in.</span></span>
  
1. <span data-ttu-id="c497a-139">Abra o PowerShell do Windows.</span><span class="sxs-lookup"><span data-stu-id="c497a-139">Open Windows PowerShell.</span></span>
    
2. <span data-ttu-id="c497a-140">Execute este comando e digite as credenciais da sua conta corporativa ou de estudante do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c497a-140">Run this command and enter your Microsoft 365 work or school account credentials.</span></span>
    
   ```powershell
   $credential = Get-Credential
   ```

3. <span data-ttu-id="c497a-141">Execute este comando para se conectar ao Azure AD usando o PowerShell do Azure Active Directory para o módulo Gráfico.</span><span class="sxs-lookup"><span data-stu-id="c497a-141">Run this command to connect to Azure AD using the Azure Active Directory PowerShell for Graph module.</span></span>
    
   ```powershell
   Connect-AzureAD -Credential $credential
   ```
  
   <span data-ttu-id="c497a-142">Alternativamente, se você estiver usando o Módulo do Microsoft Azure Active Directory para o módulo PowerShell do Windows, execute este comando.</span><span class="sxs-lookup"><span data-stu-id="c497a-142">Alternately, if you are using the Microsoft Azure Active Directory Module for Windows PowerShell module, run this command.</span></span>
      
   ```powershell
   Connect-MsolService -Credential $credential
   ```

   > [!Note]
   > <span data-ttu-id="c497a-143">O PowerShell Core não é compatível com o módulo do Microsoft Azure Active Directory para módulo e cmdlets do Windows PowerShell com **MSol** no nome.</span><span class="sxs-lookup"><span data-stu-id="c497a-143">PowerShell Core does not support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="c497a-144">Para continuar usando esses cmdlets, você deve executá-los a partir do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c497a-144">To continue using these cmdlets, you must run them from PowerShell.</span></span>

4. <span data-ttu-id="c497a-145">Execute estes comandos para se conectar ao SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="c497a-145">Run these commands to connect to SharePoint Online.</span></span> <span data-ttu-id="c497a-146">Especifique o nome da organização para o seu domínio.</span><span class="sxs-lookup"><span data-stu-id="c497a-146">Specify the organization name for your domain.</span></span> <span data-ttu-id="c497a-147">Por exemplo, para "litwareinc.onmicrosoft.com" o valor nome da organização é "litwareinc".</span><span class="sxs-lookup"><span data-stu-id="c497a-147">For example, for "litwareinc.onmicrosoft.com", the  organization name value is "litwareinc".</span></span>
    
   ```powershell
   $orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
   Connect-SPOService -Url https://$orgName-admin.sharepoint.com -Credential $userCredential
   ```

5. <span data-ttu-id="c497a-148">Execute estes comandos para se conectar ao Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="c497a-148">Run these commands to connect to Skype for Business Online.</span></span> <span data-ttu-id="c497a-149">Um aviso sobre o aumento do valor de `WSMan NetworkDelayms` é esperado na primeira vez que você se conectar e deve ser ignorado.</span><span class="sxs-lookup"><span data-stu-id="c497a-149">A warning about increasing the `WSMan NetworkDelayms` value is expected the first time you connect and should be ignored.</span></span>
     
   ```powershell
   Import-Module SkypeOnlineConnector
   $sfboSession = New-CsOnlineSession -Credential $credential
   Import-PSSession $sfboSession
   ```

6. <span data-ttu-id="c497a-150">Execute este comando para se conectar ao Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="c497a-150">Run this command to connect to Exchange Online.</span></span>
    
   ```powershell
   Import-Module ExchangeOnlineManagement
   Connect-ExchangeOnline -Credential $credential -ShowProgress $true
   ```

   > [!Note]
   > <span data-ttu-id="c497a-151">Para se conectar às nuvens do Exchange Online para Microsoft 365 que não sejam Mundiais, confira[Conectar ao PowerShell do Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="c497a-151">To connect to Exchange Online for Microsoft 365 clouds other than Worldwide, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

7. <span data-ttu-id="c497a-152">Como alternativa, execute estes comandos para se conectar ao Centro de Conformidade &amp; e Segurança.</span><span class="sxs-lookup"><span data-stu-id="c497a-152">Alternately, run these commands to connect to the Security &amp; Compliance Center.</span></span>
    
   ```powershell
   $acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
   Import-Module ExchangeOnlineManagement
   Connect-IPPSSession -UserPrincipalName $acctName
   ```

   > [!Note]
   > <span data-ttu-id="c497a-153">Para se conectar às nuvens do Centro de Conformidade &amp; e Segurança do Microsoft 365 que não sejam Mundiais, confira o artigo [Conectar-se ao PowerShell do Centro de Conformidade e Segurança](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span><span class="sxs-lookup"><span data-stu-id="c497a-153">To connect to the Security &amp; Compliance Center for Microsoft 365 clouds other than Worldwide, see [Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span></span>

8. <span data-ttu-id="c497a-154">Execute estes comandos para se conectar ao PowerShell do Teams.</span><span class="sxs-lookup"><span data-stu-id="c497a-154">Run these commands to connect to Teams PowerShell.</span></span>
    
   ```powershell
   Import-Module MicrosoftTeams
   Connect-MicrosoftTeams -Credential $credential
   ```
  
   > [!Note]
   > <span data-ttu-id="c497a-155">Para se conectar às nuvens do Microsoft Teams que não sejam Mundiais, confira o artigo [Conectar-se ao MicrosoftTeams](https://docs.microsoft.com/powershell/module/teams/connect-microsoftteams).</span><span class="sxs-lookup"><span data-stu-id="c497a-155">To connect to Microsoft Teams clouds other than Worldwide, see [Connect-MicrosoftTeams](https://docs.microsoft.com/powershell/module/teams/connect-microsoftteams).</span></span>


### <a name="azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="c497a-156">Use o Windows PowerShell do Azure Active Directory para o módulo do Graph</span><span class="sxs-lookup"><span data-stu-id="c497a-156">Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="c497a-157">Estes são os comandos para todos os serviços *exceto o &amp; Centro de Conformidade* e Segurança em um único bloco ao usar o módulo do Windows PowerShell do Azure Active Directory para Graph.</span><span class="sxs-lookup"><span data-stu-id="c497a-157">Here are the commands for all of the services *except Security &amp; Compliance Center* in a single block when using the Azure Active Directory PowerShell for Graph module.</span></span> <span data-ttu-id="c497a-158">Especifique o nome do seu host de domínio e, em seguida, execute todos eles ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="c497a-158">Specify the name of your domain host, and then run them all at one time.</span></span>
  
```powershell
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
$credential = Get-Credential
Connect-AzureAD -Credential $credential
Import-Module Microsoft.Online.SharePoint.PowerShell -DisableNameChecking
Connect-SPOService -Url https://$orgName-admin.sharepoint.com -credential $credential
Import-Module SkypeOnlineConnector
$sfboSession = New-CsOnlineSession -Credential $credential
Import-PSSession $sfboSession
Import-Module ExchangeOnlineManagement
Connect-ExchangeOnline -Credential $credential -ShowProgress $true
Import-Module MicrosoftTeams
Connect-MicrosoftTeams -Credential $credential
```

<span data-ttu-id="c497a-159">Estes são os comandos para todos os serviços *, exceto o Exchange Online* em um único bloco ao usar o módulo do Windows PowerShell do Azure Active Directory para o módulo do Graph.</span><span class="sxs-lookup"><span data-stu-id="c497a-159">Here are the commands for all of the services *except Exchange Online* in a single block when using the Azure Active Directory PowerShell for Graph module.</span></span> <span data-ttu-id="c497a-160">Especifique o nome do seu host de domínio e a UPN para entrar e, em seguida, execute todos eles ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="c497a-160">Specify the name of your domain host and the UPN for the sign-in, and then run them all at one time.</span></span>
  
```powershell
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$credential = Get-Credential -UserName $acctName
Connect-AzureAD -Credential $credential
Import-Module Microsoft.Online.SharePoint.PowerShell -DisableNameChecking
Connect-SPOService -Url https://$orgName-admin.sharepoint.com -credential $credential
Import-Module SkypeOnlineConnector
$sfboSession = New-CsOnlineSession -Credential $credential
Import-PSSession $sfboSession
Import-Module ExchangeOnlineManagement
Connect-IPPSSession -UserPrincipalName $acctName
Import-Module MicrosoftTeams
Connect-MicrosoftTeams -Credential $credential
```

### <a name="microsoft-azure-active-directory-module-for-windows-powershell-module"></a><span data-ttu-id="c497a-161">Módulo Microsoft Azure Active Directory para Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c497a-161">Microsoft Azure Active Directory Module for Windows PowerShell module</span></span>

<span data-ttu-id="c497a-162">Aqui estão os comandos para todos os serviços *, exceto o &amp;Centro de Conformidade* e Segurança em um único bloco ao usar o Módulo Microsoft Azure Active Directory para Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c497a-162">Here are the commands for all of the services *except Security &amp; Compliance Center* in a single block when using the Microsoft Azure Active Directory Module for Windows PowerShell module.</span></span> <span data-ttu-id="c497a-163">Especifique o nome do seu host de domínio e, em seguida, execute todos eles ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="c497a-163">Specify the name of your domain host, and then run them all at one time.</span></span>
  
```powershell
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
$credential = Get-Credential
Connect-MsolService -Credential $credential
Import-Module Microsoft.Online.SharePoint.PowerShell -DisableNameChecking
Connect-SPOService -Url https://$orgName-admin.sharepoint.com -credential $credential
Import-Module SkypeOnlineConnector
$sfboSession = New-CsOnlineSession -Credential $credential
Import-PSSession $sfboSession
Import-Module ExchangeOnlineManagement
Connect-ExchangeOnline -Credential $credential -ShowProgress $true
Import-Module MicrosoftTeams
Connect-MicrosoftTeams -Credential $credential
```

<span data-ttu-id="c497a-164">Aqui estão os comandos para todos os serviços *, exceto o Exchange Online* em um único bloco ao usar o Módulo Microsoft Azure Active Directory para Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c497a-164">Here are the commands for all of the services *except Exchange Online* in a single block when using the Microsoft Azure Active Directory Module for Windows PowerShell module.</span></span> <span data-ttu-id="c497a-165">Especifique o nome do seu host de domínio e a UPN para entrar e, em seguida, execute todos eles ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="c497a-165">Specify the name of your domain host and the UPN for the sign-in, and then run them all at one time.</span></span>
  
```powershell
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$credential = Get-Credential -UserName $acctName
Connect-AzureAD -Credential $credential
Import-Module Microsoft.Online.SharePoint.PowerShell -DisableNameChecking
Connect-SPOService -Url https://$orgName-admin.sharepoint.com -credential $credential
Import-Module SkypeOnlineConnector
$sfboSession = New-CsOnlineSession -Credential $credential
Import-PSSession $sfboSession
Import-Module ExchangeOnlineManagement
Connect-IPPSSession -UserPrincipalName $acctName
Import-Module MicrosoftTeams
Connect-MicrosoftTeams -Credential $credential
```
## <a name="connection-steps-when-using-multi-factor-authentication"></a><span data-ttu-id="c497a-166">Etapas de conexão quando estiver usando a autenticação multifator</span><span class="sxs-lookup"><span data-stu-id="c497a-166">Connection steps when using multi-factor authentication</span></span>

### <a name="azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="c497a-167">Use o Windows PowerShell do Azure Active Directory para o módulo do Graph</span><span class="sxs-lookup"><span data-stu-id="c497a-167">Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="c497a-168">Aqui estão todos os comandos em um único bloco para se conectar a vários serviços do Microsoft 365, *exceto o &amp;Centro de Conformidade* e Segurança com a autenticação multifator usando o Microsoft Windows PowerShell do Azure Active Directory para módulo do Graph.</span><span class="sxs-lookup"><span data-stu-id="c497a-168">Here are all the commands in a single block to connect to multiple Microsoft 365 services *except Security &amp; Compliance Center* with multi-factor authentication using the Azure Active Directory PowerShell for Graph module.</span></span>

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
Import-Module ExchangeOnlineManagement
Connect-ExchangeOnline -UserPrincipalName $acctName -ShowProgress $true
#Teams
Import-Module MicrosoftTeams
Connect-MicrosoftTeams
```
<span data-ttu-id="c497a-169">Aqui estão todos os comandos em um único bloco para se conectar a vários serviços do Microsoft 365, *exceto o Exchange Online* com a autenticação multifator usando o Windows PowerShell do Azure Active Directory para módulo do Graph.</span><span class="sxs-lookup"><span data-stu-id="c497a-169">Here are all the commands in a single block to connect to multiple Microsoft 365 services *except Exchange Online* with multi-factor authentication using the Azure Active Directory PowerShell for Graph module.</span></span>

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
#Security & Compliance Center
Import-Module ExchangeOnlineManagement
Connect-IPPSSession -UserPrincipalName $acctName
#Teams
Import-Module MicrosoftTeams
Connect-MicrosoftTeams
```
### <a name="microsoft-azure-active-directory-module-for-windows-powershell-module"></a><span data-ttu-id="c497a-170">Módulo Microsoft Azure Active Directory para Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c497a-170">Microsoft Azure Active Directory Module for Windows PowerShell module</span></span>

<span data-ttu-id="c497a-171">Aqui estão todos os comandos em um único bloco para se conectar a vários serviços do Microsoft 365, *exceto o &amp;Centro de Conformidade* e Segurança com a autenticação multifator usando o Módulo Microsoft Azure Active Directory para Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c497a-171">Here are all the commands in a single block to connect to multiple Microsoft 365 services *except Security &amp; Compliance Center* with multi-factor authentication using the Microsoft Azure Active Directory Module for Windows PowerShell module.</span></span>

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
Import-Module ExchangeOnlineManagement
Connect-ExchangeOnline -UserPrincipalName $acctName -ShowProgress $true
#Teams
Import-Module MicrosoftTeams
Connect-MicrosoftTeams
```
<span data-ttu-id="c497a-172">Aqui estão todos os comandos em um único bloco para se conectar a vários serviços do Microsoft 365, *exceto o Exchange Online* usando a autenticação multifator com o Módulo Microsoft Azure Active Directory para Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c497a-172">Here are all the commands in a single block to connect to multiple Microsoft 365 services *except Exchange Online* using multi-factor authentication with the Microsoft Azure Active Directory Module for Windows PowerShell module.</span></span>

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
#Security & Compliance Center
Import-Module ExchangeOnlineManagement
Connect-IPPSSession -UserPrincipalName $acctName
#Teams
Import-Module MicrosoftTeams
Connect-MicrosoftTeams
```

## <a name="close-the-powershell-window"></a><span data-ttu-id="c497a-173">Fechar a janela do PowerShell</span><span class="sxs-lookup"><span data-stu-id="c497a-173">Close the PowerShell window</span></span>

<span data-ttu-id="c497a-174">Quando estiver pronto para fechar a janela do PowerShell, execute este comando para remover as sessões ativas do Skype for Business Online, SharePoint Online e Teams:</span><span class="sxs-lookup"><span data-stu-id="c497a-174">When you are ready to close down the PowerShell window, run this command to remove the active sessions to Skype for Business Online, SharePoint Online, and Teams:</span></span>
  
```powershell
Remove-PSSession $sfboSession ; Disconnect-SPOService ; Disconnect-MicrosoftTeams 
```


## <a name="see-also"></a><span data-ttu-id="c497a-175">Confira também</span><span class="sxs-lookup"><span data-stu-id="c497a-175">See also</span></span>

- [<span data-ttu-id="c497a-176">Conectar-se ao Microsoft 365 com o PowerShell</span><span class="sxs-lookup"><span data-stu-id="c497a-176">Connect to Microsoft 365 with PowerShell</span></span>](connect-to-microsoft-365-powershell.md)
- [<span data-ttu-id="c497a-177">Gerenciar o SharePoint Online com o PowerShell</span><span class="sxs-lookup"><span data-stu-id="c497a-177">Manage SharePoint Online with PowerShell</span></span>](manage-sharepoint-online-with-microsoft-365-powershell.md)
- [<span data-ttu-id="c497a-178">Gerenciar contas de usuário, licenças e grupos do Microsoft 365 com o PowerShell</span><span class="sxs-lookup"><span data-stu-id="c497a-178">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
