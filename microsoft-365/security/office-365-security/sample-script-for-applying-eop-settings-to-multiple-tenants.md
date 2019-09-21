---
title: Amostra de script para aplicação de configurações de EOP a vários locatários
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 11/17/2014
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: e87e84e1-7be0-44bf-a414-d91d60ed8817
description: A seguinte amostra de script permite que os administradores do Microsoft Proteção do Exchange Online (EOP) que gerenciam vários locatários (empresas) usem o Windows PowerShell para aplicar configurações aos seus locatários.
ms.openlocfilehash: 2886d2c1dd4dc2f324e8cc21babc3a9f4bf51e5f
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/20/2019
ms.locfileid: "37073013"
---
# <a name="sample-script-for-applying-eop-settings-to-multiple-tenants"></a>Amostra de script para aplicação de configurações de EOP a vários locatários

A seguinte amostra de script permite que os administradores do Microsoft Proteção do Exchange Online (EOP) que gerenciam vários locatários (empresas) usem o Windows PowerShell para aplicar configurações aos seus locatários.
  
### <a name="to-run-a-script-or-cmdlet-on-multiple-tenants"></a>Para executar um script ou cmdlet em vários locatários

1. Usando um aplicativo como o Excel, crie um arquivo .csv (por exemplo, c:\scripts\inputfile.csv):

2. No arquivo .csv, especifique dois nomes de coluna: UserName e Cmdlet.

3. Para cada linha no arquivo .csv, adicione o nome de administrador do locatário na coluna UserName e o cmdlet a ser executado para esse locatário na coluna Cmdlet. Por exemplo, use admin@contoso.com e Get-AcceptedDomain.

4. Copie o script [RunCmdletOnMultipleTenants.ps1](#runcmdletonmultipletenantsps1) em um editor como o Bloco de Notas, e salve o arquivo em um local (como c:\scripts) que facilite a localização dos arquivos .ps1.

5. Execute o script usando a seguinte sintaxe:

   ```Powershell
   & "<file path>\RunCmdletOnMultipleTenants.ps1" "<file path>\inputfile.csv"
   ```

   Veja um exemplo.

   ```Powershell
   & "c:\scripts\RunCmdletOnMultipleTenanats.ps1" "c:\scripts\inputfile.csv"
   ```

6. Cada locatário efetuará logon e executará o cmdlet.

## <a name="runcmdletonmultipletenantsps1"></a>RunCmdletOnMultipleTenants. ps1

```Powershell
# This script runs Windows PowerShell cmdlets on multiple tenants.
# Usage: RunCmdletOnMultipleTenants.ps1 inputfile.csv
#  
# .csv input file sample:
# UserName,Cmdlet
# admin@contoso.com,Get-AcceptedDomain | ft Name
# URI for connecting to remote Windows PowerShell
$URI = "https://ps.protection.outlook.com/powershell-liveid/"
# Get the .csv file name as an argument to this script.
$FilePath = $args[0]
# Import the UserName and Cmdlet values from the .csv file.
$CompanyList = Import-CSV $FilePath
# Loop through each entry from the .csv file.
ForEach ($Company in $CompanyList) {
# Get the current entry's UserName.
$UserName = $Company.UserName
# Get the current entry's Cmdlet.
$Cmdlet = $Company.Cmdlet
# Create a PowerShell credential object by using the current entry's UserName. Prompt for the password.
$UserCredential = Get-Credential -username $UserName
# Log on to a new Windows PowerShell session.
$Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri $URI -Credential $UserCredential -Authentication Basic -AllowRedirection
Import-PSSession $Session
# Here's where the script to be run on the tenant goes.
# In this example, the cmdlet in the .csv file runs.
Invoke-Expression $Cmdlet
# End the current PowerShell session.
Remove-PsSession -Session $Session
}
```
