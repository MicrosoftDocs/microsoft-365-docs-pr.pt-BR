---
title: Gerenciar o Skype for Business Online com o Windows PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/17/2020
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection: Ent_O365
f1.keywords:
- NOCSH
ms.custom: ''
ms.assetid: 054c16e6-9fd1-4e85-a0e6-81788b8410ea
description: Use o Windows PowerShell para Microsoft 365 para gerenciar as políticas do Skype for Business Online, políticas por usuário e configurações de reunião.
ms.openlocfilehash: 4477dadf0ea38a81ac0ae282da3f74fc12f3406f
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50916675"
---
# <a name="manage-skype-for-business-online-with-powershell"></a><span data-ttu-id="18281-103">Gerenciar o Skype for Business Online com o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="18281-103">Manage Skype for Business Online with PowerShell</span></span>

<span data-ttu-id="18281-104">*Este artigo se aplica tanto ao Microsoft 365 Enterprise quanto ao Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="18281-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="18281-105">Os administradores do Skype for Business Online são responsáveis pelas políticas de gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="18281-105">Skype for Business Online administrators are responsible for managing policies.</span></span> <span data-ttu-id="18281-106">Embora você possa executar algumas dessas tarefas no Centro de administração do Microsoft 365, outras tarefas são mais fáceis no Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="18281-106">Although you can do some of these tasks in the Microsoft 365 admin center, others are easier to do in PowerShell.</span></span>

## <a name="before-you-start"></a><span data-ttu-id="18281-107">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="18281-107">Before you start</span></span>

  > [!Note]
   > <span data-ttu-id="18281-108">O Conector Skype for Business Online atualmente faz parte do módulo mais recente do PowerShell do Teams.</span><span class="sxs-lookup"><span data-stu-id="18281-108">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span> <span data-ttu-id="18281-109">Se você estiver usando o último lançamento público do PowerShell Teams, você não precisa instalar o Conector do Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="18281-109">If you're using the latest Teams PowerShell public release, you don't need to install the Skype for Business Online Connector.</span></span>
   
<span data-ttu-id="18281-110">Instale o [módulo PowerShell do Teams](/microsoftteams/teams-powershell-install).</span><span class="sxs-lookup"><span data-stu-id="18281-110">Install the [Teams PowerShell module](/microsoftteams/teams-powershell-install).</span></span>


## <a name="connect-using-admin-credentials"></a><span data-ttu-id="18281-111">Conecte-se usando as credenciais administrativas</span><span class="sxs-lookup"><span data-stu-id="18281-111">Connect using admin credentials</span></span>

1. <span data-ttu-id="18281-112">Abra uma janela de prompt de comando do Windows PowerShell e execute os seguintes comandos:</span><span class="sxs-lookup"><span data-stu-id="18281-112">Open a Windows PowerShell command prompt window and run the following commands:</span></span>
    
   ```powershell
   Import-Module MicrosoftTeams
   $userCredential = Get-Credential
   Connect-MicrosoftTeams -Credential $userCredential
   ```

2. <span data-ttu-id="18281-113">Na caixa de diálogo **Solicitação de Credenciais do Windows PowerShell**, digite o nome e senha da sua conta de administrador, e então selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="18281-113">In the **Windows PowerShell Credential Request** dialog box, type your administrator account name and password, and then select **OK**.</span></span>


## <a name="connect-using-an-admin-account-with-multi-factor-authentication"></a><span data-ttu-id="18281-114">Conectar usando uma conta de administrador com a autenticação multifator</span><span class="sxs-lookup"><span data-stu-id="18281-114">Connect using an admin account with multi-factor authentication</span></span>

1. <span data-ttu-id="18281-115">Abra uma janela de prompt de comando do Windows PowerShell e execute os seguintes comandos:</span><span class="sxs-lookup"><span data-stu-id="18281-115">Open a Windows PowerShell command prompt window, and run the following commands:</span></span>

   ```powershell
   Import-Module MicrosoftTeams
   Connect-MicrosoftTeams
   ```

2. <span data-ttu-id="18281-116">Quando solicitado, digite o nome da sua conta de administrador do Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="18281-116">When prompted enter your Skype for Business Online administrator account name.</span></span>

3. <span data-ttu-id="18281-117">Na caixa de diálogo **Entre em sua conta**, digite sua senha de administrador do Skype for Business Online e clique em **Entrar**.</span><span class="sxs-lookup"><span data-stu-id="18281-117">In the **Sign in to your account** dialog box, type your Skype for Business Online administrator password and select **Sign in**.</span></span>

4. <span data-ttu-id="18281-118">Siga as instruções na caixa de diálogo **Entre em sua conta** para fornecer informações adicionais de autenticação, como um código de verificação, e clique em **Verificar**.</span><span class="sxs-lookup"><span data-stu-id="18281-118">In the **Sign in to your account** dialog box, follow the instructions to add authentication information, such as a verification code, and then select **Verify**.</span></span>

<span data-ttu-id="18281-119">Para mais informações, confira:</span><span class="sxs-lookup"><span data-stu-id="18281-119">For more information, see:</span></span>
  
- [<span data-ttu-id="18281-120">Gerenciar as políticas do Skype for Business Online com o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="18281-120">Manage Skype for Business Online policies with PowerShell</span></span>](manage-skype-for-business-online-policies-with-microsoft-365-powershell.md)
    
- [<span data-ttu-id="18281-121">Atribuir políticas do Skype for Business online por usuário com o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="18281-121">Assign per-user Skype for Business Online policies with PowerShell</span></span>](assign-per-user-skype-for-business-online-policies-with-microsoft-365-powershell.md)
    
## <a name="see-also"></a><span data-ttu-id="18281-122">Confira também</span><span class="sxs-lookup"><span data-stu-id="18281-122">See also</span></span>

[<span data-ttu-id="18281-123">Gerenciar o Microsoft 365 com o PowerShell</span><span class="sxs-lookup"><span data-stu-id="18281-123">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="18281-124">Introdução ao Windows PowerShell para o Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="18281-124">Get started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)

[<span data-ttu-id="18281-125">Referências de cmdlet do Windows PowerShell do Skype for Business</span><span class="sxs-lookup"><span data-stu-id="18281-125">Skype for Business PowerShell cmdlet references</span></span>](/powershell/module/skype/?view=skype-ps)