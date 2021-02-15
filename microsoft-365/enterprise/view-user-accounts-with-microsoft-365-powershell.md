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
description: Saiba como exibir, listar ou exibir suas contas de usuário do Microsoft 365 de maneiras diferentes com o PowerShell.
ms.openlocfilehash: 312e9fb983c4d1f4de8bc74586c88f1e669eb90a
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754067"
---
# <a name="view-microsoft-365-user-accounts-with-powershell"></a>Exibir contas de usuário do Microsoft 365 com o PowerShell

*Esse artigo se aplica ao Microsoft 365 Enterprise e ao Office 365 Enterprise.*

Você pode usar o Centro de administração do Microsoft 365 para exibir as contas do locatário do Microsoft 365. O PowerShell para Microsoft 365 habilita isso, mas também fornece funcionalidade adicional.
  
## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Use o PowerShell do Azure Active Directory para o módulo do gráfico

Primeiro, [conecte-se ao locatário do Microsoft 365.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)
  
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

Para exibir uma conta de usuário específica, execute o seguinte comando. Preencha o nome da conta de logon da conta de usuário, que também é conhecido como nome UPN. Remova os caracteres "<" e ">".
  
```powershell
Get-AzureADUser -ObjectID <sign-in name of the user account>
```

Exemplo:
  
```powershell
Get-AzureADUser -ObjectID BelindaN@litwareinc.onmicosoft.com
```

### <a name="view-additional-property-values-for-a-specific-account"></a>Exibir valores de propriedade adicionais para uma conta específica

Por padrão, o cmdlet **Get-AzureADUser** exibe apenas as propriedades *ObjectID*, *DisplayName* e *UserPrincipalName* das contas.

Para ser mais seletivo sobre as propriedades a serem exibidas, use o cmdlet **Select** em combinação com o cmdlet **Get-AzureADUser.** Para combinar os dois cmdlets, use o caractere "pipe" ("|"), que informa ao PowerShell do Azure Active Directory para Graph para que pegue os resultados de um comando e o envie para o próximo comando. Aqui está um comando de exemplo que exibe *DisplayName*, *Department* e *UsageLocation para* cada conta de usuário:
  
```powershell
Get-AzureADUser | Select DisplayName,Department,UsageLocation
```

Este comando instrui o PowerShell a:
  
1. Obter todas as informações sobre as contas de usuário (**Get-AzureADUser**) e enviá-lo para o próximo comando ( **|** ).
    
1.  Exibe somente o nome da conta de usuário, o departamento e o local de uso (**Selecione DisplayName, Departamento, UsageLocation**).
  
Para ver todas as propriedades de uma conta de usuário específica, use o cmdlet **Select** e o caractere curinga (*). Exemplo:
  
```powershell
Get-AzureADUser -ObjectID BelindaN@litwareinc.onmicosoft.com | Select *
```

Como outro exemplo, execute o seguinte comando para verificar o status habilitado de uma conta de usuário específica:
  
```powershell
Get-AzureADUser -ObjectID <sign-in name of the user account> | Select DisplayName,UserPrincipalName,AccountEnabled
```

### <a name="view-account-synchronization-status"></a>Exibir status de sincronização de conta

As contas de usuário têm duas fontes: 

- Windows Server Active Directory (AD), que são contas sincronizadas do AD local com a nuvem.

- Contas do Azure Active Directory (Azure AD), que são criadas diretamente na nuvem.


O comando a seguir instrui o PowerShell a obter todos os usuários que têm o atributo *DirSyncEnabled* definido como *True*. Você pode usá-lo para encontrar contas que estão sincronizando a partir do AD local.

```powershell
Get-AzureADUser | Where {$_.DirSyncEnabled -eq $true}
```

O comando a seguir instrui o PowerShell a obter todos os usuários que têm o atributo *DirSyncEnabled* definido como *False*. Você pode usá-lo para encontrar contas somente na nuvem.

```powershell
Get-AzureADUser | Where {$_.DirSyncEnabled -ne $false}
```

### <a name="view-accounts-based-on-a-common-property"></a>Exibir contas com base em uma propriedade comum

Para ser mais seletivo sobre a lista de contas a serem exibidas, você pode usar o cmdlet **Where** em combinação com o cmdlet **Get-AzureADUser.** Para combinar os dois cmdlets, use o caractere "pipe" ("|"), que informa ao PowerShell do Azure Active Directory para Graph para que pegue os resultados de um comando e o envie para o próximo comando. Aqui está um comando de exemplo que exibe apenas as contas de usuário que têm um local de uso não especificado:
  
```powershell
Get-AzureADUser | Where {$_.UsageLocation -eq $Null}
```

Este comando instrui o PowerShell do Azure Active Directory para o Graph a:
  
1. Obter todas as informações sobre as contas de usuário (**Get-AzureADUser**) e enviá-lo para o próximo comando ( **|** ).
    
1. Encontre todas as contas de usuário que tenham um local de uso não especificado (**Onde {$ \_ . UsageLocation -eq $Null}**). Entre chaves, o comando instrui o PowerShell a encontrar apenas o conjunto de contas para as quais a propriedade de conta de usuário UsageLocation (**$ \_ . UsageLocation**) não é especificado (**-eq $Null**).
    
A **propriedade UsageLocation** é apenas uma das muitas propriedades associadas a uma conta de usuário. Para exibir todas as propriedades de uma conta de usuário específica, use o cmdlet **Select** e o caractere curinga (*). Exemplo:
  
```powershell
Get-AzureADUser -ObjectID BelindaN@litwareinc.onmicosoft.com | Select *
```

Por exemplo, **Cidade** é o nome de uma propriedade de conta de usuário. Você pode usar o seguinte comando para listar todas as contas de usuários que moram em Londres:
  
```powershell
Get-AzureADUser | Where {$_.City -eq "London"}
```

> [!TIP]
>  A sintaxe para o cmdlet **Where** nesses exemplos é **Where {$ \_ .** [nome da propriedade da conta de usuário] [operador de comparação] [value] **}**.> [operador de comparação] é **-eq** para igual a, **-ne** para não é igual a, **-lt** para menor que, **-gt** para maior que e outros.  [valor] é geralmente uma cadeia de caracteres (uma sequência de letras,  números e outros caracteres), um valor numérico ou $Null para não especificado. Para obter mais informações, consulte [Where](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/where-object?view=powershell-7).
  

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Use o Módulo Microsoft Azure Active Directory para Windows PowerShell.

Primeiro, [conecte-se ao locatário do Microsoft 365.](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)

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

O cmdlet **Get-MsolUser** também tem um conjunto de parâmetros para filtrar o conjunto de contas de usuário exibido. Por exemplo, para a lista de usuários não licenciados (usuários que foram adicionados ao Microsoft 365, mas ainda não foram licenciados para usar qualquer um dos serviços), execute este comando:
  
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

Para obter informações sobre parâmetros adicionais para filtrar o conjunto de contas de usuário que são exibidas, consulte [Get-MsolUser](https://docs.microsoft.com/previous-versions/azure/dn194133(v=azure.100)).
  
### <a name="view-a-specific-account"></a>Exibir uma conta específica

Para exibir uma conta de usuário específica, execute o seguinte comando. Preencha o nome de logon da conta de usuário, que também é conhecido como nome UPN. Remova os caracteres "<" e ">".
  
```powershell
Get-MsolUser -UserPrincipalName <sign-in name of the user account>
```

### <a name="view-accounts-based-on-a-common-property"></a>Exibir contas com base em uma propriedade comum

Para ser mais seletivo sobre a lista de contas a serem exibidas, você pode usar o cmdlet **Where** em combinação com o cmdlet **Get-MsolUser.** Para combinar os dois cmdlets, use o caractere "pipe" ("|"), que informa ao PowerShell para usar os resultados de um comando e enviá-lo para o próximo comando. Veja um exemplo que exibe apenas as contas de usuário que possuem um local de uso não especificado:
  
```powershell
Get-MsolUser | Where {$_.UsageLocation -eq $Null}
```

Este comando instrui o PowerShell a:
  
1. Obter todas as informações sobre as contas de usuário (**Get-MsolUser**) e enviá-lo para o próximo comando ( **|** ).
    
1. Localizar todas as contas de usuário que tenham um local de uso não especificado (**Onde {$ \_ . UsageLocation -eq $Null}**). Entre chaves, o comando instrui o PowerShell a encontrar apenas o conjunto de contas para as quais a propriedade de conta de usuário UsageLocation (**$ \_ . UsageLocation**) não é especificado (**-eq $Null**).
    
Você deve obter informações semelhantes a esta:
  
```powershell
UserPrincipalName                     DisplayName           isLicensed
-----------------                     -----------           ----------
BrianJ@litwareinc.onmicrosoft.com     Brian Johnson         False 
ScottW@litwareinc.onmicrosoft.com     Scott Wallace         False

```

A *propriedade UsageLocation* é apenas uma das muitas propriedades associadas a uma conta de usuário. Para ver todas as propriedades de contas de usuário, use o cmdlet **Select** e o caractere curinga (*) para exibir todas elas para uma conta de usuário específica. Exemplo:
  
```powershell
Get-MsolUser -UserPrincipalName BelindaN@litwareinc.onmicosoft.com | Select *
```

Por exemplo, *Cidade* é o nome de uma propriedade de conta de usuário. Você pode usar o seguinte comando para listar todas as contas de usuário para usuários que moram em Londres:
  
```powershell
Get-MsolUser | Where {$_.City -eq "London"}
```

> [!TIP]
>  A sintaxe para o cmdlet **Where** nesses exemplos é **Where {$ \_ .** [nome da propriedade da conta de usuário] [operador de comparação] [value] **}**.  [operador de comparação] é **-eq** para igual, **-ne** para não igual a, **-lt** para menor que, **-gt** para maior que e outros.  [valor] é geralmente uma cadeia de caracteres (uma sequência de letras,  números e outros caracteres), um valor numérico ou $Null para não especificado. Para obter mais informações, consulte [Where](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/where-object?view=powershell-7).
  
Para verificar o status bloqueado de uma conta de usuário, use o seguinte comando:
  
```powershell
Get-MsolUser -UserPrincipalName <UPN of user account> | Select DisplayName,BlockCredential
```

### <a name="view-additional-property-values-for-accounts"></a>Exibir valores de propriedade adicionais para contas

Por padrão, o cmdlet **Get-MsolUser** exibe estas três propriedades de contas de usuário:
  
- UserPrincipalName
    
- DisplayName
    
- isLicensed
    
Se você precisar de propriedades adicionais, como o departamento onde o usuário trabalha e o país/região onde ele usa os serviços do Microsoft 365, você pode executar **Get-MsolUser** em combinação com o cmdlet **Select** para especificar a lista de propriedades de conta de usuário. Exemplo:
  
```powershell
Get-MsolUser | Select DisplayName, Department, UsageLocation
```

Este comando instrui o PowerShell a:
  
1. Obter todas as informações sobre as contas de usuário (**Get-MsolUser**) e enviá-lo para o próximo comando ( **|** ).
    
1. Exibe somente o nome da conta de usuário, o departamento e o local de uso (**Selecione DisplayName, Departamento, UsageLocation**).
    
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

O cmdlet **Select** permite escolher quais propriedades exibir. Para exibir todas as propriedades de uma conta de usuário específica, use o caractere curinga (*). Exemplo:
  
```powershell
Get-MsolUser -UserPrincipalName BelindaN@litwareinc.onmicosoft.com | Select *
```

Para ser mais seletivo sobre a lista de contas a serem exibidas, você também pode usar o cmdlet **Where.** Aqui está um comando de exemplo que exibe apenas as contas de usuário que têm um local de uso não especificado:
  
```powershell
Get-MsolUser | Where {$_.UsageLocation -eq $Null} | Select DisplayName, Department, UsageLocation
```

Este comando instrui o PowerShell a:
  
1. Obter todas as informações sobre as contas de usuário (**Get-MsolUser**) e enviá-lo para o próximo comando ( **|** ).
    
1. Localizar todas as contas de usuário que tenham um local de uso não especificado (**Onde {$ \_ . UsageLocation -eq $Null}**) e envie as informações resultantes para o próximo comando ( **|** ). Entre chaves, o comando instrui o PowerShell a encontrar apenas o conjunto de contas para as quais a propriedade de conta de usuário UsageLocation (**$ \_ . UsageLocation**) não é especificado (**-eq $Null**).
    
1. Exibe somente o nome da conta de usuário, o departamento e o local de uso (**Selecione DisplayName, Departamento, UsageLocation**).
    
Você deve obter informações semelhantes a esta:
  
```powershell
DisplayName              Department                      UsageLocation
-----------              ----------                      -------------
Brian Johnson 
Scott Wallace            Operations
```

Se você estiver usando a sincronização de diretórios para criar e gerenciar seus usuários do Microsoft 365, poderá exibir a conta local da qual um usuário do Microsoft 365 foi projetado. O exemplo a seguir pressupo que:

- O Azure AD Connect está configurado para usar a âncora de origem padrão do ObjectGUID. (Para obter mais informações sobre como configurar uma âncora de origem, consulte [Azure AD Connect: conceitos de design).](https://docs.microsoft.com/azure/active-directory/hybrid/plan-connect-design-concepts)
- O módulo serviços de domínio do Active Directory para PowerShell foi instalado (consulte ferramentas [RSAT](https://www.microsoft.com/en-gb/download/details.aspx?id=45520)).

```powershell
Get-ADUser ([guid][System.Convert]::FromBase64String((Get-MsolUser -UserPrincipalName <UPN of user account>).ImmutableID)).guid
```

## <a name="see-also"></a>Confira também

[Gerenciar contas de usuário, licenças e grupos do Microsoft 365 com o PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[Gerenciar o Microsoft 365 com o PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Introdução ao Windows PowerShell para o Microsoft 365](getting-started-with-microsoft-365-powershell.md)
