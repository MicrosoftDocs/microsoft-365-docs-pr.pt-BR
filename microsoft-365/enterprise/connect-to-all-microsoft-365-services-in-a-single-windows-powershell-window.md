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
ms.openlocfilehash: 4128e360a3664d3a61559139bc4e6e346418fa61
ms.sourcegitcommit: e7bf23df4852b78912229d1d38ec475223597f34
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "49087022"
---
# <a name="connect-to-all-microsoft-365-services-in-a-single-powershell-window"></a>Conectar-se a todos os serviços do Microsoft 365 usando uma única janela do PowerShell

Ao usar o Windows PowerShell para gerenciar o Microsoft 365, você pode ter várias sessões do PowerShell abertas ao mesmo tempo. Você pode ter diferentes janelas do PowerShell para gerenciar contas de usuário, Microsoft Office SharePoint Online, Exchange Online, Skype for Business Online, Microsoft Teams e o &amp; Centro de Conformidade de Segurança.
  
Este cenário não é ideal para gerenciar o Microsoft 365, porque você não pode trocar dados entre essas janelas para gerenciamento entre serviços. Este artigo descreve como usar uma única instância do Windows PowerShell para gerenciar contas do Microsoft 365, Skype for Business Online, Exchange Online, Microsoft Office SharePoint Online, Microsoft Teams e o &amp; Centro de Conformidade de Segurança.

>[!Note]
>Atualmente este artigo contém apenas os comandos necessários para se conectar com a nuvem mundial (+GCC). As notas fornecem links para artigos sobre conexão com outras nuvens do Microsoft 365.

## <a name="before-you-begin"></a>Antes de começar

Antes que você possa gerenciar o Microsoft 365 inteiro a partir de uma única instância do PowerShell, considere os seguinte pré-requisitos:
  
- A conta corporativa ou de estudante do Microsoft 365 que você usa deve ser membro de uma função de administrador do Microsoft 365. Para obter mais informações, confira o artigo [Sobre funções de administrador](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles). Este é um requisito do Windows PowerShell para Microsoft 365, mas não necessariamente para todos os outros serviços do Microsoft 365.
    
- Você pode usar as seguintes versões de 64 bits do Windows:
    
  - Windows 10
    
  - Windows 8.1 ou Windows 8
    
  - Windows Server 2019
    
  - Windows Server 2016
    
  - Windows Server 2012 R2 ou Windows Server 2012
    
  - Windows 7 Service Pack 1 (SP1)*
    
  - Windows Server 2008 R2 SP1*
    
    \* É necessário instalar o Microsoft .NET Framework 4.5. *x* e o Windows Management Framework 3.0 ou 4.0. Para obter mais informações, confira [Windows Management Framework](https://docs.microsoft.com/powershell/scripting/windows-powershell/wmf/overview?view=powershell-7).
    
    É preciso usar a versão de 64 bits do Windows devido aos requisitos do módulo do Skype for Business Online e de um dos módulos do Microsoft 365.
    
- É preciso instalar os módulos necessários para o Azure Active Directory (Azure AD), o Exchange Online, o SharePoint Online, o Skype for Business Online e o Teams:
    
  - [Azure Active Directory V2](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)
  - [Shell de Gerenciamento do SharePoint Online](https://go.microsoft.com/fwlink/p/?LinkId=255251)
  - [Skype for Business Online, módulo do PowerShell](https://docs.microsoft.com/microsoftteams/teams-powershell-overview)
  - [PowerShell do Exchange Online V2](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell-v2#install-and-maintain-the-exchange-online-powershell-v2-module)
  - [Visão Geral do PowerShell do Teams](https://docs.microsoft.com/microsoftteams/teams-powershell-overview)
    
-  O Windows PowerShell deve ser configurado para executar scripts assinados para o Cliente Skype® for Business Online e o &amp; Centro de Conformidade de Segurança. Execute o seguinte comando em uma sessão Windows PowerShell elevada (uma sessão PowerShell que você **Executa como administrador**).
    
   ```powershell
   Set-ExecutionPolicy RemoteSigned
   ```

## <a name="exchange-online-and-security-amp-compliance-center-with-the-exchange-online-powershell-v2-module"></a>O Exchange Online e o &amp; Centro de Conformidade de Segurança com o módulo do Windows PowerShell V2 do Exchange Online

Os procedimentos neste artigo usam o módulo Exchange Online Windows PowerShell V2 para ambos se conectarem ao Exchange Online e ao &amp; Centro de Conformidade de Segurança. Mas atualmente você não pode se conectar a ambos *na mesma janela do Windows PowerShell*. Portanto, você deve escolher se conectar a um ou outro ao configurar uma janela do PowerShell para vários serviços do Microsoft 365.

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
   Connect-SPOService -Url https://$orgName-admin.sharepoint.com -Credential $Credential
   ```

5. Execute esses comandos para se conectar ao Skype for Business Online. Um aviso sobre o aumento do valor de `WSMan NetworkDelayms` aparecerá na primeira vez que você se conectar. Ignore isto.
     
   > [!Note]
   > O Conector Skype for Business Online atualmente faz parte do módulo mais recente do PowerShell do Teams. Se você estiver usando o último lançamento público do PowerShell Teams, você não precisa instalar o Conector do Skype for Business Online.
   
   ```powershell
   Import-Module MicrosoftTeams
   $sfboSession = New-CsOnlineSession -Credential $credential
   Import-PSSession $sfboSession
   ```

6. Execute este comando para se conectar ao Exchange Online.
    
   ```powershell
   Import-Module ExchangeOnlineManagement
   Connect-ExchangeOnline -Credential $credential -ShowProgress $true
   ```

   > [!Note]
   > Para se conectar às nuvens do Exchange Online para Microsoft 365 que não sejam Mundiais, confira[Conectar ao PowerShell do Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).

   Como alternativa, execute estes comandos para se conectar ao &amp; Centro de Conformidade de Segurança.
    
   ```powershell
   $acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
   Import-Module ExchangeOnlineManagement
   Connect-IPPSSession -UserPrincipalName $acctName
   ```

   > [!Note]
   > Para se conectar às nuvens do Centro de Conformidade &amp; e Segurança do Microsoft 365 que não sejam Mundiais, confira o artigo [Conectar-se ao PowerShell do Centro de Conformidade e Segurança](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).

   Execute estes comandos para se conectar ao PowerShell do Teams.
    
   ```powershell
   Import-Module MicrosoftTeams
   Connect-MicrosoftTeams -Credential $credential
   ```
  
   > [!Note]
   > Para se conectar a nuvens do Microsoft Teams que não sejam *Worldwide*, confira [Connect-MicrosoftTeams](https://docs.microsoft.com/powershell/module/teams/connect-microsoftteams).


### <a name="azure-active-directory-powershell-for-graph-module"></a>Módulo do Azure Active Directory Windows PowerShell para Graph

Aqui estão os comandos para todos os serviços *exceto &amp; Centro de Conformidade de Segurança* em um único bloco quando você usa o Azure Active Directory Windows PowerShell para módulo Graph. Especifique o nome do host de domínio e execute-os todos ao mesmo tempo.
  
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

Aqui estão os comandos para todos os serviços *exceto Exchange Online* em um único bloco quando você usa o Azure Active Directory Windows PowerShell para o módulo Graph. Especifique o nome do host de domínio e o UPN para a entrada e execute-os todos ao mesmo tempo.
  
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

### <a name="microsoft-azure-active-directory-module-for-windows-powershell-module"></a>Módulo Microsoft Azure Active Directory para Windows PowerShell

Aqui estão os comandos para todos os serviços *exceto &amp; Centro de Conformidade de Segurança* em um único bloco quando você usa o Módulo Microsoft Azure Active Directory para Windows PowerShell. Especifique o nome do host de domínio e execute-os todos de uma vez.
  
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

Aqui estão os comandos para todos os serviços *exceto Exchange Online* em um único bloco quando você usa o Módulo Microsoft Azure Active Directory para Windows PowerShell. Especifique o nome do host de domínio e o UPN para a entrada e execute-os todos de uma vez.
  
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
## <a name="connection-steps-when-using-multi-factor-authentication"></a>Etapas de conexão ao usar autenticação multifator

### <a name="azure-active-directory-powershell-for-graph-module"></a>Use o Windows PowerShell do Azure Active Directory para o módulo do Graph

Aqui estão todos os comandos em um único bloco para se conectar a vários serviços do Microsoft 365 *exceto &amp; Centro de Conformidade de Segurança* quando você usa a autenticação multifator com o Azure Active Directory Windows PowerShell para módulo Graph.

```powershell
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
#Azure Active Directory
Connect-AzureAD
#SharePoint Online
Connect-SPOService -Url https://$orgName-admin.sharepoint.com
#Skype for Business Online
Import-Module MicrosoftTeams
$sfboSession = New-CsOnlineSession -UserName $acctName
Import-PSSession $sfboSession
#Exchange Online
Import-Module ExchangeOnlineManagement
Connect-ExchangeOnline -UserPrincipalName $acctName -ShowProgress $true
#Teams
Import-Module MicrosoftTeams
Connect-MicrosoftTeams
```
Aqui estão todos os comandos em um único bloco para conectar a vários serviços Microsoft 365 *exceto Exchange Online* com autenticação multifator quando você usa o Azure Active Directory Windows PowerShell para módulo Graph.

```powershell
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
#Azure Active Directory
Connect-AzureAD
#SharePoint Online
Connect-SPOService -Url https://$orgName-admin.sharepoint.com
#Skype for Business Online
Import-Module MicrosoftTeams
$sfboSession = New-CsOnlineSession -UserName $acctName
Import-PSSession $sfboSession
#Security & Compliance Center
Import-Module ExchangeOnlineManagement
Connect-IPPSSession -UserPrincipalName $acctName
#Teams
Import-Module MicrosoftTeams
Connect-MicrosoftTeams
```
### <a name="microsoft-azure-active-directory-module-for-windows-powershell-module"></a>Módulo Microsoft Azure Active Directory para Windows PowerShell

Aqui estão todos os comandos em um único bloco para se conectar a vários serviços do Microsoft 365 *exceto &amp; Centro de Conformidade de Segurança* quando você usa autenticação multifator com o Módulo Microsoft Azure Active Directory para Windows PowerShell.

```powershell
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
#Azure Active Directory
Connect-MsolService
#SharePoint Online
Connect-SPOService -Url https://$orgName-admin.sharepoint.com
#Skype for Business Online
Import-Module MicrosoftTeams
$sfboSession = New-CsOnlineSession -UserName $acctName
Import-PSSession $sfboSession
#Exchange Online
Import-Module ExchangeOnlineManagement
Connect-ExchangeOnline -UserPrincipalName $acctName -ShowProgress $true
#Teams
Import-Module MicrosoftTeams
Connect-MicrosoftTeams
```
Aqui estão todos os comandos em um único bloco para se conectar a vários serviços Microsoft 365 *exceto Exchange Online* quando você usa autenticação multifator com o Módulo Microsoft Azure Active Directory para Windows PowerShell.

```powershell
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
#Azure Active Directory
Connect-MsolService
#SharePoint Online
Connect-SPOService -Url https://$orgName-admin.sharepoint.com
#Skype for Business Online
Import-Module MicrosoftTeams
$sfboSession = New-CsOnlineSession -UserName $acctName
Import-PSSession $sfboSession
#Security & Compliance Center
Import-Module ExchangeOnlineManagement
Connect-IPPSSession -UserPrincipalName $acctName
#Teams
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
