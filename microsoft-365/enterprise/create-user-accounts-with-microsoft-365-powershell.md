---
title: Criar contas de usuário do Microsoft 365 com o PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/23/2020
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
description: Neste artigo, saiba como usar o PowerShell para criar contas de usuário ou várias contas de usuário do Microsoft 365.
ms.openlocfilehash: 00ae8806e786eada092704febd65c72c72382788
ms.sourcegitcommit: c1ee4ed3c5826872b57339e1e1aa33b4d2209711
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/23/2020
ms.locfileid: "48235589"
---
# <a name="create-microsoft-365-user-accounts-with-powershell"></a><span data-ttu-id="0e34f-103">Criar contas de usuário do Microsoft 365 com o PowerShell</span><span class="sxs-lookup"><span data-stu-id="0e34f-103">Create Microsoft 365 user accounts with PowerShell</span></span>

<span data-ttu-id="0e34f-104">*Esse artigo se aplica ao Microsoft 365 Enterprise e ao Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="0e34f-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="0e34f-105">Você pode usar o PowerShell para Microsoft 365 para criar com eficiência contas de usuário, especialmente várias contas de usuário.</span><span class="sxs-lookup"><span data-stu-id="0e34f-105">You can use PowerShell for Microsoft 365 to efficiently create user accounts, especially multiple user accounts.</span></span> <span data-ttu-id="0e34f-106">Quando você cria contas de usuário no PowerShell, determinadas propriedades de conta são sempre necessárias.</span><span class="sxs-lookup"><span data-stu-id="0e34f-106">When you create user accounts in PowerShell, certain account properties are always required.</span></span> <span data-ttu-id="0e34f-107">Outras propriedades, embora sejam importantes, não são obrigatórias para a criação de contas.</span><span class="sxs-lookup"><span data-stu-id="0e34f-107">Other properties aren't required to create the account, but are otherwise important.</span></span> <span data-ttu-id="0e34f-108">Essas propriedades são descritas na tabela a seguir:</span><span class="sxs-lookup"><span data-stu-id="0e34f-108">These properties are described in the following table:</span></span>
  
|<span data-ttu-id="0e34f-109">**Nome da propriedade**</span><span class="sxs-lookup"><span data-stu-id="0e34f-109">**Property name**</span></span>|<span data-ttu-id="0e34f-110">**Obrigatório?**</span><span class="sxs-lookup"><span data-stu-id="0e34f-110">**Required?**</span></span>|<span data-ttu-id="0e34f-111">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="0e34f-111">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="0e34f-112">**DisplayName**</span><span class="sxs-lookup"><span data-stu-id="0e34f-112">**DisplayName**</span></span> <br/> |<span data-ttu-id="0e34f-113">Sim</span><span class="sxs-lookup"><span data-stu-id="0e34f-113">Yes</span></span>  <br/> |<span data-ttu-id="0e34f-114">Este é o nome de exibição usado nos serviços do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0e34f-114">This is the display name that's used in Microsoft 365 services.</span></span> <span data-ttu-id="0e34f-115">Por exemplo, Carlos Lima.</span><span class="sxs-lookup"><span data-stu-id="0e34f-115">For example, Caleb Sills.</span></span>  <br/> |
|<span data-ttu-id="0e34f-116">**UserPrincipalName**</span><span class="sxs-lookup"><span data-stu-id="0e34f-116">**UserPrincipalName**</span></span> <br/> |<span data-ttu-id="0e34f-117">Sim</span><span class="sxs-lookup"><span data-stu-id="0e34f-117">Yes</span></span>  <br/> |<span data-ttu-id="0e34f-118">Este é o nome da conta usada para entrar nos serviços do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0e34f-118">This is the account name that's used to sign in to Microsoft 365 services.</span></span> <span data-ttu-id="0e34f-119">Por exemplo, carlosl@contoso.onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="0e34f-119">For example, CalebS@contoso.onmicrosoft.com.</span></span>  <br/> |
|<span data-ttu-id="0e34f-120">**FirstName**</span><span class="sxs-lookup"><span data-stu-id="0e34f-120">**FirstName**</span></span> <br/> |<span data-ttu-id="0e34f-121">Não</span><span class="sxs-lookup"><span data-stu-id="0e34f-121">No</span></span>  <br/> ||
|<span data-ttu-id="0e34f-122">**LastName**</span><span class="sxs-lookup"><span data-stu-id="0e34f-122">**LastName**</span></span> <br/> |<span data-ttu-id="0e34f-123">Não</span><span class="sxs-lookup"><span data-stu-id="0e34f-123">No</span></span>  <br/> ||
|<span data-ttu-id="0e34f-124">**LicenseAssignment**</span><span class="sxs-lookup"><span data-stu-id="0e34f-124">**LicenseAssignment**</span></span> <br/> |<span data-ttu-id="0e34f-125">Não</span><span class="sxs-lookup"><span data-stu-id="0e34f-125">No</span></span>  <br/> |<span data-ttu-id="0e34f-126">Este é o plano de licenciamento (também conhecido como o plano de licença ou SKU) a partir do qual uma licença disponível é atribuída à conta de usuário.</span><span class="sxs-lookup"><span data-stu-id="0e34f-126">This is the licensing plan (also known as the license plan or SKU) from which an available license is assigned to the user account.</span></span> <span data-ttu-id="0e34f-127">A licença define os serviços do Microsoft 365 que estão disponíveis para a conta.</span><span class="sxs-lookup"><span data-stu-id="0e34f-127">The license defines the Microsoft 365 services that are available to account.</span></span> <span data-ttu-id="0e34f-128">Não é necessário atribuir uma licença a um usuário quando você cria a conta, mas a conta requer uma licença para acessar os serviços do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0e34f-128">You don't have to assign a license to a user when you create the account, but the account requires a license to access Microsoft 365 services.</span></span> <span data-ttu-id="0e34f-129">Você tem 30 dias para licenciar a conta de usuário depois de criá-la.</span><span class="sxs-lookup"><span data-stu-id="0e34f-129">You have 30 days to license the user account after you create it.</span></span> |
|<span data-ttu-id="0e34f-130">**Password**</span><span class="sxs-lookup"><span data-stu-id="0e34f-130">**Password**</span></span> <br/> |<span data-ttu-id="0e34f-131">Não</span><span class="sxs-lookup"><span data-stu-id="0e34f-131">No</span></span>  <br/> | <span data-ttu-id="0e34f-p105">Caso não especifique uma senha, nosso sistema atribuirá uma senha aleatória para a conta do usuário e a senha ficará visível nos resultados do comando. Se você especificar uma senha, ela deverá Se você especificar uma senha, ela precisará ter de 8 a 16 caracteres de texto ASCII de qualquer um dos três tipos a seguir: letras minúsculas, letras maiúsculas, números e símbolos.</span><span class="sxs-lookup"><span data-stu-id="0e34f-p105">If you don't specify a password, a random password is assigned to the user account, and the password is visible in the results of the command. If you specify a password, it needs to be 8 to 16 ASCII text characters from any three of the following types: lowercase letters, uppercase letters, numbers, and symbols.</span></span> <br/> |
|<span data-ttu-id="0e34f-134">**UsageLocation**</span><span class="sxs-lookup"><span data-stu-id="0e34f-134">**UsageLocation**</span></span> <br/> |<span data-ttu-id="0e34f-135">Não</span><span class="sxs-lookup"><span data-stu-id="0e34f-135">No</span></span>  <br/> |<span data-ttu-id="0e34f-136">Este é um código de país do país 3166-1 alfa-2 válido.</span><span class="sxs-lookup"><span data-stu-id="0e34f-136">This is a valid ISO 3166-1 alpha-2 country code.</span></span> <span data-ttu-id="0e34f-137">Por exemplo, US para os Estados Unidos e FR para a França.</span><span class="sxs-lookup"><span data-stu-id="0e34f-137">For example, US for the United States, and FR for France.</span></span> <span data-ttu-id="0e34f-138">É importante fornecer esse valor, pois alguns serviços do Microsoft 365 não estão disponíveis em determinados países, portanto, você não pode atribuir uma licença a uma conta de usuário, a menos que a conta tenha esse valor configurado.</span><span class="sxs-lookup"><span data-stu-id="0e34f-138">It's important to provide this value, because some Microsoft 365 services aren't available in certain countries, so you can't assign a license to a user account unless the account has this value configured.</span></span> <span data-ttu-id="0e34f-139">Para obter mais informações, consulte [about License Restrictions](https://go.microsoft.com/fwlink/p/?LinkId=691730).</span><span class="sxs-lookup"><span data-stu-id="0e34f-139">For more information, see [About license restrictions](https://go.microsoft.com/fwlink/p/?LinkId=691730).</span></span>  <br/> |

>[!Note]
><span data-ttu-id="0e34f-140">[Saiba como criar contas de usuário](https://docs.microsoft.com/microsoft-365/admin/add-users/add-users) com o centro de administração do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0e34f-140">[Learn how to create user accounts](https://docs.microsoft.com/microsoft-365/admin/add-users/add-users) with the Microsoft 365 admin center.</span></span> <span data-ttu-id="0e34f-141">Para obter uma lista de recursos adicionais, consulte [Manage Users and Groups](https://docs.microsoft.com/microsoft-365/admin/add-users/).</span><span class="sxs-lookup"><span data-stu-id="0e34f-141">For a list of additional resources, see [Manage users and groups](https://docs.microsoft.com/microsoft-365/admin/add-users/).</span></span>
>   

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="0e34f-142">Use o PowerShell do Azure Active Directory para o módulo do gráfico</span><span class="sxs-lookup"><span data-stu-id="0e34f-142">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="0e34f-143">Primeiro, [Conecte-se ao seu locatário do Microsoft 365](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span><span class="sxs-lookup"><span data-stu-id="0e34f-143">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>

<span data-ttu-id="0e34f-144">Depois de se conectar, use a seguinte sintaxe para criar uma conta individual:</span><span class="sxs-lookup"><span data-stu-id="0e34f-144">After you have connected, use the following syntax to create an individual account:</span></span>
  
```powershell
$PasswordProfile=New-Object -TypeName Microsoft.Open.AzureAD.Model.PasswordProfile
$PasswordProfile.Password="<user account password>"
New-AzureADUser -DisplayName "<display name>" -GivenName "<first name>" -SurName "<last name>" -UserPrincipalName <sign-in name> -UsageLocation <ISO 3166-1 alpha-2 country code> -MailNickName <mailbox name> -PasswordProfile $PasswordProfile -AccountEnabled $true
```

<span data-ttu-id="0e34f-145">Neste exemplo, criamos uma conta para o usuário chamado Carlos Lima do Brasil:</span><span class="sxs-lookup"><span data-stu-id="0e34f-145">This example creates an account for the United States user named Caleb Sills:</span></span>
  
```powershell
$PasswordProfile=New-Object -TypeName Microsoft.Open.AzureAD.Model.PasswordProfile
$PasswordProfile.Password="3Rv0y1q39/chsy"
New-AzureADUser -DisplayName "Caleb Sills" -GivenName "Caleb" -SurName "Sills" -UserPrincipalName calebs@contoso.onmicrosoft.com -UsageLocation US -MailNickName calebs -PasswordProfile $PasswordProfile -AccountEnabled $true
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="0e34f-146">Use o Módulo Microsoft Azure Active Directory para Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0e34f-146">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="0e34f-147">Primeiro, [Conecte-se ao seu locatário do Microsoft 365](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="0e34f-147">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

### <a name="create-an-individual-user-account"></a><span data-ttu-id="0e34f-148">Criar uma conta de usuário individual</span><span class="sxs-lookup"><span data-stu-id="0e34f-148">Create an individual user account</span></span>

<span data-ttu-id="0e34f-149">Para criar uma conta individual, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="0e34f-149">To create an individual account, use the following syntax:</span></span>
  
```powershell
New-MsolUser -DisplayName <display name> -FirstName <first name> -LastName <last name> -UserPrincipalName <sign-in name> -UsageLocation <ISO 3166-1 alpha-2 country code> -LicenseAssignment <licensing plan name> [-Password <Password>]
```

>[!Note]
><span data-ttu-id="0e34f-150">O PowerShell Core não é compatível com o módulo do Microsoft Azure Active Directory para módulo e cmdlets do Windows PowerShell com **MSol** no nome.</span><span class="sxs-lookup"><span data-stu-id="0e34f-150">PowerShell Core does not support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="0e34f-151">Para continuar usando esses cmdlets, você deve executá-los a partir do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0e34f-151">To continue using these cmdlets, you must run them from Windows PowerShell.</span></span>
>

<span data-ttu-id="0e34f-152">Para listar os nomes do plano de licenciamento disponível, use este comando:</span><span class="sxs-lookup"><span data-stu-id="0e34f-152">To list the available licensing plan names, use this command:</span></span>

````powershell
Get-MsolAccountSku
````

<span data-ttu-id="0e34f-153">Nesse exemplo, criamos uma conta para o usuário chamado Carlos Lima do Brasil e atribuímos uma licença do plano de licenciamento `contoso:ENTERPRISEPACK` (Office 365 Enterprise E3).</span><span class="sxs-lookup"><span data-stu-id="0e34f-153">This example creates an account for the United States user named Caleb Sills, and assigns a license from the `contoso:ENTERPRISEPACK` (Office 365 Enterprise E3) licensing plan.</span></span>
  
```powershell
New-MsolUser -DisplayName "Caleb Sills" -FirstName Caleb -LastName Sills -UserPrincipalName calebs@contoso.onmicrosoft.com -UsageLocation US -LicenseAssignment contoso:ENTERPRISEPACK
```

### <a name="create-multiple-user-accounts"></a><span data-ttu-id="0e34f-154">Criar várias contas de usuários</span><span class="sxs-lookup"><span data-stu-id="0e34f-154">Create multiple user accounts</span></span>

1. <span data-ttu-id="0e34f-p109">Crie um arquivo CSV (arquivo de valores separados por vírgula) que inclua as informações necessárias da conta do usuário. Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="0e34f-p109">Create a comma-separated value (CSV) file that contains the required user account information. For example:</span></span>
    
  ```powershell
  UserPrincipalName,FirstName,LastName,DisplayName,UsageLocation,AccountSkuId
  ClaudeL@contoso.onmicrosoft.com,Claude,Loiselle,Claude Loiselle,US,contoso:ENTERPRISEPACK
  LynneB@contoso.onmicrosoft.com,Lynne,Baxter,Lynne Baxter,US,contoso:ENTERPRISEPACK
  ShawnM@contoso.onmicrosoft.com,Shawn,Melendez,Shawn Melendez,US,contoso:ENTERPRISEPACK
  ```

 > [!NOTE]
><span data-ttu-id="0e34f-157">Os nomes de coluna e sua ordem na primeira linha do arquivo CSV são arbitrários, mas certifique-se de que os dados no restante do arquivo coincidem com a ordem dos nomes de coluna e use os nomes de coluna para os valores de parâmetro no PowerShell para o Microsoft 365 Command.</span><span class="sxs-lookup"><span data-stu-id="0e34f-157">The column names and their order in the first row of the CSV file are arbitrary, but make sure the data in the rest of the file matches the order of the column names, and use the column names for the parameter values in the PowerShell for Microsoft 365 command.</span></span>
    
2. <span data-ttu-id="0e34f-158">Use a sintaxe a seguir:</span><span class="sxs-lookup"><span data-stu-id="0e34f-158">Use the following syntax:</span></span>
    
  ```powershell
  Import-Csv -Path <Input CSV File Path and Name> | foreach {New-MsolUser -DisplayName $_.DisplayName -FirstName $_.FirstName -LastName $_.LastName -UserPrincipalName $_.UserPrincipalName -UsageLocation $_.UsageLocation -LicenseAssignment $_.AccountSkuId [-Password $_.Password]} | Export-Csv -Path <Output CSV File Path and Name>
  ```

<span data-ttu-id="0e34f-159">Nesse exemplo, criamos as contas de usuários do arquivo C:\Meus Documentos\NewAccounts.csv e registramos os resultados no arquivo C:\Meus Documentos\NewAccountResults.csv</span><span class="sxs-lookup"><span data-stu-id="0e34f-159">This example creates the user accounts from the file named C:\My Documents\NewAccounts.csv, and logs the results in the file named C:\My Documents\NewAccountResults.csv</span></span>
    
  ```powershell
  Import-Csv -Path "C:\My Documents\NewAccounts.csv" | foreach {New-MsolUser -DisplayName $_.DisplayName -FirstName $_.FirstName -LastName $_.LastName -UserPrincipalName $_.UserPrincipalName -UsageLocation $_.UsageLocation -LicenseAssignment $_.AccountSkuId} | Export-Csv -Path "C:\My Documents\NewAccountResults.csv"
  ```

3. <span data-ttu-id="0e34f-160">Examine o arquivo de saída para conferir os resultados.</span><span class="sxs-lookup"><span data-stu-id="0e34f-160">Review the output file to see the results.</span></span> <span data-ttu-id="0e34f-161">Não especificamos senhas, portanto, as senhas aleatórias geradas pela Microsoft 365 são visíveis no arquivo de saída.</span><span class="sxs-lookup"><span data-stu-id="0e34f-161">We didn't specify passwords, so the random passwords that Microsoft 365 generated are visible in the output file.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="0e34f-162">Confira também</span><span class="sxs-lookup"><span data-stu-id="0e34f-162">See also</span></span>

[<span data-ttu-id="0e34f-163">Gerenciar contas de usuário, licenças e grupos do Microsoft 365 com o PowerShell</span><span class="sxs-lookup"><span data-stu-id="0e34f-163">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="0e34f-164">Gerenciar o Microsoft 365 com o PowerShell</span><span class="sxs-lookup"><span data-stu-id="0e34f-164">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="0e34f-165">Introdução ao PowerShell para o Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="0e34f-165">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
