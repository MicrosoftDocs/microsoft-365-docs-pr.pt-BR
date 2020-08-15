---
title: Configurar as propriedades da conta de usuário do Microsoft 365 com o PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/16/2020
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
- O365ITProTrain
- Ent_Office_Other
- PowerShell
ms.assetid: 30813f8d-b08d-444b-98c1-53df7c29b4d7
description: 'Resumo: Use o PowerShell para Microsoft 365 para configurar propriedades de contas de usuário individuais ou múltiplas em seu locatário do Microsoft 365.'
ms.openlocfilehash: 6a435b3981efa8d8c2be7f6d983a1d062237f0db
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46686882"
---
# <a name="configure-microsoft-365-user-account-properties-with-powershell"></a><span data-ttu-id="726cb-103">Configurar as propriedades da conta de usuário do Microsoft 365 com o PowerShell</span><span class="sxs-lookup"><span data-stu-id="726cb-103">Configure Microsoft 365 user account properties with PowerShell</span></span>

<span data-ttu-id="726cb-104">*Esse artigo se aplica ao Microsoft 365 Enterprise e ao Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="726cb-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="726cb-105">Embora você possa usar o centro de administração do Microsoft 365 para configurar as propriedades das contas de usuário do seu locatário do Microsoft 365, você também pode usar o PowerShell e realizar algumas coisas que o centro de administração do Microsoft 365 não pode.</span><span class="sxs-lookup"><span data-stu-id="726cb-105">Although you can use the Microsoft 365 admin center to configure properties for the user accounts of your Microsoft 365 tenant, you can also use PowerShell and do some things that the Microsoft 365 admin center cannot.</span></span>
  
## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="726cb-106">Use o PowerShell do Azure Active Directory para o módulo do gráfico</span><span class="sxs-lookup"><span data-stu-id="726cb-106">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="726cb-107">Para configurar propriedades de contas de usuário com o módulo PowerShell do Azure Active Directory para Graph, use o cmdlet [set-AzureADUser](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser?view=azureadps-2.0) e especifique as propriedades a serem definidas ou alteradas.</span><span class="sxs-lookup"><span data-stu-id="726cb-107">To configure properties for user accounts with the Azure Active Directory PowerShell for Graph module, you use the [Set-AzureADUser](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser?view=azureadps-2.0) cmdlet and specify the properties to set or change.</span></span> 

<span data-ttu-id="726cb-108">Primeiro, [Conecte-se ao seu locatário do Microsoft 365](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span><span class="sxs-lookup"><span data-stu-id="726cb-108">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
   
### <a name="change-properties-for-a-specific-user-account"></a><span data-ttu-id="726cb-109">Alterar as propriedades de uma conta de usuário específica</span><span class="sxs-lookup"><span data-stu-id="726cb-109">Change properties for a specific user account</span></span>

<span data-ttu-id="726cb-110">Você identifica a conta com o parâmetro **-ObjectID** e define ou altera propriedades específicas com parâmetros adicionais.</span><span class="sxs-lookup"><span data-stu-id="726cb-110">You identify the account with the **-ObjectID** parameter and set or change specific properties with additional parameters.</span></span> <span data-ttu-id="726cb-111">Veja a seguir uma lista dos parâmetros mais comuns.</span><span class="sxs-lookup"><span data-stu-id="726cb-111">Here's a list of the most common parameters.</span></span>
  
- <span data-ttu-id="726cb-112">-Department " \<department name> "</span><span class="sxs-lookup"><span data-stu-id="726cb-112">-Department "\<department name>"</span></span>
    
- <span data-ttu-id="726cb-113">-DisplayName " \<full user name> "</span><span class="sxs-lookup"><span data-stu-id="726cb-113">-DisplayName "\<full user name>"</span></span>
    
- <span data-ttu-id="726cb-114">-FacsimilieTelephoneNumber " \<fax number> "</span><span class="sxs-lookup"><span data-stu-id="726cb-114">-FacsimilieTelephoneNumber "\<fax number>"</span></span>
    
- <span data-ttu-id="726cb-115">-Excertoname " \<user first name> "</span><span class="sxs-lookup"><span data-stu-id="726cb-115">-GivenName "\<user first name>"</span></span>
    
- <span data-ttu-id="726cb-116">-Sobrenome " \<user last name> "</span><span class="sxs-lookup"><span data-stu-id="726cb-116">-Surname "\<user last name>"</span></span>
    
- <span data-ttu-id="726cb-117">-Mobile " \<mobile phone number> "</span><span class="sxs-lookup"><span data-stu-id="726cb-117">-Mobile "\<mobile phone number>"</span></span>
    
- <span data-ttu-id="726cb-118">-JobTitle " \<job title> "</span><span class="sxs-lookup"><span data-stu-id="726cb-118">-JobTitle "\<job title>"</span></span>
    
- <span data-ttu-id="726cb-119">-PreferredLanguage " \<language> "</span><span class="sxs-lookup"><span data-stu-id="726cb-119">-PreferredLanguage "\<language>"</span></span>
    
- <span data-ttu-id="726cb-120">-StreetAddress " \<street address> "</span><span class="sxs-lookup"><span data-stu-id="726cb-120">-StreetAddress "\<street address>"</span></span>
    
- <span data-ttu-id="726cb-121">-City " \<city name> "</span><span class="sxs-lookup"><span data-stu-id="726cb-121">-City "\<city name>"</span></span>
    
- <span data-ttu-id="726cb-122">-State " \<state name> "</span><span class="sxs-lookup"><span data-stu-id="726cb-122">-State "\<state name>"</span></span>
    
- <span data-ttu-id="726cb-123">-PostalCode " \<postal code> "</span><span class="sxs-lookup"><span data-stu-id="726cb-123">-PostalCode "\<postal code>"</span></span>
    
- <span data-ttu-id="726cb-124">-Country " \<country name> "</span><span class="sxs-lookup"><span data-stu-id="726cb-124">-Country "\<country name>"</span></span>
    
- <span data-ttu-id="726cb-125">-TelephoneNumber " \<office phone number> "</span><span class="sxs-lookup"><span data-stu-id="726cb-125">-TelephoneNumber "\<office phone number>"</span></span>
    
- <span data-ttu-id="726cb-126">-UsageLocation " \<2-character country or region code> "</span><span class="sxs-lookup"><span data-stu-id="726cb-126">-UsageLocation "\<2-character country or region code>"</span></span>
    
    <span data-ttu-id="726cb-127">Este é o código de país ou região ISO 3166-1 alfa-2 (a2) de duas letras.</span><span class="sxs-lookup"><span data-stu-id="726cb-127">This is the ISO 3166-1 alpha-2 (A2) two-letter country or region code.</span></span>
    
<span data-ttu-id="726cb-128">Consulte [set-AzureADUser](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser?view=azureadps-2.0) para parâmetros adicionais.</span><span class="sxs-lookup"><span data-stu-id="726cb-128">See [Set-AzureADUser](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser?view=azureadps-2.0) for additional parameters.</span></span>


<span data-ttu-id="726cb-129">Para exibir o nome principal do usuário para suas contas de usuário, execute o seguinte comando.</span><span class="sxs-lookup"><span data-stu-id="726cb-129">To display the User Principal Name for your user accounts, run the following command.</span></span>
  
```powershell
Get-AzureADUser | Sort UserPrincipalName | Select UserPrincipalName | More
```

<span data-ttu-id="726cb-130">Este comando instrui o PowerShell para:</span><span class="sxs-lookup"><span data-stu-id="726cb-130">This command instructs PowerShell to:</span></span>
  
- <span data-ttu-id="726cb-131">Obtenha todas as informações sobre as contas de usuário (**Get-AzureADUser**) e envie-o para o próximo comando ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="726cb-131">Get all of the information on the user accounts (**Get-AzureADUser**) and send it to the next command (**|**).</span></span>
    
- <span data-ttu-id="726cb-132">Classifique a lista de nomes de entidade de segurança de usuário alfabeticamente (**classificar userPrincipalName**) e enviá-lo para o próximo comando ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="726cb-132">Sort the list of User Principal Names alphabetically (**Sort UserPrincipalName**) and send it to the next command (**|**).</span></span>
    
- <span data-ttu-id="726cb-133">Exibe apenas a propriedade nome principal do usuário para cada conta (**selecione userPrincipalName**).</span><span class="sxs-lookup"><span data-stu-id="726cb-133">Display just the User Principal Name property for each account (**Select UserPrincipalName**).</span></span>

- <span data-ttu-id="726cb-134">Exibir uma tela por vez (**mais**).</span><span class="sxs-lookup"><span data-stu-id="726cb-134">Display them one screen at a time (**More**).</span></span>
    
<span data-ttu-id="726cb-135">Este comando listará todas as suas contas.</span><span class="sxs-lookup"><span data-stu-id="726cb-135">This command will list all of your accounts.</span></span> <span data-ttu-id="726cb-136">Se você deseja exibir o nome principal de usuário para uma conta com base no seu nome de exibição (nome e sobrenome), preencha a variável de **$username** abaixo (removendo os \< and > caracteres) e execute os seguintes comandos:</span><span class="sxs-lookup"><span data-stu-id="726cb-136">If you want to display the User Principal Name for an account based on its display name (first and last name), fill in the **$userName** variable below (removing the \< and > characters), and then run the following commands:</span></span>
  
```powershell
$userName="<Display name>"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="726cb-137">Este exemplo exibe o nome principal do usuário para a conta de usuário com o nome de exibição de Carlos Lima.</span><span class="sxs-lookup"><span data-stu-id="726cb-137">This example displays the User Principal Name for the user account with the display name of Caleb Sills.</span></span>
  
```powershell
$userName="Caleb Sills"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="726cb-138">Usando uma variável de **$UPN** , você pode fazer alterações em contas individuais com base no seu nome de exibição.</span><span class="sxs-lookup"><span data-stu-id="726cb-138">By using a **$upn** variable, you can make changes to individual accounts based on their display name.</span></span> <span data-ttu-id="726cb-139">Aqui está um exemplo de como definir o local de uso do Belinda Newman para a França, mas especificando seu nome de exibição em vez do nome principal do usuário:</span><span class="sxs-lookup"><span data-stu-id="726cb-139">Here is an example of setting Belinda Newman's usage location to France, but specifying her display name rather than her User Principal Name:</span></span>
  
```powershell
$userName="Belinda Newman"
$upn=(Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
Set-AzureADUser -ObjectID $upn -UsageLocation "FR"
```

### <a name="change-properties-for-all-user-accounts"></a><span data-ttu-id="726cb-140">Alterar propriedades de todas as contas de usuário</span><span class="sxs-lookup"><span data-stu-id="726cb-140">Change properties for all user accounts</span></span>

<span data-ttu-id="726cb-141">Para alterar as propriedades de todos os usuários, você pode usar a combinação dos cmdlets **Get-AzureADUser** e **set-AzureADUser** .</span><span class="sxs-lookup"><span data-stu-id="726cb-141">To change properties for all users, you can use the combination of the **Get-AzureADUser** and **Set-AzureADUser** cmdlets.</span></span> <span data-ttu-id="726cb-142">O exemplo a seguir altera o local de uso de todos os usuários para a França:</span><span class="sxs-lookup"><span data-stu-id="726cb-142">The following example changes the usage location for all users to France:</span></span>
  
```powershell
Get-AzureADUser | Set-AzureADUser -UsageLocation "FR"
```

<span data-ttu-id="726cb-143">Este comando instrui o PowerShell para:</span><span class="sxs-lookup"><span data-stu-id="726cb-143">This command instructs PowerShell to:</span></span>
  
- <span data-ttu-id="726cb-144">Obtenha todas as informações sobre as contas de usuário (**Get-AzureADUser**) e envie-o para o próximo comando ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="726cb-144">Get all of the information on the user accounts (**Get-AzureADUser**) and send it to the next command (**|**).</span></span>
    
- <span data-ttu-id="726cb-145">Defina o local do usuário como França (**set-AzureADUser-UsageLocation "fr"**).</span><span class="sxs-lookup"><span data-stu-id="726cb-145">Set the user location to France (**Set-AzureADUser -UsageLocation "FR"**).</span></span>
    
### <a name="change-properties-for-a-specific-set-of-user-accounts"></a><span data-ttu-id="726cb-146">Alterar propriedades de um conjunto específico de contas de usuário</span><span class="sxs-lookup"><span data-stu-id="726cb-146">Change properties for a specific set of user accounts</span></span>

<span data-ttu-id="726cb-147">Para alterar as propriedades de um conjunto específico de contas de usuário, você pode usar a combinação dos cmdlets **Get-AzureADUser**, **Where**e **set-AzureADUser** .</span><span class="sxs-lookup"><span data-stu-id="726cb-147">To change properties for a specific set of user account, you can use the combination of the **Get-AzureADUser**, **Where**, and **Set-AzureADUser** cmdlets.</span></span> <span data-ttu-id="726cb-148">O exemplo a seguir altera o local de uso de todos os usuários no departamento de contabilidade para a França:</span><span class="sxs-lookup"><span data-stu-id="726cb-148">The following example changes the usage location for all the users in the Accounting department to France:</span></span>
  
```powershell
Get-AzureADUser | Where {$_.Department -eq "Accounting"} | Set-AzureADUser -UsageLocation "FR"
```

<span data-ttu-id="726cb-149">Este comando instrui o PowerShell para:</span><span class="sxs-lookup"><span data-stu-id="726cb-149">This command instructs PowerShell to:</span></span>
  
- <span data-ttu-id="726cb-150">Obtenha todas as informações sobre as contas de usuário (**Get-AzureADUser**) e envie-o para o próximo comando ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="726cb-150">Get all of the information on the user accounts (**Get-AzureADUser**) and send it to the next command (**|**).</span></span>
    
- <span data-ttu-id="726cb-151">Encontre todas as contas de usuário que têm a propriedade Department definida como "Accounting" (**onde {$ _. Department-EQ "Accounting"}**) e envie as informações resultantes para o próximo comando ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="726cb-151">Find all of the user accounts that have their Department property set to "Accounting" (**Where {$_.Department -eq "Accounting"}**) and send the resulting information to the next command (**|**).</span></span>
    
- <span data-ttu-id="726cb-152">Defina o local do usuário como França (**set-AzureADUser-UsageLocation "fr"**).</span><span class="sxs-lookup"><span data-stu-id="726cb-152">Set the user location to France (**Set-AzureADUser -UsageLocation "FR"**).</span></span>
    
## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="726cb-153">Use o Módulo Microsoft Azure Active Directory para Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="726cb-153">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="726cb-154">Para configurar propriedades de contas de usuário com o módulo Microsoft Azure Active Directory para Windows PowerShell, use o cmdlet **set-MsolUser** e especifique as propriedades a serem definidas ou alteradas.</span><span class="sxs-lookup"><span data-stu-id="726cb-154">To configure properties for user accounts with the Microsoft Azure Active Directory Module for Windows PowerShell, you use the **Set-MsolUser** cmdlet and specify the properties to set or change.</span></span> 

<span data-ttu-id="726cb-155">Primeiro, [Conecte-se ao seu locatário do Microsoft 365](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="726cb-155">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>
  
>[!Note]
><span data-ttu-id="726cb-156">O PowerShell Core não é compatível com o módulo do Microsoft Azure Active Directory para módulo e cmdlets do Windows PowerShell com **MSol** no nome.</span><span class="sxs-lookup"><span data-stu-id="726cb-156">PowerShell Core does not support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="726cb-157">Para continuar usando esses cmdlets, você deve executá-los a partir do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="726cb-157">To continue using these cmdlets, you must run them from Windows PowerShell.</span></span>
>

### <a name="change-properties-for-a-specific-user-account"></a><span data-ttu-id="726cb-158">Alterar as propriedades de uma conta de usuário específica</span><span class="sxs-lookup"><span data-stu-id="726cb-158">Change properties for a specific user account</span></span>

<span data-ttu-id="726cb-159">Para configurar as propriedades de uma conta de usuário específica, use o cmdlet [set-MsolUser](https://docs.microsoft.com/previous-versions/azure/dn194136(v=azure.100)) e especifique as propriedades a serem definidas ou alteradas.</span><span class="sxs-lookup"><span data-stu-id="726cb-159">To configure properties for a specific user account, you use the [Set-MsolUser](https://docs.microsoft.com/previous-versions/azure/dn194136(v=azure.100)) cmdlet and specify the properties to set or change.</span></span> 

<span data-ttu-id="726cb-160">Você identifica a conta com o parâmetro **-userPrincipalName** e define ou altera propriedades específicas com parâmetros adicionais.</span><span class="sxs-lookup"><span data-stu-id="726cb-160">You identify the account with the **-UserPrincipalName** parameter and set or change specific properties with additional parameters.</span></span> <span data-ttu-id="726cb-161">Veja a seguir uma lista dos parâmetros mais comuns.</span><span class="sxs-lookup"><span data-stu-id="726cb-161">Here is a list of the most common parameters.</span></span>
  
- <span data-ttu-id="726cb-162">-City " \<city name> "</span><span class="sxs-lookup"><span data-stu-id="726cb-162">-City "\<city name>"</span></span>
    
- <span data-ttu-id="726cb-163">-Country " \<country name> "</span><span class="sxs-lookup"><span data-stu-id="726cb-163">-Country "\<country name>"</span></span>
    
- <span data-ttu-id="726cb-164">-Department " \<department name> "</span><span class="sxs-lookup"><span data-stu-id="726cb-164">-Department "\<department name>"</span></span>
    
- <span data-ttu-id="726cb-165">-DisplayName " \<full user name> "</span><span class="sxs-lookup"><span data-stu-id="726cb-165">-DisplayName "\<full user name>"</span></span>
    
- <span data-ttu-id="726cb-166">– Fax " \<fax number> "</span><span class="sxs-lookup"><span data-stu-id="726cb-166">-Fax "\<fax number>"</span></span>
    
- <span data-ttu-id="726cb-167">-FirstName " \<user first name> "</span><span class="sxs-lookup"><span data-stu-id="726cb-167">-FirstName "\<user first name>"</span></span>
    
- <span data-ttu-id="726cb-168">-LastName " \<user last name> "</span><span class="sxs-lookup"><span data-stu-id="726cb-168">-LastName "\<user last name>"</span></span>
    
- <span data-ttu-id="726cb-169">-MobilePhone " \<mobile phone number> "</span><span class="sxs-lookup"><span data-stu-id="726cb-169">-MobilePhone "\<mobile phone number>"</span></span>
    
- <span data-ttu-id="726cb-170">-Office " \<office location> "</span><span class="sxs-lookup"><span data-stu-id="726cb-170">-Office "\<office location>"</span></span>
    
- <span data-ttu-id="726cb-171">-PhoneNumber " \<office phone number> "</span><span class="sxs-lookup"><span data-stu-id="726cb-171">-PhoneNumber "\<office phone number>"</span></span>
    
- <span data-ttu-id="726cb-172">-PostalCode " \<postal code> "</span><span class="sxs-lookup"><span data-stu-id="726cb-172">-PostalCode "\<postal code>"</span></span>
    
- <span data-ttu-id="726cb-173">-PreferredLanguage " \<language> "</span><span class="sxs-lookup"><span data-stu-id="726cb-173">-PreferredLanguage "\<language>"</span></span>
    
- <span data-ttu-id="726cb-174">-State " \<state name> "</span><span class="sxs-lookup"><span data-stu-id="726cb-174">-State "\<state name>"</span></span>
    
- <span data-ttu-id="726cb-175">-StreetAddress " \<street address> "</span><span class="sxs-lookup"><span data-stu-id="726cb-175">-StreetAddress "\<street address>"</span></span>
    
- <span data-ttu-id="726cb-176">-Title " \<title name> "</span><span class="sxs-lookup"><span data-stu-id="726cb-176">-Title "\<title name>"</span></span>
    
- <span data-ttu-id="726cb-177">-UsageLocation " \<2-character country or region code> "</span><span class="sxs-lookup"><span data-stu-id="726cb-177">-UsageLocation "\<2-character country or region code>"</span></span>
    
    <span data-ttu-id="726cb-178">Este é o código de país ou região ISO 3166-1 alfa-2 (a2) de duas letras.</span><span class="sxs-lookup"><span data-stu-id="726cb-178">This is the ISO 3166-1 alpha-2 (A2) two-letter country or region code.</span></span>
    
<span data-ttu-id="726cb-179">Consulte [set-MsolUser](https://docs.microsoft.com/previous-versions/azure/dn194136(v=azure.100)) para parâmetros adicionais.</span><span class="sxs-lookup"><span data-stu-id="726cb-179">See [Set-MsolUser](https://docs.microsoft.com/previous-versions/azure/dn194136(v=azure.100)) for additional parameters.</span></span>

<span data-ttu-id="726cb-180">Para ver os nomes principais de usuário de todos os seus usuários, execute o seguinte comando.</span><span class="sxs-lookup"><span data-stu-id="726cb-180">To see the User Principal Names of all your users, run the following command.</span></span>
  
```powershell
Get-MSolUser | Sort UserPrincipalName | Select UserPrincipalName | More
```

<span data-ttu-id="726cb-181">Este comando instrui o PowerShell para:</span><span class="sxs-lookup"><span data-stu-id="726cb-181">This command instructs PowerShell to:</span></span>
  
- <span data-ttu-id="726cb-182">Obtenha todas as informações sobre as contas de usuário (**Get-MsolUser**) e envie-o para o próximo comando ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="726cb-182">Get all of the information on the user accounts (**Get-MsolUser**) and send it to the next command (**|**).</span></span>
    
- <span data-ttu-id="726cb-183">Classifique a lista de nomes de entidade de segurança de usuário alfabeticamente (**classificar userPrincipalName**) e enviá-lo para o próximo comando ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="726cb-183">Sort the list of User Principal Names alphabetically (**Sort UserPrincipalName**) and send it to the next command (**|**).</span></span>
    
- <span data-ttu-id="726cb-184">Exibe apenas a propriedade nome principal do usuário para cada conta (**selecione userPrincipalName**).</span><span class="sxs-lookup"><span data-stu-id="726cb-184">Display just the User Principal Name property for each account (**Select UserPrincipalName**).</span></span>
    
- <span data-ttu-id="726cb-185">Exibir uma tela por vez (**mais**).</span><span class="sxs-lookup"><span data-stu-id="726cb-185">Display them one screen at a time (**More**).</span></span>
    
<span data-ttu-id="726cb-186">Este comando listará todas as suas contas.</span><span class="sxs-lookup"><span data-stu-id="726cb-186">This command will list all of your accounts.</span></span> <span data-ttu-id="726cb-187">Se você deseja exibir o nome principal de usuário para uma conta com base no seu nome de exibição (nome e sobrenome), preencha a variável de **$username** abaixo (removendo os \< and > caracteres) e execute os seguintes comandos:</span><span class="sxs-lookup"><span data-stu-id="726cb-187">If you want to display the User Principal Name for an account based on its display name (first and last name), fill in the **$userName** variable below (removing the \< and > characters), and then run the following commands:</span></span>
  
```powershell
$userName="<Display name>"
Write-Host (Get-MsolUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="726cb-188">Este exemplo exibe o nome principal do usuário chamado Carlos Lima.</span><span class="sxs-lookup"><span data-stu-id="726cb-188">This example displays the User Principal Name for the user named Caleb Sills.</span></span>
  
```powershell
$userName="Caleb Sills"
Write-Host (Get-MsolUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="726cb-189">Usando uma variável de **$UPN** , você pode fazer alterações em contas individuais com base no seu nome de exibição.</span><span class="sxs-lookup"><span data-stu-id="726cb-189">By using a **$upn** variable, you can make changes to individual accounts based on their display name.</span></span> <span data-ttu-id="726cb-190">Aqui está um exemplo de como definir o local de uso do Belinda Newman para a França, mas especificando seu nome de exibição em vez do nome principal do usuário:</span><span class="sxs-lookup"><span data-stu-id="726cb-190">Here is an example of setting Belinda Newman's usage location to France, but specifying her display name rather than her User Principal Name:</span></span>
  
```powershell
$userName="<display name>"
$upn=(Get-MsolUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
Set-MsolUser -UserPrincipalName $upn -UsageLocation "FR"
```

### <a name="change-properties-for-all-user-accounts"></a><span data-ttu-id="726cb-191">Alterar propriedades de todas as contas de usuário</span><span class="sxs-lookup"><span data-stu-id="726cb-191">Change properties for all user accounts</span></span>

<span data-ttu-id="726cb-192">Para alterar as propriedades de todos os usuários, você pode usar a combinação dos cmdlets **Get-MsolUser** e **set-MsolUser** .</span><span class="sxs-lookup"><span data-stu-id="726cb-192">To change properties for all users, you can use the combination of the **Get-MsolUser** and **Set-MsolUser** cmdlets.</span></span> <span data-ttu-id="726cb-193">O exemplo a seguir altera o local de uso de todos os usuários para a França:</span><span class="sxs-lookup"><span data-stu-id="726cb-193">The following example changes the usage location for all users to France:</span></span>
  
```powershell
Get-MsolUser | Set-MsolUser -UsageLocation "FR"
```

<span data-ttu-id="726cb-194">Este comando instrui o PowerShell para:</span><span class="sxs-lookup"><span data-stu-id="726cb-194">This command instructs PowerShell to:</span></span>
  
- <span data-ttu-id="726cb-195">Obtenha todas as informações sobre as contas de usuário (**Get-MsolUser**) e envie-o para o próximo comando ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="726cb-195">Get all of the information on the user accounts (**Get-MsolUser**) and send it to the next command (**|**).</span></span>
    
- <span data-ttu-id="726cb-196">Defina o local do usuário como França (**set-MsolUser-UsageLocation "fr"**).</span><span class="sxs-lookup"><span data-stu-id="726cb-196">Set the user location to France (**Set-MsolUser -UsageLocation "FR"**).</span></span>
    
### <a name="change-properties-for-a-specific-set-of-user-accounts"></a><span data-ttu-id="726cb-197">Alterar propriedades de um conjunto específico de contas de usuário</span><span class="sxs-lookup"><span data-stu-id="726cb-197">Change properties for a specific set of user accounts</span></span>

<span data-ttu-id="726cb-198">Para alterar as propriedades de um conjunto específico de contas de usuário, você pode usar a combinação dos cmdlets **Get-MsolUser**, **Where**e **set-MsolUser** .</span><span class="sxs-lookup"><span data-stu-id="726cb-198">To change properties for a specific set of user account, you can use the combination of the **Get-MsolUser**, **Where**, and **Set-MsolUser** cmdlets.</span></span> <span data-ttu-id="726cb-199">O exemplo a seguir altera o local de uso de todos os usuários no departamento de contabilidade para a França:</span><span class="sxs-lookup"><span data-stu-id="726cb-199">The following example changes the usage location for all the users in the Accounting department to France:</span></span>
  
```powershell
Get-MsolUser | Where {$_.Department -eq "Accounting"} | Set-MsolUser -UsageLocation "FR"
```

<span data-ttu-id="726cb-200">Este comando instrui o PowerShell para:</span><span class="sxs-lookup"><span data-stu-id="726cb-200">This command instructs PowerShell to:</span></span>
  
- <span data-ttu-id="726cb-201">Obtenha todas as informações sobre as contas de usuário (**Get-MsolUser**) e envie-o para o próximo comando ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="726cb-201">Get all of the information on the user accounts (**Get-MsolUser**) and send it to the next command (**|**).</span></span>
    
- <span data-ttu-id="726cb-202">Encontre todas as contas de usuário que têm a propriedade Department definida como "Accounting" (**onde {$ _. Department-EQ "Accounting"}**) e envie as informações resultantes para o próximo comando ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="726cb-202">Find all of the user accounts that have their Department property set to "Accounting" (**Where {$_.Department -eq "Accounting"}**) and send the resulting information to the next command (**|**).</span></span>
    
- <span data-ttu-id="726cb-203">Defina o local do usuário como França (**set-MsolUser-UsageLocation "fr"**).</span><span class="sxs-lookup"><span data-stu-id="726cb-203">Set the user location to France (**Set-MsolUser -UsageLocation "FR"**).</span></span>
    

## <a name="see-also"></a><span data-ttu-id="726cb-204">Confira também</span><span class="sxs-lookup"><span data-stu-id="726cb-204">See also</span></span>

[<span data-ttu-id="726cb-205">Gerenciar contas de usuário, licenças e grupos do Microsoft 365 com o PowerShell</span><span class="sxs-lookup"><span data-stu-id="726cb-205">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="726cb-206">Gerenciar o Microsoft 365 com o PowerShell</span><span class="sxs-lookup"><span data-stu-id="726cb-206">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="726cb-207">Introdução ao PowerShell para o Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="726cb-207">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
