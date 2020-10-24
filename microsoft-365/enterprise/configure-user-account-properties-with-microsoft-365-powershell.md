---
title: Configurar as propriedades da conta de usuário do Microsoft 365 com o PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
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
description: Use o PowerShell para Microsoft 365 para configurar propriedades de várias contas de usuário ou individuais em seu locatário do Microsoft 365.
ms.openlocfilehash: 830cede93a6c14db2dcc5626d41d0dd296b9ac29
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754323"
---
# <a name="configure-microsoft-365-user-account-properties-with-powershell"></a><span data-ttu-id="fe20f-103">Configurar as propriedades da conta de usuário do Microsoft 365 com o PowerShell</span><span class="sxs-lookup"><span data-stu-id="fe20f-103">Configure Microsoft 365 user account properties with PowerShell</span></span>

<span data-ttu-id="fe20f-104">*Este artigo se aplica tanto ao Microsoft 365 Enterprise quanto ao Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="fe20f-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="fe20f-105">Você pode usar o centro de administração do Microsoft 365 para configurar as propriedades das contas de usuário do seu locatário do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="fe20f-105">You can use the Microsoft 365 admin center to configure properties for the user accounts of your Microsoft 365 tenant.</span></span> <span data-ttu-id="fe20f-106">No PowerShell, você também pode fazer isso, além de outras coisas que você não pode fazer no centro de administração.</span><span class="sxs-lookup"><span data-stu-id="fe20f-106">In PowerShell, you can also do this, plus some other things you can't do in the admin center.</span></span>
  
## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="fe20f-107">Use o PowerShell do Azure Active Directory para o módulo do gráfico</span><span class="sxs-lookup"><span data-stu-id="fe20f-107">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="fe20f-108">Para configurar propriedades para contas de usuário no módulo do PowerShell do Azure Active Directory para Graph, use o cmdlet [**set-AzureADUser**](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser?view=azureadps-2.0) e especifique as propriedades a serem definidas ou alteradas.</span><span class="sxs-lookup"><span data-stu-id="fe20f-108">To configure properties for user accounts in the Azure Active Directory PowerShell for Graph module, use the [**Set-AzureADUser**](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser?view=azureadps-2.0) cmdlet and specify the properties to set or change.</span></span>

<span data-ttu-id="fe20f-109">Primeiro, [Conecte-se ao seu locatário do Microsoft 365](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span><span class="sxs-lookup"><span data-stu-id="fe20f-109">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
   
### <a name="change-properties-for-a-specific-user-account"></a><span data-ttu-id="fe20f-110">Alterar as propriedades de uma conta de usuário específica</span><span class="sxs-lookup"><span data-stu-id="fe20f-110">Change properties for a specific user account</span></span>

<span data-ttu-id="fe20f-111">Você identifica a conta com o parâmetro *-ObjectID* e define ou altera propriedades específicas usando parâmetros adicionais.</span><span class="sxs-lookup"><span data-stu-id="fe20f-111">You identify the account with the *-ObjectID* parameter and set or change specific properties by using additional parameters.</span></span> <span data-ttu-id="fe20f-112">Veja a seguir uma lista dos parâmetros mais comuns:</span><span class="sxs-lookup"><span data-stu-id="fe20f-112">Here's a list of the most common parameters:</span></span>
  
- <span data-ttu-id="fe20f-113">-Department " \<department name> "</span><span class="sxs-lookup"><span data-stu-id="fe20f-113">-Department "\<department name>"</span></span>
    
- <span data-ttu-id="fe20f-114">-DisplayName " \<full user name> "</span><span class="sxs-lookup"><span data-stu-id="fe20f-114">-DisplayName "\<full user name>"</span></span>
    
- <span data-ttu-id="fe20f-115">-FacsimilieTelephoneNumber " \<fax number> "</span><span class="sxs-lookup"><span data-stu-id="fe20f-115">-FacsimilieTelephoneNumber "\<fax number>"</span></span>
    
- <span data-ttu-id="fe20f-116">-Excertoname " \<user first name> "</span><span class="sxs-lookup"><span data-stu-id="fe20f-116">-GivenName "\<user first name>"</span></span>
    
- <span data-ttu-id="fe20f-117">-Sobrenome " \<user last name> "</span><span class="sxs-lookup"><span data-stu-id="fe20f-117">-Surname "\<user last name>"</span></span>
    
- <span data-ttu-id="fe20f-118">-Mobile " \<mobile phone number> "</span><span class="sxs-lookup"><span data-stu-id="fe20f-118">-Mobile "\<mobile phone number>"</span></span>
    
- <span data-ttu-id="fe20f-119">-JobTitle " \<job title> "</span><span class="sxs-lookup"><span data-stu-id="fe20f-119">-JobTitle "\<job title>"</span></span>
    
- <span data-ttu-id="fe20f-120">-PreferredLanguage " \<language> "</span><span class="sxs-lookup"><span data-stu-id="fe20f-120">-PreferredLanguage "\<language>"</span></span>
    
- <span data-ttu-id="fe20f-121">-StreetAddress " \<street address> "</span><span class="sxs-lookup"><span data-stu-id="fe20f-121">-StreetAddress "\<street address>"</span></span>
    
- <span data-ttu-id="fe20f-122">-City " \<city name> "</span><span class="sxs-lookup"><span data-stu-id="fe20f-122">-City "\<city name>"</span></span>
    
- <span data-ttu-id="fe20f-123">-State " \<state name> "</span><span class="sxs-lookup"><span data-stu-id="fe20f-123">-State "\<state name>"</span></span>
    
- <span data-ttu-id="fe20f-124">-PostalCode " \<postal code> "</span><span class="sxs-lookup"><span data-stu-id="fe20f-124">-PostalCode "\<postal code>"</span></span>
    
- <span data-ttu-id="fe20f-125">-Country " \<country name> "</span><span class="sxs-lookup"><span data-stu-id="fe20f-125">-Country "\<country name>"</span></span>
    
- <span data-ttu-id="fe20f-126">-TelephoneNumber " \<office phone number> "</span><span class="sxs-lookup"><span data-stu-id="fe20f-126">-TelephoneNumber "\<office phone number>"</span></span>
    
- <span data-ttu-id="fe20f-127">-UsageLocation " \<2-character country or region code> "</span><span class="sxs-lookup"><span data-stu-id="fe20f-127">-UsageLocation "\<2-character country or region code>"</span></span>
    
    <span data-ttu-id="fe20f-128">Este é o código de país ou região ISO 3166-1 alfa-2 (a2) de duas letras.</span><span class="sxs-lookup"><span data-stu-id="fe20f-128">This is the ISO 3166-1 alpha-2 (A2) two-letter country or region code.</span></span>
    
<span data-ttu-id="fe20f-129">Para parâmetros adicionais, consulte [set-AzureADUser](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser?view=azureadps-2.0) .</span><span class="sxs-lookup"><span data-stu-id="fe20f-129">For additional parameters, see [Set-AzureADUser](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser?view=azureadps-2.0) .</span></span>

>[!Note]
><span data-ttu-id="fe20f-130">Antes de poder atribuir licenças a uma conta de usuário, você deve atribuir um local de uso.</span><span class="sxs-lookup"><span data-stu-id="fe20f-130">Before you can assign licenses to a user account, you must assign a usage location.</span></span>
>

<span data-ttu-id="fe20f-131">Para exibir o nome principal do usuário para suas contas de usuário, execute o seguinte comando.</span><span class="sxs-lookup"><span data-stu-id="fe20f-131">To display the User Principal Name for your user accounts, run the following command.</span></span>
  
```powershell
Get-AzureADUser | Sort UserPrincipalName | Select UserPrincipalName | More
```

<span data-ttu-id="fe20f-132">Este comando instrui o PowerShell para:</span><span class="sxs-lookup"><span data-stu-id="fe20f-132">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="fe20f-133">Obtenha todas as informações sobre as contas de usuário (**Get-AzureADUser**) e envie-as para o próximo comando ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="fe20f-133">Get all the information on the user accounts (**Get-AzureADUser**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="fe20f-134">Classifique a lista de nomes de entidade de segurança de usuário alfabeticamente (**classificar userPrincipalName**) e enviá-lo para o próximo comando ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="fe20f-134">Sort the list of User Principal Names alphabetically (**Sort UserPrincipalName**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="fe20f-135">Exibe apenas a propriedade nome principal do usuário para cada conta (**selecione userPrincipalName**).</span><span class="sxs-lookup"><span data-stu-id="fe20f-135">Display just the User Principal Name property for each account (**Select UserPrincipalName**).</span></span>

1. <span data-ttu-id="fe20f-136">Exibir uma tela por vez (**mais**).</span><span class="sxs-lookup"><span data-stu-id="fe20f-136">Display them one screen at a time (**More**).</span></span>
    
<span data-ttu-id="fe20f-137">Para exibir o nome principal de usuário de uma conta com base no seu nome de exibição (nome e sobrenome), execute os seguintes comandos.</span><span class="sxs-lookup"><span data-stu-id="fe20f-137">To display the User Principal Name for an account based on its display name (first and last name), run the following commands.</span></span> <span data-ttu-id="fe20f-138">Preencha a variável *$username* e remova os \< and > caracteres:</span><span class="sxs-lookup"><span data-stu-id="fe20f-138">Fill in the *$userName* variable, and remove the \< and > characters:</span></span>
  
```powershell
$userName="<Display name>"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="fe20f-139">Este exemplo exibe o nome principal do usuário para a conta de usuário que tem o nome de exibição *Carlos Lima*.</span><span class="sxs-lookup"><span data-stu-id="fe20f-139">This example displays the User Principal Name for the user account that has the display name *Caleb Sills*.</span></span>
  
```powershell
$userName="Caleb Sills"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="fe20f-140">Usando uma variável de *$UPN* , você pode fazer alterações em contas individuais com base no seu nome de exibição.</span><span class="sxs-lookup"><span data-stu-id="fe20f-140">By using a *$upn* variable, you can make changes to individual accounts based on their display name.</span></span> <span data-ttu-id="fe20f-141">Veja um exemplo que define o local de uso de *Belinda Newman*como França.</span><span class="sxs-lookup"><span data-stu-id="fe20f-141">Here's an example that sets *Belinda Newman*'s usage location to France.</span></span> <span data-ttu-id="fe20f-142">Mas especifica seu nome de exibição em vez do nome principal do usuário:</span><span class="sxs-lookup"><span data-stu-id="fe20f-142">But it specifies her display name rather than her User Principal Name:</span></span>
  
```powershell
$userName="Belinda Newman"
$upn=(Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
Set-AzureADUser -ObjectID $upn -UsageLocation "FR"
```

### <a name="change-properties-for-all-user-accounts"></a><span data-ttu-id="fe20f-143">Alterar propriedades de todas as contas de usuário</span><span class="sxs-lookup"><span data-stu-id="fe20f-143">Change properties for all user accounts</span></span>

<span data-ttu-id="fe20f-144">Para alterar as propriedades de todos os usuários, você pode usar uma combinação dos cmdlets **Get-AzureADUser** e **set-AzureADUser** .</span><span class="sxs-lookup"><span data-stu-id="fe20f-144">To change properties for all users, you can use a combination of the **Get-AzureADUser** and **Set-AzureADUser** cmdlets.</span></span> <span data-ttu-id="fe20f-145">O exemplo a seguir altera o local de uso de todos os usuários para a *França*:</span><span class="sxs-lookup"><span data-stu-id="fe20f-145">The following example changes the usage location for all users to *France*:</span></span>
  
```powershell
Get-AzureADUser | Set-AzureADUser -UsageLocation "FR"
```

<span data-ttu-id="fe20f-146">Este comando instrui o PowerShell para:</span><span class="sxs-lookup"><span data-stu-id="fe20f-146">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="fe20f-147">Obtenha todas as informações sobre as contas de usuário (**Get-AzureADUser**) e envie-o para o próximo comando ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="fe20f-147">Get all of the information on the user accounts (**Get-AzureADUser**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="fe20f-148">Defina o local do usuário como França (**set-AzureADUser-UsageLocation "fr"**).</span><span class="sxs-lookup"><span data-stu-id="fe20f-148">Set the user location to France (**Set-AzureADUser -UsageLocation "FR"**).</span></span>
    
### <a name="change-properties-for-a-specific-set-of-user-accounts"></a><span data-ttu-id="fe20f-149">Alterar propriedades de um conjunto específico de contas de usuário</span><span class="sxs-lookup"><span data-stu-id="fe20f-149">Change properties for a specific set of user accounts</span></span>

<span data-ttu-id="fe20f-150">Para alterar as propriedades de um conjunto específico de contas de usuário, você pode usar uma combinação dos cmdlets **Get-AzureADUser**, **Where**e **set-AzureADUser** .</span><span class="sxs-lookup"><span data-stu-id="fe20f-150">To change properties for a specific set of user accounts, you can use a combination of the **Get-AzureADUser**, **Where**, and **Set-AzureADUser** cmdlets.</span></span> <span data-ttu-id="fe20f-151">O exemplo a seguir altera o local de uso de todos os usuários no departamento de contabilidade para a *França*:</span><span class="sxs-lookup"><span data-stu-id="fe20f-151">The following example changes the usage location for all the users in the Accounting department to *France*:</span></span>
  
```powershell
Get-AzureADUser | Where {$_.Department -eq "Accounting"} | Set-AzureADUser -UsageLocation "FR"
```

<span data-ttu-id="fe20f-152">Este comando instrui o PowerShell para:</span><span class="sxs-lookup"><span data-stu-id="fe20f-152">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="fe20f-153">Obtenha todas as informações sobre as contas de usuário (**Get-AzureADUser**) e envie-as para o próximo comando ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="fe20f-153">Get all the information on the user accounts (**Get-AzureADUser**), and send it to the next command (**|**).</span></span>
    
1.  <span data-ttu-id="fe20f-154">Encontre todas as contas de usuário que têm a propriedade *Department* definida como "contabilidade" (**onde {$ _. Department-EQ "Accounting"}**) e envie as informações resultantes para o próximo comando ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="fe20f-154">Find all the user accounts that have their *Department* property set to "Accounting" (**Where {$_.Department -eq "Accounting"}**), and send the resulting information to the next command (**|**).</span></span>
    
1. <span data-ttu-id="fe20f-155">Defina o local do usuário como França (**set-AzureADUser-UsageLocation "fr"**).</span><span class="sxs-lookup"><span data-stu-id="fe20f-155">Set the user location to France (**Set-AzureADUser -UsageLocation "FR"**).</span></span>
    
## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="fe20f-156">Use o Módulo Microsoft Azure Active Directory para Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fe20f-156">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="fe20f-157">Para configurar propriedades de contas de usuário com o módulo Microsoft Azure Active Directory para Windows PowerShell, use o cmdlet **set-MsolUser** e especifique as propriedades a serem definidas ou alteradas.</span><span class="sxs-lookup"><span data-stu-id="fe20f-157">To configure properties for user accounts with the Microsoft Azure Active Directory Module for Windows PowerShell, use the **Set-MsolUser** cmdlet and specify the properties to set or change.</span></span>

<span data-ttu-id="fe20f-158">Primeiro, [Conecte-se ao seu locatário do Microsoft 365](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="fe20f-158">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>
  
>[!Note]
><span data-ttu-id="fe20f-159">O PowerShell Core não é compatível com o módulo do Microsoft Azure Active Directory para o módulo e cmdlets do Windows PowerShell com o *MSol* em seu nome.</span><span class="sxs-lookup"><span data-stu-id="fe20f-159">PowerShell Core doesn't support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with *Msol* in their name.</span></span> <span data-ttu-id="fe20f-160">Execute estes cmdlets do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fe20f-160">Run these cmdlets from Windows PowerShell.</span></span>
>

### <a name="change-properties-for-a-specific-user-account"></a><span data-ttu-id="fe20f-161">Alterar as propriedades de uma conta de usuário específica</span><span class="sxs-lookup"><span data-stu-id="fe20f-161">Change properties for a specific user account</span></span>

<span data-ttu-id="fe20f-162">Para configurar as propriedades de uma conta de usuário específica, use o cmdlet [**set-MsolUser**](https://docs.microsoft.com/previous-versions/azure/dn194136(v=azure.100)) e especifique as propriedades a serem definidas ou alteradas.</span><span class="sxs-lookup"><span data-stu-id="fe20f-162">To configure properties for a specific user account, use the [**Set-MsolUser**](https://docs.microsoft.com/previous-versions/azure/dn194136(v=azure.100)) cmdlet and specify the properties to set or change.</span></span> 

<span data-ttu-id="fe20f-163">Você identifica a conta com o parâmetro *-userPrincipalName* e define ou altera propriedades específicas usando parâmetros adicionais.</span><span class="sxs-lookup"><span data-stu-id="fe20f-163">You identify the account with the *-UserPrincipalName* parameter and set or change specific properties by using additional parameters.</span></span> <span data-ttu-id="fe20f-164">Veja a seguir uma lista dos parâmetros mais comuns.</span><span class="sxs-lookup"><span data-stu-id="fe20f-164">Here's a list of the most common parameters.</span></span>
  
- <span data-ttu-id="fe20f-165">-City " \<city name> "</span><span class="sxs-lookup"><span data-stu-id="fe20f-165">-City "\<city name>"</span></span>
    
- <span data-ttu-id="fe20f-166">-Country " \<country name> "</span><span class="sxs-lookup"><span data-stu-id="fe20f-166">-Country "\<country name>"</span></span>
    
- <span data-ttu-id="fe20f-167">-Department " \<department name> "</span><span class="sxs-lookup"><span data-stu-id="fe20f-167">-Department "\<department name>"</span></span>
    
- <span data-ttu-id="fe20f-168">-DisplayName " \<full user name> "</span><span class="sxs-lookup"><span data-stu-id="fe20f-168">-DisplayName "\<full user name>"</span></span>
    
- <span data-ttu-id="fe20f-169">– Fax " \<fax number> "</span><span class="sxs-lookup"><span data-stu-id="fe20f-169">-Fax "\<fax number>"</span></span>
    
- <span data-ttu-id="fe20f-170">-FirstName " \<user first name> "</span><span class="sxs-lookup"><span data-stu-id="fe20f-170">-FirstName "\<user first name>"</span></span>
    
- <span data-ttu-id="fe20f-171">-LastName " \<user last name> "</span><span class="sxs-lookup"><span data-stu-id="fe20f-171">-LastName "\<user last name>"</span></span>
    
- <span data-ttu-id="fe20f-172">-MobilePhone " \<mobile phone number> "</span><span class="sxs-lookup"><span data-stu-id="fe20f-172">-MobilePhone "\<mobile phone number>"</span></span>
    
- <span data-ttu-id="fe20f-173">-Office " \<office location> "</span><span class="sxs-lookup"><span data-stu-id="fe20f-173">-Office "\<office location>"</span></span>
    
- <span data-ttu-id="fe20f-174">-PhoneNumber " \<office phone number> "</span><span class="sxs-lookup"><span data-stu-id="fe20f-174">-PhoneNumber "\<office phone number>"</span></span>
    
- <span data-ttu-id="fe20f-175">-PostalCode " \<postal code> "</span><span class="sxs-lookup"><span data-stu-id="fe20f-175">-PostalCode "\<postal code>"</span></span>
    
- <span data-ttu-id="fe20f-176">-PreferredLanguage " \<language> "</span><span class="sxs-lookup"><span data-stu-id="fe20f-176">-PreferredLanguage "\<language>"</span></span>
    
- <span data-ttu-id="fe20f-177">-State " \<state name> "</span><span class="sxs-lookup"><span data-stu-id="fe20f-177">-State "\<state name>"</span></span>
    
- <span data-ttu-id="fe20f-178">-StreetAddress " \<street address> "</span><span class="sxs-lookup"><span data-stu-id="fe20f-178">-StreetAddress "\<street address>"</span></span>
    
- <span data-ttu-id="fe20f-179">-Title " \<title name> "</span><span class="sxs-lookup"><span data-stu-id="fe20f-179">-Title "\<title name>"</span></span>
    
- <span data-ttu-id="fe20f-180">-UsageLocation " \<2-character country or region code> "</span><span class="sxs-lookup"><span data-stu-id="fe20f-180">-UsageLocation "\<2-character country or region code>"</span></span>
    
    <span data-ttu-id="fe20f-181">Este é o código de país ou região ISO 3166-1 alfa-2 (a2) de duas letras.</span><span class="sxs-lookup"><span data-stu-id="fe20f-181">This is the ISO 3166-1 alpha-2 (A2) two-letter country or region code.</span></span>
    
<span data-ttu-id="fe20f-182">Para parâmetros adicionais, consulte [set-MsolUser](https://docs.microsoft.com/previous-versions/azure/dn194136(v=azure.100)).</span><span class="sxs-lookup"><span data-stu-id="fe20f-182">For additional parameters, see [Set-MsolUser](https://docs.microsoft.com/previous-versions/azure/dn194136(v=azure.100)).</span></span>

<span data-ttu-id="fe20f-183">Para ver os nomes principais de usuário de todos os seus usuários, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="fe20f-183">To see the User Principal Names of all your users, run the following command:</span></span>
  
```powershell
Get-MSolUser | Sort UserPrincipalName | Select UserPrincipalName | More
```

<span data-ttu-id="fe20f-184">Este comando instrui o PowerShell para:</span><span class="sxs-lookup"><span data-stu-id="fe20f-184">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="fe20f-185">Obtenha todas as informações para as contas de usuário (**Get-MsolUser**) e envie-as para o próximo comando ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="fe20f-185">Get all of information for the user accounts (**Get-MsolUser**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="fe20f-186">Classifique a lista de nomes de entidade de segurança de usuário alfabeticamente (**classificar userPrincipalName**) e enviá-lo para o próximo comando ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="fe20f-186">Sort the list of User Principal Names alphabetically (**Sort UserPrincipalName**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="fe20f-187">Exibe apenas a propriedade nome principal do usuário para cada conta (**selecione userPrincipalName**).</span><span class="sxs-lookup"><span data-stu-id="fe20f-187">Display just the User Principal Name property for each account (**Select UserPrincipalName**).</span></span>
    
1. <span data-ttu-id="fe20f-188">Exibir uma tela por vez (**mais**).</span><span class="sxs-lookup"><span data-stu-id="fe20f-188">Display them one screen at a time (**More**).</span></span>
    
<span data-ttu-id="fe20f-189">Para exibir o nome principal de usuário de uma conta com base no seu nome de exibição (nome e sobrenome), execute os seguintes comandos.</span><span class="sxs-lookup"><span data-stu-id="fe20f-189">To display the User Principal Name for an account based on its display name (first and last name), run the following commands.</span></span> <span data-ttu-id="fe20f-190">Preencha a variável *$username* e remova os \< and > caracteres.</span><span class="sxs-lookup"><span data-stu-id="fe20f-190">Fill in the *$userName* variable, and remove the \< and > characters.</span></span>
  
```powershell
$userName="<Display name>"
Write-Host (Get-MsolUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="fe20f-191">Este exemplo exibe o nome principal do usuário chamado Carlos Lima:</span><span class="sxs-lookup"><span data-stu-id="fe20f-191">This example displays the User Principal Name for the user named Caleb Sills:</span></span>
  
```powershell
$userName="Caleb Sills"
Write-Host (Get-MsolUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="fe20f-192">Usando uma variável de *$UPN* , você pode fazer alterações em contas individuais com base no seu nome de exibição.</span><span class="sxs-lookup"><span data-stu-id="fe20f-192">By using a *$upn* variable, you can make changes to individual accounts based on their display name.</span></span> <span data-ttu-id="fe20f-193">Veja um exemplo que define o local de uso do *Belinda Newman*para a *França*, mas especifica seu nome de exibição em vez do nome principal do usuário:</span><span class="sxs-lookup"><span data-stu-id="fe20f-193">Here's an example that sets *Belinda Newman*'s usage location to *France*, but specifies her display name rather than her User Principal Name:</span></span>
  
```powershell
$userName="<display name>"
$upn=(Get-MsolUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
Set-MsolUser -UserPrincipalName $upn -UsageLocation "FR"
```

### <a name="change-properties-for-all-user-accounts"></a><span data-ttu-id="fe20f-194">Alterar propriedades de todas as contas de usuário</span><span class="sxs-lookup"><span data-stu-id="fe20f-194">Change properties for all user accounts</span></span>

<span data-ttu-id="fe20f-195">Para alterar as propriedades de todos os usuários, use uma combinação dos cmdlets **Get-MsolUser** e **set-MsolUser** .</span><span class="sxs-lookup"><span data-stu-id="fe20f-195">To change properties for all users,  use a combination of the **Get-MsolUser** and **Set-MsolUser** cmdlets.</span></span> <span data-ttu-id="fe20f-196">O exemplo a seguir altera o local de uso de todos os usuários para a *França*:</span><span class="sxs-lookup"><span data-stu-id="fe20f-196">The following example changes the usage location for all users to *France*:</span></span>
  
```powershell
Get-MsolUser | Set-MsolUser -UsageLocation "FR"
```

<span data-ttu-id="fe20f-197">Este comando instrui o PowerShell para:</span><span class="sxs-lookup"><span data-stu-id="fe20f-197">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="fe20f-198">Obtenha todas as informações para as contas de usuário (**Get-MsolUser**) e enviá-las ao próximo comando ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="fe20f-198">Get all the information for the user accounts (**Get-MsolUser**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="fe20f-199">Defina o local do usuário como França (**set-MsolUser-UsageLocation "fr"**).</span><span class="sxs-lookup"><span data-stu-id="fe20f-199">Set the user location to France (**Set-MsolUser -UsageLocation "FR"**).</span></span>
    
### <a name="change-properties-for-a-specific-set-of-user-accounts"></a><span data-ttu-id="fe20f-200">Alterar propriedades de um conjunto específico de contas de usuário</span><span class="sxs-lookup"><span data-stu-id="fe20f-200">Change properties for a specific set of user accounts</span></span>

<span data-ttu-id="fe20f-201">Para alterar as propriedades de um conjunto específico de contas de usuário, você pode usar uma combinação dos cmdlets **Get-MsolUser**, **Where**e **set-MsolUser** .</span><span class="sxs-lookup"><span data-stu-id="fe20f-201">To change properties for a specific set of user accounts, you can use a combination of the **Get-MsolUser**, **Where**, and **Set-MsolUser** cmdlets.</span></span> <span data-ttu-id="fe20f-202">O exemplo a seguir altera o local de uso de todos os usuários no departamento de contabilidade para a *França*:</span><span class="sxs-lookup"><span data-stu-id="fe20f-202">The following example changes the usage location for all the users in the Accounting department to *France*:</span></span>
  
```powershell
Get-MsolUser | Where {$_.Department -eq "Accounting"} | Set-MsolUser -UsageLocation "FR"
```

<span data-ttu-id="fe20f-203">Este comando instrui o PowerShell para:</span><span class="sxs-lookup"><span data-stu-id="fe20f-203">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="fe20f-204">Obtenha todas as informações para as contas de usuário (**Get-MsolUser**) e enviá-las ao próximo comando ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="fe20f-204">Get all the information for the user accounts (**Get-MsolUser**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="fe20f-205">Encontre todas as contas de usuário que têm a propriedade *Department* definida como "contabilidade" (**onde {$ _. Department-EQ "Accounting"}**) e envie as informações resultantes para o próximo comando ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="fe20f-205">Find all user accounts that have their *Department* property set to "Accounting" (**Where {$_.Department -eq "Accounting"}**) and send the resulting information to the next command (**|**).</span></span>
    
1. <span data-ttu-id="fe20f-206">Defina o local do usuário como França (**set-MsolUser-UsageLocation "fr"**).</span><span class="sxs-lookup"><span data-stu-id="fe20f-206">Set the user location to France (**Set-MsolUser -UsageLocation "FR"**).</span></span>

## <a name="see-also"></a><span data-ttu-id="fe20f-207">Confira também</span><span class="sxs-lookup"><span data-stu-id="fe20f-207">See also</span></span>

[<span data-ttu-id="fe20f-208">Gerenciar contas de usuário, licenças e grupos do Microsoft 365 com o PowerShell</span><span class="sxs-lookup"><span data-stu-id="fe20f-208">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="fe20f-209">Gerenciar o Microsoft 365 com o PowerShell</span><span class="sxs-lookup"><span data-stu-id="fe20f-209">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="fe20f-210">Introdução ao Windows PowerShell para o Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="fe20f-210">Get started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
