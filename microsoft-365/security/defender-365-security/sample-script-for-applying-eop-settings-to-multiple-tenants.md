---
title: Script de exemplo para configurações do EOP - vários locatários
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
ms.assetid: e87e84e1-7be0-44bf-a414-d91d60ed8817
ms.custom:
- seo-marvel-apr2020
description: Neste artigo, você aprenderá a usar o PowerShell para aplicar configurações aos locatários no Microsoft Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 77a1dce25901845628f8148c44a0d0783088255e
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51054242"
---
# <a name="sample-script-for-applying-eop-settings-to-multiple-tenants"></a><span data-ttu-id="adcef-103">Amostra de script para aplicação de configurações de EOP a vários locatários</span><span class="sxs-lookup"><span data-stu-id="adcef-103">Sample script for applying EOP settings to multiple tenants</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="adcef-104">**Aplica-se a**</span><span class="sxs-lookup"><span data-stu-id="adcef-104">**Applies to**</span></span>
-  [<span data-ttu-id="adcef-105">Proteção autônoma do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="adcef-105">Exchange Online Protection standalone</span></span>](exchange-online-protection-overview.md)

<span data-ttu-id="adcef-106">O script de exemplo a seguir permite que Microsoft Exchange Online administradores do EOP que gerenciam vários locatários (empresas) usem o PowerShell do Exchange Online para exibir e/ou aplicar configurações a seus locatários.</span><span class="sxs-lookup"><span data-stu-id="adcef-106">The following sample script lets Microsoft Exchange Online Protection (EOP) admins who manage multiple tenants (companies) use Exchange Online PowerShell to view and/or apply configuration settings to their tenants.</span></span>

## <a name="to-run-a-script-or-cmdlet-on-multiple-tenants"></a><span data-ttu-id="adcef-107">Para executar um script ou cmdlet em vários locatários</span><span class="sxs-lookup"><span data-stu-id="adcef-107">To run a script or cmdlet on multiple tenants</span></span>

1. <span data-ttu-id="adcef-108">Caso ainda não tenha feito isso, [instale o módulo V2](/powershell/exchange/exchange-online-powershell-v2#install-and-maintain-the-exo-v2-module)do Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="adcef-108">If you haven't already, [install the Exchange Online V2 module](/powershell/exchange/exchange-online-powershell-v2#install-and-maintain-the-exo-v2-module).</span></span>

2. <span data-ttu-id="adcef-109">Usando um aplicativo de planilha (por exemplo, Excel), crie um arquivo .csv com os seguintes detalhes:</span><span class="sxs-lookup"><span data-stu-id="adcef-109">Using an spreadsheet app (for example, Excel), create a .csv file with the following details:</span></span>

   - <span data-ttu-id="adcef-110">Coluna UserName: a conta que você usará para se conectar (por exemplo, `admin@contoso.onmicrosoft.com` ).</span><span class="sxs-lookup"><span data-stu-id="adcef-110">UserName column: The account that you'll use to connect (for example, `admin@contoso.onmicrosoft.com`).</span></span>
   - <span data-ttu-id="adcef-111">Coluna cmdlet: o cmdlet ou comando a ser executado (por exemplo, `Get-AcceptedDomain` ou `Get-AcceptedDomain | FT Name` ).</span><span class="sxs-lookup"><span data-stu-id="adcef-111">Cmdlet column: The cmdlet or command to run (for example, `Get-AcceptedDomain` or `Get-AcceptedDomain | FT Name`).</span></span>

   <span data-ttu-id="adcef-112">O arquivo terá esta aparência:</span><span class="sxs-lookup"><span data-stu-id="adcef-112">The file will look like this:</span></span>

   ```text
   UserName,Cmdlet
   admin@contoso.onmicrosoft.com,Get-AcceptedDomain | FT Name
   admin@fabrikam.onmicrosoft.com,Get-AcceptedDomain | FT Name
   ```

3. <span data-ttu-id="adcef-113">Salve o arquivo .csv em um local fácil de localizar (por exemplo, c:\scripts\inputfile.csv).</span><span class="sxs-lookup"><span data-stu-id="adcef-113">Save the .csv file in a location that's easy to find (for example, c:\scripts\inputfile.csv).</span></span>

4. <span data-ttu-id="adcef-114">Copie o [RunCmdletOnMultipleTenants.ps1](#runcmdletonmultipletenantsps1) script no Bloco de Notas e salve o arquivo em um local fácil de localizar (por exemplo, c:\scripts).</span><span class="sxs-lookup"><span data-stu-id="adcef-114">Copy the [RunCmdletOnMultipleTenants.ps1](#runcmdletonmultipletenantsps1) script into Notepad, and then save the file to a location that's easy to find (for example, c:\scripts).</span></span>

5. <span data-ttu-id="adcef-115">Execute o script usando a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="adcef-115">Run the script by using the following syntax:</span></span>

   ```powershell
   & "<file path>\RunCmdletOnMultipleTenants.ps1" "<file path>\inputfile.csv"
   ```

   <span data-ttu-id="adcef-116">Exemplo:</span><span class="sxs-lookup"><span data-stu-id="adcef-116">Here's an example:</span></span>

   ```powershell
   & "c:\scripts\RunCmdletOnMultipleTenants.ps1" "c:\scripts\inputfile.csv"
   ```

6. <span data-ttu-id="adcef-117">Cada locatário será conectado e o script será executado.</span><span class="sxs-lookup"><span data-stu-id="adcef-117">Each tenant will be logged on to, and the script will be run.</span></span>

## <a name="runcmdletonmultipletenantsps1"></a><span data-ttu-id="adcef-118">RunCmdletOnMultipleTenants.ps1</span><span class="sxs-lookup"><span data-stu-id="adcef-118">RunCmdletOnMultipleTenants.ps1</span></span>

> [!NOTE]
> <span data-ttu-id="adcef-119">Talvez seja necessário modificar a `Connect-IPPSSession` linha no script para corresponder ao seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="adcef-119">You might need to modify the `Connect-IPPSSession` line in the script to match your environment.</span></span> <span data-ttu-id="adcef-120">Por exemplo, o Office 365 Germany requer um valor _ConnectionUri_ diferente do valor atual em um script.</span><span class="sxs-lookup"><span data-stu-id="adcef-120">For example, Office 365 Germany requires a different _ConnectionUri_ value than the current value in a script.</span></span> <span data-ttu-id="adcef-121">Para obter detalhes, consulte Connect to [Exchange Online Powershell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="adcef-121">For details, see Connect to [Exchange Online Powershell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

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