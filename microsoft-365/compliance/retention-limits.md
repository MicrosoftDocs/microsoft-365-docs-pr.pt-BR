---
title: Limites para políticas de retenção e políticas de rótulo de retenção
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
hideEdit: true
description: Entenda o número máximo de políticas e itens por política para políticas de retenção e políticas de rótulos de retenção
ms.openlocfilehash: 2dac852342c080c4f8334562dc76449d6963facc
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/10/2021
ms.locfileid: "52878047"
---
# <a name="limits-for-retention-policies-and-retention-label-policies"></a><span data-ttu-id="d37b7-103">Limites para políticas de retenção e políticas de rótulo de retenção</span><span class="sxs-lookup"><span data-stu-id="d37b7-103">Limits for retention policies and retention label policies</span></span>

><span data-ttu-id="d37b7-104">*[Diretrizes de licenciamento do Microsoft 365 para segurança e conformidade](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*</span><span class="sxs-lookup"><span data-stu-id="d37b7-104">*[Microsoft 365 licensing guidance for security & compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*</span></span>

<span data-ttu-id="d37b7-105">Haverá números máximos a serem considerados ao usar [políticas de retenção e políticas de rótulos de retenção](retention.md#retention-policies-and-retention-labels) para reter ou excluir dados automaticamente da organização.</span><span class="sxs-lookup"><span data-stu-id="d37b7-105">When you use [retention policies and retention label policies](retention.md#retention-policies-and-retention-labels) to automatically retain or delete data for your organization, there are some maximum numbers to be aware of.</span></span>

## <a name="maximum-number-of-policies-per-tenant"></a><span data-ttu-id="d37b7-106">Número máximo de políticas por locatário</span><span class="sxs-lookup"><span data-stu-id="d37b7-106">Maximum number of policies per tenant</span></span>

<span data-ttu-id="d37b7-107">Um único locatário pode ter no máximo 10.000 políticas (qualquer configuração).</span><span class="sxs-lookup"><span data-stu-id="d37b7-107">A single tenant can have a maximum of 10,000 policies (any configuration).</span></span> <span data-ttu-id="d37b7-108">Esse número máximo inclui as diferentes políticas de retenção e outras políticas de conformidade, como políticas para DLP, barreiras de informações, retenções de Descoberta eletrônica e rótulos de confidencialidade.</span><span class="sxs-lookup"><span data-stu-id="d37b7-108">This maximum number includes the different policies for retention, and other policies for compliance such as policies for DLP, information barriers, eDiscovery holds, and sensitivity labels.</span></span>

<span data-ttu-id="d37b7-109">Dentro desse limite de 10.000 políticas, também existem alguns limites no número máximo de políticas para retenção por carga de trabalho:</span><span class="sxs-lookup"><span data-stu-id="d37b7-109">Within this 10,000 policies limit, there are also some limits on the maximum number of policies for retention per workload:</span></span>

- <span data-ttu-id="d37b7-110">Exchange Online (qualquer configuração): 1.800</span><span class="sxs-lookup"><span data-stu-id="d37b7-110">Exchange Online (any configuration): 1,800</span></span>
- <span data-ttu-id="d37b7-111">SharePoint ou OneDrive: (todos os sites incluídos automaticamente): 13</span><span class="sxs-lookup"><span data-stu-id="d37b7-111">SharePoint or OneDrive: (all sites automatically included): 13</span></span>
- <span data-ttu-id="d37b7-112">SharePoint ou OneDrive (locais específicos incluídos ou excluídos): 2.600</span><span class="sxs-lookup"><span data-stu-id="d37b7-112">SharePoint or OneDrive (specific locations included or excluded): 2,600</span></span>

<span data-ttu-id="d37b7-113">Embora as políticas de retenção para o Microsoft Teams e Yammer usem caixas de correio para armazenar dados para fins de retenção, o número máximo de políticas para Exchange Online exclui políticas de retenção para o Teams e o Yammer.</span><span class="sxs-lookup"><span data-stu-id="d37b7-113">Although retention policies for Microsoft Teams and Yammer use mailboxes to store data for retention purposes, the maximum number of policies for Exchange Online exclude retention policies for Teams and Yammer.</span></span>

## <a name="maximum-number-of-items-per-policy"></a><span data-ttu-id="d37b7-114">Número máximo de itens por política</span><span class="sxs-lookup"><span data-stu-id="d37b7-114">Maximum number of items per policy</span></span>

<span data-ttu-id="d37b7-115">Se você usar a configuração opcional para definir o escopo de suas configurações de retenção para usuários específicos, grupos específicos do Microsoft 365 ou sites específicos, haverá alguns limites por política a serem considerados:</span><span class="sxs-lookup"><span data-stu-id="d37b7-115">If you use the optional configuration to scope your retention settings to specific users, specific Microsoft 365 groups, or specific sites, there are some limits per policy to be aware of:</span></span> 

<span data-ttu-id="d37b7-116">Número máximo de itens por política de retenção:</span><span class="sxs-lookup"><span data-stu-id="d37b7-116">Maximum numbers of items per policy for retention:</span></span>

  - <span data-ttu-id="d37b7-117">1.000 caixas de correio (caixas de correio do usuário ou de grupos)</span><span class="sxs-lookup"><span data-stu-id="d37b7-117">1,000 mailboxes (user mailboxes or group mailboxes)</span></span>
  - <span data-ttu-id="d37b7-118">1.000 grupos do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="d37b7-118">1,000 Microsoft 365 groups</span></span>
  - <span data-ttu-id="d37b7-119">1.000 usuários para conversas privadas do Teams</span><span class="sxs-lookup"><span data-stu-id="d37b7-119">1,000 users for Teams private chats</span></span>
  - <span data-ttu-id="d37b7-120">100 sites (OneDrive ou SharePoint)</span><span class="sxs-lookup"><span data-stu-id="d37b7-120">100 sites (OneDrive or SharePoint)</span></span>

<span data-ttu-id="d37b7-121">Como essas limitações são por política, se você precisar usar inclusões ou exclusões específicas que resultem em passar por esses números, você poderá criar políticas de retenção adicionais que tenham as mesmas configurações de retenção.</span><span class="sxs-lookup"><span data-stu-id="d37b7-121">Because these limitations are per policy, if you need to use specific inclusions or exclusions that result in going over these numbers, you can create additional policies that have the same retention settings.</span></span> <span data-ttu-id="d37b7-122">Confira a próxima seção com alguns [cenários de exemplo e soluções](#examples-of-using-multiple-policies-to-avoid-exceeding-maximum-numbers) que usam várias políticas de retenção por esse motivo.</span><span class="sxs-lookup"><span data-stu-id="d37b7-122">See the next section for some [example scenarios and solutions](#examples-of-using-multiple-policies-to-avoid-exceeding-maximum-numbers) that use multiple retention policies for this reason.</span></span>

<span data-ttu-id="d37b7-123">No entanto, várias políticas de retenção resultam em maiores sobrecargas administrativas, portanto, sempre se questione se realmente precisa de inclusões e exclusões.</span><span class="sxs-lookup"><span data-stu-id="d37b7-123">However, multiple policies result in higher administrative overheads, so always confirm whether you really need inclusions and exclusions.</span></span> <span data-ttu-id="d37b7-124">Lembre-se de que a configuração padrão que se aplica a todo o local não tem limitações, e essa escolha de configuração pode ser uma solução melhor do que a criação e a manutenção de várias políticas.</span><span class="sxs-lookup"><span data-stu-id="d37b7-124">Remember that the default configuration that applies to the entire location doesn't have any limitations, and this configuration choice might be a better solution than creating and maintaining multiple policies.</span></span>

> [!TIP]
> <span data-ttu-id="d37b7-125">Se você precisar criar e manter várias políticas para esse cenário, considere usar o [PowerShell](retention.md#powershell-cmdlets-for-retention-policies-and-retention-labels) para uma configuração mais eficaz.</span><span class="sxs-lookup"><span data-stu-id="d37b7-125">If do you need to create and maintain multiple policies for this scenario, consider using [PowerShell](retention.md#powershell-cmdlets-for-retention-policies-and-retention-labels) for more efficient configuration.</span></span>

### <a name="examples-of-using-multiple-policies-to-avoid-exceeding-maximum-numbers"></a><span data-ttu-id="d37b7-126">Exemplos de como usar várias políticas para evitar exceder o número máximo</span><span class="sxs-lookup"><span data-stu-id="d37b7-126">Examples of using multiple policies to avoid exceeding maximum numbers</span></span>

<span data-ttu-id="d37b7-127">Os exemplos a seguir fornecem algumas soluções de design para quando você não puder especificar o local de uma política de retenção, e leve em consideração o numero máximo de itens documentados na seção anterior.</span><span class="sxs-lookup"><span data-stu-id="d37b7-127">The following examples provide some design solutions for when you can't specify just the location for a retention policy, and must take into account the maximum number of items documented in the previous section.</span></span>

<span data-ttu-id="d37b7-128">Exemplo do Exchange:</span><span class="sxs-lookup"><span data-stu-id="d37b7-128">Exchange example:</span></span>

- <span data-ttu-id="d37b7-129">**Requisito**: em uma organização que tenha mais de 40.000 caixas de correio de usuário, a maioria dos usuários deve ter o email mantido por sete anos, mas um subconjunto de usuários identificados (425) deve ter seus emails mantidos por apenas cinco anos.</span><span class="sxs-lookup"><span data-stu-id="d37b7-129">**Requirement**: In an organization that has over 40,000 user mailboxes, most users must have their email retained for 7 years but a subset of identified users (425) must have their email retained for only 5 years.</span></span>

- <span data-ttu-id="d37b7-130">**Solução**: crie uma política de retenção para o email do Exchange com um período de retenção de 7 anos e exclua o subconjunto de usuários.</span><span class="sxs-lookup"><span data-stu-id="d37b7-130">**Solution**: Create one retention policy for Exchange email with a retention period of 7 years and exclude the subset of users.</span></span> <span data-ttu-id="d37b7-131">Em seguida, crie uma segunda política de retenção para o email do Exchange com um período de retenção de cinco anos e inclua o subconjunto de usuários.</span><span class="sxs-lookup"><span data-stu-id="d37b7-131">Then create a second retention policy for Exchange email with a retention period of 5 years and include the subset of users.</span></span> 
    
    <span data-ttu-id="d37b7-132">Em ambos os casos, o número incluído e excluído fica abaixo do número máximo de caixas de correio especificadas para uma única política, e o subconjunto de usuários deve ser explicitamente excluído da primeira política, pois tem um período de retenção [maior](retention.md#the-principles-of-retention-or-what-takes-precedence) do que a segunda política.</span><span class="sxs-lookup"><span data-stu-id="d37b7-132">In both cases, the number included and excluded is below the maximum number of specified mailboxes for a single policy, and the subset of users must be explicitly excluded from the first policy because it has a [longer retention period](retention.md#the-principles-of-retention-or-what-takes-precedence) than the second policy.</span></span> <span data-ttu-id="d37b7-133">Se o subconjunto de usuários exigir uma política de retenção maior, não será necessário excluí-los da primeira política.</span><span class="sxs-lookup"><span data-stu-id="d37b7-133">If the subset of users required a longer retention policy, you wouldn't need to exclude them from the first policy.</span></span>
     
    <span data-ttu-id="d37b7-134">Com essa solução, se alguém novo ingressar na organização, a caixa de correio será incluída automaticamente na primeira política por sete anos e não haverá impacto nos números máximos suportados.</span><span class="sxs-lookup"><span data-stu-id="d37b7-134">With this solution, if anybody new joins the organization, their mailbox is automatically included in the first policy for 7 years and there is no impact to the maximum numbers supported.</span></span> <span data-ttu-id="d37b7-135">No entanto, novos usuários que exigem o período de retenção de 5 anos seja adicionado aos números de inclusão e exclusão, esse limite seria atingido em 1.000.</span><span class="sxs-lookup"><span data-stu-id="d37b7-135">However, new users that require the 5-year retention period add to the include and exclude numbers, and this limit would be reached at 1,000.</span></span>

<span data-ttu-id="d37b7-136">Exemplo do SharePoint:</span><span class="sxs-lookup"><span data-stu-id="d37b7-136">SharePoint example:</span></span>

- <span data-ttu-id="d37b7-137">**Requisito**: uma organização tem milhares de sites do SharePoint, mas somente 2.000 sites exigem um período de retenção de 10 anos e 8.000 os sites exigem um período de retenção de 4 anos.</span><span class="sxs-lookup"><span data-stu-id="d37b7-137">**Requirement**: An organization has several thousand SharePoint sites but only 2,000 sites require a retention period of 10 years, and 8,000 sites require a retention period of 4 years.</span></span>

- <span data-ttu-id="d37b7-138">**Solução**: criar 20 políticas de retenção para o SharePoint com um período de retenção de 10 anos que inclui 100 sites específicos e criar 80 políticas de retenção para o SharePoint com um período de retenção de 4 anos que inclui 100 sites específicos.</span><span class="sxs-lookup"><span data-stu-id="d37b7-138">**Solution**: Create 20 retention policies for SharePoint with a retention period of 10 years that includes 100 specific sites, and create 80 retention policies for SharePoint with a retention period of 4 years that includes 100 specific sites.</span></span>
    
    <span data-ttu-id="d37b7-139">Como não é necessário manter todos os sites do SharePoint, você deve criar políticas de retenção que especificam os sites específicos.</span><span class="sxs-lookup"><span data-stu-id="d37b7-139">Because you don't need to retain all SharePoint sites, you must create retention policies that specify the specific sites.</span></span> <span data-ttu-id="d37b7-140">Como uma política de retenção não dá suporte a mais de 100 sites especificados, você deve criar várias políticas para os dois períodos de retenção.</span><span class="sxs-lookup"><span data-stu-id="d37b7-140">Because a retention policy doesn't support more than 100 specified sites, you must create multiple policies for the two retention periods.</span></span> <span data-ttu-id="d37b7-141">Essas políticas de retenção têm o número máximo de sites incluídos, para que o próximo novo site que precise da retenção exija uma nova política, independentemente do período de retenção.</span><span class="sxs-lookup"><span data-stu-id="d37b7-141">These retention policies  have the maximum number of included sites, so the next new site that needs retaining would require a new retention policy, irrespective of the retention period.</span></span>

## <a name="maximum-number-of-items-for-disposition"></a><span data-ttu-id="d37b7-142">Número máximo de itens para disposição</span><span class="sxs-lookup"><span data-stu-id="d37b7-142">Maximum number of items for disposition</span></span>

<span data-ttu-id="d37b7-143">Para a [disposição do conteúdo](disposition.md), existem alguns limites a serem cientes:</span><span class="sxs-lookup"><span data-stu-id="d37b7-143">For the [disposition of content](disposition.md), there are some limits to be aware of:</span></span>

- <span data-ttu-id="d37b7-144">1.000.000 itens pendentes de disposição por estágio para cada rótulo de retenção</span><span class="sxs-lookup"><span data-stu-id="d37b7-144">1,000,000 items pending disposition per stage for each retention label</span></span>

- <span data-ttu-id="d37b7-145">Prova de disposição por até sete anos após o item ser descartado, com um limite de 1.000.000 itens por rótulo de retenção para esse período.</span><span class="sxs-lookup"><span data-stu-id="d37b7-145">Proof of disposition for up to seven years after the item was disposed, with a limit of 1,000,000 items per retention label for that period.</span></span> 
    
    <span data-ttu-id="d37b7-146">Se você precisar da prova de disposição maior do que esse limite de 1.000.000 para itens marcados como registros, entre em contato com o [Suporte da Microsoft](../business-video/get-help-support.md).</span><span class="sxs-lookup"><span data-stu-id="d37b7-146">If you need proof of disposition higher than this limit of 1,000,000 for items that are marked as records, contact [Microsoft Support](../business-video/get-help-support.md).</span></span>