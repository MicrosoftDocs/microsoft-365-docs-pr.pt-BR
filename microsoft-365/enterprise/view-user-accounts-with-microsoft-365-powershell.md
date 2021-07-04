---
title: Exibir Microsoft 365 contas de usuário com o PowerShell
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
description: Saiba como exibir, listar ou exibir suas Microsoft 365 de usuário de maneiras diferentes com o PowerShell.
ms.openlocfilehash: 77219fb89430ed257ef2a68a7b24bf9ebac715b2
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2021
ms.locfileid: "53290166"
---
# <a name="view-microsoft-365-user-accounts-with-powershell"></a><span data-ttu-id="87081-103">Exibir Microsoft 365 contas de usuário com o PowerShell</span><span class="sxs-lookup"><span data-stu-id="87081-103">View Microsoft 365 user accounts with PowerShell</span></span>

<span data-ttu-id="87081-104">*Esse artigo se aplica ao Microsoft 365 Enterprise e ao Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="87081-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="87081-105">Você pode usar o Centro de administração do Microsoft 365 para exibir as contas do seu Microsoft 365 locatário.</span><span class="sxs-lookup"><span data-stu-id="87081-105">You can use the Microsoft 365 admin center to view the accounts for your Microsoft 365 tenant.</span></span> <span data-ttu-id="87081-106">O PowerShell para Microsoft 365 permite isso, mas também fornece funcionalidade adicional.</span><span class="sxs-lookup"><span data-stu-id="87081-106">PowerShell for Microsoft 365 enables this but also provides additional functionality.</span></span>
  
## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="87081-107">Use o PowerShell do Azure Active Directory para o módulo do gráfico</span><span class="sxs-lookup"><span data-stu-id="87081-107">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="87081-108">Primeiro, [conecte-se ao seu Microsoft 365 locatário](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span><span class="sxs-lookup"><span data-stu-id="87081-108">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
  
### <a name="view-all-accounts"></a><span data-ttu-id="87081-109">Exibir todas as contas</span><span class="sxs-lookup"><span data-stu-id="87081-109">View all accounts</span></span>

<span data-ttu-id="87081-110">Para exibir a lista completa de contas de usuário, execute este comando:</span><span class="sxs-lookup"><span data-stu-id="87081-110">To display the full list of user accounts, run this command:</span></span>
  
```powershell
Get-AzureADUser
```

<span data-ttu-id="87081-111">Você deve obter informações semelhantes a esta:</span><span class="sxs-lookup"><span data-stu-id="87081-111">You should get information similar to this:</span></span>
  
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

### <a name="view-a-specific-account"></a><span data-ttu-id="87081-112">Exibir uma conta específica</span><span class="sxs-lookup"><span data-stu-id="87081-112">View a specific account</span></span>

<span data-ttu-id="87081-113">Para exibir uma conta de usuário específica, execute o seguinte comando.</span><span class="sxs-lookup"><span data-stu-id="87081-113">To display a specific user account, run the following command.</span></span> <span data-ttu-id="87081-114">Preencha o nome da conta de login da conta de usuário, que também é conhecido como o nome principal do usuário (UPN).</span><span class="sxs-lookup"><span data-stu-id="87081-114">Fill in the sign-in account name of the user account, which is also known as the user principal name (UPN).</span></span> <span data-ttu-id="87081-115">Remova os caracteres "<" e ">".</span><span class="sxs-lookup"><span data-stu-id="87081-115">Remove the "<" and ">" characters.</span></span>
  
```powershell
Get-AzureADUser -ObjectID <sign-in name of the user account>
```

<span data-ttu-id="87081-116">Veja um exemplo:</span><span class="sxs-lookup"><span data-stu-id="87081-116">Here's an example:</span></span>
  
```powershell
Get-AzureADUser -ObjectID BelindaN@litwareinc.onmicosoft.com
```

### <a name="view-additional-property-values-for-a-specific-account"></a><span data-ttu-id="87081-117">Exibir valores de propriedade adicionais para uma conta específica</span><span class="sxs-lookup"><span data-stu-id="87081-117">View additional property values for a specific account</span></span>

<span data-ttu-id="87081-118">Por padrão, o cmdlet **Get-AzureADUser** exibe apenas as propriedades *ObjectID,* *DisplayName* e *UserPrincipalName* das contas.</span><span class="sxs-lookup"><span data-stu-id="87081-118">By default, the **Get-AzureADUser** cmdlet only displays the *ObjectID*, *DisplayName*, and *UserPrincipalName* properties of accounts.</span></span>

<span data-ttu-id="87081-119">Para ser mais seletivo sobre as propriedades a serem exibidas, use o cmdlet **Select** em combinação com o cmdlet **Get-AzureADUser.**</span><span class="sxs-lookup"><span data-stu-id="87081-119">To be more selective about the properties to display, use the **Select** cmdlet in combination with the **Get-AzureADUser** cmdlet.</span></span> <span data-ttu-id="87081-120">Para combinar os dois cmdlets, use o caractere "pipe" ("|"), que informa Azure Active Directory PowerShell para que Graph pegue os resultados de um comando e envie-o para o próximo comando.</span><span class="sxs-lookup"><span data-stu-id="87081-120">To combine the two cmdlets, use the "pipe" character ("|"), which tells Azure Active Directory PowerShell for Graph to take the results of one command and send it to the next command.</span></span> <span data-ttu-id="87081-121">Aqui está um comando de exemplo que exibe *DisplayName*, *Department* e *UsageLocation* para cada conta de usuário:</span><span class="sxs-lookup"><span data-stu-id="87081-121">Here's an example command that displays the *DisplayName*, *Department*, and *UsageLocation* for every user account:</span></span>
  
```powershell
Get-AzureADUser | Select DisplayName,Department,UsageLocation
```

<span data-ttu-id="87081-122">Este comando instrui o PowerShell a:</span><span class="sxs-lookup"><span data-stu-id="87081-122">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="87081-123">Obter todas as informações sobre as contas de usuário (**Get-AzureADUser**) e enviá-la para o próximo comando ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="87081-123">Get all the information on the user accounts (**Get-AzureADUser**) and send it to the next command (**|**).</span></span>
    
1.  <span data-ttu-id="87081-124">Exibe apenas o nome da conta de usuário, o departamento e o local de uso (**Selecione DisplayName, Department, UsageLocation**).</span><span class="sxs-lookup"><span data-stu-id="87081-124">Display only the user account name, department, and usage location (**Select DisplayName, Department, UsageLocation**).</span></span>
  
<span data-ttu-id="87081-125">Para ver todas as propriedades de uma conta de usuário específica, use o cmdlet **Select** e o caractere curinga (\*).</span><span class="sxs-lookup"><span data-stu-id="87081-125">To see all the properties for a specific user account, use the **Select** cmdlet and the wildcard character (\*).</span></span> <span data-ttu-id="87081-126">Veja um exemplo:</span><span class="sxs-lookup"><span data-stu-id="87081-126">Here's an example:</span></span>
  
```powershell
Get-AzureADUser -ObjectID BelindaN@litwareinc.onmicosoft.com | Select *
```

<span data-ttu-id="87081-127">Como outro exemplo, execute o seguinte comando para verificar o status habilitado de uma conta de usuário específica:</span><span class="sxs-lookup"><span data-stu-id="87081-127">As another example, run the following command to check the enabled status of a specific user account:</span></span>
  
```powershell
Get-AzureADUser -ObjectID <sign-in name of the user account> | Select DisplayName,UserPrincipalName,AccountEnabled
```

### <a name="view-account-synchronization-status"></a><span data-ttu-id="87081-128">Exibir status de sincronização de conta</span><span class="sxs-lookup"><span data-stu-id="87081-128">View account synchronization status</span></span>

<span data-ttu-id="87081-129">As contas de usuário têm duas fontes:</span><span class="sxs-lookup"><span data-stu-id="87081-129">User accounts have two sources:</span></span> 

- <span data-ttu-id="87081-130">Windows Server Active Directory (AD), que são contas que sincronizam do AD local para a nuvem.</span><span class="sxs-lookup"><span data-stu-id="87081-130">Windows Server Active Directory (AD), which are accounts that sync from on-premises AD to the cloud.</span></span>

- <span data-ttu-id="87081-131">Azure Active Directory contas do AD (Azure AD), que são criadas diretamente na nuvem.</span><span class="sxs-lookup"><span data-stu-id="87081-131">Azure Active Directory (Azure AD) AD accounts, which are created directly in the cloud.</span></span>


<span data-ttu-id="87081-132">O comando a seguir instrui o PowerShell a obter todos os usuários que tenham o atributo *DirSyncEnabled* definido como *True*.</span><span class="sxs-lookup"><span data-stu-id="87081-132">The following command instructs PowerShell to get all users who have the attribute *DirSyncEnabled* set to *True*.</span></span> <span data-ttu-id="87081-133">Você pode usá-lo para encontrar contas que estão sincronizando do AD local.</span><span class="sxs-lookup"><span data-stu-id="87081-133">You can use it to find accounts that are synchronizing from on-premise AD.</span></span>

```powershell
Get-AzureADUser | Where {$_.DirSyncEnabled -eq $true}
```

<span data-ttu-id="87081-134">O comando a seguir instrui o PowerShell a obter todos os usuários que tenham o atributo *DirSyncEnabled* definido como *False*.</span><span class="sxs-lookup"><span data-stu-id="87081-134">The following command instructs PowerShell to get all users who have the attribute *DirSyncEnabled* set to *False*.</span></span> <span data-ttu-id="87081-135">Você pode usá-lo para encontrar contas somente na nuvem.</span><span class="sxs-lookup"><span data-stu-id="87081-135">You can use it to find cloud-only accounts.</span></span>

```powershell
Get-AzureADUser | Where {$_.DirSyncEnabled -ne $false}
```

### <a name="view-accounts-based-on-a-common-property"></a><span data-ttu-id="87081-136">Exibir contas com base em uma propriedade comum</span><span class="sxs-lookup"><span data-stu-id="87081-136">View accounts based on a common property</span></span>

<span data-ttu-id="87081-137">Para ser mais seletivo sobre a lista de contas a serem exibidas, você pode usar o cmdlet **Where** em combinação com o cmdlet **Get-AzureADUser.**</span><span class="sxs-lookup"><span data-stu-id="87081-137">To be more selective about the list of accounts to display, you can use the **Where** cmdlet in combination with the **Get-AzureADUser** cmdlet.</span></span> <span data-ttu-id="87081-138">Para combinar os dois cmdlets, use o caractere "pipe" ("|"), que informa Azure Active Directory PowerShell para que Graph pegue os resultados de um comando e envie-o para o próximo comando.</span><span class="sxs-lookup"><span data-stu-id="87081-138">To combine the two cmdlets, use the "pipe" character ("|"), which tells Azure Active Directory PowerShell for Graph to take the results of one command and send it to the next command.</span></span> <span data-ttu-id="87081-139">Aqui está um comando de exemplo que exibe apenas as contas de usuário que têm um local de uso não especificado:</span><span class="sxs-lookup"><span data-stu-id="87081-139">Here's an example command that displays only those user accounts that have an unspecified usage location:</span></span>
  
```powershell
Get-AzureADUser | Where {$_.UsageLocation -eq $Null}
```

<span data-ttu-id="87081-140">Este comando instrui o Azure Active Directory PowerShell para Graph para:</span><span class="sxs-lookup"><span data-stu-id="87081-140">This command instructs Azure Active Directory PowerShell for Graph to:</span></span>
  
1. <span data-ttu-id="87081-141">Obter todas as informações sobre as contas de usuário (**Get-AzureADUser**) e enviá-la para o próximo comando ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="87081-141">Get all the information on the user accounts (**Get-AzureADUser**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="87081-142">Encontre todas as contas de usuário que tenham um local de uso não especificado (**Onde {$ \_ . UsageLocation -eq $Null}**).</span><span class="sxs-lookup"><span data-stu-id="87081-142">Find all the user accounts that have an unspecified usage location (**Where {$\_.UsageLocation -eq $Null}**).</span></span> <span data-ttu-id="87081-143">Dentro das chaves, o comando instrui o PowerShell a encontrar apenas o conjunto de contas para as quais a propriedade de conta de usuário UsageLocation (**$ \_ . UsageLocation**) não é especificado (**-eq $Null**).</span><span class="sxs-lookup"><span data-stu-id="87081-143">Inside the braces, the command instructs PowerShell to only find the set of accounts for which the UsageLocation user account property (**$\_.UsageLocation**) is not specified (**-eq $Null**).</span></span>
    
<span data-ttu-id="87081-144">A **propriedade UsageLocation** é apenas uma das muitas propriedades associadas a uma conta de usuário.</span><span class="sxs-lookup"><span data-stu-id="87081-144">The **UsageLocation** property is only one of many properties associated with a user account.</span></span> <span data-ttu-id="87081-145">Para exibir todas as propriedades de uma conta de usuário específica, use o cmdlet **Select** e o caractere curinga (\*).</span><span class="sxs-lookup"><span data-stu-id="87081-145">To display all the properties for a specific user account, use the **Select** cmdlet and the wildcard character (\*).</span></span> <span data-ttu-id="87081-146">Veja um exemplo:</span><span class="sxs-lookup"><span data-stu-id="87081-146">Here's an example:</span></span>
  
```powershell
Get-AzureADUser -ObjectID BelindaN@litwareinc.onmicosoft.com | Select *
```

<span data-ttu-id="87081-147">Por exemplo, **City** é o nome de uma propriedade de conta de usuário.</span><span class="sxs-lookup"><span data-stu-id="87081-147">For example, **City** is the name of a user account property.</span></span> <span data-ttu-id="87081-148">Você pode usar o seguinte comando para listar todas as contas de usuários que moram em Londres:</span><span class="sxs-lookup"><span data-stu-id="87081-148">You can use the following command to list all accounts of users who live in London:</span></span>
  
```powershell
Get-AzureADUser | Where {$_.City -eq "London"}
```

> [!TIP]
> <span data-ttu-id="87081-149">A sintaxe do cmdlet **Where** nestes exemplos é **Where {$ \_ .**</span><span class="sxs-lookup"><span data-stu-id="87081-149">The syntax for the **Where** cmdlet in these examples is **Where {$\_.**</span></span> <span data-ttu-id="87081-150">[nome da propriedade de conta de usuário] [operador de comparação] [value] **}**.> [operador de comparação] é **-eq** para igual, **-ne** para não igual, **-lt** para menos que, **-gt** para maior que e outros.</span><span class="sxs-lookup"><span data-stu-id="87081-150">[user account property name] [comparison operator] [value] **}**.> [comparison operator] is **-eq** for equals, **-ne** for not equals, **-lt** for less than, **-gt** for greater than, and others.</span></span>  <span data-ttu-id="87081-151">[value] é normalmente uma cadeia de caracteres (uma sequência de letras,  números e outros caracteres), um valor numérico ou $Null para não especificado.</span><span class="sxs-lookup"><span data-stu-id="87081-151">[value] is typically a string (a sequence of letters, numbers, and other characters), a numerical value, or **$Null** for unspecified.</span></span> <span data-ttu-id="87081-152">Para obter mais informações, consulte [Where](/powershell/module/microsoft.powershell.core/where-object).</span><span class="sxs-lookup"><span data-stu-id="87081-152">For more information, see [Where](/powershell/module/microsoft.powershell.core/where-object).</span></span>

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="87081-153">Use o Módulo Microsoft Azure Active Directory para Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="87081-153">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="87081-154">Primeiro, [conecte-se ao seu Microsoft 365 locatário](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="87081-154">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

### <a name="view-all-accounts"></a><span data-ttu-id="87081-155">Exibir todas as contas</span><span class="sxs-lookup"><span data-stu-id="87081-155">View all accounts</span></span>

<span data-ttu-id="87081-156">Para exibir a lista completa de contas de usuário, execute este comando:</span><span class="sxs-lookup"><span data-stu-id="87081-156">To display the full list of user accounts, run this command:</span></span>
  
```powershell
Get-MsolUser
```

>[!Note]
><span data-ttu-id="87081-157">O PowerShell Core não oferece suporte ao Módulo Microsoft Azure Active Directory para Windows PowerShell para o módulo do Windows PowerShell e cmdlets com *Msol* em seus nomes.</span><span class="sxs-lookup"><span data-stu-id="87081-157">PowerShell Core doesn't support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with *Msol* in their name.</span></span> <span data-ttu-id="87081-158">Execute esses cmdlets do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="87081-158">Run these cmdlets from Windows PowerShell.</span></span>
>

<span data-ttu-id="87081-159">Você deve obter informações semelhantes a esta:</span><span class="sxs-lookup"><span data-stu-id="87081-159">You should get information similar to this:</span></span>
  
```powershell
UserPrincipalName                     DisplayName           isLicensed
-----------------                     -----------           ----------
BonnieK@litwareinc.onmicrosoft.com    Bonnie Kearney        True
FabriceC@litwareinc.onmicrosoft.com   Fabrice Canel         True
BrianJ@litwareinc.onmicrosoft.com     Brian Johnson         False 
AnneWlitwareinc.onmicrosoft.com       Anne Wallace          True
ScottW@litwareinc.onmicrosoft.com     Scott Wallace         False
```

<span data-ttu-id="87081-160">O cmdlet **Get-MsolUser** também tem um conjunto de parâmetros para filtrar o conjunto de contas de usuário exibidas.</span><span class="sxs-lookup"><span data-stu-id="87081-160">The **Get-MsolUser** cmdlet also has a set of parameters to filter the set of user accounts displayed.</span></span> <span data-ttu-id="87081-161">Por exemplo, para a lista de usuários não licenciados (usuários que foram adicionados ao Microsoft 365 mas ainda não foram licenciados para usar qualquer um dos serviços), execute este comando:</span><span class="sxs-lookup"><span data-stu-id="87081-161">For example, for the list of unlicensed users (users who have been added to Microsoft 365 but haven't yet been licensed to use any of the services), run this command:</span></span>
  
```powershell
Get-MsolUser -UnlicensedUsersOnly
```

<span data-ttu-id="87081-162">Você deve obter informações semelhantes a esta:</span><span class="sxs-lookup"><span data-stu-id="87081-162">You should get information similar to this:</span></span>
  
```powershell
UserPrincipalName                     DisplayName           isLicensed
-----------------                     -----------           ----------
BrianJ@litwareinc.onmicrosoft.com     Brian Johnson         False
ScottW@litwareinc.onmicrosoft.com     Scott Wallace         False
```

<span data-ttu-id="87081-163">Para obter informações sobre parâmetros adicionais para filtrar o conjunto de contas de usuário que são exibidas, consulte [Get-MsolUser](/previous-versions/azure/dn194133(v=azure.100)).</span><span class="sxs-lookup"><span data-stu-id="87081-163">For information about additional parameters to filter the set of user accounts that are displayed, see [Get-MsolUser](/previous-versions/azure/dn194133(v=azure.100)).</span></span>
  
### <a name="view-a-specific-account"></a><span data-ttu-id="87081-164">Exibir uma conta específica</span><span class="sxs-lookup"><span data-stu-id="87081-164">View a specific account</span></span>

<span data-ttu-id="87081-165">Para exibir uma conta de usuário específica, execute o seguinte comando.</span><span class="sxs-lookup"><span data-stu-id="87081-165">To display a specific user account, run the following command.</span></span> <span data-ttu-id="87081-166">Preencha o nome de logon da conta de usuário, que também é conhecido como o nome principal do usuário (UPN).</span><span class="sxs-lookup"><span data-stu-id="87081-166">Fill in the sign-in name of the user account, which is also known as the user principal name (UPN).</span></span> <span data-ttu-id="87081-167">Remova os caracteres "<" e ">".</span><span class="sxs-lookup"><span data-stu-id="87081-167">Remove the "<" and ">" characters.</span></span>
  
```powershell
Get-MsolUser -UserPrincipalName <sign-in name of the user account>
```

### <a name="view-accounts-based-on-a-common-property"></a><span data-ttu-id="87081-168">Exibir contas com base em uma propriedade comum</span><span class="sxs-lookup"><span data-stu-id="87081-168">View accounts based on a common property</span></span>

<span data-ttu-id="87081-169">Para ser mais seletivo sobre a lista de contas a serem exibidas, você pode usar o cmdlet **Where** em combinação com o cmdlet **Get-MsolUser.**</span><span class="sxs-lookup"><span data-stu-id="87081-169">To be more selective about the list of accounts to display, you can use the **Where** cmdlet in combination with the **Get-MsolUser** cmdlet.</span></span> <span data-ttu-id="87081-170">Para combinar os dois cmdlets, use o caractere "pipe" ("|"), que diz ao PowerShell para levar os resultados de um comando e enviá-lo para o próximo comando.</span><span class="sxs-lookup"><span data-stu-id="87081-170">To combine the two cmdlets, use the "pipe" character ("|"), which tells PowerShell to take the results of one command and send it to the next command.</span></span> <span data-ttu-id="87081-171">Veja um exemplo que exibe apenas as contas de usuário que têm um local de uso não especificado:</span><span class="sxs-lookup"><span data-stu-id="87081-171">Here's an example that displays only those user accounts that have an unspecified usage location:</span></span>
  
```powershell
Get-MsolUser | Where {$_.UsageLocation -eq $Null}
```

<span data-ttu-id="87081-172">Este comando instrui o PowerShell a:</span><span class="sxs-lookup"><span data-stu-id="87081-172">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="87081-173">Obter todas as informações sobre as contas de usuário (**Get-MsolUser**) e enviá-la para o próximo comando ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="87081-173">Get all the information on the user accounts (**Get-MsolUser**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="87081-174">Encontre todas as contas de usuário que tenham um local de uso não especificado (**Onde {$ \_ . UsageLocation -eq $Null}**).</span><span class="sxs-lookup"><span data-stu-id="87081-174">Find all user accounts that have an unspecified usage location (**Where {$\_.UsageLocation -eq $Null}**).</span></span> <span data-ttu-id="87081-175">Dentro das chaves, o comando instrui o PowerShell a encontrar apenas o conjunto de contas para as quais a propriedade de conta de usuário UsageLocation (**$ \_ . UsageLocation**) não é especificado (**-eq $Null**).</span><span class="sxs-lookup"><span data-stu-id="87081-175">Inside the braces, the command instructs PowerShell to find only the set of accounts for which the UsageLocation user account property (**$\_.UsageLocation**) is not specified (**-eq $Null**).</span></span>
    
<span data-ttu-id="87081-176">Você deve obter informações semelhantes a esta:</span><span class="sxs-lookup"><span data-stu-id="87081-176">You should get information similar to this:</span></span>
  
```powershell
UserPrincipalName                     DisplayName           isLicensed
-----------------                     -----------           ----------
BrianJ@litwareinc.onmicrosoft.com     Brian Johnson         False 
ScottW@litwareinc.onmicrosoft.com     Scott Wallace         False

```

<span data-ttu-id="87081-177">A *propriedade UsageLocation* é apenas uma das muitas propriedades associadas a uma conta de usuário.</span><span class="sxs-lookup"><span data-stu-id="87081-177">The *UsageLocation* property is only one of many properties associated with a user account.</span></span> <span data-ttu-id="87081-178">Para ver todas as propriedades para contas de usuário, use o cmdlet **Select** e o caractere curinga (\*) para exibi-las todas para uma conta de usuário específica.</span><span class="sxs-lookup"><span data-stu-id="87081-178">To see all of the properties for user accounts, use the **Select** cmdlet and the wildcard character (\*) to display them all for a specific user account.</span></span> <span data-ttu-id="87081-179">Veja um exemplo:</span><span class="sxs-lookup"><span data-stu-id="87081-179">Here's an example:</span></span>
  
```powershell
Get-MsolUser -UserPrincipalName BelindaN@litwareinc.onmicosoft.com | Select *
```

<span data-ttu-id="87081-180">Por exemplo, *City* é o nome de uma propriedade de conta de usuário.</span><span class="sxs-lookup"><span data-stu-id="87081-180">For example, *City* is the name of a user account property.</span></span> <span data-ttu-id="87081-181">Você pode usar o seguinte comando para listar todas as contas de usuário para usuários que moram em Londres:</span><span class="sxs-lookup"><span data-stu-id="87081-181">You can use the following command to list all of the user accounts for users who live in London:</span></span>
  
```powershell
Get-MsolUser | Where {$_.City -eq "London"}
```

> [!TIP]
> <span data-ttu-id="87081-182">A sintaxe do cmdlet **Where** nestes exemplos é **Where {$ \_ .**</span><span class="sxs-lookup"><span data-stu-id="87081-182">The syntax for the **Where** cmdlet in these examples is **Where {$\_.**</span></span> <span data-ttu-id="87081-183">[nome da propriedade de conta de usuário] [operador de comparação] [value] **}**.</span><span class="sxs-lookup"><span data-stu-id="87081-183">[user account property name] [comparison operator] [value] **}**.</span></span>  <span data-ttu-id="87081-184">[operador de comparação] é **-eq** para igual, **-ne** para não igual, **-lt** para menos que, **-gt** para maior do que e outros.</span><span class="sxs-lookup"><span data-stu-id="87081-184">[comparison operator] is **-eq** for equals, **-ne** for not equals, **-lt** for less than, **-gt** for greater than, and others.</span></span>  <span data-ttu-id="87081-185">[value] é normalmente uma cadeia de caracteres (uma sequência de letras,  números e outros caracteres), um valor numérico ou $Null para não especificado.</span><span class="sxs-lookup"><span data-stu-id="87081-185">[value] is typically a string (a sequence of letters, numbers, and other characters), a numerical value, or **$Null** for unspecified.</span></span> <span data-ttu-id="87081-186">Para obter mais informações, consulte [Where](/powershell/module/microsoft.powershell.core/where-object).</span><span class="sxs-lookup"><span data-stu-id="87081-186">For more information, see [Where](/powershell/module/microsoft.powershell.core/where-object).</span></span>
  
<span data-ttu-id="87081-187">Para verificar o status bloqueado de uma conta de usuário, use o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="87081-187">To check the blocked status of a user account, use the following command:</span></span>
  
```powershell
Get-MsolUser -UserPrincipalName <UPN of user account> | Select DisplayName,BlockCredential
```

### <a name="view-additional-property-values-for-accounts"></a><span data-ttu-id="87081-188">Exibir valores de propriedade adicionais para contas</span><span class="sxs-lookup"><span data-stu-id="87081-188">View additional property values for accounts</span></span>

<span data-ttu-id="87081-189">Por padrão, o cmdlet **Get-MsolUser** exibe essas três propriedades de contas de usuário:</span><span class="sxs-lookup"><span data-stu-id="87081-189">By default, the **Get-MsolUser** cmdlet displays these three properties of user accounts:</span></span>
  
- <span data-ttu-id="87081-190">UserPrincipalName</span><span class="sxs-lookup"><span data-stu-id="87081-190">UserPrincipalName</span></span>

- <span data-ttu-id="87081-191">DisplayName</span><span class="sxs-lookup"><span data-stu-id="87081-191">DisplayName</span></span>

- <span data-ttu-id="87081-192">isLicensed</span><span class="sxs-lookup"><span data-stu-id="87081-192">isLicensed</span></span>

<span data-ttu-id="87081-193">Se você precisar de propriedades adicionais, como o departamento onde o usuário trabalha e o país/região onde ele usa serviços Microsoft 365, você pode executar **Get-MsolUser** em combinação com o cmdlet **Select** para especificar a lista de propriedades da conta de usuário.</span><span class="sxs-lookup"><span data-stu-id="87081-193">If you need additional properties, such as the department where the user works and the country/region where they use Microsoft 365 services, you can run **Get-MsolUser** in combination with the **Select** cmdlet to specify the list of user account properties.</span></span> <span data-ttu-id="87081-194">Veja um exemplo:</span><span class="sxs-lookup"><span data-stu-id="87081-194">Here's an example:</span></span>
  
```powershell
Get-MsolUser | Select DisplayName, Department, UsageLocation
```

<span data-ttu-id="87081-195">Este comando instrui o PowerShell a:</span><span class="sxs-lookup"><span data-stu-id="87081-195">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="87081-196">Obter todas as informações sobre as contas de usuário (**Get-MsolUser**) e enviá-la para o próximo comando ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="87081-196">Get all the information about the user accounts (**Get-MsolUser**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="87081-197">Exibe apenas o nome da conta de usuário, o departamento e o local de uso (**Selecione DisplayName, Department, UsageLocation**).</span><span class="sxs-lookup"><span data-stu-id="87081-197">Display only the user account name, department, and usage location (**Select DisplayName, Department, UsageLocation**).</span></span>
    
<span data-ttu-id="87081-198">Você deve obter informações semelhantes a esta:</span><span class="sxs-lookup"><span data-stu-id="87081-198">You should get information similar to this:</span></span>
  
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

<span data-ttu-id="87081-199">O cmdlet **Select** permite que você escolha quais propriedades exibir.</span><span class="sxs-lookup"><span data-stu-id="87081-199">The **Select** cmdlet lets you choose what properties to display.</span></span> <span data-ttu-id="87081-200">Para exibir todas as propriedades de uma conta de usuário específica, use o caractere curinga (\*).</span><span class="sxs-lookup"><span data-stu-id="87081-200">To display all the properties for a specific user account, use the wildcard character (\*).</span></span> <span data-ttu-id="87081-201">Veja um exemplo:</span><span class="sxs-lookup"><span data-stu-id="87081-201">Here's an example:</span></span>
  
```powershell
Get-MsolUser -UserPrincipalName BelindaN@litwareinc.onmicosoft.com | Select *
```

<span data-ttu-id="87081-202">Para ser mais seletivo sobre a lista de contas a serem exibidas, você também pode usar o cmdlet **Where.**</span><span class="sxs-lookup"><span data-stu-id="87081-202">To be more selective about the list of accounts to display, you can also use the **Where** cmdlet.</span></span> <span data-ttu-id="87081-203">Aqui está um comando de exemplo que exibe apenas as contas de usuário que têm um local de uso não especificado:</span><span class="sxs-lookup"><span data-stu-id="87081-203">Here's an example command that displays only those user accounts that have an unspecified usage location:</span></span>
  
```powershell
Get-MsolUser | Where {$_.UsageLocation -eq $Null} | Select DisplayName, Department, UsageLocation
```

<span data-ttu-id="87081-204">Este comando instrui o PowerShell a:</span><span class="sxs-lookup"><span data-stu-id="87081-204">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="87081-205">Obter todas as informações sobre as contas de usuário (**Get-MsolUser**) e enviá-la para o próximo comando ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="87081-205">Get all the information about the user accounts (**Get-MsolUser**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="87081-206">Encontre todas as contas de usuário que tenham um local de uso não especificado (**Onde {$ \_ . UsageLocation -eq $Null}**), e envie as informações resultantes para o próximo comando ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="87081-206">Find all user accounts that have an unspecified usage location (**Where {$\_.UsageLocation -eq $Null}**), and send the resulting information to the next command (**|**).</span></span> <span data-ttu-id="87081-207">Dentro das chaves, o comando instrui o PowerShell a encontrar apenas o conjunto de contas para as quais a propriedade de conta de usuário UsageLocation (**$ \_ . UsageLocation**) não é especificado (**-eq $Null**).</span><span class="sxs-lookup"><span data-stu-id="87081-207">Inside the braces, the command instructs PowerShell to only find the set of accounts for which the UsageLocation user account property (**$\_.UsageLocation**) is not specified (**-eq $Null**).</span></span>
    
1. <span data-ttu-id="87081-208">Exibe apenas o nome da conta de usuário, o departamento e o local de uso (**Selecione DisplayName, Department, UsageLocation**).</span><span class="sxs-lookup"><span data-stu-id="87081-208">Display only the user account name, department, and usage location (**Select DisplayName, Department, UsageLocation**).</span></span>
    
<span data-ttu-id="87081-209">Você deve obter informações semelhantes a esta:</span><span class="sxs-lookup"><span data-stu-id="87081-209">You should get information similar to this:</span></span>
  
```powershell
DisplayName              Department                      UsageLocation
-----------              ----------                      -------------
Brian Johnson 
Scott Wallace            Operations
```

<span data-ttu-id="87081-210">Se você estiver usando a sincronização de diretórios para criar e gerenciar seus usuários Microsoft 365, você poderá exibir a conta local da qual um usuário Microsoft 365 foi projetado.</span><span class="sxs-lookup"><span data-stu-id="87081-210">If you're using directory synchronization to create and manage your Microsoft 365 users, you can display the local account from which a Microsoft 365 user has been projected.</span></span> <span data-ttu-id="87081-211">O exemplo a seguir supõe que:</span><span class="sxs-lookup"><span data-stu-id="87081-211">The following example assumes that:</span></span>

- <span data-ttu-id="87081-212">O Azure AD Conexão configurado para usar a âncora de origem padrão do ObjectGUID.</span><span class="sxs-lookup"><span data-stu-id="87081-212">Azure AD Connect is configured to use the default source anchor of ObjectGUID.</span></span> <span data-ttu-id="87081-213">(Para obter mais informações sobre como configurar uma âncora de origem, consulte [Azure AD Conexão: Conceitos de design).](/azure/active-directory/hybrid/plan-connect-design-concepts)</span><span class="sxs-lookup"><span data-stu-id="87081-213">(For more information about configuring a source anchor, see [Azure AD Connect: Design concepts](/azure/active-directory/hybrid/plan-connect-design-concepts)).</span></span>
- <span data-ttu-id="87081-214">O módulo serviços de domínio do Active Directory para PowerShell foi instalado (consulte [ferramentas RSAT](https://www.microsoft.com/en-gb/download/details.aspx?id=45520)).</span><span class="sxs-lookup"><span data-stu-id="87081-214">The Active Directory Domain Services module for PowerShell has been installed (see [RSAT tools](https://www.microsoft.com/en-gb/download/details.aspx?id=45520)).</span></span>

```powershell
Get-ADUser ([guid][System.Convert]::FromBase64String((Get-MsolUser -UserPrincipalName <UPN of user account>).ImmutableID)).guid
```

## <a name="see-also"></a><span data-ttu-id="87081-215">Confira também</span><span class="sxs-lookup"><span data-stu-id="87081-215">See also</span></span>

[<span data-ttu-id="87081-216">Gerenciar contas de usuário, licenças e grupos do Microsoft 365 com o PowerShell</span><span class="sxs-lookup"><span data-stu-id="87081-216">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="87081-217">Gerenciar o Microsoft 365 com o PowerShell</span><span class="sxs-lookup"><span data-stu-id="87081-217">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="87081-218">Introdução ao Windows PowerShell para o Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="87081-218">Get started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)