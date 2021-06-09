---
title: Criar Microsoft 365 de usuário com o PowerShell
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
- PowerShell
- Ent_Office_Other
- O365ITProTrain
- seo-marvel-apr2020
ms.assetid: 6770c5fa-b886-4512-8c67-ffd53226589e
description: Como usar o PowerShell para criar contas de usuário individuais ou Microsoft 365 usuário.
ms.openlocfilehash: c3676acdec3bbba328809ee1528206bbc44f94f1
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50907559"
---
# <a name="create-microsoft-365-user-accounts-with-powershell"></a>Criar Microsoft 365 de usuário com o PowerShell

*Esse artigo se aplica ao Microsoft 365 Enterprise e ao Office 365 Enterprise.*

Você pode usar o PowerShell para Microsoft 365 criar contas de usuário de forma eficiente, incluindo várias contas.

Quando você cria contas de usuário no PowerShell, determinadas propriedades de conta são sempre necessárias. Outras propriedades não são necessárias, mas são importantes. Consulte a tabela a seguir.
  
|**Nome da propriedade**|**Obrigatório?**|**Descrição**|
|:-----|:-----|:-----|
|**DisplayName** <br/> |Sim  <br/> |Esse é o nome de exibição usado nos serviços Microsoft 365 de exibição. Por exemplo, *Caleb Sills*. <br/> |
|**UserPrincipalName** <br/> |Sim  <br/> |Esse é o nome da conta usado para entrar em serviços Microsoft 365. Por exemplo, *CalebS \@ contoso.onmicrosoft.com*.  <br/> |
|**FirstName** <br/> |Não  <br/> ||
|**LastName** <br/> |Não  <br/> ||
|**LicenseAssignment** <br/> |Não  <br/> |Este é o plano de licenciamento (também conhecido como plano de licença ou SKU) do qual uma licença disponível é atribuída à conta de usuário. A licença define os serviços Microsoft 365 que estão disponíveis para a conta. Você não precisa atribuir uma licença a um usuário ao criar a conta, mas a conta deve ter uma licença para acessar Microsoft 365 serviços. Você tem 30 dias para licenciar a conta de usuário depois de criá-la. |
|**Password** <br/> |Não  <br/> | Caso não especifique uma senha, nosso sistema atribuirá uma senha aleatória para a conta do usuário e a senha ficará visível nos resultados do comando. Se você especificar uma senha, ela precisará ser de 8 a 16 caracteres de texto ASCII dos seguintes tipos: letras minúsculas, letras maiúsculas, números e símbolos.<br/> |
|**UsageLocation** <br/> |Não  <br/> |Este é um código de país iso 3166-1 alfa-2 válido. Por exemplo, *EUA* para os Estados Unidos e *FR* para França. É importante fornecer esse valor, pois alguns serviços Microsoft 365 não estão disponíveis em determinados países. Você não pode atribuir uma licença a uma conta de usuário, a menos que a conta tenha esse valor configurado. Para obter mais informações, consulte [Sobre restrições de licença](https://go.microsoft.com/fwlink/p/?LinkId=691730).<br/> |

>[!Note]
>[Saiba como criar contas de usuário](../admin/add-users/add-users.md) usando o Microsoft 365 de administração.
> 
> Para obter uma lista de recursos adicionais, consulte [Gerenciar usuários e grupos.](../admin/add-users/index.yml)
>   

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Use o PowerShell do Azure Active Directory para o módulo do gráfico

Primeiro, [conecte-se ao seu Microsoft 365 locatário](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).

Depois de se conectar, use a seguinte sintaxe para criar uma conta individual:
  
```powershell
$PasswordProfile=New-Object -TypeName Microsoft.Open.AzureAD.Model.PasswordProfile
$PasswordProfile.Password="<user account password>"
New-AzureADUser -DisplayName "<display name>" -GivenName "<first name>" -SurName "<last name>" -UserPrincipalName <sign-in name> -UsageLocation <ISO 3166-1 alpha-2 country code> -MailNickName <mailbox name> -PasswordProfile $PasswordProfile -AccountEnabled $true
```

Este exemplo cria uma conta para o usuário dos EUA *Caleb Sills*:
  
```powershell
$PasswordProfile=New-Object -TypeName Microsoft.Open.AzureAD.Model.PasswordProfile
$PasswordProfile.Password="3Rv0y1q39/chsy"
New-AzureADUser -DisplayName "Caleb Sills" -GivenName "Caleb" -SurName "Sills" -UserPrincipalName calebs@contoso.onmicrosoft.com -UsageLocation US -MailNickName calebs -PasswordProfile $PasswordProfile -AccountEnabled $true
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Use o Módulo Microsoft Azure Active Directory para Windows PowerShell.

Primeiro, [conecte-se ao seu Microsoft 365 locatário](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).

### <a name="create-an-individual-user-account"></a>Criar uma conta de usuário individual

Para criar uma conta individual, use a seguinte sintaxe:
  
```powershell
New-MsolUser -DisplayName <display name> -FirstName <first name> -LastName <last name> -UserPrincipalName <sign-in name> -UsageLocation <ISO 3166-1 alpha-2 country code> -LicenseAssignment <licensing plan name> [-Password <Password>]
```

>[!Note]
>O PowerShell Core não dá suporte ao módulo Microsoft Azure Active Directory para Windows PowerShell e cmdlets que têm *Msol* em seu nome. Execute esses cmdlets do Windows PowerShell.
>

Para listar os nomes do plano de licenciamento disponível, use este comando:

````powershell
Get-MsolAccountSku
````

Este exemplo cria uma conta para o usuário dos EUA *Caleb Sills* e atribui uma licença do plano de licenciamento `contoso:ENTERPRISEPACK` (Office 365 Enterprise E3).
  
```powershell
New-MsolUser -DisplayName "Caleb Sills" -FirstName Caleb -LastName Sills -UserPrincipalName calebs@contoso.onmicrosoft.com -UsageLocation US -LicenseAssignment contoso:ENTERPRISEPACK
```

### <a name="create-multiple-user-accounts"></a>Criar várias contas de usuários

1. Crie um arquivo CSV (arquivo de valores separados por vírgula) que inclua as informações necessárias da conta do usuário. Por exemplo:

     ```powershell
     UserPrincipalName,FirstName,LastName,DisplayName,UsageLocation,AccountSkuId
     ClaudeL@contoso.onmicrosoft.com,Claude,Loiselle,Claude Loiselle,US,contoso:ENTERPRISEPACK
     LynneB@contoso.onmicrosoft.com,Lynne,Baxter,Lynne Baxter,US,contoso:ENTERPRISEPACK
     ShawnM@contoso.onmicrosoft.com,Shawn,Melendez,Shawn Melendez,US,contoso:ENTERPRISEPACK
     ```

   >[!NOTE]
   >Os nomes das colunas e sua ordem na primeira linha do arquivo CSV são arbitrários. Mas certifique-se de que a ordem dos dados no restante do arquivo corresponde à ordem dos nomes das colunas. E use os nomes de coluna para os valores de parâmetro no comando PowerShell para Microsoft 365.
    
2. Use a seguinte sintaxe:
    
    ```powershell
     Import-Csv -Path <Input CSV File Path and Name> | foreach {New-MsolUser -DisplayName $_.DisplayName -FirstName $_.FirstName -LastName $_.LastName -UserPrincipalName $_.UserPrincipalName -UsageLocation $_.UsageLocation -LicenseAssignment $_.AccountSkuId [-Password $_.Password]} | Export-Csv -Path <Output CSV File Path and Name>
    ```

   Este exemplo cria contas de usuário do arquivo *C:\My Documents\NewAccounts.csv* e registra os resultados em um arquivo chamado *C:\My Documents\NewAccountResults.csv*.
    
    ```powershell
    Import-Csv -Path "C:\My Documents\NewAccounts.csv" | foreach {New-MsolUser -DisplayName $_.DisplayName -FirstName $_.FirstName -LastName $_.LastName -UserPrincipalName $_.UserPrincipalName -UsageLocation $_.UsageLocation -LicenseAssignment $_.AccountSkuId} | Export-Csv -Path "C:\My Documents\NewAccountResults.csv"
    ```

3. Examine o arquivo de saída para conferir os resultados. Não especificamos senhas, portanto, as senhas aleatórias que Microsoft 365 geradas ficam visíveis no arquivo de saída.
    
## <a name="see-also"></a>Confira também

[Gerenciar contas de usuário, licenças e grupos do Microsoft 365 com o PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[Gerenciar o Microsoft 365 com o PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Introdução ao PowerShell para o Microsoft 365](getting-started-with-microsoft-365-powershell.md)