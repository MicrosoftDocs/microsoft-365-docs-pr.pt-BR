---
title: Gerenciar senhas com o PowerShell
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
description: Saiba como usar o PowerShell para gerenciar senhas.
ms.openlocfilehash: ac0a47edb4ccbed93c1a3b88df083d463784b4a4
ms.sourcegitcommit: fcc1b40732f28f075d95faffc1655473e262dd95
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/14/2020
ms.locfileid: "49073182"
---
# <a name="manage-passwords-with-powershell"></a><span data-ttu-id="da3ac-103">Gerenciar senhas com o PowerShell</span><span class="sxs-lookup"><span data-stu-id="da3ac-103">Manage passwords with PowerShell</span></span>

<span data-ttu-id="da3ac-104">*Esse artigo se aplica ao Microsoft 365 Enterprise e ao Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="da3ac-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="da3ac-105">Você pode usar o PowerShell para Microsoft 365 como alternativa ao centro de administração do Microsoft 365 para gerenciar senhas no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="da3ac-105">You can use PowerShell for Microsoft 365 as an alternative to the Microsoft 365 admin center to manage passwords in Microsoft 365.</span></span> 

<span data-ttu-id="da3ac-106">Quando um bloco de comandos neste artigo exigir que você especifique valores variáveis, use estas etapas.</span><span class="sxs-lookup"><span data-stu-id="da3ac-106">When a command block in this article requires that you specify variable values, use these steps.</span></span>

1. <span data-ttu-id="da3ac-107">Copie o bloco de comando para a área de transferência e o colar no Bloco de Notas ou no ISE (Ambiente de Script Integrado) do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="da3ac-107">Copy the command block to the clipboard and paste it into Notepad or the PowerShell Integrated Script Environment (ISE).</span></span>
2. <span data-ttu-id="da3ac-108">Preencha os valores variáveis e remova os caracteres "<" e ">".</span><span class="sxs-lookup"><span data-stu-id="da3ac-108">Fill in the variable values and remove the "<" and ">" characters.</span></span>
3. <span data-ttu-id="da3ac-109">Execute os comandos na janela do PowerShell ou no ISE do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="da3ac-109">Run the commands in the PowerShell window or the PowerShell ISE.</span></span>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="da3ac-110">Use o PowerShell do Azure Active Directory para o módulo do gráfico</span><span class="sxs-lookup"><span data-stu-id="da3ac-110">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="da3ac-111">Primeiro, [conecte-se ao locatário do Microsoft 365.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)</span><span class="sxs-lookup"><span data-stu-id="da3ac-111">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>

### <a name="set-a-password"></a><span data-ttu-id="da3ac-112">Definir uma senha</span><span class="sxs-lookup"><span data-stu-id="da3ac-112">Set a password</span></span>

<span data-ttu-id="da3ac-113">Use estes comandos para especificar uma senha para uma conta de usuário.</span><span class="sxs-lookup"><span data-stu-id="da3ac-113">Use these commands to specify a password for a user account.</span></span>

```powershell
$userUPN="<user account sign in name, such as belindan@contoso.com>"
$newPassword="<new password>"
$secPassword = ConvertTo-SecureString $newPassword -AsPlainText -Force
Set-AzureADUserPassword -ObjectId  $userUPN -Password $secPassword
```
### <a name="force-a-user-to-change-their-password"></a><span data-ttu-id="da3ac-114">Forçar um usuário a alterar a senha</span><span class="sxs-lookup"><span data-stu-id="da3ac-114">Force a user to change their password</span></span>

<span data-ttu-id="da3ac-115">Use estes comandos para definir uma senha e forçar um usuário a alterar sua nova senha.</span><span class="sxs-lookup"><span data-stu-id="da3ac-115">Use these commands to set a password and force a user to change their new password.</span></span>

```powershell
$userUPN="<user account sign in name, such as belindan@contoso.com>"
$newPassword="<new password>"
$secPassword = ConvertTo-SecureString $newPassword -AsPlainText -Force
Set-AzureADUserPassword -ObjectId  $userUPN -Password $secPassword -EnforceChangePasswordPolicy $true
```

<span data-ttu-id="da3ac-116">Use estes comandos para definir uma senha e forçar um usuário a alterar sua nova senha na próxima vez que entrar.</span><span class="sxs-lookup"><span data-stu-id="da3ac-116">Use these commands to set a password and force a user to change their new password the next time they sign in.</span></span>

```powershell
$userUPN="<user account sign in name, such as belindan@contoso.com>"
$newPassword="<new password>"
$secPassword = ConvertTo-SecureString $newPassword -AsPlainText -Force
Set-AzureADUserPassword -ObjectId  $userUPN -Password $secPassword -ForceChangePasswordNextLogin $true
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="da3ac-117">Use o Módulo Microsoft Azure Active Directory para Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="da3ac-117">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="da3ac-118">Primeiro, [conecte-se ao locatário do Microsoft 365.](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)</span><span class="sxs-lookup"><span data-stu-id="da3ac-118">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

### <a name="set-a-password"></a><span data-ttu-id="da3ac-119">Definir uma senha</span><span class="sxs-lookup"><span data-stu-id="da3ac-119">Set a password</span></span>

<span data-ttu-id="da3ac-120">Use estes comandos para especificar uma senha para uma conta de usuário.</span><span class="sxs-lookup"><span data-stu-id="da3ac-120">Use these commands to specify a password for a user account.</span></span>

```powershell
$userUPN="<user account sign in name>"
$newPassword="<new password>"
Set-MsolUserPassword -UserPrincipalName $userUPN -NewPassword $newPassword
```

### <a name="force-a-user-to-change-their-password"></a><span data-ttu-id="da3ac-121">Forçar um usuário a alterar a senha</span><span class="sxs-lookup"><span data-stu-id="da3ac-121">Force a user to change their password</span></span>

<span data-ttu-id="da3ac-122">Use estes comandos para forçar um usuário a alterar sua senha.</span><span class="sxs-lookup"><span data-stu-id="da3ac-122">Use these commands to force a user to change their password.</span></span>

```powershell
$userUPN="<user account sign in name>"
Set-MsolUserPassword -UserPrincipalName $userUPN -ForceChangePassword $true
```

## <a name="see-also"></a><span data-ttu-id="da3ac-123">Confira também</span><span class="sxs-lookup"><span data-stu-id="da3ac-123">See also</span></span>

[<span data-ttu-id="da3ac-124">Gerenciar contas de usuário, licenças e grupos do Microsoft 365 com o PowerShell</span><span class="sxs-lookup"><span data-stu-id="da3ac-124">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="da3ac-125">Gerenciar o Microsoft 365 com o PowerShell</span><span class="sxs-lookup"><span data-stu-id="da3ac-125">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="da3ac-126">Introdução ao PowerShell para o Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="da3ac-126">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)

