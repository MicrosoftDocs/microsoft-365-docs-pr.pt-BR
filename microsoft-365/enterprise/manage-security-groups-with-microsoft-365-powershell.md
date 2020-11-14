---
title: Gerenciar grupos de segurança com o PowerShell
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
- PowerShell
- Ent_Office_Other
- O365ITProTrain
description: Saiba como usar o PowerShell para gerenciar grupos de segurança.
ms.openlocfilehash: a52fcf6a20598e92f9d5ac8d673a4b1c026030f8
ms.sourcegitcommit: fcc1b40732f28f075d95faffc1655473e262dd95
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/14/2020
ms.locfileid: "49073185"
---
# <a name="manage-security-groups-with-powershell"></a><span data-ttu-id="833a5-103">Gerenciar grupos de segurança com o PowerShell</span><span class="sxs-lookup"><span data-stu-id="833a5-103">Manage security groups with PowerShell</span></span>

<span data-ttu-id="833a5-104">*Este artigo se aplica tanto ao Microsoft 365 Enterprise quanto ao Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="833a5-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="833a5-105">Você pode usar o PowerShell para Microsoft 365 como uma alternativa para o centro de administração do Microsoft 365 para gerenciar grupos de segurança.</span><span class="sxs-lookup"><span data-stu-id="833a5-105">You can use PowerShell for Microsoft 365 as an alternative to the Microsoft 365 admin center to manage security groups.</span></span> 

<span data-ttu-id="833a5-106">Este artigo descreve a listagem, a criação, a alteração das configurações e a remoção de grupos de segurança.</span><span class="sxs-lookup"><span data-stu-id="833a5-106">This article describes listing, creating, changing settings, and removing security groups.</span></span> 

<span data-ttu-id="833a5-107">Quando um bloco de comando neste artigo requer que você especifique valores de variáveis, use estas etapas.</span><span class="sxs-lookup"><span data-stu-id="833a5-107">When a command block in this article requires that you specify variable values, use these steps.</span></span>

1. <span data-ttu-id="833a5-108">Copie o bloco de comando para a área de transferência e cole-o no bloco de notas ou no ambiente de script integrado (ISE) do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="833a5-108">Copy the command block to the clipboard and paste it into Notepad or the PowerShell Integrated Script Environment (ISE).</span></span>
2. <span data-ttu-id="833a5-109">Preencha os valores de variáveis e remova os caracteres "<" e ">".</span><span class="sxs-lookup"><span data-stu-id="833a5-109">Fill in the variable values and remove the "<" and ">" characters.</span></span>
3. <span data-ttu-id="833a5-110">Execute os comandos na janela do PowerShell ou no ISE do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="833a5-110">Run the commands in the PowerShell window or the PowerShell ISE.</span></span>

<span data-ttu-id="833a5-111">Confira [manter a associação de grupo de segurança](maintain-group-membership-with-microsoft-365-powershell.md) para gerenciar a associação de grupo com o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="833a5-111">See [Maintain security group membership](maintain-group-membership-with-microsoft-365-powershell.md) to manage group membership with PowerShell.</span></span>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="833a5-112">Use o PowerShell do Azure Active Directory para o módulo do gráfico</span><span class="sxs-lookup"><span data-stu-id="833a5-112">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="833a5-113">Primeiro, [Conecte-se ao seu locatário do Microsoft 365](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span><span class="sxs-lookup"><span data-stu-id="833a5-113">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>

### <a name="list-your-groups"></a><span data-ttu-id="833a5-114">Listar seus grupos</span><span class="sxs-lookup"><span data-stu-id="833a5-114">List your groups</span></span>

<span data-ttu-id="833a5-115">Use este comando para listar todos os seus grupos.</span><span class="sxs-lookup"><span data-stu-id="833a5-115">Use this command to list all of your groups.</span></span>

```powershell
Get-AzureADGroup
```
<span data-ttu-id="833a5-116">Use estes comandos para exibir as configurações de um grupo específico por seu nome de exibição.</span><span class="sxs-lookup"><span data-stu-id="833a5-116">Use these commands to display the settings of a specific group by its display name.</span></span>

```powershell
$groupName="<display name of the group>"
Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }
```

### <a name="create-a-new-group"></a><span data-ttu-id="833a5-117">Criar um novo grupo</span><span class="sxs-lookup"><span data-stu-id="833a5-117">Create a new group</span></span>

<span data-ttu-id="833a5-118">Use este comando para criar um novo grupo de segurança.</span><span class="sxs-lookup"><span data-stu-id="833a5-118">Use this command to create a new security group.</span></span>

```powershell
New-AzureADGroup -Description "<group purpose>" -DisplayName "<name>" -MailEnabled $false -SecurityEnabled $true -MailNickName "<email name>"
```

### <a name="change-the-settings-on-a-group"></a><span data-ttu-id="833a5-119">Alterar as configurações em um grupo</span><span class="sxs-lookup"><span data-stu-id="833a5-119">Change the settings on a group</span></span>

<span data-ttu-id="833a5-120">Exibir as configurações do grupo com estes comandos.</span><span class="sxs-lookup"><span data-stu-id="833a5-120">Display the settings of the group with these commands.</span></span>

```powershell
$groupName="<display name of the group>"
Get-AzureADGroup | Where { $_.DisplayName -eq $groupName } | Select *
```

<span data-ttu-id="833a5-121">Em seguida, use o artigo [set-AzureADGroup](https://docs.microsoft.com/powershell/module/azuread/set-azureadgroup) para determinar como alterar uma configuração.</span><span class="sxs-lookup"><span data-stu-id="833a5-121">Then, use the [Set-AzureADGroup](https://docs.microsoft.com/powershell/module/azuread/set-azureadgroup) article to determine how to change a setting.</span></span>

### <a name="remove-a-security-group"></a><span data-ttu-id="833a5-122">Remover um grupo de segurança</span><span class="sxs-lookup"><span data-stu-id="833a5-122">Remove a security group</span></span>

<span data-ttu-id="833a5-123">Use estes comandos para remover um grupo de segurança.</span><span class="sxs-lookup"><span data-stu-id="833a5-123">Use these commands to remove a security group.</span></span>

```powershell
$groupName="<display name of the group>"
Remove-AzureADGroup -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId
```

### <a name="manage-the-owners-of-a-security-group"></a><span data-ttu-id="833a5-124">Gerenciar os proprietários de um grupo de segurança</span><span class="sxs-lookup"><span data-stu-id="833a5-124">Manage the owners of a security group</span></span>

<span data-ttu-id="833a5-125">Use estes comandos para exibir os proprietários atuais de um grupo de segurança.</span><span class="sxs-lookup"><span data-stu-id="833a5-125">Use these commands to display the current owners of a security group.</span></span>

```powershell
$groupName="<display name of the group>"
Get-AzureADGroupOwner -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId
```
<span data-ttu-id="833a5-126">Use estes comandos para adicionar uma conta de usuário pelo **nome principal do usuário (UPN)** aos proprietários atuais de um grupo de segurança.</span><span class="sxs-lookup"><span data-stu-id="833a5-126">Use these commands to add a user account by its **user principal name (UPN)** to the current owners of a security group.</span></span>

```powershell
$userUPN="<UPN of the user account to add>"
$groupName="<display name of the group>"
Add-AzureADGroupOwner -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectId
```
<span data-ttu-id="833a5-127">Use estes comandos para adicionar uma conta de usuário pelo **nome de exibição** aos proprietários atuais de um grupo de segurança.</span><span class="sxs-lookup"><span data-stu-id="833a5-127">Use these commands to add a user account by its **display name** to the current owners of a security group.</span></span>

```powershell
$userName="<Display name of the user account to add>"
$groupName="<display name of the group>"
Add-AzureADGroupOwner -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $userName }).ObjectId
```
<span data-ttu-id="833a5-128">Use estes comandos para remover uma conta de usuário por seu **UPN** para os proprietários atuais de um grupo de segurança.</span><span class="sxs-lookup"><span data-stu-id="833a5-128">Use these commands to remove a user account by its **UPN** to the current owners of a security group.</span></span>

```powershell
$userUPN="<UPN of the user account to remove>"
$groupName="<display name of the group>"
Remove-AzureADGroupOwner -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId -OwnerId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectId
```

<span data-ttu-id="833a5-129">Use estes comandos para remover uma conta de usuário pelo **nome de exibição** para os proprietários atuais de um grupo de segurança.</span><span class="sxs-lookup"><span data-stu-id="833a5-129">Use these commands to remove a user account by its **display name** to the current owners of a security group.</span></span>

```powershell
$userName="<Display name of the user account to remove>"
$groupName="<display name of the group>"
Remove-AzureADGroupOwner -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId -OwnerId (Get-AzureADUser | Where { $_.DisplayName -eq $userName }).ObjectId
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="833a5-130">Use o Módulo Microsoft Azure Active Directory para Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="833a5-130">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="833a5-131">Primeiro, [Conecte-se ao seu locatário do Microsoft 365](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="833a5-131">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

### <a name="list-your-groups"></a><span data-ttu-id="833a5-132">Listar seus grupos</span><span class="sxs-lookup"><span data-stu-id="833a5-132">List your groups</span></span>

<span data-ttu-id="833a5-133">Use este comando para listar todos os seus grupos.</span><span class="sxs-lookup"><span data-stu-id="833a5-133">Use this command to list all of your groups.</span></span>

```powershell
Get-MsolGroup
```
<span data-ttu-id="833a5-134">Use estes comandos para exibir as configurações de um grupo específico por seu nome de exibição.</span><span class="sxs-lookup"><span data-stu-id="833a5-134">Use these commands to display the settings of a specific group by its display name.</span></span>

```powershell
$groupName="<display name of the group>"
Get-MsolGroup | Where { $_.DisplayName -eq $groupName }
```

### <a name="create-a-new-group"></a><span data-ttu-id="833a5-135">Criar um novo grupo</span><span class="sxs-lookup"><span data-stu-id="833a5-135">Create a new group</span></span>

<span data-ttu-id="833a5-136">Use este comando para criar um novo grupo de segurança.</span><span class="sxs-lookup"><span data-stu-id="833a5-136">Use this command to create a new security group.</span></span>

```powershell
New-MsolGroup -Description "<group purpose>" -DisplayName "<name>"
```

### <a name="change-the-settings-on-a-group"></a><span data-ttu-id="833a5-137">Alterar as configurações em um grupo</span><span class="sxs-lookup"><span data-stu-id="833a5-137">Change the settings on a group</span></span>

<span data-ttu-id="833a5-138">Exibir as configurações do grupo com estes comandos.</span><span class="sxs-lookup"><span data-stu-id="833a5-138">Display the settings of the group with these commands.</span></span>

```powershell
$groupName="<display name of the group>"
Get-MsolGroup | Where { $_.DisplayName -eq $groupName } | Select *
```

<span data-ttu-id="833a5-139">Em seguida, use o artigo [set-MsolGroup](https://docs.microsoft.com/powershell/module/msonline/set-msolgroup) para determinar como alterar uma configuração.</span><span class="sxs-lookup"><span data-stu-id="833a5-139">Then, use the [Set-MsolGroup](https://docs.microsoft.com/powershell/module/msonline/set-msolgroup) article to determine how to change a setting.</span></span>

### <a name="remove-a-security-group"></a><span data-ttu-id="833a5-140">Remover um grupo de segurança</span><span class="sxs-lookup"><span data-stu-id="833a5-140">Remove a security group</span></span>

<span data-ttu-id="833a5-141">Use estes comandos para remover um grupo de segurança.</span><span class="sxs-lookup"><span data-stu-id="833a5-141">Use these commands to remove a security group.</span></span>

```powershell
$groupName="<display name of the group>"
Remove-MsolGroup -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId
```

## <a name="see-also"></a><span data-ttu-id="833a5-142">Confira também</span><span class="sxs-lookup"><span data-stu-id="833a5-142">See also</span></span>

[<span data-ttu-id="833a5-143">Gerenciar contas de usuário, licenças e grupos do Microsoft 365 com o PowerShell</span><span class="sxs-lookup"><span data-stu-id="833a5-143">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="833a5-144">Gerenciar o Microsoft 365 com o PowerShell</span><span class="sxs-lookup"><span data-stu-id="833a5-144">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="833a5-145">Introdução ao PowerShell para o Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="833a5-145">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)

