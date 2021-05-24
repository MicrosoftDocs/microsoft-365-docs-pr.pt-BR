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
ms.openlocfilehash: 923e4bc39ae4391d4deaa2c232e19b9479c2efbe
ms.sourcegitcommit: 9541d5e6720a06327dc785e3ad7e8fb11246fd72
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2021
ms.locfileid: "52583119"
---
# <a name="connect-to-all-microsoft-365-services-in-a-single-powershell-window"></a>Conectar-se a todos os serviços do Microsoft 365 usando uma única janela do PowerShell

Ao usar o Windows PowerShell para gerenciar o Microsoft 365, você pode ter várias sessões do PowerShell abertas ao mesmo tempo. Você pode ter diferentes janelas do PowerShell para gerenciar contas de usuário, Microsoft Office SharePoint Online, Exchange Online, Skype for Business Online, Microsoft Teams e o &amp; Centro de Conformidade de Segurança.
  
Este cenário não é ideal para gerenciar o Microsoft 365, porque você não pode trocar dados entre essas janelas para gerenciamento entre serviços. Este artigo descreve como usar uma única instância do Windows PowerShell para gerenciar contas do Microsoft 365, Skype for Business Online, Exchange Online, Microsoft Office SharePoint Online, Microsoft Teams e o &amp; Centro de Conformidade de Segurança.

>[!Note]
>Atualmente este artigo contém apenas os comandos necessários para se conectar com a nuvem mundial (+GCC). As notas fornecem links para artigos sobre conexão com outras nuvens do Microsoft 365.

## <a name="before-you-begin"></a>Antes de começar

Antes que você possa gerenciar o Microsoft 365 inteiro a partir de uma única instância do PowerShell, considere os seguinte pré-requisitos:
  
- A conta corporativa ou de estudante do Microsoft 365 que você usa deve ser membro de uma função de administrador do Microsoft 365. Para obter mais informações, confira o artigo [Sobre funções de administrador](../admin/add-users/about-admin-roles.md). Este é um requisito do Windows PowerShell para Microsoft 365, mas não necessariamente para todos os outros serviços do Microsoft 365.
    
- Você pode usar as seguintes versões de 64 bits do Windows:
    
  - Windows 10
    
  - Windows 8.1 ou Windows 8
    
  - Windows Server 2019
    
  - Windows Server 2016
    
  - Windows Server 2012 R2 ou Windows Server 2012
    
  - Windows 7 Service Pack 1 (SP1)*
    
  - Windows Server 2008 R2 SP1*
    
    \* É necessário instalar o Microsoft .NET Framework 4.5. *x* e o Windows Management Framework 3.0 ou 4.0. Para obter mais informações, confira [Windows Management Framework](/powershell/scripting/windows-powershell/wmf/overview).
    
    É preciso usar a versão de 64 bits do Windows devido aos requisitos do módulo do Skype for Business Online e de um dos módulos do Microsoft 365.
    
- É preciso instalar os módulos necessários para o Azure Active Directory (Azure AD), o Exchange Online, o SharePoint Online, o Skype for Business Online e o Teams:
    
  - [Azure Active Directory V2](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)
  - [Shell de Gerenciamento do SharePoint Online](https://go.microsoft.com/fwlink/p/?LinkId=255251)
  - [Skype for Business Online, módulo do PowerShell](/microsoftteams/teams-powershell-overview)
  - [PowerShell do Exchange Online V2](/powershell/exchange/exchange-online-powershell-v2#install-and-maintain-the-exchange-online-powershell-v2-module)
  - [Visão Geral do PowerShell do Teams](/microsoftteams/teams-powershell-overview)
    
-  O Windows PowerShell deve ser configurado para executar scripts assinados para o Cliente Skype® for Business Online e o &amp; Centro de Conformidade de Segurança. Execute o seguinte comando em uma sessão Windows PowerShell elevada (uma sessão PowerShell que você **Executa como administrador**).
    
   ```powershell
   Set-ExecutionPolicy RemoteSigned
   ```

## <a name="connection-steps-when-using-just-a-password"></a>Etapas de conexão quando estiver usando apenas uma senha

Siga estas etapas para se conectar a todos os serviços em uma única janela do PowerShell quando estiver usando apenas uma senha para entrar.
  
1. Abra o PowerShell do Windows.
    
2. Execute este comando e digite as credenciais da sua conta corporativa ou de estudante do Microsoft 365.
    
   ```powershell
   $credential = Get-Credential
   ```

3. Execute este comando para se conectar ao Azure AD usando o módulo Azure Active Directory Windows PowerShell para Graph.
    
   ```powershell
   Connect-AzureAD -Credential $credential
   ```
  
   Ou se você estiver usando o Módulo Microsoft Azure Active Directory para Windows PowerShell, execute este comando.
      
   ```powershell
   Connect-MsolService -Credential $credential
   ```

   > [!Note]
   > O PowerShell Core não oferece suporte ao Módulo Microsoft Azure Active Directory para Windows PowerShell para o módulo do Windows PowerShell e cmdlets com *Msol* em seus nomes. Você deve executar esses cmdlets do Windows PowerShell.

4. Execute estes comandos para se conectar ao SharePoint Online. Especifique o nome da organização para o seu domínio. Por exemplo, para "litwareinc\.onmicrosoft.com", o valor do nome da organização é "litwareinc".
    
   ```powershell
   $orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
   Import-Module Microsoft.Online.SharePoint.PowerShell -DisableNameChecking
   Connect-SPOService -Url https://$orgName-admin.sharepoint.com -Credential $Credential
   ```

5. Execute estes comandos para se conectar ao Exchange Online.
    
   ```powershell
   Import-Module ExchangeOnlineManagement
   Connect-ExchangeOnline -ShowProgress $true
   ```

   > [!Note]
   > Para se conectar às nuvens do Exchange Online para Microsoft 365 que não sejam Mundiais, confira[Conectar ao PowerShell do Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).

6. Execute estes comandos para se conectar ao Centro de Conformidade &amp; Segurança.
    
   ```powershell
   $acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
   Connect-IPPSSession -UserPrincipalName $acctName
   ```

   > [!Note]
   > Para se conectar às nuvens do Centro de Conformidade &amp; e Segurança do Microsoft 365 que não sejam Mundiais, confira o artigo [Conectar-se ao PowerShell do Centro de Conformidade e Segurança](/powershell/exchange/connect-to-scc-powershell).

7. Execute estes comandos para se conectar ao PowerShell do Teams (e ao Skype for Business Online).
    
   ```powershell
   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```
  
   > [!Note]
   > O Conector Skype for Business Online atualmente faz parte do módulo mais recente do PowerShell do Teams. Se você estiver usando o último lançamento público do PowerShell Teams, você não precisa instalar o Conector do Skype for Business Online.
  
   > [!Note]
   > Para se conectar a nuvens do Microsoft Teams que não sejam *Worldwide*, confira [Connect-MicrosoftTeams](/powershell/module/teams/connect-microsoftteams).
  


### <a name="azure-active-directory-powershell-for-graph-module"></a>Módulo do Azure Active Directory Windows PowerShell para Graph

Aqui estão os comandos para todos os serviços em um único bloco quando você usa o módulo do PowerShell para Graph do Azure Active Directory. Especifique o nome do host de domínio e o UPN para a entrada e execute-os todos ao mesmo tempo.
  
```powershell
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$credential = Get-Credential -UserName $acctName -Message "Type the account's password."
#Azure Active Directory
Connect-AzureAD -Credential $credential
#SharePoint Online
Import-Module Microsoft.Online.SharePoint.PowerShell -DisableNameChecking
Connect-SPOService -Url https://$orgName-admin.sharepoint.com -credential $credential
#Exchange Online
Import-Module ExchangeOnlineManagement
Connect-ExchangeOnline -ShowProgress $true
#Security & Compliance Center
Connect-IPPSSession -UserPrincipalName $acctName
#Teams and Skype for Business Online
Import-Module MicrosoftTeams
Connect-MicrosoftTeams -Credential $credential
```

### <a name="microsoft-azure-active-directory-module-for-windows-powershell-module"></a>Módulo Microsoft Azure Active Directory para Windows PowerShell

Aqui estão os comandos para todos os serviços em um único bloco quando você usa o Módulo Microsoft Azure Active Directory para Windows PowerShell. Especifique o nome do host de domínio e o UPN para a entrada e execute-os todos de uma vez.
  
```powershell
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$credential = Get-Credential -UserName $acctName -Message "Type the account's password."
#Azure Active Directory
Connect-MsolService -Credential $credential
#SharePoint Online
Import-Module Microsoft.Online.SharePoint.PowerShell -DisableNameChecking
Connect-SPOService -Url https://$orgName-admin.sharepoint.com -credential $credential
#Exchange Online
Import-Module ExchangeOnlineManagement
Connect-ExchangeOnline -ShowProgress $true
#Security & Compliance Center
Connect-IPPSSession -UserPrincipalName $acctName
#Teams and Skype for Business Online
Import-Module MicrosoftTeams
Connect-MicrosoftTeams -Credential $credential
```

## <a name="connection-steps-when-using-multi-factor-authentication"></a>Etapas de conexão quando estiver usando a autenticação multifator

### <a name="azure-active-directory-powershell-for-graph-module"></a>Use o Windows PowerShell do Azure Active Directory para o módulo do Graph

Aqui estão todos os comandos em um único bloco para se conectar a vários serviços do Microsoft 365 ao usar a autenticação multifator com o módulo do PowerShell para Graph do Azure Active Directory.

```powershell
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
#Azure Active Directory
Connect-AzureAD
#SharePoint Online
Connect-SPOService -Url https://$orgName-admin.sharepoint.com
#Exchange Online
Import-Module ExchangeOnlineManagement
Connect-ExchangeOnline -UserPrincipalName $acctName -ShowProgress $true
#Security & Compliance Center
Connect-IPPSSession -UserPrincipalName $acctName
#Teams and Skype for Business Online
Import-Module MicrosoftTeams
Connect-MicrosoftTeams
```
### <a name="microsoft-azure-active-directory-module-for-windows-powershell-module"></a>Módulo Microsoft Azure Active Directory para Windows PowerShell

Aqui estão todos os comandos em um único bloco para se conectar a vários serviços do Microsoft 365 ao usar a autenticação multifator com o Módulo do Microsoft Azure Active Directory para Windows PowerShell.

```powershell
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
#Azure Active Directory
Connect-MsolService
#SharePoint Online
Connect-SPOService -Url https://$orgName-admin.sharepoint.com
#Exchange Online
Import-Module ExchangeOnlineManagement
Connect-ExchangeOnline -UserPrincipalName $acctName -ShowProgress $true
#Security & Compliance Center
Connect-IPPSSession -UserPrincipalName $acctName
#Teams and Skype for Business Online
Import-Module MicrosoftTeams
Connect-MicrosoftTeams
```

## <a name="close-the-powershell-window"></a>Fechar a janela do PowerShell

Para fechar a janela do PowerShell, execute este comando para remover as sessões ativas do Skype for Business Online, Microsoft Office SharePoint Online e Teams:
  
```powershell
Remove-PSSession $sfboSession ; Disconnect-SPOService ; Disconnect-MicrosoftTeams 
```

## <a name="see-also"></a>Confira também

- [Conectar-se ao Microsoft 365 com o PowerShell](connect-to-microsoft-365-powershell.md)
- [Gerenciar o SharePoint Online com o PowerShell](manage-sharepoint-online-with-microsoft-365-powershell.md)
- [Gerenciar contas de usuário, licenças e grupos do Microsoft 365 com o PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
