---
title: Manter a associação do grupo de segurança com o PowerShell
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
ms.assetid: 6770c5fa-b886-4512-8c67-ffd53226589e
description: Saiba como usar o PowerShell para manter a associação em Microsoft 365 grupos.
ms.openlocfilehash: 9696c9093ae6f24a2edaf544e80794bde45d18d1
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909569"
---
# <a name="maintain-security-group-membership-with-powershell"></a><span data-ttu-id="4ad50-103">Manter a associação do grupo de segurança com o PowerShell</span><span class="sxs-lookup"><span data-stu-id="4ad50-103">Maintain security group membership with PowerShell</span></span>

<span data-ttu-id="4ad50-104">*Esse artigo se aplica ao Microsoft 365 Enterprise e ao Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="4ad50-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="4ad50-105">Você pode usar o PowerShell para Microsoft 365 como uma alternativa ao centro de administração Microsoft 365 para manter a associação do grupo de segurança no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4ad50-105">You can use PowerShell for Microsoft 365 as an alternative to the Microsoft 365 admin center to maintain security group membership in Microsoft 365.</span></span> 

>[!Note]
><span data-ttu-id="4ad50-106">[Saiba como manter a Microsoft 365 de grupo](../admin/create-groups/add-or-remove-members-from-groups.md) com o Microsoft 365 de administração.</span><span class="sxs-lookup"><span data-stu-id="4ad50-106">[Learn how to maintain Microsoft 365 group membership](../admin/create-groups/add-or-remove-members-from-groups.md) with the Microsoft 365 admin center.</span></span> <span data-ttu-id="4ad50-107">Para obter uma lista de recursos adicionais, consulte [Gerenciar usuários e grupos.](../admin/add-users/index.yml)</span><span class="sxs-lookup"><span data-stu-id="4ad50-107">For a list of additional resources, see [Manage users and groups](../admin/add-users/index.yml).</span></span>
>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="4ad50-108">Use o PowerShell do Azure Active Directory para o módulo do gráfico</span><span class="sxs-lookup"><span data-stu-id="4ad50-108">Use the Azure Active Directory PowerShell for Graph module</span></span>
<span data-ttu-id="4ad50-109">Primeiro, [conecte-se ao seu Microsoft 365 locatário](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span><span class="sxs-lookup"><span data-stu-id="4ad50-109">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>

### <a name="add-or-remove-user-accounts-as-members-of-a-group"></a><span data-ttu-id="4ad50-110">Adicionar ou remover contas de usuário como membros de um grupo</span><span class="sxs-lookup"><span data-stu-id="4ad50-110">Add or remove user accounts as members of a group</span></span>

<span data-ttu-id="4ad50-111">Para adicionar uma conta de usuário por seu **UPN**, preencha a conta de usuário Nome principal do usuário (UPN) (exemplo: belindan@contoso.com) e o nome de exibição do grupo de segurança, removendo os caracteres "<" e ">" e execute esses comandos na janela do PowerShell ou no Ambiente de Script Integrado do PowerShell (ISE).</span><span class="sxs-lookup"><span data-stu-id="4ad50-111">**To add a user account by its UPN**, fill in the user account User Principal Name (UPN) (example: belindan@contoso.com) and the security group display name, removing the “<” and “>” characters, and run these commands in the PowerShell window or the PowerShell Integrated Script Environment (ISE).</span></span>

```powershell
$userUPN="<UPN of the user account to add>"
$groupName="<display name of the group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

<span data-ttu-id="4ad50-112">Para adicionar uma conta de usuário pelo nome de exibição **,** preencha o nome de exibição da conta de usuário (exemplo: Belinda Newman) e o nome de exibição do grupo e execute esses comandos na janela do PowerShell ou no ISE do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4ad50-112">**To add a user account by its display name**, fill in the user account display name (example: Belinda Newman) and the group display name and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$userName="<display name of the user account to add>"
$groupName="<display name of the group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $userName }).ObjectID -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

<span data-ttu-id="4ad50-113">Para remover uma conta de usuário por **seu UPN**, preencha a conta de usuário UPN (exemplo: belindan@contoso.com) e o nome de exibição do grupo e execute esses comandos na janela do PowerShell ou no ISE do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4ad50-113">**To remove a user account by its UPN**, fill in the user account UPN (example: belindan@contoso.com) and the group display name and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$userUPN="<UPN of the user account to remove>"
$groupName="<display name of the group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

<span data-ttu-id="4ad50-114">Para **remover uma** conta de usuário pelo nome de exibição , preencha o nome de exibição da conta de usuário (exemplo: Belinda Newman) e o nome de exibição do grupo e execute esses comandos na janela do PowerShell ou no ISE do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4ad50-114">**To remove a user account by its display name**, fill in the user account display name (example: Belinda Newman) and the group display name and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$userName="<display name of the user account to remove>"
$groupName="<display name of the group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADUser | Where { $_.DisplayName -eq $userName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

### <a name="add-or-remove-groups-as-members-of-a-group"></a><span data-ttu-id="4ad50-115">Adicionar ou remover grupos como membros de um grupo</span><span class="sxs-lookup"><span data-stu-id="4ad50-115">Add or remove groups as members of a group</span></span>

<span data-ttu-id="4ad50-116">Os grupos de segurança podem conter outros grupos como membros.</span><span class="sxs-lookup"><span data-stu-id="4ad50-116">Security groups can contain other groups as members.</span></span> <span data-ttu-id="4ad50-117">Microsoft 365 grupos, no entanto, não podem.</span><span class="sxs-lookup"><span data-stu-id="4ad50-117">Microsoft 365 groups, however, cannot.</span></span> <span data-ttu-id="4ad50-118">Esta seção contém comandos do PowerShell para adicionar ou remover grupos apenas para um grupo de segurança.</span><span class="sxs-lookup"><span data-stu-id="4ad50-118">This section contains PowerShell commands to add or remove groups only for a security group.</span></span>

<span data-ttu-id="4ad50-119">Para adicionar um grupo pelo nome de exibição **,** preencha o nome de exibição do grupo que você adicionará e o nome de exibição do grupo que conterá o grupo de membros e execute esses comandos na janela do PowerShell ou no ISE do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4ad50-119">**To add a group by its display name**, fill in the display name of the group you’re going to add and the display name of the group that will contain the member group and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$groupMemberName="<display name of the group to add>"
$groupName="<display name of the group that will contain the member group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

<span data-ttu-id="4ad50-120">Para **remover** um grupo pelo nome de exibição , preencha o nome de exibição do grupo que você removerá e o nome de exibição do grupo que conterá o grupo de membros e execute esses comandos na janela do PowerShell ou no ISE do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4ad50-120">**To remove a group by its display name**, fill in the display name of the group you’re going to remove and the display name of the group that will contain the member group and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$groupMemberName="<display name of the group to add>"
$groupName="<display name of the group that will contain the member group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="4ad50-121">Use o Módulo Microsoft Azure Active Directory para Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4ad50-121">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="4ad50-122">Primeiro, [conecte-se ao seu Microsoft 365 locatário](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="4ad50-122">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>


### <a name="add-or-remove-user-accounts-as-members-of-a-group"></a><span data-ttu-id="4ad50-123">Adicionar ou remover contas de usuário como membros de um grupo</span><span class="sxs-lookup"><span data-stu-id="4ad50-123">Add or remove user accounts as members of a group</span></span>

<span data-ttu-id="4ad50-124">Para adicionar uma conta de usuário por **sua UPN**, preencha a conta de usuário Nome principal do usuário (UPN) (exemplo: belindan@contoso.com) e o nome de exibição do grupo, removendo os caracteres "<" e ">" e execute esses comandos na janela do PowerShell ou no ISE do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4ad50-124">**To add a user account by its UPN**, fill in the user account User Principal Name (UPN) (example: belindan@contoso.com) and the group display name, removing the “<” and “>” characters, and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$userUPN="<UPN of the user account to add>"
$groupName="<display name of the group>"
Add-MsolGroupMember -GroupMemberObjectId (Get-MsolUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

<span data-ttu-id="4ad50-125">Para adicionar uma conta de usuário pelo nome de exibição **,** preencha o nome de exibição da conta de usuário (exemplo: Belinda Newman) e o nome de exibição do grupo e execute esses comandos na janela do PowerShell ou no ISE do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4ad50-125">**To add a user account by its display name**, fill in the user account display name (example: Belinda Newman) and the group display name and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$userName="<display name of the user account to add>"
$groupName="<display name of the group>"
Add-MsolGroupMember -GroupMemberObjectId (Get-MsolUser | Where { $_.DisplayName -eq $userName }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

<span data-ttu-id="4ad50-126">Para remover uma conta de usuário por **seu UPN**, preencha a conta de usuário UPN (exemplo: belindan@contoso.com) e o nome de exibição do grupo e execute esses comandos na janela do PowerShell ou no ISE do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4ad50-126">**To remove a user account by its UPN**, fill in the user account UPN (example: belindan@contoso.com) and the group display name and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$userUPN="<UPN of the user account to remove>"
$groupName="<display name of the group>"
Remove-MsolGroupMember -GroupMemberObjectId (Get-MsolUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

<span data-ttu-id="4ad50-127">Para **remover uma** conta de usuário pelo nome de exibição , preencha o nome de exibição da conta de usuário (exemplo: Belinda Newman) e o nome de exibição do grupo e execute esses comandos na janela do PowerShell ou no ISE do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4ad50-127">**To remove a user account by its display name**, fill in the user account display name (example: Belinda Newman) and the group display name and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$userName="<display name of the user account to remove>"
$groupName="<display name of the group>"
Remove-MsolGroupMember -GroupMemberObjectId (Get-MsolUser | Where { $_.DisplayName -eq $userName }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

### <a name="add-or-remove-groups-as-members-of-a-group"></a><span data-ttu-id="4ad50-128">Adicionar ou remover grupos como membros de um grupo</span><span class="sxs-lookup"><span data-stu-id="4ad50-128">Add or remove groups as members of a group</span></span>

<span data-ttu-id="4ad50-129">Os grupos de segurança podem conter outros grupos como membros.</span><span class="sxs-lookup"><span data-stu-id="4ad50-129">Security groups can contain other groups as members.</span></span> <span data-ttu-id="4ad50-130">Microsoft 365 grupos, no entanto, não podem.</span><span class="sxs-lookup"><span data-stu-id="4ad50-130">Microsoft 365 groups, however, cannot.</span></span> <span data-ttu-id="4ad50-131">Esta seção contém comandos do PowerShell para adicionar ou remover grupos apenas para um grupo de segurança.</span><span class="sxs-lookup"><span data-stu-id="4ad50-131">This section contains PowerShell commands to add or remove groups only for a security group.</span></span>

<span data-ttu-id="4ad50-132">Para adicionar um grupo pelo nome de exibição **,** preencha o nome de exibição do grupo que você adicionará e o nome de exibição do grupo que conterá o grupo de membros e execute esses comandos na janela do PowerShell ou no ISE do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4ad50-132">**To add a group by its display name**, fill in the display name of the group you’re going to add and the display name of the group that will contain the member group and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$groupMemberName="<display name of the group to add>"
$groupName="<display name of the group that will contain the member group>"
Add-MsolGroupMember -GroupMemberObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID -GroupMemberType Group
```

<span data-ttu-id="4ad50-133">Para **remover** um grupo pelo nome de exibição , preencha o nome de exibição do grupo que você removerá e o nome de exibição do grupo que conterá o grupo de membros e execute esses comandos na janela do PowerShell ou no ISE do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4ad50-133">**To remove a group by its display name**, fill in the display name of the group you’re going to remove and the display name of the group that will contain the member group and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$groupMemberName="<display name of the group to add>"
$groupName="<display name of the group contains the member group>"
Remove-MsolGroupMember -GroupMemberObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID -GroupMemberType Group
```

## <a name="see-also"></a><span data-ttu-id="4ad50-134">Confira também</span><span class="sxs-lookup"><span data-stu-id="4ad50-134">See also</span></span>

[<span data-ttu-id="4ad50-135">Gerenciar contas de usuário, licenças e grupos do Microsoft 365 com o PowerShell</span><span class="sxs-lookup"><span data-stu-id="4ad50-135">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="4ad50-136">Gerenciar o Microsoft 365 com o PowerShell</span><span class="sxs-lookup"><span data-stu-id="4ad50-136">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="4ad50-137">Introdução ao PowerShell para o Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="4ad50-137">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)