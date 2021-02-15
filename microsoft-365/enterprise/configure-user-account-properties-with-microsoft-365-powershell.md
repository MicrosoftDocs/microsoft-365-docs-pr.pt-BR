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
description: Use o PowerShell para o Microsoft 365 para configurar propriedades de contas de usuário individuais ou múltiplas em seu locatário do Microsoft 365.
ms.openlocfilehash: 830cede93a6c14db2dcc5626d41d0dd296b9ac29
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754323"
---
# <a name="configure-microsoft-365-user-account-properties-with-powershell"></a><span data-ttu-id="da51a-103">Configurar as propriedades da conta de usuário do Microsoft 365 com o PowerShell</span><span class="sxs-lookup"><span data-stu-id="da51a-103">Configure Microsoft 365 user account properties with PowerShell</span></span>

<span data-ttu-id="da51a-104">*Esse artigo se aplica ao Microsoft 365 Enterprise e ao Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="da51a-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="da51a-105">Você pode usar o Centro de administração do Microsoft 365 para configurar propriedades para as contas de usuário do seu locatário do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="da51a-105">You can use the Microsoft 365 admin center to configure properties for the user accounts of your Microsoft 365 tenant.</span></span> <span data-ttu-id="da51a-106">No PowerShell, você também pode fazer isso, além de outras coisas que não pode fazer no centro de administração.</span><span class="sxs-lookup"><span data-stu-id="da51a-106">In PowerShell, you can also do this, plus some other things you can't do in the admin center.</span></span>
  
## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="da51a-107">Use o PowerShell do Azure Active Directory para o módulo do gráfico</span><span class="sxs-lookup"><span data-stu-id="da51a-107">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="da51a-108">Para configurar propriedades para contas de usuário no PowerShell do Azure Active Directory para o módulo do Graph, use o cmdlet [**Set-AzureADUser**](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser?view=azureadps-2.0) e especifique as propriedades a definir ou alterar.</span><span class="sxs-lookup"><span data-stu-id="da51a-108">To configure properties for user accounts in the Azure Active Directory PowerShell for Graph module, use the [**Set-AzureADUser**](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser?view=azureadps-2.0) cmdlet and specify the properties to set or change.</span></span>

<span data-ttu-id="da51a-109">Primeiro, [conecte-se ao locatário do Microsoft 365.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)</span><span class="sxs-lookup"><span data-stu-id="da51a-109">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
   
### <a name="change-properties-for-a-specific-user-account"></a><span data-ttu-id="da51a-110">Alterar propriedades de uma conta de usuário específica</span><span class="sxs-lookup"><span data-stu-id="da51a-110">Change properties for a specific user account</span></span>

<span data-ttu-id="da51a-111">Você pode identificar a conta com o *parâmetro -ObjectID* e definir ou alterar propriedades específicas usando parâmetros adicionais.</span><span class="sxs-lookup"><span data-stu-id="da51a-111">You identify the account with the *-ObjectID* parameter and set or change specific properties by using additional parameters.</span></span> <span data-ttu-id="da51a-112">Aqui está uma lista dos parâmetros mais comuns:</span><span class="sxs-lookup"><span data-stu-id="da51a-112">Here's a list of the most common parameters:</span></span>
  
- <span data-ttu-id="da51a-113">-Department \<department name> "</span><span class="sxs-lookup"><span data-stu-id="da51a-113">-Department "\<department name>"</span></span>
    
- <span data-ttu-id="da51a-114">-DisplayName \<full user name> "</span><span class="sxs-lookup"><span data-stu-id="da51a-114">-DisplayName "\<full user name>"</span></span>
    
- <span data-ttu-id="da51a-115">-QuesimilieTelephoneNumber \<fax number> "</span><span class="sxs-lookup"><span data-stu-id="da51a-115">-FacsimilieTelephoneNumber "\<fax number>"</span></span>
    
- <span data-ttu-id="da51a-116">-GivenName \<user first name> "</span><span class="sxs-lookup"><span data-stu-id="da51a-116">-GivenName "\<user first name>"</span></span>
    
- <span data-ttu-id="da51a-117">-Surname \<user last name> "</span><span class="sxs-lookup"><span data-stu-id="da51a-117">-Surname "\<user last name>"</span></span>
    
- <span data-ttu-id="da51a-118">-Mobile \<mobile phone number> "</span><span class="sxs-lookup"><span data-stu-id="da51a-118">-Mobile "\<mobile phone number>"</span></span>
    
- <span data-ttu-id="da51a-119">-JobTitle \<job title> "</span><span class="sxs-lookup"><span data-stu-id="da51a-119">-JobTitle "\<job title>"</span></span>
    
- <span data-ttu-id="da51a-120">-PreferredLanguage \<language> "</span><span class="sxs-lookup"><span data-stu-id="da51a-120">-PreferredLanguage "\<language>"</span></span>
    
- <span data-ttu-id="da51a-121">-StreetAddress \<street address> "</span><span class="sxs-lookup"><span data-stu-id="da51a-121">-StreetAddress "\<street address>"</span></span>
    
- <span data-ttu-id="da51a-122">-City \<city name> "</span><span class="sxs-lookup"><span data-stu-id="da51a-122">-City "\<city name>"</span></span>
    
- <span data-ttu-id="da51a-123">-State \<state name> "</span><span class="sxs-lookup"><span data-stu-id="da51a-123">-State "\<state name>"</span></span>
    
- <span data-ttu-id="da51a-124">-PostalCode \<postal code> "</span><span class="sxs-lookup"><span data-stu-id="da51a-124">-PostalCode "\<postal code>"</span></span>
    
- <span data-ttu-id="da51a-125">-Country \<country name> "</span><span class="sxs-lookup"><span data-stu-id="da51a-125">-Country "\<country name>"</span></span>
    
- <span data-ttu-id="da51a-126">-TelephoneNumber \<office phone number> "</span><span class="sxs-lookup"><span data-stu-id="da51a-126">-TelephoneNumber "\<office phone number>"</span></span>
    
- <span data-ttu-id="da51a-127">-UsageLocation \<2-character country or region code> "</span><span class="sxs-lookup"><span data-stu-id="da51a-127">-UsageLocation "\<2-character country or region code>"</span></span>
    
    <span data-ttu-id="da51a-128">Este é o código iso 3166-1 alpha-2 (A2) de duas letras do país ou região.</span><span class="sxs-lookup"><span data-stu-id="da51a-128">This is the ISO 3166-1 alpha-2 (A2) two-letter country or region code.</span></span>
    
<span data-ttu-id="da51a-129">Para obter parâmetros adicionais, [consulte Set-AzureADUser](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser?view=azureadps-2.0) .</span><span class="sxs-lookup"><span data-stu-id="da51a-129">For additional parameters, see [Set-AzureADUser](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser?view=azureadps-2.0) .</span></span>

>[!Note]
><span data-ttu-id="da51a-130">Antes de atribuir licenças a uma conta de usuário, você deve atribuir um local de uso.</span><span class="sxs-lookup"><span data-stu-id="da51a-130">Before you can assign licenses to a user account, you must assign a usage location.</span></span>
>

<span data-ttu-id="da51a-131">Para exibir o Nome Principal do Usuário para suas contas de usuário, execute o seguinte comando.</span><span class="sxs-lookup"><span data-stu-id="da51a-131">To display the User Principal Name for your user accounts, run the following command.</span></span>
  
```powershell
Get-AzureADUser | Sort UserPrincipalName | Select UserPrincipalName | More
```

<span data-ttu-id="da51a-132">Este comando instrui o PowerShell a:</span><span class="sxs-lookup"><span data-stu-id="da51a-132">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="da51a-133">Obter todas as informações sobre as contas de usuário (**Get-AzureADUser**) e enviá-lo para o próximo comando ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="da51a-133">Get all the information on the user accounts (**Get-AzureADUser**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="da51a-134">Classificar a lista de nomes de usuários principais em ordem alfabética (**Classificar UserPrincipalName**) e enviá-la para o próximo comando ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="da51a-134">Sort the list of User Principal Names alphabetically (**Sort UserPrincipalName**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="da51a-135">Exibe apenas a propriedade Nome Principal do Usuário para cada conta (**Selecione UserPrincipalName**).</span><span class="sxs-lookup"><span data-stu-id="da51a-135">Display just the User Principal Name property for each account (**Select UserPrincipalName**).</span></span>

1. <span data-ttu-id="da51a-136">Exibir uma tela por vez (**Mais**).</span><span class="sxs-lookup"><span data-stu-id="da51a-136">Display them one screen at a time (**More**).</span></span>
    
<span data-ttu-id="da51a-137">Para exibir o Nome Principal do Usuário para uma conta com base em seu nome de exibição (nome e sobrenome), execute os seguintes comandos.</span><span class="sxs-lookup"><span data-stu-id="da51a-137">To display the User Principal Name for an account based on its display name (first and last name), run the following commands.</span></span> <span data-ttu-id="da51a-138">Preencha a *variável $userName* e remova os \< and > caracteres:</span><span class="sxs-lookup"><span data-stu-id="da51a-138">Fill in the *$userName* variable, and remove the \< and > characters:</span></span>
  
```powershell
$userName="<Display name>"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="da51a-139">Este exemplo exibe o Nome Principal do Usuário para a conta de usuário que tem o nome de exibição *Paulo Alsão.*</span><span class="sxs-lookup"><span data-stu-id="da51a-139">This example displays the User Principal Name for the user account that has the display name *Caleb Sills*.</span></span>
  
```powershell
$userName="Caleb Sills"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="da51a-140">Usando uma *variável $upn,* você pode fazer alterações em contas individuais com base no nome de exibição.</span><span class="sxs-lookup"><span data-stu-id="da51a-140">By using a *$upn* variable, you can make changes to individual accounts based on their display name.</span></span> <span data-ttu-id="da51a-141">Veja um exemplo que define o local de uso de *Belinda Cindy* como França.</span><span class="sxs-lookup"><span data-stu-id="da51a-141">Here's an example that sets *Belinda Newman*'s usage location to France.</span></span> <span data-ttu-id="da51a-142">Mas especifica seu nome de exibição em vez de seu Nome Principal de Usuário:</span><span class="sxs-lookup"><span data-stu-id="da51a-142">But it specifies her display name rather than her User Principal Name:</span></span>
  
```powershell
$userName="Belinda Newman"
$upn=(Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
Set-AzureADUser -ObjectID $upn -UsageLocation "FR"
```

### <a name="change-properties-for-all-user-accounts"></a><span data-ttu-id="da51a-143">Alterar propriedades de todas as contas de usuário</span><span class="sxs-lookup"><span data-stu-id="da51a-143">Change properties for all user accounts</span></span>

<span data-ttu-id="da51a-144">Para alterar as propriedades de todos os usuários, você pode usar uma combinação dos cmdlets **Get-AzureADUser** e **Set-AzureADUser.**</span><span class="sxs-lookup"><span data-stu-id="da51a-144">To change properties for all users, you can use a combination of the **Get-AzureADUser** and **Set-AzureADUser** cmdlets.</span></span> <span data-ttu-id="da51a-145">O exemplo a seguir altera o local de uso de todos os usuários para a *França:*</span><span class="sxs-lookup"><span data-stu-id="da51a-145">The following example changes the usage location for all users to *France*:</span></span>
  
```powershell
Get-AzureADUser | Set-AzureADUser -UsageLocation "FR"
```

<span data-ttu-id="da51a-146">Este comando instrui o PowerShell a:</span><span class="sxs-lookup"><span data-stu-id="da51a-146">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="da51a-147">Obter todas as informações sobre as contas de usuário (**Get-AzureADUser**) e enviá-lo para o próximo comando ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="da51a-147">Get all of the information on the user accounts (**Get-AzureADUser**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="da51a-148">Definir o local do usuário como França (**Set-AzureADUser -UsageLocation "FR"**).</span><span class="sxs-lookup"><span data-stu-id="da51a-148">Set the user location to France (**Set-AzureADUser -UsageLocation "FR"**).</span></span>
    
### <a name="change-properties-for-a-specific-set-of-user-accounts"></a><span data-ttu-id="da51a-149">Alterar propriedades de um conjunto específico de contas de usuário</span><span class="sxs-lookup"><span data-stu-id="da51a-149">Change properties for a specific set of user accounts</span></span>

<span data-ttu-id="da51a-150">Para alterar as propriedades de um conjunto específico de contas de usuário, você pode usar uma combinação dos cmdlets **Get-AzureADUser**, **Where** e **Set-AzureADUser.**</span><span class="sxs-lookup"><span data-stu-id="da51a-150">To change properties for a specific set of user accounts, you can use a combination of the **Get-AzureADUser**, **Where**, and **Set-AzureADUser** cmdlets.</span></span> <span data-ttu-id="da51a-151">O exemplo a seguir altera o local de uso de todos os usuários do departamento de Contabilidade para a *França:*</span><span class="sxs-lookup"><span data-stu-id="da51a-151">The following example changes the usage location for all the users in the Accounting department to *France*:</span></span>
  
```powershell
Get-AzureADUser | Where {$_.Department -eq "Accounting"} | Set-AzureADUser -UsageLocation "FR"
```

<span data-ttu-id="da51a-152">Este comando instrui o PowerShell a:</span><span class="sxs-lookup"><span data-stu-id="da51a-152">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="da51a-153">Obter todas as informações sobre as contas de usuário (**Get-AzureADUser**) e enviá-lo para o próximo comando ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="da51a-153">Get all the information on the user accounts (**Get-AzureADUser**), and send it to the next command (**|**).</span></span>
    
1.  <span data-ttu-id="da51a-154">Encontre todas as contas de usuário que tenham *a propriedade Departamento* definida como "Contabilidade" ( Onde **{$_. Department -eq "Accounting"}**) e envie as informações resultantes para o próximo comando ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="da51a-154">Find all the user accounts that have their *Department* property set to "Accounting" (**Where {$_.Department -eq "Accounting"}**), and send the resulting information to the next command (**|**).</span></span>
    
1. <span data-ttu-id="da51a-155">Definir o local do usuário como França (**Set-AzureADUser -UsageLocation "FR"**).</span><span class="sxs-lookup"><span data-stu-id="da51a-155">Set the user location to France (**Set-AzureADUser -UsageLocation "FR"**).</span></span>
    
## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="da51a-156">Use o Módulo Microsoft Azure Active Directory para Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="da51a-156">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="da51a-157">Para configurar propriedades para contas de usuário com o Módulo Microsoft Azure Active Directory para Windows PowerShell, use o cmdlet **Set-MsolUser** e especifique as propriedades a definir ou alterar.</span><span class="sxs-lookup"><span data-stu-id="da51a-157">To configure properties for user accounts with the Microsoft Azure Active Directory Module for Windows PowerShell, use the **Set-MsolUser** cmdlet and specify the properties to set or change.</span></span>

<span data-ttu-id="da51a-158">Primeiro, [conecte-se ao locatário do Microsoft 365.](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)</span><span class="sxs-lookup"><span data-stu-id="da51a-158">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>
  
>[!Note]
><span data-ttu-id="da51a-159">O PowerShell Core não oferece suporte ao Módulo Microsoft Azure Active Directory para Windows PowerShell para o módulo do Windows PowerShell e cmdlets com *Msol* em seus nomes.</span><span class="sxs-lookup"><span data-stu-id="da51a-159">PowerShell Core doesn't support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with *Msol* in their name.</span></span> <span data-ttu-id="da51a-160">Execute esses cmdlets do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="da51a-160">Run these cmdlets from Windows PowerShell.</span></span>
>

### <a name="change-properties-for-a-specific-user-account"></a><span data-ttu-id="da51a-161">Alterar propriedades de uma conta de usuário específica</span><span class="sxs-lookup"><span data-stu-id="da51a-161">Change properties for a specific user account</span></span>

<span data-ttu-id="da51a-162">Para configurar propriedades para uma conta de usuário específica, use o cmdlet [**Set-MsolUser**](https://docs.microsoft.com/previous-versions/azure/dn194136(v=azure.100)) e especifique as propriedades a definir ou alterar.</span><span class="sxs-lookup"><span data-stu-id="da51a-162">To configure properties for a specific user account, use the [**Set-MsolUser**](https://docs.microsoft.com/previous-versions/azure/dn194136(v=azure.100)) cmdlet and specify the properties to set or change.</span></span> 

<span data-ttu-id="da51a-163">Você pode identificar a conta com o *parâmetro -UserPrincipalName* e definir ou alterar propriedades específicas usando parâmetros adicionais.</span><span class="sxs-lookup"><span data-stu-id="da51a-163">You identify the account with the *-UserPrincipalName* parameter and set or change specific properties by using additional parameters.</span></span> <span data-ttu-id="da51a-164">Aqui está uma lista dos parâmetros mais comuns.</span><span class="sxs-lookup"><span data-stu-id="da51a-164">Here's a list of the most common parameters.</span></span>
  
- <span data-ttu-id="da51a-165">-City \<city name> "</span><span class="sxs-lookup"><span data-stu-id="da51a-165">-City "\<city name>"</span></span>
    
- <span data-ttu-id="da51a-166">-Country \<country name> "</span><span class="sxs-lookup"><span data-stu-id="da51a-166">-Country "\<country name>"</span></span>
    
- <span data-ttu-id="da51a-167">-Department \<department name> "</span><span class="sxs-lookup"><span data-stu-id="da51a-167">-Department "\<department name>"</span></span>
    
- <span data-ttu-id="da51a-168">-DisplayName \<full user name> "</span><span class="sxs-lookup"><span data-stu-id="da51a-168">-DisplayName "\<full user name>"</span></span>
    
- <span data-ttu-id="da51a-169">-Fax \<fax number> "</span><span class="sxs-lookup"><span data-stu-id="da51a-169">-Fax "\<fax number>"</span></span>
    
- <span data-ttu-id="da51a-170">-FirstName \<user first name> "</span><span class="sxs-lookup"><span data-stu-id="da51a-170">-FirstName "\<user first name>"</span></span>
    
- <span data-ttu-id="da51a-171">-LastName \<user last name> "</span><span class="sxs-lookup"><span data-stu-id="da51a-171">-LastName "\<user last name>"</span></span>
    
- <span data-ttu-id="da51a-172">-MobilePhone \<mobile phone number> "</span><span class="sxs-lookup"><span data-stu-id="da51a-172">-MobilePhone "\<mobile phone number>"</span></span>
    
- <span data-ttu-id="da51a-173">-Office \<office location> "</span><span class="sxs-lookup"><span data-stu-id="da51a-173">-Office "\<office location>"</span></span>
    
- <span data-ttu-id="da51a-174">-PhoneNumber \<office phone number> "</span><span class="sxs-lookup"><span data-stu-id="da51a-174">-PhoneNumber "\<office phone number>"</span></span>
    
- <span data-ttu-id="da51a-175">-PostalCode \<postal code> "</span><span class="sxs-lookup"><span data-stu-id="da51a-175">-PostalCode "\<postal code>"</span></span>
    
- <span data-ttu-id="da51a-176">-PreferredLanguage \<language> "</span><span class="sxs-lookup"><span data-stu-id="da51a-176">-PreferredLanguage "\<language>"</span></span>
    
- <span data-ttu-id="da51a-177">-State \<state name> "</span><span class="sxs-lookup"><span data-stu-id="da51a-177">-State "\<state name>"</span></span>
    
- <span data-ttu-id="da51a-178">-StreetAddress \<street address> "</span><span class="sxs-lookup"><span data-stu-id="da51a-178">-StreetAddress "\<street address>"</span></span>
    
- <span data-ttu-id="da51a-179">-Title \<title name> "</span><span class="sxs-lookup"><span data-stu-id="da51a-179">-Title "\<title name>"</span></span>
    
- <span data-ttu-id="da51a-180">-UsageLocation \<2-character country or region code> "</span><span class="sxs-lookup"><span data-stu-id="da51a-180">-UsageLocation "\<2-character country or region code>"</span></span>
    
    <span data-ttu-id="da51a-181">Este é o código iso 3166-1 alpha-2 (A2) de duas letras do país ou região.</span><span class="sxs-lookup"><span data-stu-id="da51a-181">This is the ISO 3166-1 alpha-2 (A2) two-letter country or region code.</span></span>
    
<span data-ttu-id="da51a-182">Para obter parâmetros adicionais, [consulte Set-MsolUser](https://docs.microsoft.com/previous-versions/azure/dn194136(v=azure.100)).</span><span class="sxs-lookup"><span data-stu-id="da51a-182">For additional parameters, see [Set-MsolUser](https://docs.microsoft.com/previous-versions/azure/dn194136(v=azure.100)).</span></span>

<span data-ttu-id="da51a-183">Para ver os Nomes De Usuário Principais de todos os seus usuários, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="da51a-183">To see the User Principal Names of all your users, run the following command:</span></span>
  
```powershell
Get-MSolUser | Sort UserPrincipalName | Select UserPrincipalName | More
```

<span data-ttu-id="da51a-184">Este comando instrui o PowerShell a:</span><span class="sxs-lookup"><span data-stu-id="da51a-184">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="da51a-185">Obter todas as informações das contas de usuário (**Get-MsolUser**) e enviá-lo para o próximo comando ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="da51a-185">Get all of information for the user accounts (**Get-MsolUser**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="da51a-186">Classificar a lista de nomes de usuários principais em ordem alfabética (**Classificar UserPrincipalName**) e enviá-la para o próximo comando ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="da51a-186">Sort the list of User Principal Names alphabetically (**Sort UserPrincipalName**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="da51a-187">Exibe apenas a propriedade Nome Principal do Usuário para cada conta (**Selecione UserPrincipalName**).</span><span class="sxs-lookup"><span data-stu-id="da51a-187">Display just the User Principal Name property for each account (**Select UserPrincipalName**).</span></span>
    
1. <span data-ttu-id="da51a-188">Exibir uma tela por vez (**Mais**).</span><span class="sxs-lookup"><span data-stu-id="da51a-188">Display them one screen at a time (**More**).</span></span>
    
<span data-ttu-id="da51a-189">Para exibir o Nome Principal do Usuário para uma conta com base em seu nome de exibição (nome e sobrenome), execute os seguintes comandos.</span><span class="sxs-lookup"><span data-stu-id="da51a-189">To display the User Principal Name for an account based on its display name (first and last name), run the following commands.</span></span> <span data-ttu-id="da51a-190">Preencha a *variável $userName* e remova os \< and > caracteres.</span><span class="sxs-lookup"><span data-stu-id="da51a-190">Fill in the *$userName* variable, and remove the \< and > characters.</span></span>
  
```powershell
$userName="<Display name>"
Write-Host (Get-MsolUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="da51a-191">Este exemplo exibe o Nome Principal do Usuário para o usuário chamado Sills:</span><span class="sxs-lookup"><span data-stu-id="da51a-191">This example displays the User Principal Name for the user named Caleb Sills:</span></span>
  
```powershell
$userName="Caleb Sills"
Write-Host (Get-MsolUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="da51a-192">Usando uma *variável $upn,* você pode fazer alterações em contas individuais com base no nome de exibição.</span><span class="sxs-lookup"><span data-stu-id="da51a-192">By using a *$upn* variable, you can make changes to individual accounts based on their display name.</span></span> <span data-ttu-id="da51a-193">Veja um exemplo que define o local de uso de *Belinda Cindy* como *França,* mas especifica seu nome de exibição em vez de seu Nome Principal de Usuário:</span><span class="sxs-lookup"><span data-stu-id="da51a-193">Here's an example that sets *Belinda Newman*'s usage location to *France*, but specifies her display name rather than her User Principal Name:</span></span>
  
```powershell
$userName="<display name>"
$upn=(Get-MsolUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
Set-MsolUser -UserPrincipalName $upn -UsageLocation "FR"
```

### <a name="change-properties-for-all-user-accounts"></a><span data-ttu-id="da51a-194">Alterar propriedades de todas as contas de usuário</span><span class="sxs-lookup"><span data-stu-id="da51a-194">Change properties for all user accounts</span></span>

<span data-ttu-id="da51a-195">Para alterar as propriedades de todos os usuários, use uma combinação dos cmdlets **Get-MsolUser** e **Set-MsolUser.**</span><span class="sxs-lookup"><span data-stu-id="da51a-195">To change properties for all users,  use a combination of the **Get-MsolUser** and **Set-MsolUser** cmdlets.</span></span> <span data-ttu-id="da51a-196">O exemplo a seguir altera o local de uso de todos os usuários para a *França:*</span><span class="sxs-lookup"><span data-stu-id="da51a-196">The following example changes the usage location for all users to *France*:</span></span>
  
```powershell
Get-MsolUser | Set-MsolUser -UsageLocation "FR"
```

<span data-ttu-id="da51a-197">Este comando instrui o PowerShell a:</span><span class="sxs-lookup"><span data-stu-id="da51a-197">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="da51a-198">Obter todas as informações das contas de usuário (**Get-MsolUser**) e enviá-lo para o próximo comando ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="da51a-198">Get all the information for the user accounts (**Get-MsolUser**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="da51a-199">Definir o local do usuário como França (**Set-MsolUser -UsageLocation "FR"**).</span><span class="sxs-lookup"><span data-stu-id="da51a-199">Set the user location to France (**Set-MsolUser -UsageLocation "FR"**).</span></span>
    
### <a name="change-properties-for-a-specific-set-of-user-accounts"></a><span data-ttu-id="da51a-200">Alterar propriedades de um conjunto específico de contas de usuário</span><span class="sxs-lookup"><span data-stu-id="da51a-200">Change properties for a specific set of user accounts</span></span>

<span data-ttu-id="da51a-201">Para alterar as propriedades de um conjunto específico de contas de usuário, você pode usar uma combinação dos cmdlets **Get-MsolUser**, **Where** e **Set-MsolUser.**</span><span class="sxs-lookup"><span data-stu-id="da51a-201">To change properties for a specific set of user accounts, you can use a combination of the **Get-MsolUser**, **Where**, and **Set-MsolUser** cmdlets.</span></span> <span data-ttu-id="da51a-202">O exemplo a seguir altera o local de uso de todos os usuários do departamento de Contabilidade para a *França:*</span><span class="sxs-lookup"><span data-stu-id="da51a-202">The following example changes the usage location for all the users in the Accounting department to *France*:</span></span>
  
```powershell
Get-MsolUser | Where {$_.Department -eq "Accounting"} | Set-MsolUser -UsageLocation "FR"
```

<span data-ttu-id="da51a-203">Este comando instrui o PowerShell a:</span><span class="sxs-lookup"><span data-stu-id="da51a-203">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="da51a-204">Obter todas as informações das contas de usuário (**Get-MsolUser**) e enviá-lo para o próximo comando ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="da51a-204">Get all the information for the user accounts (**Get-MsolUser**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="da51a-205">Encontre todas as contas de usuário que tenham *a propriedade Departamento* definida como "Contabilidade" ( Onde **{$_. Department -eq "Accounting"}**) e envie as informações resultantes para o próximo comando ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="da51a-205">Find all user accounts that have their *Department* property set to "Accounting" (**Where {$_.Department -eq "Accounting"}**) and send the resulting information to the next command (**|**).</span></span>
    
1. <span data-ttu-id="da51a-206">Definir o local do usuário como França (**Set-MsolUser -UsageLocation "FR"**).</span><span class="sxs-lookup"><span data-stu-id="da51a-206">Set the user location to France (**Set-MsolUser -UsageLocation "FR"**).</span></span>

## <a name="see-also"></a><span data-ttu-id="da51a-207">Confira também</span><span class="sxs-lookup"><span data-stu-id="da51a-207">See also</span></span>

[<span data-ttu-id="da51a-208">Gerenciar contas de usuário, licenças e grupos do Microsoft 365 com o PowerShell</span><span class="sxs-lookup"><span data-stu-id="da51a-208">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="da51a-209">Gerenciar o Microsoft 365 com o PowerShell</span><span class="sxs-lookup"><span data-stu-id="da51a-209">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="da51a-210">Introdução ao Windows PowerShell para o Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="da51a-210">Get started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
