---
title: Exemplo de script para configurações do EOP-vários locatários
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: e87e84e1-7be0-44bf-a414-d91d60ed8817
ms.custom:
- seo-marvel-apr2020
description: Neste artigo, você aprenderá a usar o PowerShell para aplicar definições de configuração aos seus locatários no Microsoft Exchange Online Protection (EOP).
ms.openlocfilehash: c25bafe9ece71264931d8f059dd726147a6d28a4
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/12/2020
ms.locfileid: "44209134"
---
# <a name="sample-script-for-applying-eop-settings-to-multiple-tenants"></a><span data-ttu-id="1759f-103">Amostra de script para aplicação de configurações de EOP a vários locatários</span><span class="sxs-lookup"><span data-stu-id="1759f-103">Sample script for applying EOP settings to multiple tenants</span></span>

<span data-ttu-id="1759f-104">A seguinte amostra de script permite que os administradores do Microsoft Proteção do Exchange Online (EOP) que gerenciam vários locatários (empresas) usem o Windows PowerShell para aplicar configurações aos seus locatários.</span><span class="sxs-lookup"><span data-stu-id="1759f-104">The following sample script lets Microsoft Exchange Online Protection (EOP) admins who manage multiple tenants (companies) use Windows PowerShell to apply configuration settings to their tenants.</span></span>

## <a name="to-run-a-script-or-cmdlet-on-multiple-tenants"></a><span data-ttu-id="1759f-105">Para executar um script ou cmdlet em vários locatários</span><span class="sxs-lookup"><span data-stu-id="1759f-105">To run a script or cmdlet on multiple tenants</span></span>

1. <span data-ttu-id="1759f-106">Usando um aplicativo como o Excel, crie um arquivo .csv (por exemplo, c:\scripts\inputfile.csv):</span><span class="sxs-lookup"><span data-stu-id="1759f-106">Using an application such as Excel, create a .csv file (for example, c:\scripts\inputfile.csv):</span></span>

2. <span data-ttu-id="1759f-107">No arquivo .csv, especifique dois nomes de coluna: UserName e Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="1759f-107">In the .csv file, specify two column names: UserName and Cmdlet.</span></span>

3. <span data-ttu-id="1759f-p101">Para cada linha no arquivo .csv, adicione o nome de administrador do locatário na coluna UserName e o cmdlet a ser executado para esse locatário na coluna Cmdlet. Por exemplo, use admin@contoso.com e Get-AcceptedDomain.</span><span class="sxs-lookup"><span data-stu-id="1759f-p101">For each row in the .csv file, add the tenant's admin name in the UserName column and the cmdlet to run for that tenant in the Cmdlet column. For example, use admin@contoso.com and Get-AcceptedDomain.</span></span>

4. <span data-ttu-id="1759f-110">Copie o script [RunCmdletOnMultipleTenants. ps1](#runcmdletonmultipletenantsps1) para o bloco de notas e salve o arquivo em um local que seja fácil de encontrar (por exemplo, c:\Scripts).</span><span class="sxs-lookup"><span data-stu-id="1759f-110">Copy the [RunCmdletOnMultipleTenants.ps1](#runcmdletonmultipletenantsps1) script into Notepad, and then save the file to a location that's easy to find  (for example, c:\scripts).</span></span>

5. <span data-ttu-id="1759f-111">Execute o script usando a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="1759f-111">Run the script by using the following syntax:</span></span>

   ```powershell
   & "<file path>\RunCmdletOnMultipleTenants.ps1" "<file path>\inputfile.csv"
   ```

   <span data-ttu-id="1759f-112">Exemplo:</span><span class="sxs-lookup"><span data-stu-id="1759f-112">Here's an example:</span></span>

   ```powershell
   & "c:\scripts\RunCmdletOnMultipleTenanats.ps1" "c:\scripts\inputfile.csv"
   ```

6. <span data-ttu-id="1759f-113">Cada locatário será conectado ao e o script será executado.</span><span class="sxs-lookup"><span data-stu-id="1759f-113">Each tenant will be logged on to, and the script will be run.</span></span>

## <a name="runcmdletonmultipletenantsps1"></a><span data-ttu-id="1759f-114">RunCmdletOnMultipleTenants. ps1</span><span class="sxs-lookup"><span data-stu-id="1759f-114">RunCmdletOnMultipleTenants.ps1</span></span>

```powershell
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
