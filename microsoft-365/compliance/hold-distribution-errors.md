---
title: Resolver erros de retenção da descoberta eletrônica
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
description: Solucionar erros relacionados a rescisões legais aplicadas a custodiantes e fontes de dados não custodiais na Descoberta Principal.
ms.openlocfilehash: b101bf92c6a304262b3886a4ce0280f427a4a847
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538466"
---
# <a name="troubleshoot-ediscovery-hold-errors"></a><span data-ttu-id="0c27d-103">Resolver erros de retenção da descoberta eletrônica</span><span class="sxs-lookup"><span data-stu-id="0c27d-103">Troubleshoot eDiscovery hold errors</span></span>

<span data-ttu-id="0c27d-104">Este artigo discute problemas comuns que podem ocorrer com resites de Descoberta e como resolvê-los.</span><span class="sxs-lookup"><span data-stu-id="0c27d-104">This article discusses common issues that may occur with eDiscovery holds and how to resolve them.</span></span> <span data-ttu-id="0c27d-105">O artigo também inclui práticas recomendadas para ajudá-lo a mitigar ou evitar esses problemas.</span><span class="sxs-lookup"><span data-stu-id="0c27d-105">The article also includes recommended practices to help you mitigate or avoid these issues.</span></span>

## <a name="recommended-practices"></a><span data-ttu-id="0c27d-106">Práticas recomendadas</span><span class="sxs-lookup"><span data-stu-id="0c27d-106">Recommended practices</span></span>

<span data-ttu-id="0c27d-107">Para reduzir o número de erros relacionados a ressarções de Descoberta e, recomendamos as seguintes práticas:</span><span class="sxs-lookup"><span data-stu-id="0c27d-107">To reduce the number of errors related to eDiscovery holds, we recommend the following practices:</span></span>

- <span data-ttu-id="0c27d-108">Se uma distribuição de espera ainda estiver pendente, com um status de ou , aguarde até que a distribuição de espera seja concluída antes de fazer `On (Pending)` `Off (Pending)` outras atualizações.</span><span class="sxs-lookup"><span data-stu-id="0c27d-108">If a hold distribution is still pending, with a status of either `On (Pending)` or `Off (Pending)`, wait until the hold distribution is complete before you make any further updates.</span></span>

- <span data-ttu-id="0c27d-109">Verifique se uma política de espera está pendente antes de fazer outras atualizações.</span><span class="sxs-lookup"><span data-stu-id="0c27d-109">Check whether a hold policy is pending before you make any further updates to it.</span></span> <span data-ttu-id="0c27d-110">Execute os comandos a seguir ou salve-os em um script do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0c27d-110">Run the following commands or save them to a PowerShell script.</span></span>

    ```powershell
    $status = Get-CaseHoldPolicy -Identity <policyname> 
    if($status.DistributionStatus -ne "Pending"){
        # policy no longer pending
        Set-CaseHoldPolicy -Identity <policyname> -AddExchangeLocation $user1
    }else{
        # policy still pending
        Write-Host "Hold policy still pending."
    }
   ```

- <span data-ttu-id="0c27d-111">Mesclar suas atualizações a uma parada de Descoberta Automática em uma única solicitação em massa, em vez de atualizar a política de espera repetidamente para cada transação.</span><span class="sxs-lookup"><span data-stu-id="0c27d-111">Merge your updates to an eDiscovery hold in a single bulk request rather than updating the hold policy repeatedly for each transaction.</span></span> <span data-ttu-id="0c27d-112">Por exemplo, para adicionar várias caixas de correio de usuário a uma política de bloqueio existente usando o cmdlet [Set-CaseHoldPolicy,](/powershell/module/exchange/set-caseholdpolicy) execute o comando (ou adicione como um bloco de código a um script) para que ele seja executado apenas uma vez para adicionar vários usuários.</span><span class="sxs-lookup"><span data-stu-id="0c27d-112">For example, to add multiple user mailboxes to an existing hold policy using the [Set-CaseHoldPolicy](/powershell/module/exchange/set-caseholdpolicy) cmdlet, run the command (or add as a code block to a script) so that it runs only once to add multiple users.</span></span>

  <span data-ttu-id="0c27d-113">**Correto**</span><span class="sxs-lookup"><span data-stu-id="0c27d-113">**Correct**</span></span>

    ```powershell
    Set-CaseHoldPolicy -Identity <policyname> -AddExchangeLocation {$user1, $user2, $user3, $user4, $user5}
    ```

   <span data-ttu-id="0c27d-114">**Incorreto**</span><span class="sxs-lookup"><span data-stu-id="0c27d-114">**Incorrect**</span></span>

    ```powershell
    $users = {$user1, $user2, $user3, $user4, $user5}
    ForEach($user in $users)
    {
        Set-CaseHoldPolicy -Identity <policyname> -AddExchangeLocation $user
    }
    ```

   <span data-ttu-id="0c27d-115">No exemplo incorreto anterior, o cmdlet é executado cinco vezes separadamente para concluir a tarefa.</span><span class="sxs-lookup"><span data-stu-id="0c27d-115">In the previous incorrect example, the cmdlet is run five separate times to complete the task.</span></span> <span data-ttu-id="0c27d-116">Para obter mais informações sobre as práticas recomendadas para adicionar usuários a uma política de espera, consulte a [seção Mais](#more-information) informações.</span><span class="sxs-lookup"><span data-stu-id="0c27d-116">For more information about the recommended practices for adding users to a hold policy, see the [More information](#more-information) section.</span></span>

- <span data-ttu-id="0c27d-117">Antes de entrar em contato com o Suporte da Microsoft sobre problemas de responsabilidade de Descoberta eDiscovery, siga as etapas na seção [Erro/problema:](#errorissue-holds-dont-sync) Retém não sincronizar para tentar novamente a distribuição de espera.</span><span class="sxs-lookup"><span data-stu-id="0c27d-117">Before contacting Microsoft Support about eDiscovery hold issues, follow the steps in the [Error/issue: Holds don't sync](#errorissue-holds-dont-sync) section to retry the hold distribution.</span></span> <span data-ttu-id="0c27d-118">Esse processo geralmente resolve problemas temporários, incluindo erros internos do servidor.</span><span class="sxs-lookup"><span data-stu-id="0c27d-118">This process often resolves temporary issues including, internal server errors.</span></span>

## <a name="errorissue-holds-dont-sync"></a><span data-ttu-id="0c27d-119">Erro/problema: retém não sincronizar</span><span class="sxs-lookup"><span data-stu-id="0c27d-119">Error/issue: Holds don't sync</span></span>

<span data-ttu-id="0c27d-120">Se você vir uma das seguintes mensagens de erro ao colocar os custodiantes e fontes de dados em espera, use as etapas de resolução para solucionar o problema.</span><span class="sxs-lookup"><span data-stu-id="0c27d-120">If you see one the following error messages when putting custodians and data sources on hold, use the resolution steps to troubleshoot the issue.</span></span>

> <span data-ttu-id="0c27d-121">Recursos: está demorando mais do que o esperado para implantar a política.</span><span class="sxs-lookup"><span data-stu-id="0c27d-121">Resources: It's taking longer than expected to deploy the policy.</span></span> <span data-ttu-id="0c27d-122">Pode levar mais duas horas para atualizar o status final da implantação, portanto, volte em algumas horas.</span><span class="sxs-lookup"><span data-stu-id="0c27d-122">It might take an additional 2 hours to update the final deployment status, so check back in a couple hours.</span></span>

> <span data-ttu-id="0c27d-123">A política não pode ser implantada na fonte de conteúdo devido a um problema Office 365 datacenter temporário.</span><span class="sxs-lookup"><span data-stu-id="0c27d-123">Policy cannot be deployed to the content source due to a temporary Office 365 datacenter issue.</span></span> <span data-ttu-id="0c27d-124">A política atual não é aplicada a qualquer conteúdo na origem, portanto, não há impacto da implantação bloqueada.</span><span class="sxs-lookup"><span data-stu-id="0c27d-124">The current policy is not applied to any content in the source, so there's no impact from the blocked deployment.</span></span> <span data-ttu-id="0c27d-125">Para corrigir esse problema, tente reimplantar a política.</span><span class="sxs-lookup"><span data-stu-id="0c27d-125">To fix this issue, please try redeploying the policy.</span></span>

> <span data-ttu-id="0c27d-126">Não foi possível executar as alterações solicitadas na política devido a um erro de servidor interno transitório.</span><span class="sxs-lookup"><span data-stu-id="0c27d-126">Sorry, we could not perform the requested changes to policy due to a transient internal server error.</span></span> <span data-ttu-id="0c27d-127">Tente novamente em 30 minutos.</span><span class="sxs-lookup"><span data-stu-id="0c27d-127">Please try again in 30 minutes.</span></span>

### <a name="resolution"></a><span data-ttu-id="0c27d-128">Resolução</span><span class="sxs-lookup"><span data-stu-id="0c27d-128">Resolution</span></span>

1. <span data-ttu-id="0c27d-129">Conexão ao [Centro de Conformidade & Segurança](/powershell/exchange/connect-to-scc-powershell) do PowerShell e execute o seguinte comando para uma ressarção de Descoberta Digital:</span><span class="sxs-lookup"><span data-stu-id="0c27d-129">Connect to [Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell) and run the following command for an eDiscovery hold:</span></span>

   ```powershell
   Get-CaseHoldPolicy <policyname> -DistributionDetail | FL
   ```

2. <span data-ttu-id="0c27d-130">Examine o valor no parâmetro *DistributionDetail.*</span><span class="sxs-lookup"><span data-stu-id="0c27d-130">Examine the value in the *DistributionDetail* parameter.</span></span> <span data-ttu-id="0c27d-131">Procure erros como o seguinte:</span><span class="sxs-lookup"><span data-stu-id="0c27d-131">Look for errors like the following:</span></span>

   > <span data-ttu-id="0c27d-132">Erro: Recursos: está demorando mais do que o esperado para implantar a política.</span><span class="sxs-lookup"><span data-stu-id="0c27d-132">Error: Resources: It's taking longer than expected to deploy the policy.</span></span> <span data-ttu-id="0c27d-133">Pode levar mais duas horas para atualizar o status final da implantação, portanto, volte em algumas horas.</span><span class="sxs-lookup"><span data-stu-id="0c27d-133">It might take an additional 2 hours to update the final deployment status, so check back in a couple hours.</span></span>

3. <span data-ttu-id="0c27d-134">Tente executar o **comando Set-CaseHoldPolicy -RetryDistribution** na política de espera em questão; por exemplo:</span><span class="sxs-lookup"><span data-stu-id="0c27d-134">Try running the **Set-CaseHoldPolicy -RetryDistribution** command on the hold policy in question; for example:</span></span>

   ```powershell
   Set-CaseHoldPolicy <policyname> -RetryDistribution
   ```

## <a name="error-the-sharepoint-site-is-read-only-or-not-accessible"></a><span data-ttu-id="0c27d-135">Erro: o SharePoint site é somente leitura ou não acessível</span><span class="sxs-lookup"><span data-stu-id="0c27d-135">Error: The SharePoint site is read-only or not accessible</span></span>

<span data-ttu-id="0c27d-136">Se você vir a seguinte mensagem de erro ao colocar os custodiantes e fontes de dados em espera, isso significa que o administrador global da sua organização ou SharePoint [o](/sharepoint/sharepoint-admin-role) site foi bloqueado.</span><span class="sxs-lookup"><span data-stu-id="0c27d-136">If you see the following error message when putting custodians and data sources on hold, it means that your organization's [global admin or SharePoint admin](/sharepoint/sharepoint-admin-role) has locked the site.</span></span> <span data-ttu-id="0c27d-137">Um site bloqueado bloqueia a Descoberta Interna de colocar uma bloqueio no site.</span><span class="sxs-lookup"><span data-stu-id="0c27d-137">A locked site blocks eDiscovery from placing a hold on the site.</span></span>

> <span data-ttu-id="0c27d-138">O SharePoint site é somente leitura ou não acessível.</span><span class="sxs-lookup"><span data-stu-id="0c27d-138">The SharePoint site is read-only or not accessible.</span></span> <span data-ttu-id="0c27d-139">Entre em contato com o administrador do site para tornar o site writable e reimplantar essa política.</span><span class="sxs-lookup"><span data-stu-id="0c27d-139">Please contact the site administrator to make the site writable, and then redeploy this policy.</span></span>

### <a name="resolution"></a><span data-ttu-id="0c27d-140">Resolução</span><span class="sxs-lookup"><span data-stu-id="0c27d-140">Resolution</span></span>

<span data-ttu-id="0c27d-141">Desbloqueie o site (ou peça a um administrador para desbloqueá-lo) para resolver esse problema.</span><span class="sxs-lookup"><span data-stu-id="0c27d-141">Unlock the site (or ask an admin to unlock it) to resolve this issue.</span></span> <span data-ttu-id="0c27d-142">Para saber mais sobre como alterar o estado de bloqueio de um site, consulte [Bloquear e desbloquear sites](/sharepoint/manage-lock-status).</span><span class="sxs-lookup"><span data-stu-id="0c27d-142">To learn more about how to change the lock state for a site, see [Lock and unlock sites](/sharepoint/manage-lock-status).</span></span>

## <a name="error-the-mailbox-or-sharepoint-site-may-not-exist"></a><span data-ttu-id="0c27d-143">Erro: a caixa de correio ou SharePoint site pode não existir</span><span class="sxs-lookup"><span data-stu-id="0c27d-143">Error: The mailbox or SharePoint site may not exist</span></span>

<span data-ttu-id="0c27d-144">Se você vir a seguinte mensagem de erro ao colocar os custodiantes e fontes de dados em espera, use as etapas de resolução para solucionar o problema.</span><span class="sxs-lookup"><span data-stu-id="0c27d-144">If you see the following error message when putting custodians and data sources on hold, use the resolution steps to troubleshoot the issue.</span></span>

> <span data-ttu-id="0c27d-145">A caixa de correio ou SharePoint site pode não existir.</span><span class="sxs-lookup"><span data-stu-id="0c27d-145">The mailbox or SharePoint site may not exist.</span></span>  <span data-ttu-id="0c27d-146">Se estiver incorreto, entre em contato com o suporte da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="0c27d-146">If this is incorrect, please contact Microsoft support.</span></span>  <span data-ttu-id="0c27d-147">Caso contrário, remova-o desta política.</span><span class="sxs-lookup"><span data-stu-id="0c27d-147">Otherwise, please remove it from this policy.</span></span>

### <a name="resolution"></a><span data-ttu-id="0c27d-148">Resolução</span><span class="sxs-lookup"><span data-stu-id="0c27d-148">Resolution</span></span>

- <span data-ttu-id="0c27d-149">Execute o [Get-Mailbox](/powershell/module/exchange/get-mailbox) no Exchange Online PowerShell para verificar se a caixa de correio do usuário existe em sua organização.</span><span class="sxs-lookup"><span data-stu-id="0c27d-149">Run the [Get-Mailbox](/powershell/module/exchange/get-mailbox) in Exchange Online PowerShell to check if the user mailbox exists in your organization.</span></span>

- <span data-ttu-id="0c27d-150">Execute o cmdlet [Get-SPOSite](/powershell/module/sharepoint-online/get-sposite) no SharePoint PowerShell Online para verificar se o site existe em sua organização.</span><span class="sxs-lookup"><span data-stu-id="0c27d-150">Run the [Get-SPOSite](/powershell/module/sharepoint-online/get-sposite) cmdlet in SharePoint Online PowerShell to check if the site exists in your organization.</span></span>

- <span data-ttu-id="0c27d-151">Verifique se a URL do site foi alterada.</span><span class="sxs-lookup"><span data-stu-id="0c27d-151">Check to see if the site URL has changed.</span></span>

## <a name="more-information"></a><span data-ttu-id="0c27d-152">Mais informações</span><span class="sxs-lookup"><span data-stu-id="0c27d-152">More information</span></span>

<span data-ttu-id="0c27d-153">As diretrizes sobre a atualização de políticas de bloqueio para vários usuários na seção "Práticas recomendadas" resulta do fato de que o sistema bloqueia atualizações simultâneas para uma política de bloqueio.</span><span class="sxs-lookup"><span data-stu-id="0c27d-153">The guidance about updating hold policies for multiple users in the "Recommended practices" section results from the fact that the system blocks simultaneous updates to a hold policy.</span></span> <span data-ttu-id="0c27d-154">Isso significa que, quando uma política de espera atualizada é aplicada a novos locais de conteúdo e a política de espera está em um estado pendente, locais de conteúdo adicionais não podem ser adicionados à política de espera.</span><span class="sxs-lookup"><span data-stu-id="0c27d-154">That means when an updated hold policy is applied to new content locations and the hold policy is in a pending state, additional content locations can't be added to the hold policy.</span></span> <span data-ttu-id="0c27d-155">Aqui estão algumas coisas a ter em mente para ajudá-lo a atenuar esse problema:</span><span class="sxs-lookup"><span data-stu-id="0c27d-155">Here are some things to keep in mind to help you mitigate this issue:</span></span>
  
- <span data-ttu-id="0c27d-156">Sempre que uma espera atualizada é atualizada, ela entra imediatamente em um estado pendente.</span><span class="sxs-lookup"><span data-stu-id="0c27d-156">Every time a hold updated is updated, it immediately goes into a pending state.</span></span> <span data-ttu-id="0c27d-157">O status de estado pendente significa que a ressarção está sendo aplicada a locais de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="0c27d-157">The pending state status means the hold is being applied to content locations.</span></span>
  
- <span data-ttu-id="0c27d-158">Se você tiver um script que executa um loop e adiciona locais à política um a um (semelhante ao exemplo incorreto mostrado na seção "Práticas Recomendadas"), o primeiro local de conteúdo (por exemplo, uma caixa de correio de usuário) iniciará o processo de sincronização que dispara o estado pendente.</span><span class="sxs-lookup"><span data-stu-id="0c27d-158">If you have a script that runs a loop and adds locations to policy one by one (similar to the incorrect example shown in the "Recommended practices" section), the first content location (for example, a user mailbox) initiates the sync process that triggers the pending state.</span></span> <span data-ttu-id="0c27d-159">Isso significa que os outros usuários adicionados à política em loops subsequentes resultam em um erro.</span><span class="sxs-lookup"><span data-stu-id="0c27d-159">That means the other users that are added to the policy in subsequent loops result in an error.</span></span>
  
- <span data-ttu-id="0c27d-160">Se sua organização estiver usando um script que executa um loop para atualizar os locais de conteúdo de uma política de espera, você deve atualizar o script para que ele atualize os locais em uma única operação em massa (conforme mostrado no exemplo correto na seção "Práticas Recomendadas").</span><span class="sxs-lookup"><span data-stu-id="0c27d-160">If your organization is using a script that runs a loop to update the content locations for a hold policy, you must update the script so that it updates locations in a single bulk operation (as shown in the correct example in the "Recommended practices" section).</span></span>
