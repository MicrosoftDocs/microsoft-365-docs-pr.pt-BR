---
title: Isolamento de locatário no Microsoft 365 Search
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
f1.keywords:
- NOCSH
description: Neste artigo, encontre uma explicação sobre como o isolamento de locatário funciona para separar dados de locatários na pesquisa do Microsoft 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 9b204e9c1f3ef459852900f3403a21f7ea40541f
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46686938"
---
# <a name="tenant-isolation-in-microsoft-365-search"></a><span data-ttu-id="edc37-103">Isolamento de locatário no Microsoft 365 Search</span><span class="sxs-lookup"><span data-stu-id="edc37-103">Tenant Isolation in Microsoft 365 Search</span></span>

<span data-ttu-id="edc37-104">A pesquisa do SharePoint Online usa um modelo de separação de locatários que equilibra a eficiência de estruturas de dados compartilhadas com proteção contra vazamento de informações entre locatários.</span><span class="sxs-lookup"><span data-stu-id="edc37-104">SharePoint Online search uses a tenant separation model that balances the efficiency of shared data structures with protection against information leaking between tenants.</span></span> <span data-ttu-id="edc37-105">Com esse modelo, impedimos os recursos de pesquisa de:</span><span class="sxs-lookup"><span data-stu-id="edc37-105">With this model, we prevent the Search features from:</span></span>

- <span data-ttu-id="edc37-106">Retornar resultados de consulta que contenham documentos de outros locatários</span><span class="sxs-lookup"><span data-stu-id="edc37-106">Returning query results that contain documents from other tenants</span></span>
- <span data-ttu-id="edc37-107">Expor informações suficientes nos resultados de consulta que um usuário experiente pode inferir informações sobre outros locatários</span><span class="sxs-lookup"><span data-stu-id="edc37-107">Exposing sufficient information in query results that a skilled user could infer information about other tenants</span></span>
- <span data-ttu-id="edc37-108">Mostrando o esquema ou as configurações de outro locatário</span><span class="sxs-lookup"><span data-stu-id="edc37-108">Showing schema or settings from another tenant</span></span>
- <span data-ttu-id="edc37-109">Misturar informações de processamento de análise entre locatários ou armazenar resultados no locatário incorreto</span><span class="sxs-lookup"><span data-stu-id="edc37-109">Mixing analytics processing information between tenants or store results in the wrong tenant</span></span>
- <span data-ttu-id="edc37-110">Usando entradas de dicionário de outro locatário</span><span class="sxs-lookup"><span data-stu-id="edc37-110">Using dictionary entries from another tenant</span></span>

<span data-ttu-id="edc37-111">Para cada tipo de dados de locatário, usamos uma ou mais camadas de proteção no código para evitar vazamento acidental de informações.</span><span class="sxs-lookup"><span data-stu-id="edc37-111">For each type of tenant data, we use one or more layers of protection in the code to prevent accidental leaking of information.</span></span> <span data-ttu-id="edc37-112">Os dados mais importantes têm mais camadas de proteção para garantir que um único defeito não resulte em vazamento real ou percebido.</span><span class="sxs-lookup"><span data-stu-id="edc37-112">The most critical data has the most layers of protection to make sure that a single defect doesn't result in actual or perceived information leakage.</span></span>

## <a name="tenant-separation-for-the-search-index"></a><span data-ttu-id="edc37-113">Separação de locatário para o índice de pesquisa</span><span class="sxs-lookup"><span data-stu-id="edc37-113">Tenant Separation for the Search Index</span></span>

<span data-ttu-id="edc37-114">O índice de pesquisa é armazenado em disco nos servidores que hospedam os componentes do índice e os locatários compartilham os arquivos de índice.</span><span class="sxs-lookup"><span data-stu-id="edc37-114">The search index is stored on disk in the servers hosting the index components and the tenants share the index files.</span></span> <span data-ttu-id="edc37-115">Os documentos indexados de um locatário são visíveis apenas para consultas para o locatário.</span><span class="sxs-lookup"><span data-stu-id="edc37-115">A tenant's indexed documents are visible only for queries for that tenant.</span></span> <span data-ttu-id="edc37-116">Três mecanismos independentes impedem o vazamento de informações:</span><span class="sxs-lookup"><span data-stu-id="edc37-116">Three independent mechanisms prevent information leakage:</span></span>

- <span data-ttu-id="edc37-117">Filtragem de ID de locatário</span><span class="sxs-lookup"><span data-stu-id="edc37-117">Tenant ID filtering</span></span>
- <span data-ttu-id="edc37-118">Prefixação de termo de ID de locatário</span><span class="sxs-lookup"><span data-stu-id="edc37-118">Tenant ID term prefixing</span></span>
- <span data-ttu-id="edc37-119">Verificações de ACL</span><span class="sxs-lookup"><span data-stu-id="edc37-119">ACL checks</span></span>

<span data-ttu-id="edc37-120">Todos os três mecanismos teriam falhado para a pesquisa retornar documentos ao locatário errado.</span><span class="sxs-lookup"><span data-stu-id="edc37-120">All three mechanisms would have to fail for Search to return documents to the wrong tenant.</span></span>

## <a name="tenant-id-filtering-and-tenant-id-term-prefixing"></a><span data-ttu-id="edc37-121">Filtragem de ID de locatário e prefixação de termos de ID de locatário</span><span class="sxs-lookup"><span data-stu-id="edc37-121">Tenant ID Filtering and Tenant ID Term Prefixing</span></span>

<span data-ttu-id="edc37-122">Os prefixos de pesquisa a cada termo indexado no índice de texto completo com a ID do locatário.</span><span class="sxs-lookup"><span data-stu-id="edc37-122">Search prefixes every term that is indexed in the full-text index with the tenant ID.</span></span> <span data-ttu-id="edc37-123">Por exemplo, quando o termo "*foo*" é indexado para um locatário com uma ID de "*123*", a entrada no índice de texto completo é "*123foo".*</span><span class="sxs-lookup"><span data-stu-id="edc37-123">For example, when the term "*foo*" is indexed for a tenant with an ID of "*123*", the entry in the full-text index is "*123foo.*"</span></span>

<span data-ttu-id="edc37-124">Cada consulta é convertida para incluir a ID de locatário usando um processo chamado filtragem de ID de locatário.</span><span class="sxs-lookup"><span data-stu-id="edc37-124">Every query is converted to include the tenant ID using a process called tenant ID filtering.</span></span> <span data-ttu-id="edc37-125">Por exemplo, a consulta "*foo*" é convertida em "<> *GUID* . *foo* E *tenantid*: <*GUID*> ", onde <*GUID*> representa o locatário executando a consulta.</span><span class="sxs-lookup"><span data-stu-id="edc37-125">For example, the query "*foo*" is converted to "<*guid*>.*foo* AND *tenantID*:<*guid*>", where <*guid*> represents the tenant performing the query.</span></span> <span data-ttu-id="edc37-126">Essa conversão de consulta ocorre em cada nó de índice, e nenhuma consulta ou o processamento de conteúdo pode influenciar.</span><span class="sxs-lookup"><span data-stu-id="edc37-126">This query conversion occurs within each index node and neither query nor content processing can influence it.</span></span> <span data-ttu-id="edc37-127">Como a ID do locatário é adicionada a todas as consultas, a frequência de um termo em outros locatários não pode ser deduzida examinando a melhor classificação de correspondência em um locatário.</span><span class="sxs-lookup"><span data-stu-id="edc37-127">Because the tenant ID is added to every query, the frequency of a term in other tenants can't be inferred by looking at best match ranking in one tenant.</span></span>

<span data-ttu-id="edc37-128">A prefixação de termos de ID de locatário ocorre somente no índice de texto completo.</span><span class="sxs-lookup"><span data-stu-id="edc37-128">Tenant ID term prefixing occurs only in the full-text index.</span></span> <span data-ttu-id="edc37-129">Pesquisas em campo, como "*título: foo*", acesse um índice de pesquisa sintético em que os termos não são prefixados por ID de locatário.</span><span class="sxs-lookup"><span data-stu-id="edc37-129">Fielded searches, such as "*title:foo*", go to a synthetic search index where terms aren't prefixed by tenant ID.</span></span> <span data-ttu-id="edc37-130">Em vez disso, as pesquisas de campo são prefixadas com o nome do campo.</span><span class="sxs-lookup"><span data-stu-id="edc37-130">Instead, fielded searches are prefixed with the field name.</span></span> <span data-ttu-id="edc37-131">Por exemplo, a consulta "*título: foo*" é convertida em "*Fields. title: foo e Fields. tenantid*: <*GUID*>".</span><span class="sxs-lookup"><span data-stu-id="edc37-131">For example, the query "*title:foo*" is converted to "*fields.title:foo AND fields.tenantID*:<*guid*>."</span></span> <span data-ttu-id="edc37-132">Como a frequência de um termo não influencia a classificação de acertos no índice de pesquisa sintética, não há necessidade de separação de locatários por prefixação de termos.</span><span class="sxs-lookup"><span data-stu-id="edc37-132">Because the frequency of a term doesn't influence ranking of hits in the synthetic search index, there's no need for tenant separation by term prefixing.</span></span> <span data-ttu-id="edc37-133">Para uma pesquisa em campo como "*título: foo*", a separação de conteúdo do locatário depende da filtragem da ID do locatário por conversão de consulta.</span><span class="sxs-lookup"><span data-stu-id="edc37-133">For a fielded search like "*title:foo*", tenant content separation depends on tenant ID filtering by query conversion.</span></span>

## <a name="document-access-control-list-checks"></a><span data-ttu-id="edc37-134">Verificações de lista de controle de acesso a documentos</span><span class="sxs-lookup"><span data-stu-id="edc37-134">Document Access Control List Checks</span></span>

<span data-ttu-id="edc37-135">A pesquisa controla o acesso a documentos por meio de ACLs salvas no índice de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="edc37-135">Search controls access to documents through ACLs that are saved in the search index.</span></span> <span data-ttu-id="edc37-136">Cada item é indexado com um conjunto de termos em um campo de ACL especial.</span><span class="sxs-lookup"><span data-stu-id="edc37-136">Every item is indexed with a set of terms in a special ACL field.</span></span> <span data-ttu-id="edc37-137">O campo ACL contém um termo por grupo ou usuário que pode exibir o documento.</span><span class="sxs-lookup"><span data-stu-id="edc37-137">The ACL field contains one term per group or user that can view the document.</span></span> <span data-ttu-id="edc37-138">Cada consulta é aumentada com uma lista de termos de ACE (entrada de controle de acesso), uma para cada grupo ao qual o usuário autenticado pertence.</span><span class="sxs-lookup"><span data-stu-id="edc37-138">Every query is augmented with a list of access control entry (ACE) terms, one for each group to which the authenticated user belongs.</span></span>

<span data-ttu-id="edc37-139">Por exemplo, uma consulta como "<*guid*>. *foo e tenantid*: <*GUID*> "torna-se:" <> *GUID* . *foo e tenantid*: <*GUID* >  *e* (*docacls:* < *ACE1* >  *ou docacls*: <*ACE2* >  *ou docacls*: <*ace3* >  *...*) "</span><span class="sxs-lookup"><span data-stu-id="edc37-139">For example, a query like "<*guid*>.*foo AND tenantID*:<*guid*>" becomes: "<*guid*>.*foo AND tenantID*:<*guid*> *AND* (*docACL:*<*ace1*> *OR docACL*:<*ace2*> *OR docACL*:<*ace3*> *...*)"</span></span>

<span data-ttu-id="edc37-140">Como os identificadores de usuário e de grupo e as ACEs são exclusivos, isso fornece um nível extra de segurança entre os locatários para documentos que são visíveis apenas para alguns usuários.</span><span class="sxs-lookup"><span data-stu-id="edc37-140">Because user and group identifiers and hence ACEs are unique, this provides an extra level of security between tenants for documents that are only visible to some users.</span></span> <span data-ttu-id="edc37-141">O mesmo é o caso da ACE especial "todos exceto usuários externos" que concede acesso a usuários regulares no locatário.</span><span class="sxs-lookup"><span data-stu-id="edc37-141">The same is the case for the special "Everyone except external users" ACE that grants access to regular users in the tenant.</span></span> <span data-ttu-id="edc37-142">No entanto, como as ACEs de "todos" são as mesmas para todos os locatários, a separação de locatários para documentos públicos depende da filtragem da ID do locatário.</span><span class="sxs-lookup"><span data-stu-id="edc37-142">But since ACEs for "Everyone" are the same for all tenants, tenant separation for public documents depends on tenant ID filtering.</span></span> <span data-ttu-id="edc37-143">As ACEs de negação também são suportadas.</span><span class="sxs-lookup"><span data-stu-id="edc37-143">Deny ACEs are also supported.</span></span> <span data-ttu-id="edc37-144">O aumento da consulta adiciona uma cláusula que remove um documento do resultado quando há uma correspondência com uma ACE de negação.</span><span class="sxs-lookup"><span data-stu-id="edc37-144">The query augmentation adds a clause that removes a document from the result when there is a match with a deny ACE.</span></span>

<span data-ttu-id="edc37-145">Na pesquisa do Exchange Online, o índice é particionado na ID da caixa de correio para caixas de correio do usuário individual em vez de ID do locatário (ID da assinatura) como no SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="edc37-145">In Exchange Online search, the index is partitioned on mailbox ID for individual user's mailboxes instead of tenant ID (subscription ID) as in SharePoint Online.</span></span> <span data-ttu-id="edc37-146">O mecanismo de particionamento é o mesmo que o SharePoint Online, mas não há filtragem de ACL.</span><span class="sxs-lookup"><span data-stu-id="edc37-146">The partitioning mechanism is the same as SharePoint Online, but there is no ACL filtering.</span></span>