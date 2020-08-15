---
title: Configurar as propriedades da conta de usuário do Microsoft 365 com o PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/16/2020
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
description: 'Resumo: Use o PowerShell para Microsoft 365 para configurar propriedades de contas de usuário individuais ou múltiplas em seu locatário do Microsoft 365.'
ms.openlocfilehash: 6a435b3981efa8d8c2be7f6d983a1d062237f0db
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46686882"
---
# <a name="configure-microsoft-365-user-account-properties-with-powershell"></a>Configurar as propriedades da conta de usuário do Microsoft 365 com o PowerShell

*Esse artigo se aplica ao Microsoft 365 Enterprise e ao Office 365 Enterprise.*

Embora você possa usar o centro de administração do Microsoft 365 para configurar as propriedades das contas de usuário do seu locatário do Microsoft 365, você também pode usar o PowerShell e realizar algumas coisas que o centro de administração do Microsoft 365 não pode.
  
## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Use o PowerShell do Azure Active Directory para o módulo do gráfico

Para configurar propriedades de contas de usuário com o módulo PowerShell do Azure Active Directory para Graph, use o cmdlet [set-AzureADUser](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser?view=azureadps-2.0) e especifique as propriedades a serem definidas ou alteradas. 

Primeiro, [Conecte-se ao seu locatário do Microsoft 365](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).
   
### <a name="change-properties-for-a-specific-user-account"></a>Alterar as propriedades de uma conta de usuário específica

Você identifica a conta com o parâmetro **-ObjectID** e define ou altera propriedades específicas com parâmetros adicionais. Veja a seguir uma lista dos parâmetros mais comuns.
  
- -Department " \<department name> "
    
- -DisplayName " \<full user name> "
    
- -FacsimilieTelephoneNumber " \<fax number> "
    
- -Excertoname " \<user first name> "
    
- -Sobrenome " \<user last name> "
    
- -Mobile " \<mobile phone number> "
    
- -JobTitle " \<job title> "
    
- -PreferredLanguage " \<language> "
    
- -StreetAddress " \<street address> "
    
- -City " \<city name> "
    
- -State " \<state name> "
    
- -PostalCode " \<postal code> "
    
- -Country " \<country name> "
    
- -TelephoneNumber " \<office phone number> "
    
- -UsageLocation " \<2-character country or region code> "
    
    Este é o código de país ou região ISO 3166-1 alfa-2 (a2) de duas letras.
    
Consulte [set-AzureADUser](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser?view=azureadps-2.0) para parâmetros adicionais.


Para exibir o nome principal do usuário para suas contas de usuário, execute o seguinte comando.
  
```powershell
Get-AzureADUser | Sort UserPrincipalName | Select UserPrincipalName | More
```

Este comando instrui o PowerShell para:
  
- Obtenha todas as informações sobre as contas de usuário (**Get-AzureADUser**) e envie-o para o próximo comando ( **|** ).
    
- Classifique a lista de nomes de entidade de segurança de usuário alfabeticamente (**classificar userPrincipalName**) e enviá-lo para o próximo comando ( **|** ).
    
- Exibe apenas a propriedade nome principal do usuário para cada conta (**selecione userPrincipalName**).

- Exibir uma tela por vez (**mais**).
    
Este comando listará todas as suas contas. Se você deseja exibir o nome principal de usuário para uma conta com base no seu nome de exibição (nome e sobrenome), preencha a variável de **$username** abaixo (removendo os \< and > caracteres) e execute os seguintes comandos:
  
```powershell
$userName="<Display name>"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

Este exemplo exibe o nome principal do usuário para a conta de usuário com o nome de exibição de Carlos Lima.
  
```powershell
$userName="Caleb Sills"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

Usando uma variável de **$UPN** , você pode fazer alterações em contas individuais com base no seu nome de exibição. Aqui está um exemplo de como definir o local de uso do Belinda Newman para a França, mas especificando seu nome de exibição em vez do nome principal do usuário:
  
```powershell
$userName="Belinda Newman"
$upn=(Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
Set-AzureADUser -ObjectID $upn -UsageLocation "FR"
```

### <a name="change-properties-for-all-user-accounts"></a>Alterar propriedades de todas as contas de usuário

Para alterar as propriedades de todos os usuários, você pode usar a combinação dos cmdlets **Get-AzureADUser** e **set-AzureADUser** . O exemplo a seguir altera o local de uso de todos os usuários para a França:
  
```powershell
Get-AzureADUser | Set-AzureADUser -UsageLocation "FR"
```

Este comando instrui o PowerShell para:
  
- Obtenha todas as informações sobre as contas de usuário (**Get-AzureADUser**) e envie-o para o próximo comando ( **|** ).
    
- Defina o local do usuário como França (**set-AzureADUser-UsageLocation "fr"**).
    
### <a name="change-properties-for-a-specific-set-of-user-accounts"></a>Alterar propriedades de um conjunto específico de contas de usuário

Para alterar as propriedades de um conjunto específico de contas de usuário, você pode usar a combinação dos cmdlets **Get-AzureADUser**, **Where**e **set-AzureADUser** . O exemplo a seguir altera o local de uso de todos os usuários no departamento de contabilidade para a França:
  
```powershell
Get-AzureADUser | Where {$_.Department -eq "Accounting"} | Set-AzureADUser -UsageLocation "FR"
```

Este comando instrui o PowerShell para:
  
- Obtenha todas as informações sobre as contas de usuário (**Get-AzureADUser**) e envie-o para o próximo comando ( **|** ).
    
- Encontre todas as contas de usuário que têm a propriedade Department definida como "Accounting" (**onde {$ _. Department-EQ "Accounting"}**) e envie as informações resultantes para o próximo comando ( **|** ).
    
- Defina o local do usuário como França (**set-AzureADUser-UsageLocation "fr"**).
    
## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Use o Módulo Microsoft Azure Active Directory para Windows PowerShell.

Para configurar propriedades de contas de usuário com o módulo Microsoft Azure Active Directory para Windows PowerShell, use o cmdlet **set-MsolUser** e especifique as propriedades a serem definidas ou alteradas. 

Primeiro, [Conecte-se ao seu locatário do Microsoft 365](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).
  
>[!Note]
>O PowerShell Core não é compatível com o módulo do Microsoft Azure Active Directory para módulo e cmdlets do Windows PowerShell com **MSol** no nome. Para continuar usando esses cmdlets, você deve executá-los a partir do Windows PowerShell.
>

### <a name="change-properties-for-a-specific-user-account"></a>Alterar as propriedades de uma conta de usuário específica

Para configurar as propriedades de uma conta de usuário específica, use o cmdlet [set-MsolUser](https://docs.microsoft.com/previous-versions/azure/dn194136(v=azure.100)) e especifique as propriedades a serem definidas ou alteradas. 

Você identifica a conta com o parâmetro **-userPrincipalName** e define ou altera propriedades específicas com parâmetros adicionais. Veja a seguir uma lista dos parâmetros mais comuns.
  
- -City " \<city name> "
    
- -Country " \<country name> "
    
- -Department " \<department name> "
    
- -DisplayName " \<full user name> "
    
- – Fax " \<fax number> "
    
- -FirstName " \<user first name> "
    
- -LastName " \<user last name> "
    
- -MobilePhone " \<mobile phone number> "
    
- -Office " \<office location> "
    
- -PhoneNumber " \<office phone number> "
    
- -PostalCode " \<postal code> "
    
- -PreferredLanguage " \<language> "
    
- -State " \<state name> "
    
- -StreetAddress " \<street address> "
    
- -Title " \<title name> "
    
- -UsageLocation " \<2-character country or region code> "
    
    Este é o código de país ou região ISO 3166-1 alfa-2 (a2) de duas letras.
    
Consulte [set-MsolUser](https://docs.microsoft.com/previous-versions/azure/dn194136(v=azure.100)) para parâmetros adicionais.

Para ver os nomes principais de usuário de todos os seus usuários, execute o seguinte comando.
  
```powershell
Get-MSolUser | Sort UserPrincipalName | Select UserPrincipalName | More
```

Este comando instrui o PowerShell para:
  
- Obtenha todas as informações sobre as contas de usuário (**Get-MsolUser**) e envie-o para o próximo comando ( **|** ).
    
- Classifique a lista de nomes de entidade de segurança de usuário alfabeticamente (**classificar userPrincipalName**) e enviá-lo para o próximo comando ( **|** ).
    
- Exibe apenas a propriedade nome principal do usuário para cada conta (**selecione userPrincipalName**).
    
- Exibir uma tela por vez (**mais**).
    
Este comando listará todas as suas contas. Se você deseja exibir o nome principal de usuário para uma conta com base no seu nome de exibição (nome e sobrenome), preencha a variável de **$username** abaixo (removendo os \< and > caracteres) e execute os seguintes comandos:
  
```powershell
$userName="<Display name>"
Write-Host (Get-MsolUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

Este exemplo exibe o nome principal do usuário chamado Carlos Lima.
  
```powershell
$userName="Caleb Sills"
Write-Host (Get-MsolUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

Usando uma variável de **$UPN** , você pode fazer alterações em contas individuais com base no seu nome de exibição. Aqui está um exemplo de como definir o local de uso do Belinda Newman para a França, mas especificando seu nome de exibição em vez do nome principal do usuário:
  
```powershell
$userName="<display name>"
$upn=(Get-MsolUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
Set-MsolUser -UserPrincipalName $upn -UsageLocation "FR"
```

### <a name="change-properties-for-all-user-accounts"></a>Alterar propriedades de todas as contas de usuário

Para alterar as propriedades de todos os usuários, você pode usar a combinação dos cmdlets **Get-MsolUser** e **set-MsolUser** . O exemplo a seguir altera o local de uso de todos os usuários para a França:
  
```powershell
Get-MsolUser | Set-MsolUser -UsageLocation "FR"
```

Este comando instrui o PowerShell para:
  
- Obtenha todas as informações sobre as contas de usuário (**Get-MsolUser**) e envie-o para o próximo comando ( **|** ).
    
- Defina o local do usuário como França (**set-MsolUser-UsageLocation "fr"**).
    
### <a name="change-properties-for-a-specific-set-of-user-accounts"></a>Alterar propriedades de um conjunto específico de contas de usuário

Para alterar as propriedades de um conjunto específico de contas de usuário, você pode usar a combinação dos cmdlets **Get-MsolUser**, **Where**e **set-MsolUser** . O exemplo a seguir altera o local de uso de todos os usuários no departamento de contabilidade para a França:
  
```powershell
Get-MsolUser | Where {$_.Department -eq "Accounting"} | Set-MsolUser -UsageLocation "FR"
```

Este comando instrui o PowerShell para:
  
- Obtenha todas as informações sobre as contas de usuário (**Get-MsolUser**) e envie-o para o próximo comando ( **|** ).
    
- Encontre todas as contas de usuário que têm a propriedade Department definida como "Accounting" (**onde {$ _. Department-EQ "Accounting"}**) e envie as informações resultantes para o próximo comando ( **|** ).
    
- Defina o local do usuário como França (**set-MsolUser-UsageLocation "fr"**).
    

## <a name="see-also"></a>Confira também

[Gerenciar contas de usuário, licenças e grupos do Microsoft 365 com o PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[Gerenciar o Microsoft 365 com o PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Introdução ao PowerShell para o Microsoft 365](getting-started-with-microsoft-365-powershell.md)
