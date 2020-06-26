---
title: Tabela AppFileEvents no esquema de busca avançada
description: Saiba mais sobre eventos relacionados a arquivos associados a serviços e aplicativos em nuvem na tabela AppFileEvents do esquema de busca avançada
keywords: caça avançada, busca de ameaças, busca de ameaças da CyberSource, proteção de ameaças da Microsoft, Microsoft 365, MTP, M365, pesquisa, consulta, telemetria, referência de esquema, Kusto, tabela, coluna, tipo de dados, descrição, AppFileEvents, segurança do aplicativo em nuvem, MCAS
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
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
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: da3b331d4f607aa0961e275db9444aadbec4fcf2
ms.sourcegitcommit: ab10c042e5e9c6a7b2afef930ab0d247a6aa275d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/26/2020
ms.locfileid: "44899334"
---
# <a name="appfileevents"></a><span data-ttu-id="c5f3a-104">AppFileEvents</span><span class="sxs-lookup"><span data-stu-id="c5f3a-104">AppFileEvents</span></span>

<span data-ttu-id="c5f3a-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="c5f3a-105">**Applies to:**</span></span>
- <span data-ttu-id="c5f3a-106">Proteção contra Ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="c5f3a-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="c5f3a-107">A `AppFileEvents` tabela no esquema de [busca avançada](advanced-hunting-overview.md) contém informações sobre atividades relacionadas a arquivos em aplicativos de nuvem e serviços monitorados pelo Microsoft Cloud app Security.</span><span class="sxs-lookup"><span data-stu-id="c5f3a-107">The `AppFileEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about file-related activities in cloud apps and services monitored by Microsoft Cloud App Security.</span></span> <span data-ttu-id="c5f3a-108">Use essa referência para criar consultas que retornam informações dessa tabela.</span><span class="sxs-lookup"><span data-stu-id="c5f3a-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="c5f3a-109">Para obter informações sobre outras tabelas no esquema de busca avançada, [confira a referência de busca avançada](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="c5f3a-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="c5f3a-110">Nome da coluna</span><span class="sxs-lookup"><span data-stu-id="c5f3a-110">Column name</span></span> | <span data-ttu-id="c5f3a-111">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="c5f3a-111">Data type</span></span> | <span data-ttu-id="c5f3a-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="c5f3a-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="c5f3a-113">datetime</span><span class="sxs-lookup"><span data-stu-id="c5f3a-113">datetime</span></span> | <span data-ttu-id="c5f3a-114">A data e a hora em que o evento foi gravado</span><span class="sxs-lookup"><span data-stu-id="c5f3a-114">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="c5f3a-115">string</span><span class="sxs-lookup"><span data-stu-id="c5f3a-115">string</span></span> | <span data-ttu-id="c5f3a-116">Tipo de atividade que disparou o evento</span><span class="sxs-lookup"><span data-stu-id="c5f3a-116">Type of activity that triggered the event</span></span> |
| `Application` | <span data-ttu-id="c5f3a-117">string</span><span class="sxs-lookup"><span data-stu-id="c5f3a-117">string</span></span> | <span data-ttu-id="c5f3a-118">Aplicativo que executou a ação gravada</span><span class="sxs-lookup"><span data-stu-id="c5f3a-118">Application that performed the recorded action</span></span> |
| `FileName` | <span data-ttu-id="c5f3a-119">string</span><span class="sxs-lookup"><span data-stu-id="c5f3a-119">string</span></span> | <span data-ttu-id="c5f3a-120">Nome do arquivo ao qual a ação gravada foi aplicada</span><span class="sxs-lookup"><span data-stu-id="c5f3a-120">Name of the file that the recorded action was applied to</span></span> |
| `FolderPath` | <span data-ttu-id="c5f3a-121">string</span><span class="sxs-lookup"><span data-stu-id="c5f3a-121">string</span></span> | <span data-ttu-id="c5f3a-122">Pasta que contém o arquivo para o qual a ação registrada foi aplicada</span><span class="sxs-lookup"><span data-stu-id="c5f3a-122">Folder containing the file that the recorded action was applied to</span></span> |
| `PreviousFileName` | <span data-ttu-id="c5f3a-123">string</span><span class="sxs-lookup"><span data-stu-id="c5f3a-123">string</span></span> | <span data-ttu-id="c5f3a-124">O nome original do arquivo que foi renomeado como resultado da ação</span><span class="sxs-lookup"><span data-stu-id="c5f3a-124">Original name of the file that was renamed as a result of the action</span></span> |
| `AccountName` | <span data-ttu-id="c5f3a-125">string</span><span class="sxs-lookup"><span data-stu-id="c5f3a-125">string</span></span> | <span data-ttu-id="c5f3a-126">Nome de usuário da conta</span><span class="sxs-lookup"><span data-stu-id="c5f3a-126">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="c5f3a-127">string</span><span class="sxs-lookup"><span data-stu-id="c5f3a-127">string</span></span> | <span data-ttu-id="c5f3a-128">Domínio da conta</span><span class="sxs-lookup"><span data-stu-id="c5f3a-128">Domain of the account</span></span> |
| `AccountUpn` | <span data-ttu-id="c5f3a-129">string</span><span class="sxs-lookup"><span data-stu-id="c5f3a-129">string</span></span> | <span data-ttu-id="c5f3a-130">Nome principal do usuário (UPN) da conta</span><span class="sxs-lookup"><span data-stu-id="c5f3a-130">User principal name (UPN) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="c5f3a-131">string</span><span class="sxs-lookup"><span data-stu-id="c5f3a-131">string</span></span> | <span data-ttu-id="c5f3a-132">Identificador exclusivo da conta no Azure AD</span><span class="sxs-lookup"><span data-stu-id="c5f3a-132">Unique identifier for the account in Azure AD</span></span> |
| `AccountDisplayName` | <span data-ttu-id="c5f3a-133">string</span><span class="sxs-lookup"><span data-stu-id="c5f3a-133">string</span></span> | <span data-ttu-id="c5f3a-134">Nome do usuário da conta exibido no catálogo de endereços.</span><span class="sxs-lookup"><span data-stu-id="c5f3a-134">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="c5f3a-135">Normalmente, uma combinação de um determinado nome ou primeiro, um início do meio e um sobrenome ou sobrenome.</span><span class="sxs-lookup"><span data-stu-id="c5f3a-135">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `IPAddress` | <span data-ttu-id="c5f3a-136">string</span><span class="sxs-lookup"><span data-stu-id="c5f3a-136">string</span></span> | <span data-ttu-id="c5f3a-137">Endereço IP atribuído ao ponto de extremidade e usado durante as comunicações de rede relacionadas</span><span class="sxs-lookup"><span data-stu-id="c5f3a-137">IP address assigned to the endpoint and used during related network communications</span></span> |
| `Location` | <span data-ttu-id="c5f3a-138">string</span><span class="sxs-lookup"><span data-stu-id="c5f3a-138">string</span></span> | <span data-ttu-id="c5f3a-139">Cidade, país ou outra localização geográfica associada ao evento</span><span class="sxs-lookup"><span data-stu-id="c5f3a-139">City, country, or other geographic location associated with the event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="c5f3a-140">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="c5f3a-140">Related topics</span></span>
- [<span data-ttu-id="c5f3a-141">Visão geral da caça avançada</span><span class="sxs-lookup"><span data-stu-id="c5f3a-141">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="c5f3a-142">Aprender a linguagem de consulta</span><span class="sxs-lookup"><span data-stu-id="c5f3a-142">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="c5f3a-143">Usar consultas compartilhadas</span><span class="sxs-lookup"><span data-stu-id="c5f3a-143">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="c5f3a-144">Buscar por ameaças em dispositivos e emails</span><span class="sxs-lookup"><span data-stu-id="c5f3a-144">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="c5f3a-145">Compreender o esquema</span><span class="sxs-lookup"><span data-stu-id="c5f3a-145">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="c5f3a-146">Aplicar práticas recomendadas de consulta</span><span class="sxs-lookup"><span data-stu-id="c5f3a-146">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
