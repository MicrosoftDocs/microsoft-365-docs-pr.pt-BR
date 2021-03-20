---
title: Configurar propriedades de conta de usuário do Microsoft 365 com o PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- O365ITProTrain
- Ent_Office_Other
- PowerShell
ms.assetid: 30813f8d-b08d-444b-98c1-53df7c29b4d7
description: Use o PowerShell para o Microsoft 365 para configurar propriedades de contas de usuário individuais ou múltiplas em seu locatário do Microsoft 365.
ms.openlocfilehash: 6b674641842f89fd8c8e22dc26350cdd53734b9e
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50911079"
---
# <a name="configure-microsoft-365-user-account-properties-with-powershell"></a>Configurar propriedades de conta de usuário do Microsoft 365 com o PowerShell

*Este artigo se aplica tanto ao Microsoft 365 Enterprise quanto ao Office 365 Enterprise.*

Você pode usar o Centro de administração do Microsoft 365 para configurar propriedades para as contas de usuário do locatário do Microsoft 365. No PowerShell, você também pode fazer isso, além de outras coisas que não pode fazer no centro de administração.
  
## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Use o PowerShell do Azure Active Directory para o módulo do gráfico

Para configurar propriedades para contas de usuário no módulo PowerShell do Azure Active Directory para Graph, use o cmdlet [**Set-AzureADUser**](/powershell/module/azuread/set-azureaduser?view=azureadps-2.0) e especifique as propriedades para definir ou alterar.

Primeiro, [conecte-se ao locatário do Microsoft 365.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)
   
### <a name="change-properties-for-a-specific-user-account"></a>Alterar propriedades para uma conta de usuário específica

Você identifica a conta com o parâmetro *-ObjectID* e definir ou alterar propriedades específicas usando parâmetros adicionais. Aqui está uma lista dos parâmetros mais comuns:
  
- -Department \<department name> "
    
- -DisplayName " \<full user name> "
    
- -FacsimilieTelephoneNumber " \<fax number> "
    
- -GivenName " \<user first name> "
    
- -Sobrenome \<user last name> " "
    
- -Mobile \<mobile phone number> "
    
- -JobTitle " \<job title> "
    
- -PreferredLanguage " \<language> "
    
- -StreetAddress " \<street address> "
    
- -City \<city name> "
    
- -State \<state name> "
    
- -PostalCode " \<postal code> "
    
- -Country \<country name> "
    
- -TelephoneNumber " \<office phone number> "
    
- -UsageLocation " \<2-character country or region code> "
    
    Este é o código iso 3166-1 alfa-2 (A2) de duas letras ou código de região.
    
Para obter parâmetros adicionais, consulte [Set-AzureADUser](/powershell/module/azuread/set-azureaduser?view=azureadps-2.0) .

>[!Note]
>Antes de atribuir licenças a uma conta de usuário, você deve atribuir um local de uso.
>

Para exibir o Nome principal do usuário para suas contas de usuário, execute o seguinte comando.
  
```powershell
Get-AzureADUser | Sort UserPrincipalName | Select UserPrincipalName | More
```

Este comando instrui o PowerShell a:
  
1. Obter todas as informações sobre as contas de usuário (**Get-AzureADUser**) e enviá-la para o próximo comando ( **|** ).
    
1. Classificar a lista de Nomes de Entidades de Usuário em ordem alfabética (**Classificar UserPrincipalName**) e enviá-la para o próximo comando ( **|** ).
    
1. Exibe apenas a propriedade Nome principal do usuário para cada conta (**Selecione UserPrincipalName**).

1. Exibir uma tela de cada vez (**Mais**).
    
Para exibir o Nome principal do usuário para uma conta com base no nome de exibição (nome e sobrenome), execute os seguintes comandos. Preencha a variável *$userName* e remova os \< and > caracteres:
  
```powershell
$userName="<Display name>"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

Este exemplo exibe o Nome de Entidade do Usuário para a conta de usuário que tem o nome de exibição *Caleb Sills*.
  
```powershell
$userName="Caleb Sills"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

Usando uma *variável $upn,* você pode fazer alterações em contas individuais com base no nome de exibição. Veja um exemplo que define o local de uso de *Belinda Newman* como França. Mas especifica seu nome de exibição em vez de seu Nome de Entidade de Usuário:
  
```powershell
$userName="Belinda Newman"
$upn=(Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
Set-AzureADUser -ObjectID $upn -UsageLocation "FR"
```

### <a name="change-properties-for-all-user-accounts"></a>Alterar propriedades para todas as contas de usuário

Para alterar as propriedades de todos os usuários, você pode usar uma combinação dos cmdlets **Get-AzureADUser** e **Set-AzureADUser.** O exemplo a seguir altera o local de uso de todos os usuários para *a França*:
  
```powershell
Get-AzureADUser | Set-AzureADUser -UsageLocation "FR"
```

Este comando instrui o PowerShell a:
  
1. Obter todas as informações sobre as contas de usuário (**Get-AzureADUser**) e enviá-la para o próximo comando ( **|** ).
    
1. Definir o local do usuário como França (**Set-AzureADUser -UsageLocation "FR"**).
    
### <a name="change-properties-for-a-specific-set-of-user-accounts"></a>Alterar propriedades para um conjunto específico de contas de usuário

Para alterar propriedades para um conjunto específico de contas de usuário, você pode usar uma combinação dos cmdlets **Get-AzureADUser**, **Where** e **Set-AzureADUser.** O exemplo a seguir altera o local de uso de todos os usuários no departamento de Contabilidade para *a França*:
  
```powershell
Get-AzureADUser | Where {$_.Department -eq "Accounting"} | Set-AzureADUser -UsageLocation "FR"
```

Este comando instrui o PowerShell a:
  
1. Obter todas as informações sobre as contas de usuário (**Get-AzureADUser**) e enviá-la para o próximo comando ( **|** ).
    
1.  Encontre todas as contas de usuário que tenham sua *propriedade Department* definida como "Contabilidade" (**Where {$_. Department -eq "Accounting"}**), e envie as informações resultantes para o próximo comando ( **|** ).
    
1. Definir o local do usuário como França (**Set-AzureADUser -UsageLocation "FR"**).
    
## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Use o Módulo Microsoft Azure Active Directory para Windows PowerShell.

Para configurar propriedades para contas de usuário com o Módulo do Microsoft Azure Active Directory para Windows PowerShell, use o cmdlet **Set-MsolUser** e especifique as propriedades para definir ou alterar.

Primeiro, [conecte-se ao locatário do Microsoft 365.](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)
  
>[!Note]
>O PowerShell Core não oferece suporte ao Módulo Microsoft Azure Active Directory para Windows PowerShell para o módulo do Windows PowerShell e cmdlets com *Msol* em seus nomes. Execute esses cmdlets do Windows PowerShell.
>

### <a name="change-properties-for-a-specific-user-account"></a>Alterar propriedades para uma conta de usuário específica

Para configurar propriedades para uma conta de usuário específica, use o cmdlet [**Set-MsolUser**](/previous-versions/azure/dn194136(v=azure.100)) e especifique as propriedades para definir ou alterar. 

Você identifica a conta com o *parâmetro -UserPrincipalName* e definir ou alterar propriedades específicas usando parâmetros adicionais. Aqui está uma lista dos parâmetros mais comuns.
  
- -City \<city name> "
    
- -Country \<country name> "
    
- -Department \<department name> "
    
- -DisplayName " \<full user name> "
    
- -Fax \<fax number> "
    
- -FirstName \<user first name> "
    
- -LastName " \<user last name> "
    
- -MobilePhone \<mobile phone number> " "
    
- -Office \<office location> "
    
- -PhoneNumber " \<office phone number> "
    
- -PostalCode " \<postal code> "
    
- -PreferredLanguage " \<language> "
    
- -State \<state name> "
    
- -StreetAddress " \<street address> "
    
- -Title \<title name> "
    
- -UsageLocation " \<2-character country or region code> "
    
    Este é o código iso 3166-1 alfa-2 (A2) de duas letras ou código de região.
    
Para obter parâmetros adicionais, consulte [Set-MsolUser](/previous-versions/azure/dn194136(v=azure.100)).

Para ver os Nomes principais de usuário de todos os seus usuários, execute o seguinte comando:
  
```powershell
Get-MSolUser | Sort UserPrincipalName | Select UserPrincipalName | More
```

Este comando instrui o PowerShell a:
  
1. Obter todas as informações para as contas de usuário (**Get-MsolUser**) e enviá-la para o próximo comando ( **|** ).
    
1. Classificar a lista de Nomes de Entidades de Usuário em ordem alfabética (**Classificar UserPrincipalName**) e enviá-la para o próximo comando ( **|** ).
    
1. Exibe apenas a propriedade Nome principal do usuário para cada conta (**Selecione UserPrincipalName**).
    
1. Exibir uma tela de cada vez (**Mais**).
    
Para exibir o Nome principal do usuário para uma conta com base no nome de exibição (nome e sobrenome), execute os seguintes comandos. Preencha a *variável $userName* e remova os \< and > caracteres.
  
```powershell
$userName="<Display name>"
Write-Host (Get-MsolUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

Este exemplo exibe o Nome de Entidade de Usuário para o usuário chamado Caleb Sills:
  
```powershell
$userName="Caleb Sills"
Write-Host (Get-MsolUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

Usando uma *variável $upn,* você pode fazer alterações em contas individuais com base no nome de exibição. Aqui está um exemplo que define o local de uso de *Belinda Newman* como *França*, mas especifica seu nome de exibição em vez de seu Nome de Entidade de Usuário:
  
```powershell
$userName="<display name>"
$upn=(Get-MsolUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
Set-MsolUser -UserPrincipalName $upn -UsageLocation "FR"
```

### <a name="change-properties-for-all-user-accounts"></a>Alterar propriedades para todas as contas de usuário

Para alterar as propriedades de todos os usuários, use uma combinação dos cmdlets **Get-MsolUser** e **Set-MsolUser.** O exemplo a seguir altera o local de uso de todos os usuários para *a França*:
  
```powershell
Get-MsolUser | Set-MsolUser -UsageLocation "FR"
```

Este comando instrui o PowerShell a:
  
1. Obter todas as informações para as contas de usuário (**Get-MsolUser**) e enviá-la para o próximo comando ( **|** ).
    
1. Definir o local do usuário como França (**Set-MsolUser -UsageLocation "FR"**).
    
### <a name="change-properties-for-a-specific-set-of-user-accounts"></a>Alterar propriedades para um conjunto específico de contas de usuário

Para alterar propriedades para um conjunto específico de contas de usuário, você pode usar uma combinação dos cmdlets **Get-MsolUser**, **Where** e **Set-MsolUser.** O exemplo a seguir altera o local de uso de todos os usuários no departamento de Contabilidade para *a França*:
  
```powershell
Get-MsolUser | Where {$_.Department -eq "Accounting"} | Set-MsolUser -UsageLocation "FR"
```

Este comando instrui o PowerShell a:
  
1. Obter todas as informações para as contas de usuário (**Get-MsolUser**) e enviá-la para o próximo comando ( **|** ).
    
1. Encontre todas as contas de usuário que tenham sua *propriedade Department* definida como "Contabilidade" (**Onde {$_. Departamento -eq "Contabilidade"}**) e envie as informações resultantes para o próximo comando ( **|** ).
    
1. Definir o local do usuário como França (**Set-MsolUser -UsageLocation "FR"**).

## <a name="see-also"></a>Confira também

[Gerenciar contas de usuário, licenças e grupos do Microsoft 365 com o PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[Gerenciar o Microsoft 365 com o PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Introdução ao Windows PowerShell para o Microsoft 365](getting-started-with-microsoft-365-powershell.md)