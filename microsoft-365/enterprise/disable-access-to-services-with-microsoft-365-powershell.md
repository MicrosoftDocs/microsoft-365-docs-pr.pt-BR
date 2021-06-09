---
title: Desabilitar o acesso Microsoft 365 serviços com o PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/27/2020
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
- Ent_Office_Other
- PowerShell
- LIL_Placement
- seo-marvel-apr2020
ms.assetid: 264f4f0d-e2cd-44da-a9d9-23bef250a720
description: Neste artigo, saiba como usar o PowerShell para desabilitar o acesso Microsoft 365 serviços para usuários.
ms.openlocfilehash: 292bda3b380b9ce3947b2427288da4f16198bb51
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46687142"
---
# <a name="disable-access-to-microsoft-365-services-with-powershell"></a>Desabilitar o acesso Microsoft 365 serviços com o PowerShell

*Esse artigo se aplica ao Microsoft 365 Enterprise e ao Office 365 Enterprise.*

Quando uma Microsoft 365 é atribuída a uma licença de um plano de licenciamento, Microsoft 365 serviços são disponibilizados para o usuário a partir dessa licença. No entanto, você pode controlar os serviços Microsoft 365 que o usuário pode acessar. Por exemplo, mesmo que a licença permita acesso ao serviço SharePoint Online, você pode desabilitar o acesso a ele. Você pode usar o PowerShell para desabilitar o acesso a qualquer número de serviços para um plano de licenciamento específico para:

- Uma conta individual
- Um grupo de contas.
- Todas as contas em sua organização.

>[!Note]
>Há Microsoft 365 de serviço que podem impedir que você desabilite um serviço especificado quando outros serviços dependem dele.
>

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Use o Módulo Microsoft Azure Active Directory para Windows PowerShell.

Primeiro, [conecte-se ao seu Microsoft 365 locatário](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).

Em seguida, use este comando para exibir seus planos de licenciamento disponíveis, também conhecidos como AccountSkuIds:

```powershell
Get-MsolAccountSku | Select AccountSkuId | Sort AccountSkuId
```

>[!Note]
>O PowerShell Core não é compatível com o módulo do Microsoft Azure Active Directory para módulo e cmdlets do Windows PowerShell com **MSol** no nome. Para continuar usando esses cmdlets, você deve executá-los a partir do Windows PowerShell.
>

Para obter mais informações, [consulte Exibir licenças e serviços com o PowerShell](view-licenses-and-services-with-microsoft-365-powershell.md).
    
Para ver os resultados de antes e depois dos procedimentos neste tópico, consulte Exibir detalhes de licença de conta e [serviço com o PowerShell](view-account-license-and-service-details-with-microsoft-365-powershell.md).
    
Um script do PowerShell está disponível e automatiza os procedimentos descritos neste tópico. Especificamente, o script permite exibir e desabilitar serviços em sua Microsoft 365, incluindo o Sway. Para obter mais informações, consulte [Disable access to Sway with PowerShell](disable-access-to-sway-with-microsoft-365-powershell.md).
    
    
### <a name="disable-specific-microsoft-365-services-for-specific-users-for-a-specific-licensing-plan"></a>Desabilitar serviços Microsoft 365 específicos para usuários específicos para um plano de licenciamento específico
  
Para desabilitar um conjunto específico de serviços Microsoft 365 para usuários para um plano de licenciamento específico, execute as seguintes etapas:
  
#### <a name="step-1-identify-the-undesirable-services-in-the-licensing-plan-by-using-the-following-syntax"></a>Etapa 1: Identificar os serviços indesejáveis no plano de licenciamento usando a seguinte sintaxe:
    
```powershell
$LO = New-MsolLicenseOptions -AccountSkuId <AccountSkuId> -DisabledPlans "<UndesirableService1>", "<UndesirableService2>"...
```

O exemplo a seguir cria um **objeto LicenseOptions** que desabilita os serviços Office SharePoint Online no plano de licenciamento denominado `litwareinc:ENTERPRISEPACK` (Office 365 Enterprise E3).
    
```powershell
$LO = New-MsolLicenseOptions -AccountSkuId "litwareinc:ENTERPRISEPACK" -DisabledPlans "SHAREPOINTWAC", "SHAREPOINTENTERPRISE"
```

#### <a name="step-2-use-the-licenseoptions-object-from-step-1-on-one-or-more-users"></a>Etapa 2: Use o **objeto LicenseOptions** da Etapa 1 em um ou mais usuários.
    
Para criar uma nova conta que tem serviços desabilitados, use a seguinte sintaxe:
    
```powershell
New-MsolUser -UserPrincipalName <Account> -DisplayName <DisplayName> -FirstName <FirstName> -LastName <LastName> -LicenseAssignment <AccountSkuId> -LicenseOptions $LO -UsageLocation <CountryCode>
```

O exemplo a seguir cria uma nova conta para Allie Bellew que atribui a licença e desabilita os serviços descritos na Etapa 1.
    
```powershell
New-MsolUser -UserPrincipalName allieb@litwareinc.com -DisplayName "Allie Bellew" -FirstName Allie -LastName Bellew -LicenseAssignment litwareinc:ENTERPRISEPACK -LicenseOptions $LO -UsageLocation US
```

Para obter mais informações sobre como criar contas de usuário no PowerShell para Microsoft 365, consulte [Create user accounts with PowerShell](create-user-accounts-with-microsoft-365-powershell.md).
    
Para desabilitar os serviços de um usuário licenciado existente, use a seguinte sintaxe:
    
```powershell
Set-MsolUserLicense -UserPrincipalName <Account> -LicenseOptions $LO
```

Este exemplo desabilita os serviços do usuário BrendaF@litwareinc.com.
    
```powershell
Set-MsolUserLicense -UserPrincipalName belindan@litwareinc.com -LicenseOptions $LO
```

Para desabilitar os serviços descritos na Etapa 1 para todos os usuários licenciados existentes, especifique o nome do seu plano Microsoft 365 na exibição do cmdlet **Get-MsolAccountSku** (como **litwareinc:ENTERPRISEPACK**) e execute os seguintes comandos:
    
```powershell
$acctSKU="<AccountSkuId>"
$AllLicensed = Get-MsolUser -All | Where {$_.isLicensed -eq $true -and $_.licenses.AccountSku.SkuPartNumber -contains ($acctSKU).Substring($acctSKU.IndexOf(":")+1, $acctSKU.Length-$acctSKU.IndexOf(":")-1)}
$AllLicensed | ForEach {Set-MsolUserLicense -UserPrincipalName $_.UserPrincipalName -LicenseOptions $LO}
```

 Se você usar o cmdlet **Get-MsolUser** sem usar o parâmetro _All,_ apenas as primeiras 500 contas de usuário serão retornadas.

Para desabilitar os serviços para um grupo de usuários existentes, use um dos seguintes métodos para identificar os usuários:
    
**Método 1. Filtrar as contas com base em um atributo de conta existente** 

Para isso, use a seguinte sintaxe:
    
```powershell
$x = Get-MsolUser -All <FilterableAttributes>
$x | ForEach {Set-MsolUserLicense -UserPrincipalName $_.UserPrincipalName -LicenseOptions $LO}
```

O exemplo a seguir desabilita os serviços para usuários no departamento de Vendas nos Estados Unidos.
    
```powershell
$USSales = Get-MsolUser -All -Department "Sales" -UsageLocation "US"
$USSales | ForEach {Set-MsolUserLicense -UserPrincipalName $_.UserPrincipalName -LicenseOptions $LO}
```

**Método 2: Usar uma lista de contas específicas** 

Para fazer isso, execute as seguintes etapas:
    
1. Crie um arquivo de texto que contenha uma conta em cada linha da seguinte forma:
    
   ```powershell
   akol@contoso.com
   tjohnston@contoso.com
   kakers@contoso.com
   ```

   Neste exemplo, o arquivo de texto é C: \\ Meus documentos \\Accounts.txt.
    
2. Execute o seguinte comando:
    
   ```powershell
   Get-Content "C:\My Documents\Accounts.txt" | foreach {Set-MsolUserLicense -UserPrincipalName $_ -LicenseOptions $LO}
   ```

Se você quiser desabilitar o acesso aos serviços para vários planos de licenciamento, repita as instruções acima para cada plano de licenciamento, garantindo que:

- As contas de usuário foram atribuídas ao plano de licenciamento.
- Os serviços a ser desabilitado estão disponíveis no plano de licenciamento.

Para desabilitar Microsoft 365 serviços de usuários enquanto você os atribui a um plano de licenciamento, consulte Desabilitar o acesso aos serviços ao atribuir [licenças de usuário.](disable-access-to-services-while-assigning-user-licenses.md)

### <a name="assign-all-services-in-a-licensing-plan-to-a-user-account"></a>Atribuir todos os serviços em um plano de licenciamento a uma conta de usuário

Para contas de usuário que tiveram serviços desabilitados, você pode habilitar todos os serviços para um plano de licenciamento específico com estes comandos:

```powershell
$userUPN="<user account UPN>"
$acctSKU="<AccountSkuId>"
$LO = New-MsolLicenseOptions -AccountSkuId $acctSKU
Set-MsolUserLicense -UserPrincipalName $userUPN -LicenseOptions $LO
```

## <a name="related-topic"></a>Tópicos relacionados

[Gerenciar contas de usuário, licenças e grupos do Microsoft 365 com o PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[Gerenciar o Microsoft 365 com o PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Introdução ao PowerShell para o Microsoft 365](getting-started-with-microsoft-365-powershell.md)
