---
title: Alterações de nomeação no esquema de busca avançada do Microsoft 365 Defender
description: Acompanhar e revisar as tabelas e colunas de alterações de nomeação no esquema de busca avançada
keywords: busca avançada, busca de ameaças, busca de ameaças cibernéticas, proteção contra ameaças da Microsoft, microsoft 365, mtp, m365, pesquisa, consulta, telemetria, referência de esquema, kusto, tabela, dados, alterações de nomeação, renomear, Proteção contra Ameaças da Microsoft
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 483fedd1fb152e3df5311c981b305e621ec2aec3
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932197"
---
# <a name="advanced-hunting-schema---naming-changes"></a><span data-ttu-id="1765a-104">Esquema de busca avançada - Alterações de nomeação</span><span class="sxs-lookup"><span data-stu-id="1765a-104">Advanced hunting schema - Naming changes</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="1765a-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="1765a-105">**Applies to:**</span></span>
- <span data-ttu-id="1765a-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1765a-106">Microsoft 365 Defender</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="1765a-107">O [esquema de busca avançada é](advanced-hunting-schema-tables.md) atualizado regularmente para adicionar novas tabelas e colunas.</span><span class="sxs-lookup"><span data-stu-id="1765a-107">The [advanced hunting schema](advanced-hunting-schema-tables.md) is updated regularly to add new tables and columns.</span></span> <span data-ttu-id="1765a-108">Em alguns casos, os nomes de colunas existentes são renomeados ou substituídos para melhorar a experiência do usuário.</span><span class="sxs-lookup"><span data-stu-id="1765a-108">In some cases, existing columns names are renamed or replaced to improve the user experience.</span></span> <span data-ttu-id="1765a-109">Consulte este artigo para revisar as alterações de nomeação que podem afetar suas consultas.</span><span class="sxs-lookup"><span data-stu-id="1765a-109">Refer to this article to review naming changes that could impact your queries.</span></span>

<span data-ttu-id="1765a-110">As alterações de nomeação são aplicadas automaticamente às consultas salvas no centro de segurança, incluindo consultas usadas por regras de detecção personalizadas.</span><span class="sxs-lookup"><span data-stu-id="1765a-110">Naming changes are automatically applied to queries that are saved in the security center, including queries used by custom detection rules.</span></span> <span data-ttu-id="1765a-111">Você não precisa atualizar essas consultas manualmente.</span><span class="sxs-lookup"><span data-stu-id="1765a-111">You don't need to update these queries manually.</span></span> <span data-ttu-id="1765a-112">No entanto, você precisará atualizar as seguintes consultas:</span><span class="sxs-lookup"><span data-stu-id="1765a-112">However, you will need to update the following queries:</span></span>
- <span data-ttu-id="1765a-113">Consultas que são executados usando a API</span><span class="sxs-lookup"><span data-stu-id="1765a-113">Queries that are run using the API</span></span>
- <span data-ttu-id="1765a-114">Consultas salvas em outro lugar fora da central de segurança</span><span class="sxs-lookup"><span data-stu-id="1765a-114">Queries that are saved elsewhere outside the security center</span></span>

## <a name="december-2020"></a><span data-ttu-id="1765a-115">Dezembro de 2020</span><span class="sxs-lookup"><span data-stu-id="1765a-115">December 2020</span></span>

| <span data-ttu-id="1765a-116">Nome da tabela</span><span class="sxs-lookup"><span data-stu-id="1765a-116">Table name</span></span> | <span data-ttu-id="1765a-117">Nome da coluna original</span><span class="sxs-lookup"><span data-stu-id="1765a-117">Original column name</span></span> | <span data-ttu-id="1765a-118">Novo nome de coluna</span><span class="sxs-lookup"><span data-stu-id="1765a-118">New column name</span></span> | <span data-ttu-id="1765a-119">Motivo da alteração</span><span class="sxs-lookup"><span data-stu-id="1765a-119">Reason for change</span></span>
|--|--|--|--|
| [<span data-ttu-id="1765a-120">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="1765a-120">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | <span data-ttu-id="1765a-121">FinalEmailAction</span><span class="sxs-lookup"><span data-stu-id="1765a-121">FinalEmailAction</span></span> | <span data-ttu-id="1765a-122">EmailAction</span><span class="sxs-lookup"><span data-stu-id="1765a-122">EmailAction</span></span> | <span data-ttu-id="1765a-123">Comentários dos clientes</span><span class="sxs-lookup"><span data-stu-id="1765a-123">Customer feedback</span></span> |
| [<span data-ttu-id="1765a-124">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="1765a-124">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | <span data-ttu-id="1765a-125">FinalEmailActionPolicy</span><span class="sxs-lookup"><span data-stu-id="1765a-125">FinalEmailActionPolicy</span></span> | <span data-ttu-id="1765a-126">EmailActionPolicy</span><span class="sxs-lookup"><span data-stu-id="1765a-126">EmailActionPolicy</span></span> | <span data-ttu-id="1765a-127">Comentários dos clientes</span><span class="sxs-lookup"><span data-stu-id="1765a-127">Customer feedback</span></span> |
| [<span data-ttu-id="1765a-128">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="1765a-128">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | <span data-ttu-id="1765a-129">FinalEmailActionPolicyGuid</span><span class="sxs-lookup"><span data-stu-id="1765a-129">FinalEmailActionPolicyGuid</span></span> | <span data-ttu-id="1765a-130">EmailActionPolicyGuid</span><span class="sxs-lookup"><span data-stu-id="1765a-130">EmailActionPolicyGuid</span></span> | <span data-ttu-id="1765a-131">Comentários dos clientes</span><span class="sxs-lookup"><span data-stu-id="1765a-131">Customer feedback</span></span> |

## <a name="related-topics"></a><span data-ttu-id="1765a-132">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="1765a-132">Related topics</span></span>
- [<span data-ttu-id="1765a-133">Visão geral da busca avançada</span><span class="sxs-lookup"><span data-stu-id="1765a-133">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="1765a-134">Compreender o esquema</span><span class="sxs-lookup"><span data-stu-id="1765a-134">Understand the schema</span></span>](advanced-hunting-schema-tables.md)