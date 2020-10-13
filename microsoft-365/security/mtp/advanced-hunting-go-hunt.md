---
title: Obter informações relevantes sobre uma entidade com busca no go
description: Saiba como usar a ferramenta "buscar busca" para consultar rapidamente informações relevantes sobre uma entidade ou um evento usando a busca avançada.
keywords: caça avançada, incidente, pivô, entidade, busca de Go, eventos relevantes, busca de ameaças, busca de ameaças no cyber, pesquisa, consulta, telemetria, Microsoft 365, proteção contra ameaças da Microsoft
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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.openlocfilehash: 4abbedc34b6d77e785c2096d9f334000f9ffb02f
ms.sourcegitcommit: de600339b08951d6dd3933288a8da2327a4b6ef3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "48430462"
---
# <a name="quickly-hunt-for-entity-or-event-information-with-go-hunt"></a><span data-ttu-id="e2102-104">Busca rápida de informações de entidade ou de evento com busca no go</span><span class="sxs-lookup"><span data-stu-id="e2102-104">Quickly hunt for entity or event information with go hunt</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="e2102-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="e2102-105">**Applies to:**</span></span>
- <span data-ttu-id="e2102-106">Proteção contra Ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="e2102-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="e2102-107">Com a ação de *busca do Go* , você pode investigar rapidamente eventos e vários tipos de entidade usando recursos [avançados de busca avançada](advanced-hunting-overview.md) baseados em consulta.</span><span class="sxs-lookup"><span data-stu-id="e2102-107">With the *go hunt* action, you can quickly investigate events and various entity types using powerful query-based [advanced hunting](advanced-hunting-overview.md) capabilities.</span></span> <span data-ttu-id="e2102-108">Esta ação executa automaticamente uma consulta de busca avançada para localizar informações relevantes sobre o evento ou entidade selecionado.</span><span class="sxs-lookup"><span data-stu-id="e2102-108">This action automatically runs an advanced hunting query to find relevant information about the selected event or entity.</span></span>

<span data-ttu-id="e2102-109">A ação ir para a *busca* está disponível em várias seções da central de segurança sempre que os detalhes do evento ou da entidade são exibidos.</span><span class="sxs-lookup"><span data-stu-id="e2102-109">The *go hunt* action is available in various sections of the security center whenever event or entity details are displayed.</span></span> <span data-ttu-id="e2102-110">Por exemplo, você pode usar a *busca do Go* das seguintes seções:</span><span class="sxs-lookup"><span data-stu-id="e2102-110">For example, you can use *go hunt* from the following sections:</span></span>

- <span data-ttu-id="e2102-111">Na [página incidente](investigate-incidents.md#incident-overview), você pode revisar detalhes sobre usuários, dispositivos e muitas outras entidades associadas a um incidente.</span><span class="sxs-lookup"><span data-stu-id="e2102-111">In the [incident page](investigate-incidents.md#incident-overview), you can review details about users, devices, and many other entities associated with an incident.</span></span> <span data-ttu-id="e2102-112">À medida que você seleciona uma entidade, obtém informações adicionais, bem como várias ações que podem ser executadas naquele entitity.</span><span class="sxs-lookup"><span data-stu-id="e2102-112">As you select an entity, you get additional information as well as various actions you could take on that entitity.</span></span> <span data-ttu-id="e2102-113">No exemplo abaixo, uma caixa de correio é selecionada, mostrando os detalhes sobre a caixa de correio, bem como a opção de busca para obter mais informações sobre a caixa de correio.</span><span class="sxs-lookup"><span data-stu-id="e2102-113">In the example below, a mailbox is selected, showing details about the mailbox as well the option to hunt for more information about the mailbox.</span></span>

    ![Imagem mostrando os detalhes da caixa de correio com a opção ir para a busca](../../media/mtp-ah/go-hunt-email.png)

- <span data-ttu-id="e2102-115">Na página incidente, você também pode acessar uma lista de entidades na guia evidência. Selecionar uma dessas entidades oferece uma opção de busca rápida de informações sobre essa entidade.</span><span class="sxs-lookup"><span data-stu-id="e2102-115">In the incident page, you can also access a list of entities under the evidence tab. Selecting one of those entities provides an option to quickly hunt for information about that entity.</span></span>

    ![Imagem mostrando o arquivo selecionado com a opção ir para a busca na guia evidência](../../media/mtp-ah/go-hunt-evidence-file.png)


- <span data-ttu-id="e2102-117">Ao exibir a linha do tempo de um dispositivo, você pode selecionar um evento na linha do tempo para exibir informações adicionais sobre o evento.</span><span class="sxs-lookup"><span data-stu-id="e2102-117">When viewing the timeline for a device, you can select an event in the timeline to view additional information about that event.</span></span> <span data-ttu-id="e2102-118">Depois que um evento for selecionado, você terá a opção de procurar outros eventos relevantes na busca avançada.</span><span class="sxs-lookup"><span data-stu-id="e2102-118">Once an event is selected, you get the option to hunt for other relevant events in advanced hunting.</span></span>

    ![Imagem mostrando detalhes do evento com a opção ir para a busca](../../media/mtp-ah/go-hunt-event.png)

<span data-ttu-id="e2102-120">Selecionar a **busca de ir** ou procurar **eventos relacionados passa por** diferentes consultas, dependendo se você selecionou uma entidade ou um evento.</span><span class="sxs-lookup"><span data-stu-id="e2102-120">Selecting **Go hunt** or **Hunt for related events** passes different queries, depending on whether you've selected an entity or an event.</span></span>

## <a name="query-for-entity-information"></a><span data-ttu-id="e2102-121">Consultar informações da entidade</span><span class="sxs-lookup"><span data-stu-id="e2102-121">Query for entity information</span></span>
<span data-ttu-id="e2102-122">Ao usar a *busca do Go* para consultar informações sobre um usuário, dispositivo ou qualquer outro tipo de entidade, a consulta verifica todas as tabelas de esquema relevantes para todos os eventos que envolvem essa entidade.</span><span class="sxs-lookup"><span data-stu-id="e2102-122">When using *go hunt* to query for information about a user, device, or any other type of entity, the query checks all relevant schema tables for any events involving that entity.</span></span> <span data-ttu-id="e2102-123">Para manter os resultados gerenciáveis, a consulta tem o escopo em torno do mesmo período de tempo que a atividade mais antiga nos últimos 30 dias que envolve a entidade e é associada ao incidente.</span><span class="sxs-lookup"><span data-stu-id="e2102-123">To keep the results manageable, the query is scoped to around the same time period as the earliest activity in the past 30 days that involves the entity and is associated with the incident.</span></span>

<span data-ttu-id="e2102-124">Veja um exemplo da consulta de busca do Go para um dispositivo:</span><span class="sxs-lookup"><span data-stu-id="e2102-124">Here is an example of the go hunt query for a device:</span></span>

```kusto
let selectedTimestamp = datetime(2020-06-02T02:06:47.1167157Z);
let deviceName = "fv-az770.example.com";
let deviceId = "device-guid";
search in (DeviceLogonEvents, DeviceProcessEvents, DeviceNetworkEvents, DeviceFileEvents, DeviceRegistryEvents, DeviceImageLoadEvents, DeviceEvents, DeviceImageLoadEvents, IdentityLogonEvents, IdentityQueryEvents)
Timestamp between ((selectedTimestamp - 1h) .. (selectedTimestamp + 1h))
and DeviceName == deviceName
// or RemoteDeviceName == deviceName
// or DeviceId == deviceId
| take 100
```
### <a name="supported-entity-types"></a><span data-ttu-id="e2102-125">Tipos de entidade com suporte</span><span class="sxs-lookup"><span data-stu-id="e2102-125">Supported entity types</span></span>
<span data-ttu-id="e2102-126">Você pode usar a *busca do Go* depois de selecionar qualquer um desses tipos de entidade:</span><span class="sxs-lookup"><span data-stu-id="e2102-126">You can use *go hunt* after selecting any of these entity types:</span></span>

- <span data-ttu-id="e2102-127">Arquivos</span><span class="sxs-lookup"><span data-stu-id="e2102-127">Files</span></span>
- <span data-ttu-id="e2102-128">Emails</span><span class="sxs-lookup"><span data-stu-id="e2102-128">Emails</span></span>
- <span data-ttu-id="e2102-129">Clusters de email</span><span class="sxs-lookup"><span data-stu-id="e2102-129">Email clusters</span></span>
- <span data-ttu-id="e2102-130">Caixas de correio</span><span class="sxs-lookup"><span data-stu-id="e2102-130">Mailboxes</span></span>
- <span data-ttu-id="e2102-131">Usuários</span><span class="sxs-lookup"><span data-stu-id="e2102-131">Users</span></span>
- <span data-ttu-id="e2102-132">Dispositivos</span><span class="sxs-lookup"><span data-stu-id="e2102-132">Devices</span></span>
- <span data-ttu-id="e2102-133">Endereços IP</span><span class="sxs-lookup"><span data-stu-id="e2102-133">IP addresses</span></span>
- <span data-ttu-id="e2102-134">URLs</span><span class="sxs-lookup"><span data-stu-id="e2102-134">URLs</span></span>

## <a name="query-for-event-information"></a><span data-ttu-id="e2102-135">Consultar informações de eventos</span><span class="sxs-lookup"><span data-stu-id="e2102-135">Query for event information</span></span>
<span data-ttu-id="e2102-136">Ao usar a *busca do Go* para consultar informações sobre um evento de linha do tempo, a consulta verifica todas as tabelas de esquema relevantes para outros eventos em torno do momento do evento selecionado.</span><span class="sxs-lookup"><span data-stu-id="e2102-136">When using *go hunt* to query for information about a timeline event, the query checks all relevant schema tables for other events around the time of the selected event.</span></span> <span data-ttu-id="e2102-137">Por exemplo, a consulta a seguir lista os eventos em várias tabelas de esquema que ocorreram em torno do mesmo período de tempo no mesmo dispositivo:</span><span class="sxs-lookup"><span data-stu-id="e2102-137">For example, the following query lists events in various schema tables that occured around the same time period on the same device:</span></span>

```kusto
// List relevant events 30 minutes before and after selected LogonAttempted event
let selectedEventTimestamp = datetime(2020-06-04T01:29:09.2496688Z);
search in (DeviceFileEvents, DeviceProcessEvents, DeviceEvents, DeviceRegistryEvents, DeviceNetworkEvents, DeviceImageLoadEvents, DeviceLogonEvents)
    Timestamp between ((selectedEventTimestamp - 30m) .. (selectedEventTimestamp + 30m))
    and DeviceId == "079ecf9c5798d249128817619606c1c47369eb3e"
| sort by Timestamp desc
| extend Relevance = iff(Timestamp == selectedEventTimestamp, "Selected event", iff(Timestamp < selectedEventTimestamp, "Earlier event", "Later event"))
| project-reorder Relevance
```

## <a name="adjust-the-query"></a><span data-ttu-id="e2102-138">Ajustar a consulta</span><span class="sxs-lookup"><span data-stu-id="e2102-138">Adjust the query</span></span>
<span data-ttu-id="e2102-139">Com algum conhecimento da [linguagem de consulta](advanced-hunting-query-language.md), você pode ajustar a consulta à sua preferência.</span><span class="sxs-lookup"><span data-stu-id="e2102-139">With some knowledge of the [query language](advanced-hunting-query-language.md), you can adjust the query to your preference.</span></span> <span data-ttu-id="e2102-140">Por exemplo, você pode ajustar essa linha, que determina o tamanho da janela de tempo:</span><span class="sxs-lookup"><span data-stu-id="e2102-140">For example, you can adjust this line, which determines the size of the time window:</span></span>

```kusto
Timestamp between ((selectedTimestamp - 1h) .. (selectedTimestamp + 1h))
```

<span data-ttu-id="e2102-141">Além de modificar a consulta para obter resultados mais relevantes, você também pode:</span><span class="sxs-lookup"><span data-stu-id="e2102-141">In addition to modifying the query to get more relevant results, you can also:</span></span>
- [<span data-ttu-id="e2102-142">Exibir os resultados como gráficos</span><span class="sxs-lookup"><span data-stu-id="e2102-142">View the results as charts</span></span>](advanced-hunting-query-results.md#view-query-results-as-a-table-or-chart)
- [<span data-ttu-id="e2102-143">Criar uma regra de detecção personalizada</span><span class="sxs-lookup"><span data-stu-id="e2102-143">Create a custom detection rule</span></span>](custom-detection-rules.md)

## <a name="related-topics"></a><span data-ttu-id="e2102-144">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="e2102-144">Related topics</span></span>
- [<span data-ttu-id="e2102-145">Visão geral da busca avançada</span><span class="sxs-lookup"><span data-stu-id="e2102-145">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="e2102-146">Aprender a linguagem de consulta</span><span class="sxs-lookup"><span data-stu-id="e2102-146">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="e2102-147">Trabalhar com os resultados da consulta</span><span class="sxs-lookup"><span data-stu-id="e2102-147">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="e2102-148">Regras de detecção personalizadas</span><span class="sxs-lookup"><span data-stu-id="e2102-148">Custom detection rules</span></span>](custom-detection-rules.md)
