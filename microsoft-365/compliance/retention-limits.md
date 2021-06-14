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
ms.openlocfilehash: 92647911cfc3435c2d88ce5caa0624a34467a60f
ms.sourcegitcommit: 3e197d1ff7d8100faeaf1f5a33f1ad4ed2f72e99
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/11/2021
ms.locfileid: "52908096"
---
# <a name="limits-for-retention-policies-and-retention-label-policies"></a><span data-ttu-id="37427-103">Limites para políticas de retenção e políticas de rótulo de retenção</span><span class="sxs-lookup"><span data-stu-id="37427-103">Limits for retention policies and retention label policies</span></span>

><span data-ttu-id="37427-104">*[Diretrizes de licenciamento do Microsoft 365 para segurança e conformidade](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*</span><span class="sxs-lookup"><span data-stu-id="37427-104">*[Microsoft 365 licensing guidance for security & compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*</span></span>

<span data-ttu-id="37427-105">Haverá números máximos a serem considerados ao usar [políticas de retenção e políticas de rótulos de retenção](retention.md#retention-policies-and-retention-labels) para reter ou excluir dados automaticamente da organização.</span><span class="sxs-lookup"><span data-stu-id="37427-105">When you use [retention policies and retention label policies](retention.md#retention-policies-and-retention-labels) to automatically retain or delete data for your organization, there are some maximum numbers to be aware of.</span></span>

## <a name="maximum-number-of-policies-per-tenant"></a><span data-ttu-id="37427-106">Número máximo de políticas por locatário</span><span class="sxs-lookup"><span data-stu-id="37427-106">Maximum number of policies per tenant</span></span>

<span data-ttu-id="37427-107">Um único locatário pode ter no máximo 10.000 políticas (qualquer configuração).</span><span class="sxs-lookup"><span data-stu-id="37427-107">A single tenant can have a maximum of 10,000 policies (any configuration).</span></span> <span data-ttu-id="37427-108">Esse número máximo inclui as diferentes políticas de retenção e outras políticas de conformidade, como políticas para DLP, barreiras de informações, retenções de Descoberta eletrônica e rótulos de confidencialidade.</span><span class="sxs-lookup"><span data-stu-id="37427-108">This maximum number includes the different policies for retention, and other policies for compliance such as policies for DLP, information barriers, eDiscovery holds, and sensitivity labels.</span></span>

<span data-ttu-id="37427-109">Dentro desse limite de 10.000 políticas, também existem alguns limites no número máximo de políticas para retenção por carga de trabalho:</span><span class="sxs-lookup"><span data-stu-id="37427-109">Within this 10,000 policies limit, there are also some limits on the maximum number of policies for retention per workload:</span></span>

- <span data-ttu-id="37427-110">Exchange (qualquer configuração): 1.800</span><span class="sxs-lookup"><span data-stu-id="37427-110">Exchange (any configuration): 1,800</span></span>
- <span data-ttu-id="37427-111">SharePoint ou OneDrive: (todos os sites incluídos automaticamente): 13</span><span class="sxs-lookup"><span data-stu-id="37427-111">SharePoint or OneDrive: (all sites automatically included): 13</span></span>
- <span data-ttu-id="37427-112">SharePoint ou OneDrive (locais específicos incluídos ou excluídos): 2.600</span><span class="sxs-lookup"><span data-stu-id="37427-112">SharePoint or OneDrive (specific locations included or excluded): 2,600</span></span>

<span data-ttu-id="37427-113">Embora as políticas de retenção para o Microsoft Teams e Yammer usem caixas de correio para armazenar dados para fins de retenção, o número máximo de políticas para Exchange Online exclui políticas de retenção para o Teams e o Yammer.</span><span class="sxs-lookup"><span data-stu-id="37427-113">Although retention policies for Microsoft Teams and Yammer use mailboxes to store data for retention purposes, the maximum number of policies for Exchange Online exclude retention policies for Teams and Yammer.</span></span>

## <a name="maximum-number-of-items-per-policy"></a><span data-ttu-id="37427-114">Número máximo de itens por política</span><span class="sxs-lookup"><span data-stu-id="37427-114">Maximum number of items per policy</span></span>

<span data-ttu-id="37427-115">Se você usar a configuração opcional para definir o escopo de suas configurações de retenção para usuários específicos, grupos específicos do Microsoft 365 ou sites específicos, haverá alguns limites por política a serem considerados:</span><span class="sxs-lookup"><span data-stu-id="37427-115">If you use the optional configuration to scope your retention settings to specific users, specific Microsoft 365 groups, or specific sites, there are some limits per policy to be aware of:</span></span> 

<span data-ttu-id="37427-116">Número máximo de itens por política de retenção:</span><span class="sxs-lookup"><span data-stu-id="37427-116">Maximum numbers of items per policy for retention:</span></span>

- <span data-ttu-id="37427-117">Caixas de correio do Exchange: 1.000</span><span class="sxs-lookup"><span data-stu-id="37427-117">Exchange mailboxes: 1,000</span></span>
- <span data-ttu-id="37427-118">Grupos do Microsoft 365: 1.000</span><span class="sxs-lookup"><span data-stu-id="37427-118">Microsoft 365 Groups: 1,000</span></span>
- <span data-ttu-id="37427-119">Mensagens do canal do Teams: 1.000</span><span class="sxs-lookup"><span data-stu-id="37427-119">Teams channel messages: 1,000</span></span>
- <span data-ttu-id="37427-120">Chats do Teams: 1.000</span><span class="sxs-lookup"><span data-stu-id="37427-120">Teams chats: 1,000</span></span>
- <span data-ttu-id="37427-121">Mensagens da comunidade do Yammer: 1.000</span><span class="sxs-lookup"><span data-stu-id="37427-121">Yammer community messages: 1,000</span></span>
- <span data-ttu-id="37427-122">Mensagens de usuário do Yammer: 1.000</span><span class="sxs-lookup"><span data-stu-id="37427-122">Yammer user messages: 1,000</span></span>
- <span data-ttu-id="37427-123">Sites do SharePoint: 100</span><span class="sxs-lookup"><span data-stu-id="37427-123">SharePoint sites: 100</span></span>
- <span data-ttu-id="37427-124">Contas do OneDrive: 100</span><span class="sxs-lookup"><span data-stu-id="37427-124">OneDrive accounts: 100</span></span>

<span data-ttu-id="37427-125">O Skype for Business deve ter escopo para usuários específicos, e o número máximo com suporte por política é de 1.000.</span><span class="sxs-lookup"><span data-stu-id="37427-125">Skype for Business has to be scoped to specific users and the maximum number supported per policy is 1,000.</span></span>

<span data-ttu-id="37427-126">Como essas limitações são por política, se você precisar usar inclusões ou exclusões específicas que resultem em passar por esses números, você poderá criar políticas de retenção adicionais que tenham as mesmas configurações de retenção.</span><span class="sxs-lookup"><span data-stu-id="37427-126">Because these limitations are per policy, if you need to use specific inclusions or exclusions that result in going over these numbers, you can create additional policies that have the same retention settings.</span></span> <span data-ttu-id="37427-127">Confira a próxima seção com alguns [cenários de exemplo e soluções](#examples-of-using-multiple-policies-to-avoid-exceeding-maximum-numbers) que usam várias políticas de retenção por esse motivo.</span><span class="sxs-lookup"><span data-stu-id="37427-127">See the next section for some [example scenarios and solutions](#examples-of-using-multiple-policies-to-avoid-exceeding-maximum-numbers) that use multiple retention policies for this reason.</span></span>

<span data-ttu-id="37427-128">No entanto, várias políticas de retenção resultam em maiores sobrecargas administrativas, portanto, sempre se questione se realmente precisa de inclusões e exclusões.</span><span class="sxs-lookup"><span data-stu-id="37427-128">However, multiple policies result in higher administrative overheads, so always confirm whether you really need inclusions and exclusions.</span></span> <span data-ttu-id="37427-129">Lembre-se de que a configuração padrão que se aplica a todo o local não tem limitações, e essa escolha de configuração pode ser uma solução melhor do que a criação e a manutenção de várias políticas.</span><span class="sxs-lookup"><span data-stu-id="37427-129">Remember that the default configuration that applies to the entire location doesn't have any limitations, and this configuration choice might be a better solution than creating and maintaining multiple policies.</span></span>

> [!TIP]
> <span data-ttu-id="37427-130">Se você precisar criar e manter várias políticas para esse cenário, considere usar o [PowerShell](retention.md#powershell-cmdlets-for-retention-policies-and-retention-labels) para uma configuração mais eficaz.</span><span class="sxs-lookup"><span data-stu-id="37427-130">If do you need to create and maintain multiple policies for this scenario, consider using [PowerShell](retention.md#powershell-cmdlets-for-retention-policies-and-retention-labels) for more efficient configuration.</span></span>

### <a name="examples-of-using-multiple-policies-to-avoid-exceeding-maximum-numbers"></a><span data-ttu-id="37427-131">Exemplos de como usar várias políticas para evitar exceder o número máximo</span><span class="sxs-lookup"><span data-stu-id="37427-131">Examples of using multiple policies to avoid exceeding maximum numbers</span></span>

<span data-ttu-id="37427-132">Os exemplos a seguir fornecem algumas soluções de design para quando você não puder especificar o local de uma política de retenção, e leve em consideração o numero máximo de itens documentados na seção anterior.</span><span class="sxs-lookup"><span data-stu-id="37427-132">The following examples provide some design solutions for when you can't specify just the location for a retention policy, and must take into account the maximum number of items documented in the previous section.</span></span>

<span data-ttu-id="37427-133">Exemplo do Exchange:</span><span class="sxs-lookup"><span data-stu-id="37427-133">Exchange example:</span></span>

- <span data-ttu-id="37427-134">**Requisito**: em uma organização que tenha mais de 40.000 caixas de correio de usuário, a maioria dos usuários deve ter o email mantido por sete anos, mas um subconjunto de usuários identificados (425) deve ter seus emails mantidos por apenas cinco anos.</span><span class="sxs-lookup"><span data-stu-id="37427-134">**Requirement**: In an organization that has over 40,000 user mailboxes, most users must have their email retained for 7 years but a subset of identified users (425) must have their email retained for only 5 years.</span></span>

- <span data-ttu-id="37427-135">**Solução**: crie uma política de retenção para o email do Exchange com um período de retenção de 7 anos e exclua o subconjunto de usuários.</span><span class="sxs-lookup"><span data-stu-id="37427-135">**Solution**: Create one retention policy for Exchange email with a retention period of 7 years and exclude the subset of users.</span></span> <span data-ttu-id="37427-136">Em seguida, crie uma segunda política de retenção para o email do Exchange com um período de retenção de cinco anos e inclua o subconjunto de usuários.</span><span class="sxs-lookup"><span data-stu-id="37427-136">Then create a second retention policy for Exchange email with a retention period of 5 years and include the subset of users.</span></span> 
    
    <span data-ttu-id="37427-137">Em ambos os casos, o número incluído e excluído fica abaixo do número máximo de caixas de correio especificadas para uma única política, e o subconjunto de usuários deve ser explicitamente excluído da primeira política, pois tem um período de retenção [maior](retention.md#the-principles-of-retention-or-what-takes-precedence) do que a segunda política.</span><span class="sxs-lookup"><span data-stu-id="37427-137">In both cases, the number included and excluded is below the maximum number of specified mailboxes for a single policy, and the subset of users must be explicitly excluded from the first policy because it has a [longer retention period](retention.md#the-principles-of-retention-or-what-takes-precedence) than the second policy.</span></span> <span data-ttu-id="37427-138">Se o subconjunto de usuários exigir uma política de retenção maior, não será necessário excluí-los da primeira política.</span><span class="sxs-lookup"><span data-stu-id="37427-138">If the subset of users required a longer retention policy, you wouldn't need to exclude them from the first policy.</span></span>
     
    <span data-ttu-id="37427-139">Com essa solução, se alguém novo ingressar na organização, a caixa de correio será incluída automaticamente na primeira política por sete anos e não haverá impacto nos números máximos suportados.</span><span class="sxs-lookup"><span data-stu-id="37427-139">With this solution, if anybody new joins the organization, their mailbox is automatically included in the first policy for 7 years and there is no impact to the maximum numbers supported.</span></span> <span data-ttu-id="37427-140">No entanto, novos usuários que exigem o período de retenção de 5 anos seja adicionado aos números de inclusão e exclusão, esse limite seria atingido em 1.000.</span><span class="sxs-lookup"><span data-stu-id="37427-140">However, new users that require the 5-year retention period add to the include and exclude numbers, and this limit would be reached at 1,000.</span></span>

<span data-ttu-id="37427-141">Exemplo do SharePoint:</span><span class="sxs-lookup"><span data-stu-id="37427-141">SharePoint example:</span></span>

- <span data-ttu-id="37427-142">**Requisito**: uma organização tem milhares de sites do SharePoint, mas somente 2.000 sites exigem um período de retenção de 10 anos e 8.000 os sites exigem um período de retenção de 4 anos.</span><span class="sxs-lookup"><span data-stu-id="37427-142">**Requirement**: An organization has several thousand SharePoint sites but only 2,000 sites require a retention period of 10 years, and 8,000 sites require a retention period of 4 years.</span></span>

- <span data-ttu-id="37427-143">**Solução**: criar 20 políticas de retenção para o SharePoint com um período de retenção de 10 anos que inclui 100 sites específicos e criar 80 políticas de retenção para o SharePoint com um período de retenção de 4 anos que inclui 100 sites específicos.</span><span class="sxs-lookup"><span data-stu-id="37427-143">**Solution**: Create 20 retention policies for SharePoint with a retention period of 10 years that includes 100 specific sites, and create 80 retention policies for SharePoint with a retention period of 4 years that includes 100 specific sites.</span></span>
    
    <span data-ttu-id="37427-144">Como não é necessário manter todos os sites do SharePoint, você deve criar políticas de retenção que especificam os sites específicos.</span><span class="sxs-lookup"><span data-stu-id="37427-144">Because you don't need to retain all SharePoint sites, you must create retention policies that specify the specific sites.</span></span> <span data-ttu-id="37427-145">Como uma política de retenção não dá suporte a mais de 100 sites especificados, você deve criar várias políticas para os dois períodos de retenção.</span><span class="sxs-lookup"><span data-stu-id="37427-145">Because a retention policy doesn't support more than 100 specified sites, you must create multiple policies for the two retention periods.</span></span> <span data-ttu-id="37427-146">Essas políticas de retenção têm o número máximo de sites incluídos, para que o próximo novo site que precise da retenção exija uma nova política, independentemente do período de retenção.</span><span class="sxs-lookup"><span data-stu-id="37427-146">These retention policies  have the maximum number of included sites, so the next new site that needs retaining would require a new retention policy, irrespective of the retention period.</span></span>

## <a name="maximum-number-of-items-for-disposition"></a><span data-ttu-id="37427-147">Número máximo de itens para disposição</span><span class="sxs-lookup"><span data-stu-id="37427-147">Maximum number of items for disposition</span></span>

<span data-ttu-id="37427-148">Para a [disposição do conteúdo](disposition.md), existem alguns limites a serem cientes:</span><span class="sxs-lookup"><span data-stu-id="37427-148">For the [disposition of content](disposition.md), there are some limits to be aware of:</span></span>

- <span data-ttu-id="37427-149">1.000.000 itens pendentes de disposição por estágio para cada rótulo de retenção</span><span class="sxs-lookup"><span data-stu-id="37427-149">1,000,000 items pending disposition per stage for each retention label</span></span>

- <span data-ttu-id="37427-150">Prova de disposição por até sete anos após o item ser descartado, com um limite de 1.000.000 itens por rótulo de retenção para esse período.</span><span class="sxs-lookup"><span data-stu-id="37427-150">Proof of disposition for up to seven years after the item was disposed, with a limit of 1,000,000 items per retention label for that period.</span></span> 
    
<span data-ttu-id="37427-151">Se você precisar da prova de disposição maior do que esse limite de 1.000.000 para itens marcados como registros, entre em contato com o [Suporte da Microsoft](../business-video/get-help-support.md).</span><span class="sxs-lookup"><span data-stu-id="37427-151">If you need proof of disposition higher than this limit of 1,000,000 for items that are marked as records, contact [Microsoft Support](../business-video/get-help-support.md).</span></span>
