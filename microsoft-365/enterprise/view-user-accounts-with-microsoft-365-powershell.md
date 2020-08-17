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
description: Saiba como exibir, listar ou exibir suas contas de usuário do Microsoft 365 de diferentes maneiras com o PowerShell.
ms.openlocfilehash: ea631d12a95ca813ebf9da3286e36d724d51a2f7
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46695423"
---
# <a name="view-microsoft-365-user-accounts-with-powershell"></a><span data-ttu-id="5ee2a-103">Exibir contas de usuário do Microsoft 365 com o PowerShell</span><span class="sxs-lookup"><span data-stu-id="5ee2a-103">View Microsoft 365 user accounts with PowerShell</span></span>

<span data-ttu-id="5ee2a-104">*Esse artigo se aplica ao Microsoft 365 Enterprise e ao Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="5ee2a-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="5ee2a-105">Embora você possa usar o centro de administração do Microsoft 365 para exibir as contas do seu locatário do Microsoft 365, você também pode usar o PowerShell para o Microsoft 365 e realizar algumas coisas que o centro de administração não pode.</span><span class="sxs-lookup"><span data-stu-id="5ee2a-105">Although you can use the Microsoft 365 admin center to view the accounts for your Microsoft 365 tenant, you can also use PowerShell for Microsoft 365 and do some things that the admin center cannot.</span></span>
  
## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="5ee2a-106">Use o PowerShell do Azure Active Directory para o módulo do gráfico</span><span class="sxs-lookup"><span data-stu-id="5ee2a-106">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="5ee2a-107">Primeiro, [Conecte-se ao seu locatário do Microsoft 365](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span><span class="sxs-lookup"><span data-stu-id="5ee2a-107">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
  
### <a name="view-all-accounts"></a><span data-ttu-id="5ee2a-108">Exibir todas as contas</span><span class="sxs-lookup"><span data-stu-id="5ee2a-108">View all accounts</span></span>

<span data-ttu-id="5ee2a-109">Para exibir a lista completa de contas de usuário, execute este comando:</span><span class="sxs-lookup"><span data-stu-id="5ee2a-109">To display the full list of user accounts, run this command:</span></span>
  
```powershell
Get-AzureADUser
```

<span data-ttu-id="5ee2a-110">Você deve ver informações semelhantes a estas:</span><span class="sxs-lookup"><span data-stu-id="5ee2a-110">You should see information similar to this:</span></span>
  
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

### <a name="view-a-specific-account"></a><span data-ttu-id="5ee2a-111">Exibir uma conta específica</span><span class="sxs-lookup"><span data-stu-id="5ee2a-111">View a specific account</span></span>

<span data-ttu-id="5ee2a-112">Para exibir uma conta de usuário específica, preencha o nome da conta de logon da conta de usuário, também conhecida como nome UPN, remova os caracteres "<" e ">" e execute este comando:</span><span class="sxs-lookup"><span data-stu-id="5ee2a-112">To display a specific user account, fill in the sign-in account name of the user account, also known as the user principal name (UPN), remove the "<" and ">" characters, and run this command:</span></span>
  
```powershell
Get-AzureADUser -ObjectID <sign-in name of the user account>
```

<span data-ttu-id="5ee2a-113">Veja um exemplo:</span><span class="sxs-lookup"><span data-stu-id="5ee2a-113">Here is an example:</span></span>
  
```powershell
Get-AzureADUser -ObjectID BelindaN@litwareinc.onmicosoft.com
```

### <a name="view-additional-property-values-for-a-specific-account"></a><span data-ttu-id="5ee2a-114">Exibir valores de propriedade adicionais para uma conta específica</span><span class="sxs-lookup"><span data-stu-id="5ee2a-114">View additional property values for a specific account</span></span>

<span data-ttu-id="5ee2a-115">Por padrão, o cmdlet **Get-AzureADUser** exibe apenas as propriedades ObjectID, DisplayName e userPrincipalName de accounts.</span><span class="sxs-lookup"><span data-stu-id="5ee2a-115">By default, the **Get-AzureADUser** cmdlet only displays the ObjectID, DisplayName, and UserPrincipalName properties of accounts.</span></span>

<span data-ttu-id="5ee2a-116">Para ser mais seletivo sobre a lista de propriedades a serem exibidas, você pode usar o cmdlet **Select** em combinação com o cmdlet **Get-AzureADUser** .</span><span class="sxs-lookup"><span data-stu-id="5ee2a-116">To be more selective about the list of properties to display, you can use the **Select** cmdlet in combination with the **Get-AzureADUser** cmdlet.</span></span> <span data-ttu-id="5ee2a-117">Para combinar os dois cmdlets, usamos o caractere "pipe" "|", que informa ao Azure Active Directory PowerShell para Graph para obter os resultados de um comando e enviá-lo para o próximo comando.</span><span class="sxs-lookup"><span data-stu-id="5ee2a-117">To combine the two cmdlets, we use the "pipe" character "|", which tells Azure Active Directory PowerShell for Graph to take the results of one command and send it to the next command.</span></span> <span data-ttu-id="5ee2a-118">Veja a seguir um exemplo de comando que exibe o DisplayName, o departamento e o UsageLocation para cada conta de usuário:</span><span class="sxs-lookup"><span data-stu-id="5ee2a-118">Here is an example command that displays the DisplayName, Department, and UsageLocation for every user account:</span></span>
  
```powershell
Get-AzureADUser | Select DisplayName,Department,UsageLocation
```

<span data-ttu-id="5ee2a-119">Este comando instrui o PowerShell para:</span><span class="sxs-lookup"><span data-stu-id="5ee2a-119">This command instructs PowerShell to:</span></span>
  
- <span data-ttu-id="5ee2a-120">Obtenha todas as informações sobre as contas de usuário ( **Get-AzureADUser** ) e envie-o para o próximo comando ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="5ee2a-120">Get all of the information on the user accounts ( **Get-AzureADUser** ) and send it to the next command ( **|** ).</span></span>
    
- <span data-ttu-id="5ee2a-121">Exibir apenas o nome da conta de usuário, o departamento e o local de uso ( **selecione DisplayName, Department, UsageLocation** ).</span><span class="sxs-lookup"><span data-stu-id="5ee2a-121">Display only the user account name, department, and usage location ( **Select DisplayName, Department, UsageLocation** ).</span></span>
  
<span data-ttu-id="5ee2a-122">Para ver todas as propriedades de contas de usuário, use o cmdlet **Select** e o caractere curinga (\*) para exibi-los para uma conta de usuário específica.</span><span class="sxs-lookup"><span data-stu-id="5ee2a-122">To see all of the properties for user accounts, use the **Select** cmdlet and the wildcard character (\*) to display them all for a specific user account.</span></span> <span data-ttu-id="5ee2a-123">Veja um exemplo:</span><span class="sxs-lookup"><span data-stu-id="5ee2a-123">Here is an example:</span></span>
  
```powershell
Get-AzureADUser -ObjectID BelindaN@litwareinc.onmicosoft.com | Select *
```

<span data-ttu-id="5ee2a-124">Como outro exemplo, você pode verificar o status habilitado de uma conta de usuário específica com o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="5ee2a-124">As another example, you can check the enabled status of a specific user account with the following command:</span></span>
  
```powershell
Get-AzureADUser -ObjectID <sign-in name of the user account> | Select DisplayName,UserPrincipalName,AccountEnabled
```

### <a name="view-some-accounts-based-on-a-common-property"></a><span data-ttu-id="5ee2a-125">Exibir algumas contas com base em uma propriedade comum</span><span class="sxs-lookup"><span data-stu-id="5ee2a-125">View some accounts based on a common property</span></span>

<span data-ttu-id="5ee2a-126">Para ser mais seletivo sobre a lista de contas a serem exibidas, você pode usar o cmdlet **Where** em combinação com o cmdlet **Get-AzureADUser** .</span><span class="sxs-lookup"><span data-stu-id="5ee2a-126">To be more selective about the list of accounts to display, you can use the **Where** cmdlet in combination with the **Get-AzureADUser** cmdlet.</span></span> <span data-ttu-id="5ee2a-127">Para combinar os dois cmdlets, usamos o caractere "pipe" "|", que informa ao Azure Active Directory PowerShell para Graph para obter os resultados de um comando e enviá-lo para o próximo comando.</span><span class="sxs-lookup"><span data-stu-id="5ee2a-127">To combine the two cmdlets, we use the "pipe" character "|", which tells Azure Active Directory PowerShell for Graph to take the results of one command and send it to the next command.</span></span> <span data-ttu-id="5ee2a-128">Veja a seguir um exemplo de comando que exibe apenas as contas de usuário que têm um local de uso não especificado:</span><span class="sxs-lookup"><span data-stu-id="5ee2a-128">Here is an example command that displays only those user accounts that have an unspecified usage location:</span></span>
  
```powershell
Get-AzureADUser | Where {$_.UsageLocation -eq $Null}
```

<span data-ttu-id="5ee2a-129">Este comando instrui o Azure Active Directory PowerShell para Graph para:</span><span class="sxs-lookup"><span data-stu-id="5ee2a-129">This command instructs Azure Active Directory PowerShell for Graph to:</span></span>
  
- <span data-ttu-id="5ee2a-130">Obtenha todas as informações sobre as contas de usuário ( **Get-AzureADUser** ) e envie-o para o próximo comando ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="5ee2a-130">Get all of the information on the user accounts ( **Get-AzureADUser** ) and send it to the next command ( **|** ).</span></span>
    
- <span data-ttu-id="5ee2a-131">Encontre todas as contas de usuário que têm um local de uso não especificado ( **onde {$ \_ . UsageLocation-EQ $Null}** ).</span><span class="sxs-lookup"><span data-stu-id="5ee2a-131">Find all of the user accounts that have an unspecified usage location ( **Where {$\_.UsageLocation -eq $Null}** ).</span></span> <span data-ttu-id="5ee2a-132">Dentro das chaves, o comando instrui o PowerShell a localizar apenas o conjunto de contas no qual a propriedade da conta de usuário do UsageLocation ( \*\* $ \_ . UsageLocation\*\* ) não é especificado ( **-EQ $NULL** ).</span><span class="sxs-lookup"><span data-stu-id="5ee2a-132">Inside the braces, the command instructs PowerShell to only find the set of accounts in which the UsageLocation user account property ( **$\_.UsageLocation** ) is not specified ( **-eq $Null** ).</span></span>
    
<span data-ttu-id="5ee2a-133">A propriedade **UsageLocation** é apenas uma das muitas propriedades associadas a uma conta de usuário.</span><span class="sxs-lookup"><span data-stu-id="5ee2a-133">The **UsageLocation** property is only one of many properties associated with a user account.</span></span> <span data-ttu-id="5ee2a-134">Para ver todas as propriedades de contas de usuário, use o cmdlet **Select** e o caractere curinga (\*) para exibi-los para uma conta de usuário específica.</span><span class="sxs-lookup"><span data-stu-id="5ee2a-134">To see all of the properties for user accounts, use the **Select** cmdlet and the wildcard character (\*) to display them all for a specific user account.</span></span> <span data-ttu-id="5ee2a-135">Veja um exemplo:</span><span class="sxs-lookup"><span data-stu-id="5ee2a-135">Here is an example:</span></span>
  
```powershell
Get-AzureADUser -ObjectID BelindaN@litwareinc.onmicosoft.com | Select *
```

<span data-ttu-id="5ee2a-136">Por exemplo, na lista, **City** é o nome de uma propriedade de conta de usuário.</span><span class="sxs-lookup"><span data-stu-id="5ee2a-136">For example, from this list, **City** is the name of a user account property.</span></span> <span data-ttu-id="5ee2a-137">Isso significa que você pode usar o seguinte comando para listar todas as contas de usuário para usuários em Londres:</span><span class="sxs-lookup"><span data-stu-id="5ee2a-137">This means you can use the following command to list all of the user accounts for users living in London:</span></span>
  
```powershell
Get-AzureADUser | Where {$_.City -eq "London"}
```

> [!TIP]
>  <span data-ttu-id="5ee2a-138">A sintaxe do cmdlet **Where** mostrado nesses exemplos é **onde {$ \_ .**</span><span class="sxs-lookup"><span data-stu-id="5ee2a-138">The syntax for the **Where** cmdlet shown in these examples is **Where {$\_.**</span></span> <span data-ttu-id="5ee2a-139">[nome da propriedade da conta de usuário] [operador de comparação] valor **}**. > [operador de comparação] é **-EQ** para igual a, **-ne** para não igual a, **-lt** para menor que, **-gt** para maior que e outros.</span><span class="sxs-lookup"><span data-stu-id="5ee2a-139">[user account property name] [comparison operator] [value] **}**.>  [comparison operator] is **-eq** for equals, **-ne** for not equals, **-lt** for less than, **-gt** for greater than, and others.</span></span>  <span data-ttu-id="5ee2a-140">[value] normalmente é uma cadeia de caracteres (uma sequência de letras, números e outros caracteres), um valor numérico ou **$NULL** para> não especificado Confira [onde](https://docs.microsoft.com/powershell/module/Microsoft.PowerShell.Core/Where?view=powershell-5.1) obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="5ee2a-140">[value] is typically a string (a sequence of letters, numbers, and other characters), a numerical value, or **$Null** for unspecified>  See [Where](https://docs.microsoft.com/powershell/module/Microsoft.PowerShell.Core/Where?view=powershell-5.1) for more information.</span></span>
  

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="5ee2a-141">Use o Módulo Microsoft Azure Active Directory para Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5ee2a-141">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="5ee2a-142">Primeiro, [Conecte-se ao seu locatário do Microsoft 365](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="5ee2a-142">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

### <a name="view-all-accounts"></a><span data-ttu-id="5ee2a-143">Exibir todas as contas</span><span class="sxs-lookup"><span data-stu-id="5ee2a-143">View all accounts</span></span>

<span data-ttu-id="5ee2a-144">Para exibir a lista completa de contas de usuário, execute este comando:</span><span class="sxs-lookup"><span data-stu-id="5ee2a-144">To display the full list of user accounts, run this command:</span></span>
  
```powershell
Get-MsolUser
```

>[!Note]
><span data-ttu-id="5ee2a-145">O PowerShell Core não é compatível com o módulo do Microsoft Azure Active Directory para módulo e cmdlets do Windows PowerShell com **MSol** no nome.</span><span class="sxs-lookup"><span data-stu-id="5ee2a-145">PowerShell Core does not support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="5ee2a-146">Para continuar usando esses cmdlets, você deve executá-los a partir do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5ee2a-146">To continue using these cmdlets, you must run them from Windows PowerShell.</span></span>
>

<span data-ttu-id="5ee2a-147">Você deve ver informações semelhantes a estas:</span><span class="sxs-lookup"><span data-stu-id="5ee2a-147">You should see information similar to this:</span></span>
  
```powershell
UserPrincipalName                     DisplayName           isLicensed
-----------------                     -----------           ----------
BonnieK@litwareinc.onmicrosoft.com    Bonnie Kearney        True
FabriceC@litwareinc.onmicrosoft.com   Fabrice Canel         True
BrianJ@litwareinc.onmicrosoft.com     Brian Johnson         False 
AnneWlitwareinc.onmicrosoft.com       Anne Wallace          True
ScottW@litwareinc.onmicrosoft.com     Scott Wallace         False
```

<span data-ttu-id="5ee2a-148">O cmdlet **Get-MsolUser** também tem um conjunto de parâmetros para filtrar o conjunto de contas de usuário exibidas.</span><span class="sxs-lookup"><span data-stu-id="5ee2a-148">The **Get-MsolUser** cmdlet also has a set of parameters to filter the set of user accounts displayed.</span></span> <span data-ttu-id="5ee2a-149">Por exemplo, para a lista de usuários não licenciados (usuários que foram adicionados ao Microsoft 365, mas que ainda não foram licenciados para usar qualquer um dos serviços), execute este comando.</span><span class="sxs-lookup"><span data-stu-id="5ee2a-149">For example, for the list of unlicensed users (users who've been added to Microsoft 365 but haven't yet been licensed to use any of the services), run this command.</span></span>
  
```powershell
Get-MsolUser -UnlicensedUsersOnly
```

<span data-ttu-id="5ee2a-150">Você deve ver informações semelhantes a estas:</span><span class="sxs-lookup"><span data-stu-id="5ee2a-150">You should see information similar to this:</span></span>
  
```powershell
UserPrincipalName                     DisplayName           isLicensed
-----------------                     -----------           ----------
BrianJ@litwareinc.onmicrosoft.com     Brian Johnson         False
ScottW@litwareinc.onmicrosoft.com     Scott Wallace         False
```

<span data-ttu-id="5ee2a-151">Para obter mais informações sobre parâmetros adicionais para filtrar a exibição do conjunto de contas de usuário exibidas, consulte [Get-MsolUser](https://docs.microsoft.com/previous-versions/azure/dn194133(v=azure.100)).</span><span class="sxs-lookup"><span data-stu-id="5ee2a-151">For more information about additional parameters to filter the display the set of user accounts displayed, see [Get-MsolUser](https://docs.microsoft.com/previous-versions/azure/dn194133(v=azure.100)).</span></span>
  
### <a name="view-a-specific-account"></a><span data-ttu-id="5ee2a-152">Exibir uma conta específica</span><span class="sxs-lookup"><span data-stu-id="5ee2a-152">View a specific account</span></span>

<span data-ttu-id="5ee2a-153">Para exibir uma conta de usuário específica, preencha o nome de entrada da conta de usuário da conta de usuário, também conhecida como nome de usuário principal (UPN), remova os caracteres "<" e ">" e execute este comando:</span><span class="sxs-lookup"><span data-stu-id="5ee2a-153">To display a specific user account, fill in the sign-in name of the user account of the user account, also known as the user principal name (UPN), remove the "<" and ">" characters, and run this command:</span></span>
  
```powershell
Get-MsolUser -UserPrincipalName <sign-in name of the user account>
```

### <a name="view-some-accounts-based-on-a-common-property"></a><span data-ttu-id="5ee2a-154">Exibir algumas contas com base em uma propriedade comum</span><span class="sxs-lookup"><span data-stu-id="5ee2a-154">View some accounts based on a common property</span></span>

<span data-ttu-id="5ee2a-155">Para ser mais seletivo sobre a lista de contas a serem exibidas, você pode usar o cmdlet **Where** em combinação com o cmdlet **Get-MsolUser** .</span><span class="sxs-lookup"><span data-stu-id="5ee2a-155">To be more selective about the list of accounts to display, you can use the **Where** cmdlet in combination with the **Get-MsolUser** cmdlet.</span></span> <span data-ttu-id="5ee2a-156">Para combinar os dois cmdlets, usamos o caractere "pipe" "|", que informa ao PowerShell para obter os resultados de um comando e enviá-lo para o próximo comando.</span><span class="sxs-lookup"><span data-stu-id="5ee2a-156">To combine the two cmdlets, we use the "pipe" character "|", which tells PowerShell to take the results of one command and send it to the next command.</span></span> <span data-ttu-id="5ee2a-157">Veja a seguir um exemplo de comando que exibe apenas as contas de usuário que têm um local de uso não especificado:</span><span class="sxs-lookup"><span data-stu-id="5ee2a-157">Here is an example command that displays only those user accounts that have an unspecified usage location:</span></span>
  
```powershell
Get-MsolUser | Where {$_.UsageLocation -eq $Null}
```

<span data-ttu-id="5ee2a-158">Este comando instrui o PowerShell para:</span><span class="sxs-lookup"><span data-stu-id="5ee2a-158">This command instructs PowerShell to:</span></span>
  
- <span data-ttu-id="5ee2a-159">Obtenha todas as informações sobre as contas de usuário ( **Get-MsolUser** ) e envie-o para o próximo comando ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="5ee2a-159">Get all of the information on the user accounts ( **Get-MsolUser** ) and send it to the next command ( **|** ).</span></span>
    
- <span data-ttu-id="5ee2a-160">Encontre todas as contas de usuário que têm um local de uso não especificado ( **onde {$ \_ . UsageLocation-EQ $Null}** ).</span><span class="sxs-lookup"><span data-stu-id="5ee2a-160">Find all of the user accounts that have an unspecified usage location ( **Where {$\_.UsageLocation -eq $Null}** ).</span></span> <span data-ttu-id="5ee2a-161">Dentro das chaves, o comando instrui o PowerShell a localizar apenas o conjunto de contas no qual a propriedade da conta de usuário do UsageLocation ( \*\* $ \_ . UsageLocation\*\* ) não é especificado ( **-EQ $NULL** ).</span><span class="sxs-lookup"><span data-stu-id="5ee2a-161">Inside the braces, the command instructs PowerShell to only find the set of accounts in which the UsageLocation user account property ( **$\_.UsageLocation** ) is not specified ( **-eq $Null** ).</span></span>
    
<span data-ttu-id="5ee2a-162">Você deve ver informações semelhantes a estas:</span><span class="sxs-lookup"><span data-stu-id="5ee2a-162">You should see information similar to this:</span></span>
  
```powershell
UserPrincipalName                     DisplayName           isLicensed
-----------------                     -----------           ----------
BrianJ@litwareinc.onmicrosoft.com     Brian Johnson         False 
ScottW@litwareinc.onmicrosoft.com     Scott Wallace         False

```

<span data-ttu-id="5ee2a-163">A propriedade **UsageLocation** é apenas uma das muitas propriedades associadas a uma conta de usuário.</span><span class="sxs-lookup"><span data-stu-id="5ee2a-163">The **UsageLocation** property is only one of many properties associated with a user account.</span></span> <span data-ttu-id="5ee2a-164">Para ver todas as propriedades de contas de usuário, use o cmdlet **Select** e o caractere curinga (\*) para exibi-los para uma conta de usuário específica.</span><span class="sxs-lookup"><span data-stu-id="5ee2a-164">To see all of the properties for user accounts, use the **Select** cmdlet and the wildcard character (\*) to display them all for a specific user account.</span></span> <span data-ttu-id="5ee2a-165">Veja um exemplo:</span><span class="sxs-lookup"><span data-stu-id="5ee2a-165">Here is an example:</span></span>
  
```powershell
Get-MsolUser -UserPrincipalName BelindaN@litwareinc.onmicosoft.com | Select *
```

<span data-ttu-id="5ee2a-166">Por exemplo, na lista, **City** é o nome de uma propriedade de conta de usuário.</span><span class="sxs-lookup"><span data-stu-id="5ee2a-166">For example, from this list, **City** is the name of a user account property.</span></span> <span data-ttu-id="5ee2a-167">Isso significa que você pode usar o seguinte comando para listar todas as contas de usuário para usuários em Londres:</span><span class="sxs-lookup"><span data-stu-id="5ee2a-167">This means you can use the following command to list all of the user accounts for users living in London:</span></span>
  
```powershell
Get-MsolUser | Where {$_.City -eq "London"}
```

> [!TIP]
>  <span data-ttu-id="5ee2a-168">A sintaxe do cmdlet **Where** mostrado nesses exemplos é **onde {$ \_ .**</span><span class="sxs-lookup"><span data-stu-id="5ee2a-168">The syntax for the **Where** cmdlet shown in these examples is **Where {$\_.**</span></span> <span data-ttu-id="5ee2a-169">[nome da propriedade da conta de usuário] [operador de comparação] valor **}**.</span><span class="sxs-lookup"><span data-stu-id="5ee2a-169">[user account property name] [comparison operator] [value] **}**.</span></span>  <span data-ttu-id="5ee2a-170">[operador de comparação] é **-EQ** para igual a, **-ne** para não é igual a, **-lt** para menor que, **-gt** para maior que e outros.</span><span class="sxs-lookup"><span data-stu-id="5ee2a-170">[comparison operator] is **-eq** for equals, **-ne** for not equals, **-lt** for less than, **-gt** for greater than, and others.</span></span>  <span data-ttu-id="5ee2a-171">[value] normalmente é uma cadeia de caracteres (uma sequência de letras, números e outros caracteres), um valor numérico ou **$NULL** para não especificado.</span><span class="sxs-lookup"><span data-stu-id="5ee2a-171">[value] is typically a string (a sequence of letters, numbers, and other characters), a numerical value, or **$Null** for unspecified.</span></span> <span data-ttu-id="5ee2a-172">Confira [onde](https://technet.microsoft.com/library/hh849715.aspx) obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="5ee2a-172">See [Where](https://technet.microsoft.com/library/hh849715.aspx) for more information.</span></span>
  
<span data-ttu-id="5ee2a-173">Você pode verificar o status bloqueado de uma conta de usuário com o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="5ee2a-173">You can check the blocked status of a user account with the following command:</span></span>
  
```powershell
Get-MsolUser -UserPrincipalName <UPN of user account> | Select DisplayName,BlockCredential
```

### <a name="view-additional-property-values-for-accounts"></a><span data-ttu-id="5ee2a-174">Exibir valores de propriedade adicionais para contas</span><span class="sxs-lookup"><span data-stu-id="5ee2a-174">View additional property values for accounts</span></span>

<span data-ttu-id="5ee2a-175">Por padrão, o cmdlet **Get-MsolUser** exibe três propriedades de contas de usuário:</span><span class="sxs-lookup"><span data-stu-id="5ee2a-175">The **Get-MsolUser** cmdlet by default displays three properties of user accounts:</span></span>
  
- <span data-ttu-id="5ee2a-176">UserPrincipalName</span><span class="sxs-lookup"><span data-stu-id="5ee2a-176">UserPrincipalName</span></span>
    
- <span data-ttu-id="5ee2a-177">DisplayName</span><span class="sxs-lookup"><span data-stu-id="5ee2a-177">DisplayName</span></span>
    
- <span data-ttu-id="5ee2a-178">isLicensed</span><span class="sxs-lookup"><span data-stu-id="5ee2a-178">isLicensed</span></span>
    
<span data-ttu-id="5ee2a-179">Se você precisar de propriedades adicionais, como o departamento para o qual o usuário trabalha e o país/região em que o usuário usa os serviços do Microsoft 365, é possível executar **Get-MsolUser** em combinação com o cmdlet **Select** para especificar a lista de propriedades da conta de usuário.</span><span class="sxs-lookup"><span data-stu-id="5ee2a-179">If you need additional properties, such as the department the user works for and the country/region where the user uses Microsoft 365 services, you can run **Get-MsolUser** in combination with the **Select** cmdlet to specify the list of user account properties.</span></span> <span data-ttu-id="5ee2a-180">Veja um exemplo:</span><span class="sxs-lookup"><span data-stu-id="5ee2a-180">Here is an example:</span></span>
  
```powershell
Get-MsolUser | Select DisplayName, Department, UsageLocation
```

<span data-ttu-id="5ee2a-181">Este comando instrui o PowerShell para:</span><span class="sxs-lookup"><span data-stu-id="5ee2a-181">This command instructs PowerShell to:</span></span>
  
- <span data-ttu-id="5ee2a-182">Obtenha todas as informações sobre as contas de usuário ( **Get-MsolUser** ) e envie-o para o próximo comando ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="5ee2a-182">Get all of the information on the user accounts ( **Get-MsolUser** ) and send it to the next command ( **|** ).</span></span>
    
- <span data-ttu-id="5ee2a-183">Exibir apenas o nome da conta de usuário, o departamento e o local de uso ( **selecione DisplayName, Department, UsageLocation** ).</span><span class="sxs-lookup"><span data-stu-id="5ee2a-183">Display only the user account name, department, and usage location ( **Select DisplayName, Department, UsageLocation** ).</span></span>
    
<span data-ttu-id="5ee2a-184">Você deve ver informações semelhantes a estas:</span><span class="sxs-lookup"><span data-stu-id="5ee2a-184">You should see information similar to this:</span></span>
  
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

<span data-ttu-id="5ee2a-185">O cmdlet **Select** permite que você escolha e escolha as propriedades que você deseja que um comando exiba.</span><span class="sxs-lookup"><span data-stu-id="5ee2a-185">The **Select** cmdlet lets you pick and choose the properties you want a command to display.</span></span> <span data-ttu-id="5ee2a-186">Para ver todas as propriedades de contas de usuário, use o caractere curinga (\*) para exibi-las para uma conta de usuário específica.</span><span class="sxs-lookup"><span data-stu-id="5ee2a-186">To see all of the properties for user accounts, use the wildcard character (\*) to display them all for a specific user account.</span></span> <span data-ttu-id="5ee2a-187">Veja um exemplo:</span><span class="sxs-lookup"><span data-stu-id="5ee2a-187">Here is an example:</span></span>
  
```powershell
Get-MsolUser -UserPrincipalName BelindaN@litwareinc.onmicosoft.com | Select *
```

<span data-ttu-id="5ee2a-188">Para ser mais seletivo sobre a lista de contas a serem exibidas, você também pode usar o cmdlet **Where** .</span><span class="sxs-lookup"><span data-stu-id="5ee2a-188">To be more selective about the list of accounts to display, you can also use the **Where** cmdlet.</span></span> <span data-ttu-id="5ee2a-189">Veja a seguir um exemplo de comando que exibe apenas as contas de usuário que têm um local de uso não especificado:</span><span class="sxs-lookup"><span data-stu-id="5ee2a-189">Here is an example command that displays only those user accounts that have an unspecified usage location:</span></span>
  
```powershell
Get-MsolUser | Where {$_.UsageLocation -eq $Null} | Select DisplayName, Department, UsageLocation
```

<span data-ttu-id="5ee2a-190">Este comando instrui o PowerShell para:</span><span class="sxs-lookup"><span data-stu-id="5ee2a-190">This command instructs PowerShell to:</span></span>
  
- <span data-ttu-id="5ee2a-191">Obtenha todas as informações sobre as contas de usuário ( **Get-MsolUser** ) e envie-o para o próximo comando ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="5ee2a-191">Get all of the information on the user accounts ( **Get-MsolUser** ) and send it to the next command ( **|** ).</span></span>
    
- <span data-ttu-id="5ee2a-192">Encontre todas as contas de usuário que têm um local de uso não especificado ( **onde {$ \_ . UsageLocation-EQ $Null}** ) e envie as informações resultantes para o próximo comando ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="5ee2a-192">Find all of the user accounts that have an unspecified usage location ( **Where {$\_.UsageLocation -eq $Null}** ) and send the resulting information to the next command ( **|** ).</span></span> <span data-ttu-id="5ee2a-193">Dentro das chaves, o comando instrui o PowerShell a localizar apenas o conjunto de contas no qual a propriedade da conta de usuário do UsageLocation ( \*\* $ \_ . UsageLocation\*\* ) não é especificado ( **-EQ $NULL** ).</span><span class="sxs-lookup"><span data-stu-id="5ee2a-193">Inside the braces, the command is instructing PowerShell to only find the set of accounts in which the UsageLocation user account property ( **$\_.UsageLocation** ) is not specified ( **-eq $Null** ).</span></span>
    
- <span data-ttu-id="5ee2a-194">Exibir apenas o nome da conta de usuário, o departamento e o local de uso ( **selecione DisplayName, Department, UsageLocation** ).</span><span class="sxs-lookup"><span data-stu-id="5ee2a-194">Display only the user account name, department, and usage location ( **Select DisplayName, Department, UsageLocation** ).</span></span>
    
<span data-ttu-id="5ee2a-195">Você deve ver informações semelhantes a estas:</span><span class="sxs-lookup"><span data-stu-id="5ee2a-195">You should see information similar to this:</span></span>
  
```powershell
DisplayName              Department                      UsageLocation
-----------              ----------                      -------------
Brian Johnson 
Scott Wallace            Operations
```

<span data-ttu-id="5ee2a-196">Se você estiver usando a sincronização de diretórios para criar e gerenciar seus usuários do Microsoft 365, poderá exibir a conta local em que um usuário do Microsoft 365 foi projetado.</span><span class="sxs-lookup"><span data-stu-id="5ee2a-196">If you are using directory synchronization to create and manage your Microsoft 365 users, you can display which local account a Microsoft 365 user has been projected from.</span></span> <span data-ttu-id="5ee2a-197">O seguinte pressupõe que o Azure AD Connect tenha sido configurado para usar a âncora de origem padrão de objectGUID (para saber mais sobre como configurar uma âncora de origem, confira [Azure ad Connect: design Concepts](https://docs.microsoft.com/azure/active-directory/hybrid/plan-connect-design-concepts)) e pressupõe que o módulo Active Directory Domain Services para PowerShell tenha sido instalado (consulte [rsat Tools](https://www.microsoft.com/en-gb/download/details.aspx?id=45520)):</span><span class="sxs-lookup"><span data-stu-id="5ee2a-197">The following assumes that Azure AD Connect has been configured to use the default source anchor of ObjectGUID (for more on configuring a source anchor, see [Azure AD Connect: Design concepts](https://docs.microsoft.com/azure/active-directory/hybrid/plan-connect-design-concepts)) and assumes that the Active Directory Domain Services module for PowerShell has been installed (see [RSAT tools](https://www.microsoft.com/en-gb/download/details.aspx?id=45520)):</span></span>

```powershell
Get-ADUser ([guid][System.Convert]::FromBase64String((Get-MsolUser -UserPrincipalName <UPN of user account>).ImmutableID)).guid
```

## <a name="see-also"></a><span data-ttu-id="5ee2a-198">Confira também</span><span class="sxs-lookup"><span data-stu-id="5ee2a-198">See also</span></span>

[<span data-ttu-id="5ee2a-199">Gerenciar contas de usuário, licenças e grupos do Microsoft 365 com o PowerShell</span><span class="sxs-lookup"><span data-stu-id="5ee2a-199">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="5ee2a-200">Gerenciar o Microsoft 365 com o PowerShell</span><span class="sxs-lookup"><span data-stu-id="5ee2a-200">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="5ee2a-201">Introdução ao PowerShell para o Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="5ee2a-201">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
