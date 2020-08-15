---
title: Atribuir políticas do Skype for Business online por usuário com o PowerShell para o Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/16/2020
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.assetid: 36743c86-46c2-46be-b9ed-ad9d4e85d186
description: 'Resumo: Use o PowerShell para Microsoft 365 para atribuir configurações de comunicação por usuário com as políticas do Skype for Business online.'
ms.openlocfilehash: 6ff9fce3e0287313f6725b370b6ba89cb939eb3a
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46687163"
---
# <a name="assign-per-user-skype-for-business-online-policies-with-powershell-for-microsoft-365"></a><span data-ttu-id="c020b-103">Atribuir políticas do Skype for Business online por usuário com o PowerShell para o Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="c020b-103">Assign per-user Skype for Business Online policies with PowerShell for Microsoft 365</span></span>

<span data-ttu-id="c020b-104">*Esse artigo se aplica ao Microsoft 365 Enterprise e ao Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="c020b-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="c020b-105">O uso do PowerShell para Microsoft 365 é uma maneira eficiente de atribuir configurações de comunicação por usuário com as políticas do Skype for Business online.</span><span class="sxs-lookup"><span data-stu-id="c020b-105">Using PowerShell for Microsoft 365 is an efficient way to assign per-user communication settings with Skype for Business Online policies.</span></span>
  
## <a name="prepare-to-run-the-powershell-commands"></a><span data-ttu-id="c020b-106">Preparar para executar os comandos do PowerShell</span><span class="sxs-lookup"><span data-stu-id="c020b-106">Prepare to run the PowerShell commands</span></span>

<span data-ttu-id="c020b-107">Use estas instruções para configurar a execução dos comandos (pule as etapas que você já concluiu):</span><span class="sxs-lookup"><span data-stu-id="c020b-107">Use these instructions to get set up to run the commands (skip the steps you have already completed):</span></span>
  
1. <span data-ttu-id="c020b-108">Baixe e instale o [módulo do conector do Skype for Business online](https://www.microsoft.com/download/details.aspx?id=39366).</span><span class="sxs-lookup"><span data-stu-id="c020b-108">Download and install the [Skype for Business Online Connector module](https://www.microsoft.com/download/details.aspx?id=39366).</span></span>
    
2. <span data-ttu-id="c020b-109">Abra um prompt de comando do Windows PowerShell e execute os seguintes comandos:</span><span class="sxs-lookup"><span data-stu-id="c020b-109">Open a Windows PowerShell command prompt and run the following commands:</span></span> 
    
```powershell
Import-Module LyncOnlineConnector
$userCredential = Get-Credential
$sfbSession = New-CsOnlineSession -Credential $userCredential
Import-PSSession $sfbSession
```

<span data-ttu-id="c020b-110">Quando solicitado, insira o nome da conta e a senha do administrador do Skype for Business online.</span><span class="sxs-lookup"><span data-stu-id="c020b-110">When prompted, enter your Skype for Business Online administrator account name and password.</span></span>
    
## <a name="updating-external-communication-settings-for-a-user-account"></a><span data-ttu-id="c020b-111">Atualizando configurações de comunicação externa para uma conta de usuário</span><span class="sxs-lookup"><span data-stu-id="c020b-111">Updating external communication settings for a user account</span></span>

<span data-ttu-id="c020b-112">Suponha que você queira alterar as configurações de comunicação externa em uma conta de usuário.</span><span class="sxs-lookup"><span data-stu-id="c020b-112">Suppose you want to change external communication settings on a user account.</span></span> <span data-ttu-id="c020b-113">Por exemplo, você deseja permitir que Alex se comunique com usuários federados (EnableFederationAccess é igual a true), mas não com usuários do Windows Live (EnablePublicCloudAccess é igual a false).</span><span class="sxs-lookup"><span data-stu-id="c020b-113">For example, you want to allow Alex to communicate with federated users (EnableFederationAccess is equal to True) but not with Windows Live users (EnablePublicCloudAccess equals False).</span></span> <span data-ttu-id="c020b-114">Para fazer isso, você precisa fazer duas coisas:</span><span class="sxs-lookup"><span data-stu-id="c020b-114">To do that, you need to do two things:</span></span>
  
1. <span data-ttu-id="c020b-115">Localizar uma política de acesso externo que atenda aos nossos critérios.</span><span class="sxs-lookup"><span data-stu-id="c020b-115">Find an external access policy that meets our criteria.</span></span>
    
2. <span data-ttu-id="c020b-116">Atribuir essa política de acesso externo a Antônio.</span><span class="sxs-lookup"><span data-stu-id="c020b-116">Assign that external access policy to Alex.</span></span>
    
<span data-ttu-id="c020b-117">Como determinar qual política de acesso externo atribuirá a Alex?</span><span class="sxs-lookup"><span data-stu-id="c020b-117">How do you determine which external access policy to assign Alex?</span></span> <span data-ttu-id="c020b-118">O comando a seguir retorna todas as políticas de acesso externo em que EnableFederationAccess é definido como True e EnablePublicCloudAccess como False:</span><span class="sxs-lookup"><span data-stu-id="c020b-118">The following command returns all the external access policies where EnableFederationAccess is set to True and EnablePublicCloudAccess is set to False:</span></span>
  
```powershell
Get-CsExternalAccessPolicy -Include All| Where-Object {$_.EnableFederationAccess -eq $True -and $_.EnablePublicCloudAccess -eq $False}
```

<span data-ttu-id="c020b-119">A menos que você tenha criado instâncias personalizadas do ExternalAccessPolicy, esse comando retornará uma política que atenda aos nossos critérios (FederationOnly).</span><span class="sxs-lookup"><span data-stu-id="c020b-119">Unless you have created any custom instances of ExternalAccessPolicy, that command returns one policy that meets our criteria (FederationOnly).</span></span> <span data-ttu-id="c020b-120">Veja um exemplo:</span><span class="sxs-lookup"><span data-stu-id="c020b-120">Here is an example:</span></span>
  
```powershell
Identity                          : Tag:FederationOnly
Description                       :
EnableFederationAccess            : True
EnableXmppAccess                  : False
EnablePublicCloudAccess           : False
EnablePublicCloudAudioVideoAccess : False
EnableOutsideAccess               : True
```

<span data-ttu-id="c020b-121">Agora que você sabe qual política será atribuída a Alex, podemos atribuir essa política usando o cmdlet [Grant-CsExternalAccessPolicy](https://go.microsoft.com/fwlink/?LinkId=523974) .</span><span class="sxs-lookup"><span data-stu-id="c020b-121">Now that you know which policy to assign to Alex, we can assign that policy by using the [Grant-CsExternalAccessPolicy](https://go.microsoft.com/fwlink/?LinkId=523974) cmdlet.</span></span> <span data-ttu-id="c020b-122">Veja um exemplo:</span><span class="sxs-lookup"><span data-stu-id="c020b-122">Here is an example:</span></span>
  
```powershell
Grant-CsExternalAccessPolicy -Identity "Alex Darrow" -PolicyName "FederationOnly"
```

<span data-ttu-id="c020b-123">Atribuir uma política é muito simples: basta especificar a identidade do usuário e o nome da política a ser atribuída.</span><span class="sxs-lookup"><span data-stu-id="c020b-123">Assigning a policy is pretty simple: you simply specify the Identity of the user and the name of the policy to be assigned.</span></span> 
  
<span data-ttu-id="c020b-124">E quando se trata de políticas e atribuições de política, você não está limitado a trabalhar com as contas de usuário uma vez.</span><span class="sxs-lookup"><span data-stu-id="c020b-124">And when it comes to policies and policy assignments, you're not limited to working with user accounts one a time.</span></span> <span data-ttu-id="c020b-125">Por exemplo, suponha que você precise de uma lista de todos os usuários que têm permissão para se comunicar com parceiros federados e com usuários do Windows Live.</span><span class="sxs-lookup"><span data-stu-id="c020b-125">For example, suppose you need a list of all the users who are allowed to communicate with federated partners and with Windows Live users.</span></span> <span data-ttu-id="c020b-126">Já sabemos que esses usuários foram atribuídos à política de acesso de usuário externo FederationAndPICDefault.</span><span class="sxs-lookup"><span data-stu-id="c020b-126">We already know that those users have been assigned the external user access policy FederationAndPICDefault.</span></span> <span data-ttu-id="c020b-127">Como sabemos que, você pode exibir uma lista de todos os usuários executando um comando simples.</span><span class="sxs-lookup"><span data-stu-id="c020b-127">Because we know that, you can display a list of all those users by running one simple command.</span></span> <span data-ttu-id="c020b-128">Este é o comando:</span><span class="sxs-lookup"><span data-stu-id="c020b-128">Here is the command:</span></span>
  
```powershell
Get-CsOnlineUser -Filter {ExternalAccessPolicy -eq "FederationAndPICDefault"} | Select-Object DisplayName
```

<span data-ttu-id="c020b-129">Em outras palavras, isso nos mostra todos os usuários cuja propriedade ExternalAccessPolicy está definida como FederationAndPICDefault.</span><span class="sxs-lookup"><span data-stu-id="c020b-129">In other words, show us all the users where the ExternalAccessPolicy property is set to FederationAndPICDefault.</span></span> <span data-ttu-id="c020b-130">(E, para limitar a quantidade de informações que aparece na tela, use o cmdlet Select-Object para exibir apenas mostrar o nome de exibição de cada usuário.)</span><span class="sxs-lookup"><span data-stu-id="c020b-130">(And, in order to limit the amount of information that appears onscreen, use the Select-Object cmdlet to display show us only each user's display name.)</span></span> 
  
<span data-ttu-id="c020b-131">Para configurar todas as contas de usuário para usar essa mesma política, use este comando:</span><span class="sxs-lookup"><span data-stu-id="c020b-131">To configure all our user accounts to use that same policy, use this command:</span></span>
  
```powershell
Get-CsOnlineUser | Grant-CsExternalAccessPolicy "FederationAndPICDefault"
```

<span data-ttu-id="c020b-132">Este comando usa Get-CsOnlineUser para retornar uma coleção de todos os usuários que tenham sido habilitados para o Lync e, em seguida, envia todas as informações para Grant-CsExternalAccessPolicy, que atribui a política de FederationAndPICDefault a cada e a todos os usuários da coleção.</span><span class="sxs-lookup"><span data-stu-id="c020b-132">This command uses Get-CsOnlineUser to return a collection of all the users who have been enabled for Lync, then sends all that information to Grant-CsExternalAccessPolicy, which assigns the FederationAndPICDefault policy to each and every user in the collection.</span></span>
  
<span data-ttu-id="c020b-133">Como um exemplo adicional, suponha que você tenha anteriormente atribuído a Alex a política FederationAndPICDefault e agora já alterou sua mente e gostaria que ele fosse gerenciado pela política de acesso externo global.</span><span class="sxs-lookup"><span data-stu-id="c020b-133">As an additional example, suppose you've previously assigned Alex the FederationAndPICDefault policy and now you've changed your mind and would like him to be managed by the global external access policy.</span></span> <span data-ttu-id="c020b-134">Você não pode atribuir explicitamente a política global a qualquer pessoa.</span><span class="sxs-lookup"><span data-stu-id="c020b-134">You can't explicitly assign the global policy to anyone.</span></span> <span data-ttu-id="c020b-135">Em vez disso, a política global é usada para um determinado usuário se nenhuma política por usuário é atribuída a esse usuário.</span><span class="sxs-lookup"><span data-stu-id="c020b-135">Instead, the global policy is used for a given user if no per-user policy is assigned to that user.</span></span> <span data-ttu-id="c020b-136">Portanto, se quisermos que Alex seja gerenciado pela política global, você precisará  *cancelar a atribuição*  de qualquer política por usuário atribuída anteriormente a ele.</span><span class="sxs-lookup"><span data-stu-id="c020b-136">Therefore, if we want Alex to be managed by the global policy, you need to  *unassign*  any per-user policy previously assigned to him.</span></span> <span data-ttu-id="c020b-137">Este é um exemplo de comando:</span><span class="sxs-lookup"><span data-stu-id="c020b-137">Here is an example command:</span></span>
  
```powershell
Grant-CsExternalAccessPolicy -Identity "Alex Darrow" -PolicyName $Null
```

<span data-ttu-id="c020b-138">Este comando define o nome da política de acesso externo atribuída a Alex como um valor nulo ($Null).</span><span class="sxs-lookup"><span data-stu-id="c020b-138">This command sets the name of the external access policy assigned to Alex to a null value ($Null).</span></span> <span data-ttu-id="c020b-139">NULL significa "Nothing".</span><span class="sxs-lookup"><span data-stu-id="c020b-139">Null means "nothing".</span></span> <span data-ttu-id="c020b-140">Em outras palavras, nenhuma política de acesso externo é atribuída a Alex.</span><span class="sxs-lookup"><span data-stu-id="c020b-140">In other words, no external access policy is assigned to Alex.</span></span> <span data-ttu-id="c020b-141">Quando nenhuma política de acesso externo é atribuída a um usuário, esse usuário é gerenciado pela política global.</span><span class="sxs-lookup"><span data-stu-id="c020b-141">When no external access policy is assigned to a user, that user then gets managed by the global policy.</span></span>
  

## <a name="managing-large-numbers-of-users"></a><span data-ttu-id="c020b-142">Gerenciando um grande número de usuários</span><span class="sxs-lookup"><span data-stu-id="c020b-142">Managing large numbers of users</span></span>

<span data-ttu-id="c020b-143">Para gerenciar grandes números de usuários (1000 ou mais), você precisa em lotes os comandos por meio de um bloco de script usando o cmdlet [Invoke-Command](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/invoke-command?view=powershell-7) .</span><span class="sxs-lookup"><span data-stu-id="c020b-143">To manage large numbers of users (1000 or more), you need to batch the commands via a script block using the [Invoke-Command](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/invoke-command?view=powershell-7) cmdlet.</span></span>  <span data-ttu-id="c020b-144">Nos exemplos anteriores, cada vez que um cmdlet é executado, ele deve configurar a chamada e, em seguida, aguardar o resultado antes de enviá-lo de volta.</span><span class="sxs-lookup"><span data-stu-id="c020b-144">In previous examples, each time a cmdlet is executed, it must set up the call and then wait for the result before sending it back.</span></span>  <span data-ttu-id="c020b-145">Ao usar um bloco de script, isso permite que os cmdlets sejam executados remotamente e, depois de concluídos, enviem os dados de volta.</span><span class="sxs-lookup"><span data-stu-id="c020b-145">When using a script block, this allows the cmdlets to be executed remotely, and once completed, send the data back.</span></span> 

```powershell
Import-Module LyncOnlineConnector
$sfbSession = New-CsOnlineSession
$users = Get-CsOnlineUser -Filter { ClientPolicy -eq $null } -ResultSize 500

$batch = 50
$filter = ''
$total = $users.Count
$count = 0
    $users | ForEach-Object {
    $upn = $_.UserPrincipalName
    $filter += "(UserPrincipalName -eq '$upn')"
    $batch--
    $count++
    if (($batch -eq 0) -or ($count -eq $total)) {
        $filterSB=[ScriptBlock]::Create($filter)
        Invoke-Command -Session $s -ScriptBlock {param($f) Get-CsOnlineUser -filter $f | Grant-CsClientPolicy -PolicyName "ClientPolicyNoIMURL" -Passthru | Grant-CsExternalAccessPolicy -PolicyName "FederationAndPICDefault"} -ArgumentList $filterSB

        # Reset
        $batch = 50
        $filter = ''
    } else {
        $filter += " -or "
    }
}
```

<span data-ttu-id="c020b-146">Isso encontrará 500 usuários por vez que não têm uma política de cliente.</span><span class="sxs-lookup"><span data-stu-id="c020b-146">This will find 500 users at a time who do not have a client policy.</span></span> <span data-ttu-id="c020b-147">Ele concederá a eles a política de cliente "ClientPolicyNoIMURL" e a política de acesso externo "FederationAndPicDefault".</span><span class="sxs-lookup"><span data-stu-id="c020b-147">It will grant them the client policy "ClientPolicyNoIMURL" and the external access policy "FederationAndPicDefault".</span></span> <span data-ttu-id="c020b-148">Os resultados são enviados em lotes em grupos de 50 e cada lote de 50 é enviado para a máquina remota.</span><span class="sxs-lookup"><span data-stu-id="c020b-148">The results are batched into groups of 50 and each batch of 50 is then sent to the remote machine.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="c020b-149">Confira também</span><span class="sxs-lookup"><span data-stu-id="c020b-149">See also</span></span>

[<span data-ttu-id="c020b-150">Gerenciar o Skype for Business Online com o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c020b-150">Manage Skype for Business Online with PowerShell</span></span>](manage-skype-for-business-online-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="c020b-151">Gerenciar o Microsoft 365 com o PowerShell</span><span class="sxs-lookup"><span data-stu-id="c020b-151">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="c020b-152">Introdução ao PowerShell para o Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="c020b-152">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
