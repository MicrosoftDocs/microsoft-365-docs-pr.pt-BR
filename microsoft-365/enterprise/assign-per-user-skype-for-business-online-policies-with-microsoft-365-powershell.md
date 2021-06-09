---
title: Atribuir políticas online Skype for Business por usuário com o PowerShell para Microsoft 365
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
description: 'Resumo: use o PowerShell para Microsoft 365 para atribuir configurações de comunicação por usuário com Skype for Business online.'
ms.openlocfilehash: 2d3d953fe0beb74cc63f914137942f068ce90be7
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905399"
---
# <a name="assign-per-user-skype-for-business-online-policies-with-powershell-for-microsoft-365"></a><span data-ttu-id="d575d-103">Atribuir políticas online Skype for Business por usuário com o PowerShell para Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="d575d-103">Assign per-user Skype for Business Online policies with PowerShell for Microsoft 365</span></span>

<span data-ttu-id="d575d-104">*Esse artigo se aplica ao Microsoft 365 Enterprise e ao Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="d575d-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="d575d-105">Usar o PowerShell para Microsoft 365 é uma maneira eficiente de atribuir configurações de comunicação por usuário com Skype for Business online.</span><span class="sxs-lookup"><span data-stu-id="d575d-105">Using PowerShell for Microsoft 365 is an efficient way to assign per-user communication settings with Skype for Business Online policies.</span></span>
  
## <a name="prepare-to-run-the-powershell-commands"></a><span data-ttu-id="d575d-106">Preparar para executar os comandos do PowerShell</span><span class="sxs-lookup"><span data-stu-id="d575d-106">Prepare to run the PowerShell commands</span></span>

<span data-ttu-id="d575d-107">Use estas instruções para configurar para executar os comandos (pule as etapas que você já concluiu):</span><span class="sxs-lookup"><span data-stu-id="d575d-107">Use these instructions to get set up to run the commands (skip the steps you have already completed):</span></span>
  
  > [!Note]
   > <span data-ttu-id="d575d-108">O Conector Skype for Business Online atualmente faz parte do módulo mais recente do PowerShell do Teams.</span><span class="sxs-lookup"><span data-stu-id="d575d-108">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span> <span data-ttu-id="d575d-109">Se você estiver usando o último lançamento público do PowerShell Teams, você não precisa instalar o Conector do Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="d575d-109">If you're using the latest Teams PowerShell public release, you don't need to install the Skype for Business Online Connector.</span></span>

1. <span data-ttu-id="d575d-110">Instale o [módulo PowerShell do Teams](/microsoftteams/teams-powershell-install).</span><span class="sxs-lookup"><span data-stu-id="d575d-110">Install the [Teams PowerShell module](/microsoftteams/teams-powershell-install).</span></span>
    
2. <span data-ttu-id="d575d-111">Abra um prompt de comando do Windows PowerShell e execute os seguintes comandos:</span><span class="sxs-lookup"><span data-stu-id="d575d-111">Open a Windows PowerShell command prompt and run the following commands:</span></span> 
    
   ```powershell
   Import-Module MicrosoftTeams
   Connect-MicrosoftTeams
   ```

   <span data-ttu-id="d575d-112">Quando solicitado, digite o nome e a senha Skype for Business conta de administrador online.</span><span class="sxs-lookup"><span data-stu-id="d575d-112">When prompted, enter your Skype for Business Online administrator account name and password.</span></span>
    
## <a name="updating-external-communication-settings-for-a-user-account"></a><span data-ttu-id="d575d-113">Atualizando as configurações de comunicação externa para uma conta de usuário</span><span class="sxs-lookup"><span data-stu-id="d575d-113">Updating external communication settings for a user account</span></span>

<span data-ttu-id="d575d-114">Suponha que você queira alterar as configurações de comunicação externa em uma conta de usuário.</span><span class="sxs-lookup"><span data-stu-id="d575d-114">Suppose you want to change external communication settings on a user account.</span></span> <span data-ttu-id="d575d-115">Por exemplo, você deseja permitir que Alex se comunique com usuários federados (EnableFederationAccess é igual a True), mas não com usuários do Windows Live (EnablePublicCloudAccess é igual a False).</span><span class="sxs-lookup"><span data-stu-id="d575d-115">For example, you want to allow Alex to communicate with federated users (EnableFederationAccess is equal to True) but not with Windows Live users (EnablePublicCloudAccess equals False).</span></span> <span data-ttu-id="d575d-116">Para fazer isso, você precisa fazer duas coisas:</span><span class="sxs-lookup"><span data-stu-id="d575d-116">To do that, you need to do two things:</span></span>
  
1. <span data-ttu-id="d575d-117">Localizar uma política de acesso externo que atenda aos nossos critérios.</span><span class="sxs-lookup"><span data-stu-id="d575d-117">Find an external access policy that meets our criteria.</span></span>
    
2. <span data-ttu-id="d575d-118">Atribuir essa política de acesso externo a Antônio.</span><span class="sxs-lookup"><span data-stu-id="d575d-118">Assign that external access policy to Alex.</span></span>
    
<span data-ttu-id="d575d-119">Como determinar qual política de acesso externo atribuirá a Alex?</span><span class="sxs-lookup"><span data-stu-id="d575d-119">How do you determine which external access policy to assign Alex?</span></span> <span data-ttu-id="d575d-120">O comando a seguir retorna todas as políticas de acesso externo em que EnableFederationAccess é definido como True e EnablePublicCloudAccess como False:</span><span class="sxs-lookup"><span data-stu-id="d575d-120">The following command returns all the external access policies where EnableFederationAccess is set to True and EnablePublicCloudAccess is set to False:</span></span>
  
```powershell
Get-CsExternalAccessPolicy -Include All| Where-Object {$_.EnableFederationAccess -eq $True -and $_.EnablePublicCloudAccess -eq $False}
```

<span data-ttu-id="d575d-121">A menos que você tenha criado quaisquer instâncias personalizadas de ExternalAccessPolicy, esse comando retornará uma política que atenda aos nossos critérios (FederationOnly).</span><span class="sxs-lookup"><span data-stu-id="d575d-121">Unless you have created any custom instances of ExternalAccessPolicy, that command returns one policy that meets our criteria (FederationOnly).</span></span> <span data-ttu-id="d575d-122">Veja um exemplo:</span><span class="sxs-lookup"><span data-stu-id="d575d-122">Here is an example:</span></span>
  
```powershell
Identity                          : Tag:FederationOnly
Description                       :
EnableFederationAccess            : True
EnableXmppAccess                  : False
EnablePublicCloudAccess           : False
EnablePublicCloudAudioVideoAccess : False
EnableOutsideAccess               : True
```

<span data-ttu-id="d575d-123">Agora que você sabe qual política atribuir a Alex, podemos atribuir essa política usando o cmdlet [Grant-CsExternalAccessPolicy.](/powershell/module/skype/Get-CsExternalAccessPolicy)</span><span class="sxs-lookup"><span data-stu-id="d575d-123">Now that you know which policy to assign to Alex, we can assign that policy by using the [Grant-CsExternalAccessPolicy](/powershell/module/skype/Get-CsExternalAccessPolicy) cmdlet.</span></span> <span data-ttu-id="d575d-124">Veja um exemplo:</span><span class="sxs-lookup"><span data-stu-id="d575d-124">Here is an example:</span></span>
  
```powershell
Grant-CsExternalAccessPolicy -Identity "Alex Darrow" -PolicyName "FederationOnly"
```

<span data-ttu-id="d575d-125">Atribuir uma política é muito simples: basta especificar a Identidade do usuário e o nome da política a ser atribuída.</span><span class="sxs-lookup"><span data-stu-id="d575d-125">Assigning a policy is pretty simple: you simply specify the Identity of the user and the name of the policy to be assigned.</span></span> 
  
<span data-ttu-id="d575d-126">E quando se trata de políticas e atribuições de política, você não está limitado a trabalhar com contas de usuário uma vez por vez.</span><span class="sxs-lookup"><span data-stu-id="d575d-126">And when it comes to policies and policy assignments, you're not limited to working with user accounts one a time.</span></span> <span data-ttu-id="d575d-127">Por exemplo, suponha que você precise de uma lista de todos os usuários que têm permissão para se comunicar com parceiros federados e com usuários do Windows Live.</span><span class="sxs-lookup"><span data-stu-id="d575d-127">For example, suppose you need a list of all the users who are allowed to communicate with federated partners and with Windows Live users.</span></span> <span data-ttu-id="d575d-128">Já sabemos que esses usuários foram atribuídos à política de acesso de usuário externo FederationAndPICDefault.</span><span class="sxs-lookup"><span data-stu-id="d575d-128">We already know that those users have been assigned the external user access policy FederationAndPICDefault.</span></span> <span data-ttu-id="d575d-129">Como sabemos disso, você pode exibir uma lista de todos esses usuários executando um comando simples.</span><span class="sxs-lookup"><span data-stu-id="d575d-129">Because we know that, you can display a list of all those users by running one simple command.</span></span> <span data-ttu-id="d575d-130">Este é o comando:</span><span class="sxs-lookup"><span data-stu-id="d575d-130">Here is the command:</span></span>
  
```powershell
Get-CsOnlineUser -Filter {ExternalAccessPolicy -eq "FederationAndPICDefault"} | Select-Object DisplayName
```

<span data-ttu-id="d575d-131">Em outras palavras, isso nos mostra todos os usuários cuja propriedade ExternalAccessPolicy está definida como FederationAndPICDefault.</span><span class="sxs-lookup"><span data-stu-id="d575d-131">In other words, show us all the users where the ExternalAccessPolicy property is set to FederationAndPICDefault.</span></span> <span data-ttu-id="d575d-132">(E, para limitar a quantidade de informações exibidas na tela, use o cmdlet Select-Object para exibir apenas o nome de exibição de cada usuário.)</span><span class="sxs-lookup"><span data-stu-id="d575d-132">(And, in order to limit the amount of information that appears onscreen, use the Select-Object cmdlet to display show us only each user's display name.)</span></span> 
  
<span data-ttu-id="d575d-133">Para configurar todas as nossas contas de usuário para usar essa mesma política, use este comando:</span><span class="sxs-lookup"><span data-stu-id="d575d-133">To configure all our user accounts to use that same policy, use this command:</span></span>
  
```powershell
Get-CsOnlineUser | Grant-CsExternalAccessPolicy "FederationAndPICDefault"
```

<span data-ttu-id="d575d-134">Este comando usa Get-CsOnlineUser para retornar uma coleção de todos os usuários que foram habilitados para o Lync e envia todas essas informações para Grant-CsExternalAccessPolicy, que atribui a política FederationAndPICDefault a cada usuário na coleção.</span><span class="sxs-lookup"><span data-stu-id="d575d-134">This command uses Get-CsOnlineUser to return a collection of all the users who have been enabled for Lync, then sends all that information to Grant-CsExternalAccessPolicy, which assigns the FederationAndPICDefault policy to each and every user in the collection.</span></span>
  
<span data-ttu-id="d575d-135">Como exemplo adicional, suponha que você tenha atribuído anteriormente a Alex a política FederationAndPICDefault e agora você mudou de ideia e gostaria que ele fosse gerenciado pela política de acesso externo global.</span><span class="sxs-lookup"><span data-stu-id="d575d-135">As an additional example, suppose you've previously assigned Alex the FederationAndPICDefault policy and now you've changed your mind and would like him to be managed by the global external access policy.</span></span> <span data-ttu-id="d575d-136">Não é possível atribuir explicitamente a política global a ninguém.</span><span class="sxs-lookup"><span data-stu-id="d575d-136">You can't explicitly assign the global policy to anyone.</span></span> <span data-ttu-id="d575d-137">Em vez disso, a política global será usada para um determinado usuário se nenhuma política por usuário for atribuída a esse usuário.</span><span class="sxs-lookup"><span data-stu-id="d575d-137">Instead, the global policy is used for a given user if no per-user policy is assigned to that user.</span></span> <span data-ttu-id="d575d-138">Portanto, se quisermos que Alex seja gerenciado pela política global, você precisa  *desaignar*  qualquer política por usuário atribuída anteriormente a ele.</span><span class="sxs-lookup"><span data-stu-id="d575d-138">Therefore, if we want Alex to be managed by the global policy, you need to  *unassign*  any per-user policy previously assigned to him.</span></span> <span data-ttu-id="d575d-139">Este é um exemplo de comando:</span><span class="sxs-lookup"><span data-stu-id="d575d-139">Here is an example command:</span></span>
  
```powershell
Grant-CsExternalAccessPolicy -Identity "Alex Darrow" -PolicyName $Null
```

<span data-ttu-id="d575d-140">Este comando define o nome da política de acesso externo atribuída a Alex como um valor nulo ($Null).</span><span class="sxs-lookup"><span data-stu-id="d575d-140">This command sets the name of the external access policy assigned to Alex to a null value ($Null).</span></span> <span data-ttu-id="d575d-141">Null significa "nothing".</span><span class="sxs-lookup"><span data-stu-id="d575d-141">Null means "nothing".</span></span> <span data-ttu-id="d575d-142">Em outras palavras, nenhuma política de acesso externo é atribuída a Alex.</span><span class="sxs-lookup"><span data-stu-id="d575d-142">In other words, no external access policy is assigned to Alex.</span></span> <span data-ttu-id="d575d-143">Quando nenhuma política de acesso externo é atribuída a um usuário, esse usuário é gerenciado pela política global.</span><span class="sxs-lookup"><span data-stu-id="d575d-143">When no external access policy is assigned to a user, that user then gets managed by the global policy.</span></span>
  

## <a name="managing-large-numbers-of-users"></a><span data-ttu-id="d575d-144">Gerenciando um grande número de usuários</span><span class="sxs-lookup"><span data-stu-id="d575d-144">Managing large numbers of users</span></span>

<span data-ttu-id="d575d-145">Para gerenciar um grande número de usuários (1.000 ou mais), você precisa lotar os comandos por meio de um bloco de script usando o cmdlet [Invoke-Command.](/powershell/module/microsoft.powershell.core/invoke-command?view=powershell-7)</span><span class="sxs-lookup"><span data-stu-id="d575d-145">To manage large numbers of users (1000 or more), you need to batch the commands via a script block using the [Invoke-Command](/powershell/module/microsoft.powershell.core/invoke-command?view=powershell-7) cmdlet.</span></span>  <span data-ttu-id="d575d-146">Em exemplos anteriores, sempre que um cmdlet é executado, ele deve configurar a chamada e aguardar o resultado antes de enviá-la de volta.</span><span class="sxs-lookup"><span data-stu-id="d575d-146">In previous examples, each time a cmdlet is executed, it must set up the call and then wait for the result before sending it back.</span></span>  <span data-ttu-id="d575d-147">Ao usar um bloco de scripts, isso permite que os cmdlets sejam executados remotamente e, depois de concluídos, enviem os dados de volta.</span><span class="sxs-lookup"><span data-stu-id="d575d-147">When using a script block, this allows the cmdlets to be executed remotely, and once completed, send the data back.</span></span> 

```powershell
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

<span data-ttu-id="d575d-148">Isso encontrará 500 usuários por vez que não têm uma política de cliente.</span><span class="sxs-lookup"><span data-stu-id="d575d-148">This will find 500 users at a time who do not have a client policy.</span></span> <span data-ttu-id="d575d-149">Ele concederá a eles a política de cliente "ClientPolicyNoIMURL" e a política de acesso externo "FederationAndPicDefault".</span><span class="sxs-lookup"><span data-stu-id="d575d-149">It will grant them the client policy "ClientPolicyNoIMURL" and the external access policy "FederationAndPicDefault".</span></span> <span data-ttu-id="d575d-150">Os resultados são em lotes em grupos de 50 e cada lote de 50 é enviado para a máquina remota.</span><span class="sxs-lookup"><span data-stu-id="d575d-150">The results are batched into groups of 50 and each batch of 50 is then sent to the remote machine.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="d575d-151">Confira também</span><span class="sxs-lookup"><span data-stu-id="d575d-151">See also</span></span>

[<span data-ttu-id="d575d-152">Gerenciar o Skype for Business Online com o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="d575d-152">Manage Skype for Business Online with PowerShell</span></span>](manage-skype-for-business-online-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="d575d-153">Gerenciar o Microsoft 365 com o PowerShell</span><span class="sxs-lookup"><span data-stu-id="d575d-153">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="d575d-154">Introdução ao PowerShell para o Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="d575d-154">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)