---
title: Exibir Microsoft 365 contas de usuário com o PowerShell
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
description: Saiba como exibir, listar ou exibir suas Microsoft 365 de usuário de maneiras diferentes com o PowerShell.
ms.openlocfilehash: de91195afeb8480bf231d9536e4b3a94502a6da1
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50924643"
---
# <a name="view-microsoft-365-user-accounts-with-powershell"></a>Exibir Microsoft 365 contas de usuário com o PowerShell

*Esse artigo se aplica ao Microsoft 365 Enterprise e ao Office 365 Enterprise.*

Você pode usar o centro de administração Microsoft 365 para exibir as contas do seu Microsoft 365 locatário. O PowerShell para Microsoft 365 permite isso, mas também fornece funcionalidade adicional.
  
## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Use o PowerShell do Azure Active Directory para o módulo do gráfico

Primeiro, [conecte-se ao seu Microsoft 365 locatário](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).
  
### <a name="view-all-accounts"></a>Exibir todas as contas

Para exibir a lista completa de contas de usuário, execute este comando:
  
```powershell
Get-AzureADUser
```

Você deve obter informações semelhantes a esta:
  
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

Para exibir uma conta de usuário específica, execute o seguinte comando. Preencha o nome da conta de login da conta de usuário, que também é conhecido como o nome principal do usuário (UPN). Remova os caracteres "<" e ">".
  
```powershell
Get-AzureADUser -ObjectID <sign-in name of the user account>
```

Veja um exemplo:
  
```powershell
Get-AzureADUser -ObjectID BelindaN@litwareinc.onmicosoft.com
```

### <a name="view-additional-property-values-for-a-specific-account"></a>Exibir valores de propriedade adicionais para uma conta específica

Por padrão, o cmdlet **Get-AzureADUser** exibe apenas as propriedades *ObjectID,* *DisplayName* e *UserPrincipalName* das contas.

Para ser mais seletivo sobre as propriedades a serem exibidas, use o cmdlet **Select** em combinação com o cmdlet **Get-AzureADUser.** Para combinar os dois cmdlets, use o caractere "pipe" ("|"), que informa Azure Active Directory PowerShell para que Graph pegue os resultados de um comando e envie-o para o próximo comando. Aqui está um comando de exemplo que exibe *DisplayName*, *Department* e *UsageLocation* para cada conta de usuário:
  
```powershell
Get-AzureADUser | Select DisplayName,Department,UsageLocation
```

Este comando instrui o PowerShell a:
  
1. Obter todas as informações sobre as contas de usuário (**Get-AzureADUser**) e enviá-la para o próximo comando ( **|** ).
    
1.  Exibe apenas o nome da conta de usuário, o departamento e o local de uso (**Selecione DisplayName, Department, UsageLocation**).
  
Para ver todas as propriedades de uma conta de usuário específica, use o cmdlet **Select** e o caractere curinga (*). Veja um exemplo:
  
```powershell
Get-AzureADUser -ObjectID BelindaN@litwareinc.onmicosoft.com | Select *
```

Como outro exemplo, execute o seguinte comando para verificar o status habilitado de uma conta de usuário específica:
  
```powershell
Get-AzureADUser -ObjectID <sign-in name of the user account> | Select DisplayName,UserPrincipalName,AccountEnabled
```

### <a name="view-account-synchronization-status"></a>Exibir status de sincronização de conta

As contas de usuário têm duas fontes: 

- Windows Servidor Active Directory (AD), que são contas que sincronizam do AD local para a nuvem.

- Azure Active Directory contas do AD (Azure AD), que são criadas diretamente na nuvem.


O comando a seguir instrui o PowerShell a obter todos os usuários que tenham o atributo *DirSyncEnabled* definido como *True*. Você pode usá-lo para encontrar contas que estão sincronizando do AD local.

```powershell
Get-AzureADUser | Where {$_.DirSyncEnabled -eq $true}
```

O comando a seguir instrui o PowerShell a obter todos os usuários que tenham o atributo *DirSyncEnabled* definido como *False*. Você pode usá-lo para encontrar contas somente na nuvem.

```powershell
Get-AzureADUser | Where {$_.DirSyncEnabled -ne $false}
```

### <a name="view-accounts-based-on-a-common-property"></a>Exibir contas com base em uma propriedade comum

Para ser mais seletivo sobre a lista de contas a serem exibidas, você pode usar o cmdlet **Where** em combinação com o cmdlet **Get-AzureADUser.** Para combinar os dois cmdlets, use o caractere "pipe" ("|"), que informa Azure Active Directory PowerShell para que Graph pegue os resultados de um comando e envie-o para o próximo comando. Aqui está um comando de exemplo que exibe apenas as contas de usuário que têm um local de uso não especificado:
  
```powershell
Get-AzureADUser | Where {$_.UsageLocation -eq $Null}
```

Este comando instrui o Azure Active Directory PowerShell para Graph para:
  
1. Obter todas as informações sobre as contas de usuário (**Get-AzureADUser**) e enviá-la para o próximo comando ( **|** ).
    
1. Encontre todas as contas de usuário que tenham um local de uso não especificado (**Onde {$ \_ . UsageLocation -eq $Null}**). Dentro das chaves, o comando instrui o PowerShell a encontrar apenas o conjunto de contas para as quais a propriedade de conta de usuário UsageLocation (**$ \_ . UsageLocation**) não é especificado (**-eq $Null**).
    
A **propriedade UsageLocation** é apenas uma das muitas propriedades associadas a uma conta de usuário. Para exibir todas as propriedades de uma conta de usuário específica, use o cmdlet **Select** e o caractere curinga (*). Veja um exemplo:
  
```powershell
Get-AzureADUser -ObjectID BelindaN@litwareinc.onmicosoft.com | Select *
```

Por exemplo, **City** é o nome de uma propriedade de conta de usuário. Você pode usar o seguinte comando para listar todas as contas de usuários que moram em Londres:
  
```powershell
Get-AzureADUser | Where {$_.City -eq "London"}
```

> [!TIP]
>  A sintaxe do cmdlet **Where** nestes exemplos é **Where {$ \_ .** [nome da propriedade de conta de usuário] [operador de comparação] [value] **}**.> [operador de comparação] é **-eq** para igual, **-ne** para não igual, **-lt** para menos que, **-gt** para maior que e outros.  [value] é normalmente uma cadeia de caracteres (uma sequência de letras,  números e outros caracteres), um valor numérico ou $Null para não especificado. Para obter mais informações, consulte [Where](/powershell/module/microsoft.powershell.core/where-object?view=powershell-7).
  

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Use o Módulo Microsoft Azure Active Directory para Windows PowerShell.

Primeiro, [conecte-se ao seu Microsoft 365 locatário](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).

### <a name="view-all-accounts"></a>Exibir todas as contas

Para exibir a lista completa de contas de usuário, execute este comando:
  
```powershell
Get-MsolUser
```

>[!Note]
>O PowerShell Core não oferece suporte ao Módulo Microsoft Azure Active Directory para Windows PowerShell para o módulo do Windows PowerShell e cmdlets com *Msol* em seus nomes. Execute esses cmdlets do Windows PowerShell.
>

Você deve obter informações semelhantes a esta:
  
```powershell
UserPrincipalName                     DisplayName           isLicensed
-----------------                     -----------           ----------
BonnieK@litwareinc.onmicrosoft.com    Bonnie Kearney        True
FabriceC@litwareinc.onmicrosoft.com   Fabrice Canel         True
BrianJ@litwareinc.onmicrosoft.com     Brian Johnson         False 
AnneWlitwareinc.onmicrosoft.com       Anne Wallace          True
ScottW@litwareinc.onmicrosoft.com     Scott Wallace         False
```

O cmdlet **Get-MsolUser** também tem um conjunto de parâmetros para filtrar o conjunto de contas de usuário exibidas. Por exemplo, para a lista de usuários não licenciados (usuários que foram adicionados ao Microsoft 365 mas ainda não foram licenciados para usar qualquer um dos serviços), execute este comando:
  
```powershell
Get-MsolUser -UnlicensedUsersOnly
```

Você deve obter informações semelhantes a esta:
  
```powershell
UserPrincipalName                     DisplayName           isLicensed
-----------------                     -----------           ----------
BrianJ@litwareinc.onmicrosoft.com     Brian Johnson         False
ScottW@litwareinc.onmicrosoft.com     Scott Wallace         False
```

Para obter informações sobre parâmetros adicionais para filtrar o conjunto de contas de usuário que são exibidas, consulte [Get-MsolUser](/previous-versions/azure/dn194133(v=azure.100)).
  
### <a name="view-a-specific-account"></a>Exibir uma conta específica

Para exibir uma conta de usuário específica, execute o seguinte comando. Preencha o nome de logon da conta de usuário, que também é conhecido como o nome principal do usuário (UPN). Remova os caracteres "<" e ">".
  
```powershell
Get-MsolUser -UserPrincipalName <sign-in name of the user account>
```

### <a name="view-accounts-based-on-a-common-property"></a>Exibir contas com base em uma propriedade comum

Para ser mais seletivo sobre a lista de contas a serem exibidas, você pode usar o cmdlet **Where** em combinação com o cmdlet **Get-MsolUser.** Para combinar os dois cmdlets, use o caractere "pipe" ("|"), que diz ao PowerShell para levar os resultados de um comando e enviá-lo para o próximo comando. Veja um exemplo que exibe apenas as contas de usuário que têm um local de uso não especificado:
  
```powershell
Get-MsolUser | Where {$_.UsageLocation -eq $Null}
```

Este comando instrui o PowerShell a:
  
1. Obter todas as informações sobre as contas de usuário (**Get-MsolUser**) e enviá-la para o próximo comando ( **|** ).
    
1. Encontre todas as contas de usuário que tenham um local de uso não especificado (**Onde {$ \_ . UsageLocation -eq $Null}**). Dentro das chaves, o comando instrui o PowerShell a encontrar apenas o conjunto de contas para as quais a propriedade de conta de usuário UsageLocation (**$ \_ . UsageLocation**) não é especificado (**-eq $Null**).
    
Você deve obter informações semelhantes a esta:
  
```powershell
UserPrincipalName                     DisplayName           isLicensed
-----------------                     -----------           ----------
BrianJ@litwareinc.onmicrosoft.com     Brian Johnson         False 
ScottW@litwareinc.onmicrosoft.com     Scott Wallace         False

```

A *propriedade UsageLocation* é apenas uma das muitas propriedades associadas a uma conta de usuário. Para ver todas as propriedades para contas de usuário, use o cmdlet **Select** e o caractere curinga (*) para exibi-las todas para uma conta de usuário específica. Veja um exemplo:
  
```powershell
Get-MsolUser -UserPrincipalName BelindaN@litwareinc.onmicosoft.com | Select *
```

Por exemplo, *City* é o nome de uma propriedade de conta de usuário. Você pode usar o seguinte comando para listar todas as contas de usuário para usuários que moram em Londres:
  
```powershell
Get-MsolUser | Where {$_.City -eq "London"}
```

> [!TIP]
>  A sintaxe do cmdlet **Where** nestes exemplos é **Where {$ \_ .** [nome da propriedade de conta de usuário] [operador de comparação] [value] **}**.  [operador de comparação] é **-eq** para igual, **-ne** para não igual, **-lt** para menos que, **-gt** para maior do que e outros.  [value] é normalmente uma cadeia de caracteres (uma sequência de letras,  números e outros caracteres), um valor numérico ou $Null para não especificado. Para obter mais informações, consulte [Where](/powershell/module/microsoft.powershell.core/where-object?view=powershell-7).
  
Para verificar o status bloqueado de uma conta de usuário, use o seguinte comando:
  
```powershell
Get-MsolUser -UserPrincipalName <UPN of user account> | Select DisplayName,BlockCredential
```

### <a name="view-additional-property-values-for-accounts"></a>Exibir valores de propriedade adicionais para contas

Por padrão, o cmdlet **Get-MsolUser** exibe essas três propriedades de contas de usuário:
  
- UserPrincipalName
    
- DisplayName
    
- isLicensed
    
Se você precisar de propriedades adicionais, como o departamento onde o usuário trabalha e o país/região onde ele usa serviços Microsoft 365, você pode executar **Get-MsolUser** em combinação com o cmdlet **Select** para especificar a lista de propriedades da conta de usuário. Veja um exemplo:
  
```powershell
Get-MsolUser | Select DisplayName, Department, UsageLocation
```

Este comando instrui o PowerShell a:
  
1. Obter todas as informações sobre as contas de usuário (**Get-MsolUser**) e enviá-la para o próximo comando ( **|** ).
    
1. Exibe apenas o nome da conta de usuário, o departamento e o local de uso (**Selecione DisplayName, Department, UsageLocation**).
    
Você deve obter informações semelhantes a esta:
  
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

O cmdlet **Select** permite que você escolha quais propriedades exibir. Para exibir todas as propriedades de uma conta de usuário específica, use o caractere curinga (*). Veja um exemplo:
  
```powershell
Get-MsolUser -UserPrincipalName BelindaN@litwareinc.onmicosoft.com | Select *
```

Para ser mais seletivo sobre a lista de contas a serem exibidas, você também pode usar o cmdlet **Where.** Aqui está um comando de exemplo que exibe apenas as contas de usuário que têm um local de uso não especificado:
  
```powershell
Get-MsolUser | Where {$_.UsageLocation -eq $Null} | Select DisplayName, Department, UsageLocation
```

Este comando instrui o PowerShell a:
  
1. Obter todas as informações sobre as contas de usuário (**Get-MsolUser**) e enviá-la para o próximo comando ( **|** ).
    
1. Encontre todas as contas de usuário que tenham um local de uso não especificado (**Onde {$ \_ . UsageLocation -eq $Null}**), e envie as informações resultantes para o próximo comando ( **|** ). Dentro das chaves, o comando instrui o PowerShell a encontrar apenas o conjunto de contas para as quais a propriedade de conta de usuário UsageLocation (**$ \_ . UsageLocation**) não é especificado (**-eq $Null**).
    
1. Exibe apenas o nome da conta de usuário, o departamento e o local de uso (**Selecione DisplayName, Department, UsageLocation**).
    
Você deve obter informações semelhantes a esta:
  
```powershell
DisplayName              Department                      UsageLocation
-----------              ----------                      -------------
Brian Johnson 
Scott Wallace            Operations
```

Se você estiver usando a sincronização de diretórios para criar e gerenciar seus usuários Microsoft 365, você poderá exibir a conta local da qual um usuário Microsoft 365 foi projetado. O exemplo a seguir supõe que:

- O Azure AD Conexão configurado para usar a âncora de origem padrão do ObjectGUID. (Para obter mais informações sobre como configurar uma âncora de origem, consulte [Azure AD Conexão: Conceitos de design).](/azure/active-directory/hybrid/plan-connect-design-concepts)
- O módulo serviços de domínio do Active Directory para PowerShell foi instalado (consulte [ferramentas RSAT](https://www.microsoft.com/en-gb/download/details.aspx?id=45520)).

```powershell
Get-ADUser ([guid][System.Convert]::FromBase64String((Get-MsolUser -UserPrincipalName <UPN of user account>).ImmutableID)).guid
```

## <a name="see-also"></a>Confira também

[Gerenciar contas de usuário, licenças e grupos do Microsoft 365 com o PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[Gerenciar o Microsoft 365 com o PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Introdução ao Windows PowerShell para o Microsoft 365](getting-started-with-microsoft-365-powershell.md)