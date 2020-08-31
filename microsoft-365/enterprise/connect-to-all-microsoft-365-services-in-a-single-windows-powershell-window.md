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
# <a name="connect-to-all-microsoft-365-services-in-a-single-powershell-window"></a>Conectar-se a todos os serviços do Microsoft 365 usando uma única janela do PowerShell

Quando você usa o PowerShell para gerenciar o Microsoft 365, é possível ter múltiplas sessões diferentes do PowerShell do Windows abertas ao mesmo tempo em janelas diferentes do PowerShell, correspondentes ao gerenciamento das contas de usuário, ao SharePoint Online, ao Exchange Online, ao Skype for Business Online, ao Microsoft Teams e ao Centro de Conformidade &amp; Segurança. 
  
Essa não é uma forma ideal de gerenciar o Microsoft 365 porque não é possível trocar dados entre essas janelas para o gerenciamento de diversos serviços. Este tópico descreve como usar uma única instância do PowerShell a partir da qual você pode gerenciar suas contas do Microsoft 365, do Skype for Business Online, do Exchange Online, do SharePoint Online, do Microsoft Teams e do Centro de Conformidade e &amp; Segurança.

>[!Note]
>Atualmente este artigo contém apenas os comandos necessários para se conectar com a nuvem mundial (+GCC). As observações fornecem links para os artigos que contêm informações sobre como se conectar à outras nuvens do Microsoft 365.
>

## <a name="before-you-begin"></a>Antes de começar

Antes que você possa gerenciar o Microsoft 365 inteiro a partir de uma única instância do PowerShell, considere os seguinte pré-requisitos:
  
- A conta corporativa ou de estudante do Microsoft 365 que você usa para esses procedimentos precisa ser membro de uma função de administrador do Microsoft 365. Para obter mais informações, confira o artigo [Sobre funções de administrador](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles?view=o365-worldwide). Isso é obrigatório para o PowerShell no Microsoft 365, mas não necessariamente para todos os demais serviços do Microsoft 365.
    
- Você pode usar as seguintes versões de 64 bits do Windows:
    
  - Windows 10
    
  - Windows 8.1 ou Windows 8
    
  - Windows Server 2019
    
  - Windows Server 2016
    
  - Windows Server 2012 R2 ou Windows Server 2012
    
  - Windows 7 Service Pack 1 (SP1)*
    
  - Windows Server 2008 R2 SP1*
    
    \*É necessário instalar o Microsoft .NET Framework 4.5.*x* e, em seguida, o Windows Management Framework 3.0 ou o Windows Management Framework 4.0. Para obter mais informações, consulte [Instalar o .NET Framework](https://go.microsoft.com/fwlink/p/?LinkId=257868) e [Windows Management 3.0](https://go.microsoft.com/fwlink/p/?LinkId=272757), ou o [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/p/?LinkId=391344).
    
    É preciso usar a versão de 64 bits do Windows devido aos requisitos do módulo do Skype for Business Online e de um dos módulos do Microsoft 365.
    
- É preciso instalar os módulos necessários para o Azure Active Directory (Azure AD), o Exchange Online, o SharePoint Online, o Skype for Business Online e o Teams:
    
   - [Azure Active Directory V2](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)
   - [Shell de Gerenciamento do SharePoint Online](https://go.microsoft.com/fwlink/p/?LinkId=255251)
   - [Skype for Business Online, módulo do PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=532439)
   - [PowerShell do Exchange Online V2](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell-v2/exchange-online-powershell-v2?view=exchange-ps#install-and-maintain-the-exchange-online-powershell-v2-module)
   - [Visão Geral do PowerShell do Teams](https://docs.microsoft.com/microsoftteams/teams-powershell-overview)
    
-  O PowerShell precisa ser configurado para executar os scripts assinados do Skype for Business Online e do Centro de Conformidade e &amp; Segurança. Para fazer isso, execute o comando a seguir em uma janela elevada do PowerShell (uma janela do PowerShell que você abre quando seleciona **Executar como administrador**).
    
   ```powershell
   Set-ExecutionPolicy RemoteSigned
   ```

## <a name="connection-steps-when-using-just-a-password"></a>Etapas de conexão quando estiver usando apenas uma senha

Estas são as etapas para se conectar a todos os serviços em uma única janela do PowerShell quando você estiver usando apenas uma senha para entrar.
  
1. Abra o PowerShell do Windows.
    
2. Execute este comando e digite as credenciais da sua conta corporativa ou de estudante do Microsoft 365.
    
   ```powershell
   $credential = Get-Credential
   ```

3. Execute este comando para se conectar ao Azure AD usando o PowerShell do Azure Active Directory para o módulo Gráfico.
    
   ```powershell
   Connect-AzureAD -Credential $credential
   ```
  
   Alternativamente, se você estiver usando o Módulo do Microsoft Azure Active Directory para o módulo PowerShell, execute este comando.
      
   ```powershell
   Connect-MsolService -Credential $credential
   ```

   > [!Note]
   > O PowerShell Core não é compatível com o módulo do Microsoft Azure Active Directory para o módulo e cmdlets do PowerShell com **Msol** no nome. Para continuar usando esses cmdlets, você deve executá-los a partir do PowerShell.

4. Execute estes comandos para se conectar ao SharePoint Online. Especifique o nome da organização para o seu domínio. Por exemplo, para "litwareinc.onmicrosoft.com" o valor nome da organização é "litwareinc".
    
   ```powershell
   $orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
   Connect-SPOService -Url https://$orgName-admin.sharepoint.com -Credential $userCredential
   ```

5. Execute estes comandos para se conectar ao Skype for Business Online. Um aviso sobre o aumento do valor de `WSMan NetworkDelayms` é esperado na primeira vez que você se conectar e deve ser ignorado.
     
   ```powershell
   Import-Module SkypeOnlineConnector
   $sfboSession = New-CsOnlineSession -Credential $credential
   Import-PSSession $sfboSession
   ```

6. Execute este comando para se conectar ao Exchange Online.
    
   ```powershell
   Connect-ExchangeOnline -Credential $credential -ShowProgress $true
   ```

   > [!Note]
   > Para se conectar às nuvens do Exchange Online para Microsoft 365 que não sejam Mundiais, use o parâmetro **-ExchangeEnvironmentName**. Confira o artigo [Conectar-se ao ExchangeOnline](https://docs.microsoft.com/powershell/module/exchange/powershell-v2-module/connect-exchangeonline?view=exchange-ps) para obter mais informações.

7. Execute estes comandos para se conectar ao PowerShell do Teams.
    
   ```powershell
   Import-Module MicrosoftTeams
   Connect-MicrosoftTeams -Credential $credential
   ```
  
   > [!Note]
   > Para se conectar às nuvens do Microsoft Teams que não sejam Mundiais, confira o artigo [Conectar-se ao MicrosoftTeams](https://docs.microsoft.com/powershell/module/teams/connect-microsoftteams?view=teams-ps).

8. Execute estes comandos para se conectar ao Centro de Conformidade &amp; Segurança.
    
   ```powershell
   $SccSession = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid/ -Credential $credential -Authentication "Basic" -AllowRedirection
   Import-PSSession $SccSession -Prefix cc
   ```

   > [!Note]
   > Para se conectar às nuvens do Centro de Conformidade &amp; Segurança do Microsoft 365 que não sejam Mundiais, confira o artigo [Conectar-se ao PowerShell do Centro de Conformidade & Segurança](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).

Aqui estão todos os comandos em um único bloco quando estiver usando o PowerShell do Azure Active Directory para o módulo Gráfico. Especifique o nome do seu host de domínio e, em seguida, execute todos eles ao mesmo tempo.
  
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

Alternativamente, aqui estão todos os comandos em um único bloco se você estiver usando o módulo do Microsoft Azure Active Directory para o módulo PowerShell. Especifique o nome do seu host de domínio e, em seguida, execute todos eles ao mesmo tempo.
  
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

Quando estiver pronto para fechar a janela do PowerShell, execute este comando para remover as sessões ativas do Skype for Business Online, SharePoint Online, Centro de Conformidade e &amp; Segurança, e Teams:
  
```powershell
Remove-PSSession $sfboSession ; Remove-PSSession $SccSession ; Disconnect-SPOService ; Disconnect-MicrosoftTeams 
```

## <a name="connection-steps-when-using-multi-factor-authentication"></a>Etapas de conexão quando estiver usando a autenticação multifator

Aqui estão todos os comandos em um único bloco para se conectar ao Azure AD, SharePoint Online, Skype for Business, Exchange Online e Teams usando uma autenticação multifator em uma única janela usando o PowerShell do Azure Active Directory para o módulo Gráfico. Especifique o nome do usuário principal (UPN) de uma conta de usuário e o nome do seu host de domínio e, em seguida, execute todos eles de uma só vez.

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

Alternativamente, aqui estão todos os comandos se você estiver usando o Módulo do Microsoft Azure Active Directory para o módulo PowerShell.

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

Para se conectar ao Centro de Conformidade &amp; Segurança usando a autenticação multifator, confira o artigo [Conectar-se ao PowerShell do Centro de Conformidade & Segurança usando a autenticação multifator](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/mfa-connect-to-scc-powershell?view=exchange-ps):

## <a name="see-also"></a>Confira também

- [Conectar-se ao Microsoft 365 com o PowerShell](connect-to-microsoft-365-powershell.md)
- [Gerenciar o SharePoint Online com o PowerShell](manage-sharepoint-online-with-microsoft-365-powershell.md)
- [Gerenciar contas de usuário, licenças e grupos do Microsoft 365 com o PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
