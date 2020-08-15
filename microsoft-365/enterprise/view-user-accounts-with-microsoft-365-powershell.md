---
title: Exibir contas de usuário do Microsoft 365 com o PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/17/2020
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
- LIL_Placement
- PowerShell
- Ent_Office_Other
- seo-marvel-apr2020
ms.assetid: bb12f49d-a85d-4f3b-ada2-5c4e33977b10
description: Saiba como exibir, listar ou exibir suas contas de usuário do Microsoft 365 de diferentes maneiras com o PowerShell.
ms.openlocfilehash: ea631d12a95ca813ebf9da3286e36d724d51a2f7
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46695423"
---
# <a name="view-microsoft-365-user-accounts-with-powershell"></a>Exibir contas de usuário do Microsoft 365 com o PowerShell

*Esse artigo se aplica ao Microsoft 365 Enterprise e ao Office 365 Enterprise.*

Embora você possa usar o centro de administração do Microsoft 365 para exibir as contas do seu locatário do Microsoft 365, você também pode usar o PowerShell para o Microsoft 365 e realizar algumas coisas que o centro de administração não pode.
  
## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Use o PowerShell do Azure Active Directory para o módulo do gráfico

Primeiro, [Conecte-se ao seu locatário do Microsoft 365](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).
  
### <a name="view-all-accounts"></a>Exibir todas as contas

Para exibir a lista completa de contas de usuário, execute este comando:
  
```powershell
Get-AzureADUser
```

Você deve ver informações semelhantes a estas:
  
```powershell
ObjectId                             DisplayName                                           UserPrincipalName
--------                             -----------                                           -----------------
032fc1fc-b5a2-46f1-8635-3d7dcb52c48d Adele Vance                                           AdeleV@litwareinc.OnMicr...
bd1e6af1-41e7-4f77-a2ac-5b209950135c Global Administrator                                  admin@litwareinc.onmicro...
ec37a4d6-232e-4eb7-82a5-1613490642a5 Alex Wilber                                           AlexW@litwareinc.OnMicro...
be4bdddd-c790-424c-9f96-a0cf609b7815 Allan Deyoung                                         AllanD@litwareinc.OnMicr...
598ab87b-76f0-4bf9-9538-bd46b10f4438 Christie Cline                                        ChristieC@litwareinc.OnM...
40722671-e520-4a5f-97d4-0bc9e9b2dc0f Debra Berger                                          DebraB@litwareinc.OnMicr...
```

### <a name="view-a-specific-account"></a>Exibir uma conta específica

Para exibir uma conta de usuário específica, preencha o nome da conta de logon da conta de usuário, também conhecida como nome UPN, remova os caracteres "<" e ">" e execute este comando:
  
```powershell
Get-AzureADUser -ObjectID <sign-in name of the user account>
```

Veja um exemplo:
  
```powershell
Get-AzureADUser -ObjectID BelindaN@litwareinc.onmicosoft.com
```

### <a name="view-additional-property-values-for-a-specific-account"></a>Exibir valores de propriedade adicionais para uma conta específica

Por padrão, o cmdlet **Get-AzureADUser** exibe apenas as propriedades ObjectID, DisplayName e userPrincipalName de accounts.

Para ser mais seletivo sobre a lista de propriedades a serem exibidas, você pode usar o cmdlet **Select** em combinação com o cmdlet **Get-AzureADUser** . Para combinar os dois cmdlets, usamos o caractere "pipe" "|", que informa ao Azure Active Directory PowerShell para Graph para obter os resultados de um comando e enviá-lo para o próximo comando. Veja a seguir um exemplo de comando que exibe o DisplayName, o departamento e o UsageLocation para cada conta de usuário:
  
```powershell
Get-AzureADUser | Select DisplayName,Department,UsageLocation
```

Este comando instrui o PowerShell para:
  
- Obtenha todas as informações sobre as contas de usuário ( **Get-AzureADUser** ) e envie-o para o próximo comando ( **|** ).
    
- Exibir apenas o nome da conta de usuário, o departamento e o local de uso ( **selecione DisplayName, Department, UsageLocation** ).
  
Para ver todas as propriedades de contas de usuário, use o cmdlet **Select** e o caractere curinga (*) para exibi-los para uma conta de usuário específica. Veja um exemplo:
  
```powershell
Get-AzureADUser -ObjectID BelindaN@litwareinc.onmicosoft.com | Select *
```

Como outro exemplo, você pode verificar o status habilitado de uma conta de usuário específica com o seguinte comando:
  
```powershell
Get-AzureADUser -ObjectID <sign-in name of the user account> | Select DisplayName,UserPrincipalName,AccountEnabled
```

### <a name="view-some-accounts-based-on-a-common-property"></a>Exibir algumas contas com base em uma propriedade comum

Para ser mais seletivo sobre a lista de contas a serem exibidas, você pode usar o cmdlet **Where** em combinação com o cmdlet **Get-AzureADUser** . Para combinar os dois cmdlets, usamos o caractere "pipe" "|", que informa ao Azure Active Directory PowerShell para Graph para obter os resultados de um comando e enviá-lo para o próximo comando. Veja a seguir um exemplo de comando que exibe apenas as contas de usuário que têm um local de uso não especificado:
  
```powershell
Get-AzureADUser | Where {$_.UsageLocation -eq $Null}
```

Este comando instrui o Azure Active Directory PowerShell para Graph para:
  
- Obtenha todas as informações sobre as contas de usuário ( **Get-AzureADUser** ) e envie-o para o próximo comando ( **|** ).
    
- Encontre todas as contas de usuário que têm um local de uso não especificado ( **onde {$ \_ . UsageLocation-EQ $Null}** ). Dentro das chaves, o comando instrui o PowerShell a localizar apenas o conjunto de contas no qual a propriedade da conta de usuário do UsageLocation ( ** $ \_ . UsageLocation** ) não é especificado ( **-EQ $NULL** ).
    
A propriedade **UsageLocation** é apenas uma das muitas propriedades associadas a uma conta de usuário. Para ver todas as propriedades de contas de usuário, use o cmdlet **Select** e o caractere curinga (*) para exibi-los para uma conta de usuário específica. Veja um exemplo:
  
```powershell
Get-AzureADUser -ObjectID BelindaN@litwareinc.onmicosoft.com | Select *
```

Por exemplo, na lista, **City** é o nome de uma propriedade de conta de usuário. Isso significa que você pode usar o seguinte comando para listar todas as contas de usuário para usuários em Londres:
  
```powershell
Get-AzureADUser | Where {$_.City -eq "London"}
```

> [!TIP]
>  A sintaxe do cmdlet **Where** mostrado nesses exemplos é **onde {$ \_ .** [nome da propriedade da conta de usuário] [operador de comparação] valor **}**. > [operador de comparação] é **-EQ** para igual a, **-ne** para não igual a, **-lt** para menor que, **-gt** para maior que e outros.  [value] normalmente é uma cadeia de caracteres (uma sequência de letras, números e outros caracteres), um valor numérico ou **$NULL** para> não especificado Confira [onde](https://docs.microsoft.com/powershell/module/Microsoft.PowerShell.Core/Where?view=powershell-5.1) obter mais informações.
  

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Use o Módulo Microsoft Azure Active Directory para Windows PowerShell.

Primeiro, [Conecte-se ao seu locatário do Microsoft 365](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).

### <a name="view-all-accounts"></a>Exibir todas as contas

Para exibir a lista completa de contas de usuário, execute este comando:
  
```powershell
Get-MsolUser
```

>[!Note]
>O PowerShell Core não é compatível com o módulo do Microsoft Azure Active Directory para módulo e cmdlets do Windows PowerShell com **MSol** no nome. Para continuar usando esses cmdlets, você deve executá-los a partir do Windows PowerShell.
>

Você deve ver informações semelhantes a estas:
  
```powershell
UserPrincipalName                     DisplayName           isLicensed
-----------------                     -----------           ----------
BonnieK@litwareinc.onmicrosoft.com    Bonnie Kearney        True
FabriceC@litwareinc.onmicrosoft.com   Fabrice Canel         True
BrianJ@litwareinc.onmicrosoft.com     Brian Johnson         False 
AnneWlitwareinc.onmicrosoft.com       Anne Wallace          True
ScottW@litwareinc.onmicrosoft.com     Scott Wallace         False
```

O cmdlet **Get-MsolUser** também tem um conjunto de parâmetros para filtrar o conjunto de contas de usuário exibidas. Por exemplo, para a lista de usuários não licenciados (usuários que foram adicionados ao Microsoft 365, mas que ainda não foram licenciados para usar qualquer um dos serviços), execute este comando.
  
```powershell
Get-MsolUser -UnlicensedUsersOnly
```

Você deve ver informações semelhantes a estas:
  
```powershell
UserPrincipalName                     DisplayName           isLicensed
-----------------                     -----------           ----------
BrianJ@litwareinc.onmicrosoft.com     Brian Johnson         False
ScottW@litwareinc.onmicrosoft.com     Scott Wallace         False
```

Para obter mais informações sobre parâmetros adicionais para filtrar a exibição do conjunto de contas de usuário exibidas, consulte [Get-MsolUser](https://docs.microsoft.com/previous-versions/azure/dn194133(v=azure.100)).
  
### <a name="view-a-specific-account"></a>Exibir uma conta específica

Para exibir uma conta de usuário específica, preencha o nome de entrada da conta de usuário da conta de usuário, também conhecida como nome de usuário principal (UPN), remova os caracteres "<" e ">" e execute este comando:
  
```powershell
Get-MsolUser -UserPrincipalName <sign-in name of the user account>
```

### <a name="view-some-accounts-based-on-a-common-property"></a>Exibir algumas contas com base em uma propriedade comum

Para ser mais seletivo sobre a lista de contas a serem exibidas, você pode usar o cmdlet **Where** em combinação com o cmdlet **Get-MsolUser** . Para combinar os dois cmdlets, usamos o caractere "pipe" "|", que informa ao PowerShell para obter os resultados de um comando e enviá-lo para o próximo comando. Veja a seguir um exemplo de comando que exibe apenas as contas de usuário que têm um local de uso não especificado:
  
```powershell
Get-MsolUser | Where {$_.UsageLocation -eq $Null}
```

Este comando instrui o PowerShell para:
  
- Obtenha todas as informações sobre as contas de usuário ( **Get-MsolUser** ) e envie-o para o próximo comando ( **|** ).
    
- Encontre todas as contas de usuário que têm um local de uso não especificado ( **onde {$ \_ . UsageLocation-EQ $Null}** ). Dentro das chaves, o comando instrui o PowerShell a localizar apenas o conjunto de contas no qual a propriedade da conta de usuário do UsageLocation ( ** $ \_ . UsageLocation** ) não é especificado ( **-EQ $NULL** ).
    
Você deve ver informações semelhantes a estas:
  
```powershell
UserPrincipalName                     DisplayName           isLicensed
-----------------                     -----------           ----------
BrianJ@litwareinc.onmicrosoft.com     Brian Johnson         False 
ScottW@litwareinc.onmicrosoft.com     Scott Wallace         False

```

A propriedade **UsageLocation** é apenas uma das muitas propriedades associadas a uma conta de usuário. Para ver todas as propriedades de contas de usuário, use o cmdlet **Select** e o caractere curinga (*) para exibi-los para uma conta de usuário específica. Veja um exemplo:
  
```powershell
Get-MsolUser -UserPrincipalName BelindaN@litwareinc.onmicosoft.com | Select *
```

Por exemplo, na lista, **City** é o nome de uma propriedade de conta de usuário. Isso significa que você pode usar o seguinte comando para listar todas as contas de usuário para usuários em Londres:
  
```powershell
Get-MsolUser | Where {$_.City -eq "London"}
```

> [!TIP]
>  A sintaxe do cmdlet **Where** mostrado nesses exemplos é **onde {$ \_ .** [nome da propriedade da conta de usuário] [operador de comparação] valor **}**.  [operador de comparação] é **-EQ** para igual a, **-ne** para não é igual a, **-lt** para menor que, **-gt** para maior que e outros.  [value] normalmente é uma cadeia de caracteres (uma sequência de letras, números e outros caracteres), um valor numérico ou **$NULL** para não especificado. Confira [onde](https://technet.microsoft.com/library/hh849715.aspx) obter mais informações.
  
Você pode verificar o status bloqueado de uma conta de usuário com o seguinte comando:
  
```powershell
Get-MsolUser -UserPrincipalName <UPN of user account> | Select DisplayName,BlockCredential
```

### <a name="view-additional-property-values-for-accounts"></a>Exibir valores de propriedade adicionais para contas

Por padrão, o cmdlet **Get-MsolUser** exibe três propriedades de contas de usuário:
  
- UserPrincipalName
    
- DisplayName
    
- isLicensed
    
Se você precisar de propriedades adicionais, como o departamento para o qual o usuário trabalha e o país/região em que o usuário usa os serviços do Microsoft 365, é possível executar **Get-MsolUser** em combinação com o cmdlet **Select** para especificar a lista de propriedades da conta de usuário. Veja um exemplo:
  
```powershell
Get-MsolUser | Select DisplayName, Department, UsageLocation
```

Este comando instrui o PowerShell para:
  
- Obtenha todas as informações sobre as contas de usuário ( **Get-MsolUser** ) e envie-o para o próximo comando ( **|** ).
    
- Exibir apenas o nome da conta de usuário, o departamento e o local de uso ( **selecione DisplayName, Department, UsageLocation** ).
    
Você deve ver informações semelhantes a estas:
  
```powershell
DisplayName             Department                       UsageLocation
-----------             ----------                       -------------
Bonnie Kearney          Sales & Marketing                    US
Fabrice Canel           Legal                                US
Brian Johnson
Anne Wallace            Executive Management                 US
Alex Darrow             Sales & Marketing                    US
Scott Wallace           Operations
```

O cmdlet **Select** permite que você escolha e escolha as propriedades que você deseja que um comando exiba. Para ver todas as propriedades de contas de usuário, use o caractere curinga (*) para exibi-las para uma conta de usuário específica. Veja um exemplo:
  
```powershell
Get-MsolUser -UserPrincipalName BelindaN@litwareinc.onmicosoft.com | Select *
```

Para ser mais seletivo sobre a lista de contas a serem exibidas, você também pode usar o cmdlet **Where** . Veja a seguir um exemplo de comando que exibe apenas as contas de usuário que têm um local de uso não especificado:
  
```powershell
Get-MsolUser | Where {$_.UsageLocation -eq $Null} | Select DisplayName, Department, UsageLocation
```

Este comando instrui o PowerShell para:
  
- Obtenha todas as informações sobre as contas de usuário ( **Get-MsolUser** ) e envie-o para o próximo comando ( **|** ).
    
- Encontre todas as contas de usuário que têm um local de uso não especificado ( **onde {$ \_ . UsageLocation-EQ $Null}** ) e envie as informações resultantes para o próximo comando ( **|** ). Dentro das chaves, o comando instrui o PowerShell a localizar apenas o conjunto de contas no qual a propriedade da conta de usuário do UsageLocation ( ** $ \_ . UsageLocation** ) não é especificado ( **-EQ $NULL** ).
    
- Exibir apenas o nome da conta de usuário, o departamento e o local de uso ( **selecione DisplayName, Department, UsageLocation** ).
    
Você deve ver informações semelhantes a estas:
  
```powershell
DisplayName              Department                      UsageLocation
-----------              ----------                      -------------
Brian Johnson 
Scott Wallace            Operations
```

Se você estiver usando a sincronização de diretórios para criar e gerenciar seus usuários do Microsoft 365, poderá exibir a conta local em que um usuário do Microsoft 365 foi projetado. O seguinte pressupõe que o Azure AD Connect tenha sido configurado para usar a âncora de origem padrão de objectGUID (para saber mais sobre como configurar uma âncora de origem, confira [Azure ad Connect: design Concepts](https://docs.microsoft.com/azure/active-directory/hybrid/plan-connect-design-concepts)) e pressupõe que o módulo Active Directory Domain Services para PowerShell tenha sido instalado (consulte [rsat Tools](https://www.microsoft.com/en-gb/download/details.aspx?id=45520)):

```powershell
Get-ADUser ([guid][System.Convert]::FromBase64String((Get-MsolUser -UserPrincipalName <UPN of user account>).ImmutableID)).guid
```

## <a name="see-also"></a>Confira também

[Gerenciar contas de usuário, licenças e grupos do Microsoft 365 com o PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[Gerenciar o Microsoft 365 com o PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Introdução ao PowerShell para o Microsoft 365](getting-started-with-microsoft-365-powershell.md)

