---
title: Exemplo de script para configurações do EOP-vários locatários
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: e87e84e1-7be0-44bf-a414-d91d60ed8817
ms.custom:
- seo-marvel-apr2020
description: Neste artigo, você aprenderá a usar o PowerShell para aplicar definições de configuração aos seus locatários no Microsoft Exchange Online Protection (EOP).
ms.openlocfilehash: b18fc71171a93e2a2f415800bcf2b5abd5c5a526
ms.sourcegitcommit: ee39faf3507d0edc9497117b3b2854955c959c6c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "49615859"
---
# <a name="sample-script-for-applying-eop-settings-to-multiple-tenants"></a>Amostra de script para aplicação de configurações de EOP a vários locatários

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


O seguinte exemplo de script permite que os administradores do Microsoft proteção do Exchange Online (EOP) que gerenciam vários locatários (empresas) usem o PowerShell do Exchange Online para exibir e/ou aplicar definições de configuração aos seus locatários.

## <a name="to-run-a-script-or-cmdlet-on-multiple-tenants"></a>Para executar um script ou cmdlet em vários locatários

1. Se você ainda não tiver feito isso, [Instale o módulo do Exchange Online v2](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell-v2#install-and-maintain-the-exo-v2-module).

2. Usando um aplicativo de planilha (por exemplo, Excel), crie um arquivo. csv com os seguintes detalhes:

   - Coluna de nome de usuário: a conta que você usará para se conectar (por exemplo, `admin@contoso.onmicrosoft.com` ).
   - Coluna do cmdlet: o cmdlet ou comando a ser executado (por exemplo, `Get-AcceptedDomain` ou `Get-AcceptedDomain | FT Name` ).

   O arquivo terá a seguinte aparência:

   ```text
   UserName,Cmdlet
   admin@contoso.onmicrosoft.com,Get-AcceptedDomain | FT Name
   admin@fabrikam.onmicrosoft.com,Get-AcceptedDomain | FT Name
   ```

3. Salve o arquivo. csv em um local que seja fácil de encontrar (por exemplo, c:\scripts\inputfile.csv).

4. Copie o [RunCmdletOnMultipleTenants.ps1](#runcmdletonmultipletenantsps1) script no bloco de notas e salve o arquivo em um local que seja fácil de encontrar (por exemplo, c:\Scripts).

5. Execute o script usando a seguinte sintaxe:

   ```powershell
   & "<file path>\RunCmdletOnMultipleTenants.ps1" "<file path>\inputfile.csv"
   ```

   Exemplo:

   ```powershell
   & "c:\scripts\RunCmdletOnMultipleTenants.ps1" "c:\scripts\inputfile.csv"
   ```

6. Cada locatário será conectado ao e o script será executado.

## <a name="runcmdletonmultipletenantsps1"></a>RunCmdletOnMultipleTenants.ps1

> [!NOTE]
> Talvez seja necessário modificar a `Connect-IPPSSession` linha no script para corresponder ao seu ambiente. Por exemplo, o Office 365 Alemanha requer um valor _ConnectionURI_ diferente do valor atual em um script. Para obter detalhes, consulte Connect to [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).

```powershell
# This script runs Windows PowerShell cmdlets on multiple tenants.
#
# Usage: RunCmdletOnMultipleTenants.ps1 inputfile.csv
#
# .csv input file sample:
#
# UserName,Cmdlet
# admin@contoso.onmicrosoft.com,Get-AcceptedDomain | FT Name
# admin@fabrikam.onmicrosoft.com,Get-AcceptedDomain | FT Name

# Get the .csv file name as an argument to this script.
$FilePath = $args[0]

# Import the UserName and Cmdlet values from the .csv file.
$CompanyList = Import-CSV $FilePath

# Load the EXO V2 module
Import-Module ExchangeOnlineManagement

# Loop through each entry from the .csv file.
ForEach ($Company in $CompanyList) {

# Get the current entry's UserName.
$UserName = $Company.UserName

# Get the current entry's Cmdlet.
$Cmdlet = $Company.Cmdlet

# Connect to EOP PowerShell by using the current entry's UserName. Prompt for the password.
Connect-IPPSSession -UserPrincipalName $UserName -ConnectionUri https://ps.protection.outlook.com/powershell-liveid/

# Here's where the script to be run on the tenant goes.
# In this example, the cmdlet in the .csv file runs.
Invoke-Expression $Cmdlet

# End the current PowerShell session.
Disconnect-ExchangeOnline -Confirm:$false
}
```
