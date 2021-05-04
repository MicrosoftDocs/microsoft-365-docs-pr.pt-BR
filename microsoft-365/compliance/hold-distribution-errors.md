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
ms.openlocfilehash: 3bd417f2eb6bfb8de8d4b5ccaeb48e6ae1c888eb
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/16/2021
ms.locfileid: "51860382"
---
# <a name="troubleshoot-ediscovery-hold-errors"></a><span data-ttu-id="8654a-103">Resolver erros de retenção da descoberta eletrônica</span><span class="sxs-lookup"><span data-stu-id="8654a-103">Troubleshoot eDiscovery hold errors</span></span>

<span data-ttu-id="8654a-104">Este artigo discute problemas comuns que podem ocorrer com resites de Descoberta e como resolvê-los.</span><span class="sxs-lookup"><span data-stu-id="8654a-104">This article discusses common issues that may occur with eDiscovery holds and how to resolve them.</span></span> <span data-ttu-id="8654a-105">O artigo também inclui práticas recomendadas para ajudá-lo a mitigar ou evitar esses problemas.</span><span class="sxs-lookup"><span data-stu-id="8654a-105">The article also includes recommended practices to help you mitigate or avoid these issues.</span></span>

## <a name="recommended-practices"></a><span data-ttu-id="8654a-106">Práticas recomendadas</span><span class="sxs-lookup"><span data-stu-id="8654a-106">Recommended practices</span></span>

<span data-ttu-id="8654a-107">Para reduzir o número de erros relacionados a ressarções de Descoberta e, recomendamos as seguintes práticas:</span><span class="sxs-lookup"><span data-stu-id="8654a-107">To reduce the number of errors related to eDiscovery holds, we recommend the following practices:</span></span>

- <span data-ttu-id="8654a-108">Se uma distribuição de espera ainda estiver pendente, com um status de ou , aguarde até que a distribuição de espera seja concluída antes de fazer `On (Pending)` `Off (Pending)` outras atualizações.</span><span class="sxs-lookup"><span data-stu-id="8654a-108">If a hold distribution is still pending, with a status of either `On (Pending)` or `Off (Pending)`, wait until the hold distribution is complete before you make any further updates.</span></span>

- <span data-ttu-id="8654a-109">Mesclar suas atualizações a uma parada de Descoberta Automática em uma única solicitação em massa, em vez de atualizar a política de espera repetidamente para cada transação.</span><span class="sxs-lookup"><span data-stu-id="8654a-109">Merge your updates to an eDiscovery hold in a single bulk request rather than updating the hold policy repeatedly for each transaction.</span></span> <span data-ttu-id="8654a-110">Por exemplo, para adicionar várias caixas de correio de usuário a uma política de bloqueio existente usando o cmdlet [Set-CaseHoldPolicy,](/powershell/module/exchange/set-caseholdpolicy) execute o comando (ou adicione como um bloco de código a um script) para que ele seja executado apenas uma vez para adicionar vários usuários.</span><span class="sxs-lookup"><span data-stu-id="8654a-110">For example, to add multiple user mailboxes to an existing hold policy using the [Set-CaseHoldPolicy](/powershell/module/exchange/set-caseholdpolicy) cmdlet, run the command (or add as a code block to a script) so that it runs only once to add multiple users.</span></span>

  <span data-ttu-id="8654a-111">**Correto**</span><span class="sxs-lookup"><span data-stu-id="8654a-111">**Correct**</span></span>

    ```powershell
    Set-CaseHoldPolicy -AddExchangeLocation {$user1, $user2, $user3, $user4, $user5}
    ```

   <span data-ttu-id="8654a-112">**Incorreto**</span><span class="sxs-lookup"><span data-stu-id="8654a-112">**Incorrect**</span></span>

    ```powershell
    $users = {$user1, $user2, $user3, $user4, $user5}
    ForEach($user in $users)
    {
        Set-CaseHoldPolicy -AddExchangeLocation $user
    }
    ```

   <span data-ttu-id="8654a-113">No exemplo incorreto anterior, o cmdlet é executado cinco vezes separadamente para concluir a tarefa.</span><span class="sxs-lookup"><span data-stu-id="8654a-113">In the previous incorrect example, the cmdlet is run five separate times to complete the task.</span></span> <span data-ttu-id="8654a-114">Para obter mais informações sobre as práticas recomendadas para adicionar usuários a uma política de espera, consulte a [seção Mais](#more-information) informações.</span><span class="sxs-lookup"><span data-stu-id="8654a-114">For more information about the recommended practices for adding users to a hold policy, see the [More information](#more-information) section.</span></span>

- <span data-ttu-id="8654a-115">Antes de entrar em contato com o Suporte da Microsoft sobre problemas de responsabilidade de Descoberta eDiscovery, siga as etapas na seção [Erro/problema:](#errorissue-holds-dont-sync) Retém não sincronizar para tentar novamente a distribuição de espera.</span><span class="sxs-lookup"><span data-stu-id="8654a-115">Before contacting Microsoft Support about eDiscovery hold issues, follow the steps in the [Error/issue: Holds don't sync](#errorissue-holds-dont-sync) section to retry the hold distribution.</span></span> <span data-ttu-id="8654a-116">Esse processo geralmente resolve problemas temporários, incluindo erros internos do servidor.</span><span class="sxs-lookup"><span data-stu-id="8654a-116">This process often resolves temporary issues including, internal server errors.</span></span>

## <a name="errorissue-holds-dont-sync"></a><span data-ttu-id="8654a-117">Erro/problema: retém não sincronizar</span><span class="sxs-lookup"><span data-stu-id="8654a-117">Error/issue: Holds don't sync</span></span>

<span data-ttu-id="8654a-118">Se você vir uma das seguintes mensagens de erro ao colocar os custodiantes e fontes de dados em espera, use as etapas de resolução para solucionar o problema.</span><span class="sxs-lookup"><span data-stu-id="8654a-118">If you see one the following error messages when putting custodians and data sources on hold, use the resolution steps to troubleshoot the issue.</span></span>

> <span data-ttu-id="8654a-119">Recursos: está demorando mais do que o esperado para implantar a política.</span><span class="sxs-lookup"><span data-stu-id="8654a-119">Resources: It's taking longer than expected to deploy the policy.</span></span> <span data-ttu-id="8654a-120">Pode levar mais duas horas para atualizar o status final da implantação, portanto, volte em algumas horas.</span><span class="sxs-lookup"><span data-stu-id="8654a-120">It might take an additional 2 hours to update the final deployment status, so check back in a couple hours.</span></span>

> <span data-ttu-id="8654a-121">A política não pode ser implantada na fonte de conteúdo devido a um problema Office 365 datacenter temporário.</span><span class="sxs-lookup"><span data-stu-id="8654a-121">Policy cannot be deployed to the content source due to a temporary Office 365 datacenter issue.</span></span> <span data-ttu-id="8654a-122">A política atual não é aplicada a qualquer conteúdo na origem, portanto, não há impacto da implantação bloqueada.</span><span class="sxs-lookup"><span data-stu-id="8654a-122">The current policy is not applied to any content in the source, so there's no impact from the blocked deployment.</span></span> <span data-ttu-id="8654a-123">Para corrigir esse problema, tente reimplantar a política.</span><span class="sxs-lookup"><span data-stu-id="8654a-123">To fix this issue, please try redeploying the policy.</span></span>

> <span data-ttu-id="8654a-124">Não foi possível executar as alterações solicitadas na política devido a um erro de servidor interno transitório.</span><span class="sxs-lookup"><span data-stu-id="8654a-124">Sorry, we could not perform the requested changes to policy due to a transient internal server error.</span></span> <span data-ttu-id="8654a-125">Tente novamente em 30 minutos.</span><span class="sxs-lookup"><span data-stu-id="8654a-125">Please try again in 30 minutes.</span></span>

### <a name="resolution"></a><span data-ttu-id="8654a-126">Resolução</span><span class="sxs-lookup"><span data-stu-id="8654a-126">Resolution</span></span>

1. <span data-ttu-id="8654a-127">Conexão ao [Centro de Conformidade & Segurança](/powershell/exchange/connect-to-scc-powershell) do PowerShell e execute o seguinte comando para uma ressarção de Descoberta Digital:</span><span class="sxs-lookup"><span data-stu-id="8654a-127">Connect to [Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell) and run the following command for an eDiscovery hold:</span></span>

   ```powershell
   Get-CaseHoldPolicy <policyname> -DistributionDetail | FL
   ```

2. <span data-ttu-id="8654a-128">Examine o valor no parâmetro *DistributionDetail.*</span><span class="sxs-lookup"><span data-stu-id="8654a-128">Examine the value in the *DistributionDetail* parameter.</span></span> <span data-ttu-id="8654a-129">Procure erros como o seguinte:</span><span class="sxs-lookup"><span data-stu-id="8654a-129">Look for errors like the following:</span></span>

   > <span data-ttu-id="8654a-130">Erro: Recursos: está demorando mais do que o esperado para implantar a política.</span><span class="sxs-lookup"><span data-stu-id="8654a-130">Error: Resources: It's taking longer than expected to deploy the policy.</span></span> <span data-ttu-id="8654a-131">Pode levar mais duas horas para atualizar o status final da implantação, portanto, volte em algumas horas.</span><span class="sxs-lookup"><span data-stu-id="8654a-131">It might take an additional 2 hours to update the final deployment status, so check back in a couple hours.</span></span>

3. <span data-ttu-id="8654a-132">Tente executar o **comando Set-CaseHoldPolicy -RetryDistribution** na política de espera em questão; por exemplo:</span><span class="sxs-lookup"><span data-stu-id="8654a-132">Try running the **Set-CaseHoldPolicy -RetryDistribution** command on the hold policy in question; for example:</span></span>

   ```powershell
   Set-CaseHoldPolicy <policyname> -RetryDistribution
   ```

## <a name="more-information"></a><span data-ttu-id="8654a-133">Mais informações</span><span class="sxs-lookup"><span data-stu-id="8654a-133">More information</span></span>

- <span data-ttu-id="8654a-134">As diretrizes sobre a atualização de políticas de bloqueio para vários usuários na seção "Práticas recomendadas" resulta do fato de que o sistema bloqueia atualizações simultâneas para uma política de bloqueio.</span><span class="sxs-lookup"><span data-stu-id="8654a-134">The guidance about updating hold policies for multiple users in the "Recommended practices" section results from the fact that the system blocks simultaneous updates to a hold policy.</span></span> <span data-ttu-id="8654a-135">Isso significa que, quando uma política de espera atualizada é aplicada a novos locais de conteúdo e a política de espera está em um estado pendente, locais de conteúdo adicionais não podem ser adicionados à política de espera.</span><span class="sxs-lookup"><span data-stu-id="8654a-135">That means when an updated hold policy is applied to new content locations and the hold policy is in a pending state, additional content locations can't be added to the hold policy.</span></span> <span data-ttu-id="8654a-136">Aqui estão algumas coisas a ter em mente para ajudá-lo a atenuar esse problema:</span><span class="sxs-lookup"><span data-stu-id="8654a-136">Here are some things to keep in mind to help you mitigate this issue:</span></span>
  
  - <span data-ttu-id="8654a-137">Sempre que uma espera atualizada é atualizada, ela entra imediatamente em um estado pendente.</span><span class="sxs-lookup"><span data-stu-id="8654a-137">Every time a hold updated is updated, it immediately goes into a pending state.</span></span> <span data-ttu-id="8654a-138">O status de estado pendente significa que a ressarção está sendo aplicada a locais de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="8654a-138">The pending state status means the hold is being applied to content locations.</span></span>
  
  - <span data-ttu-id="8654a-139">Se você tiver um script que executa um loop e adiciona locais à política um a um (semelhante ao exemplo incorreto mostrado na seção "Práticas Recomendadas"), o primeiro local de conteúdo (por exemplo, uma caixa de correio de usuário) iniciará o processo de sincronização que dispara o estado pendente.</span><span class="sxs-lookup"><span data-stu-id="8654a-139">If you have a script that runs a loop and adds locations to policy one by one (similar to the incorrect example shown in the "Recommended practices" section), the first content location (for example, a user mailbox) initiates the sync process that triggers the pending state.</span></span> <span data-ttu-id="8654a-140">Isso significa que os outros usuários adicionados à política em loops subsequentes resultam em um erro.</span><span class="sxs-lookup"><span data-stu-id="8654a-140">That means the other users that are added to the policy in subsequent loops result in an error.</span></span>
  
  - <span data-ttu-id="8654a-141">Se sua organização estiver usando um script que executa um loop para atualizar os locais de conteúdo de uma política de espera, você deve atualizar o script para que ele atualize os locais em uma única operação em massa (conforme mostrado no exemplo correto na seção "Práticas Recomendadas").</span><span class="sxs-lookup"><span data-stu-id="8654a-141">If your organization is using a script that runs a loop to update the content locations for a hold policy, you must update the script so that it updates locations in a single bulk operation (as shown in the correct example in the "Recommended practices" section).</span></span>
