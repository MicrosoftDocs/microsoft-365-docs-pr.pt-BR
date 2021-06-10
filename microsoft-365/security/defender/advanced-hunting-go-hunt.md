---
title: Obter informações relevantes sobre uma entidade com go hunt
description: Saiba como usar a ferramenta de busca ir para consultar rapidamente informações relevantes sobre uma entidade ou evento usando a busca avançada.
keywords: busca avançada, incidente, pivô, entidade, ir à busca, eventos relevantes, busca de ameaças, busca de ameaças cibernéticas, pesquisa, consulta, telemetria, Microsoft 365, Microsoft 365 Defender
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: a78f37d8c1fed1063095e25f19136f0362f17db7
ms.sourcegitcommit: 7cc2be0244fcc30049351e35c25369cacaaf4ca9
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/22/2021
ms.locfileid: "51952651"
---
# <a name="quickly-hunt-for-entity-or-event-information-with-go-hunt"></a><span data-ttu-id="34ac7-104">Busca rápida por informações de entidade ou evento com a busca de ida e volta</span><span class="sxs-lookup"><span data-stu-id="34ac7-104">Quickly hunt for entity or event information with go hunt</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="34ac7-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="34ac7-105">**Applies to:**</span></span>
- <span data-ttu-id="34ac7-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="34ac7-106">Microsoft 365 Defender</span></span>
- <span data-ttu-id="34ac7-107">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="34ac7-107">Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="34ac7-108">Com a *ação ir à* busca, você pode investigar rapidamente eventos e vários tipos de entidade usando recursos avançados de busca avançados baseados [em](advanced-hunting-overview.md) consulta.</span><span class="sxs-lookup"><span data-stu-id="34ac7-108">With the *go hunt* action, you can quickly investigate events and various entity types using powerful query-based [advanced hunting](advanced-hunting-overview.md) capabilities.</span></span> <span data-ttu-id="34ac7-109">Essa ação executa automaticamente uma consulta de busca avançada para encontrar informações relevantes sobre o evento ou entidade selecionado.</span><span class="sxs-lookup"><span data-stu-id="34ac7-109">This action automatically runs an advanced hunting query to find relevant information about the selected event or entity.</span></span>

<span data-ttu-id="34ac7-110">A *ação de busca* de go está disponível em várias seções do centro de segurança sempre que os detalhes do evento ou da entidade são exibidos.</span><span class="sxs-lookup"><span data-stu-id="34ac7-110">The *go hunt* action is available in various sections of the security center whenever event or entity details are displayed.</span></span> <span data-ttu-id="34ac7-111">Por exemplo, você pode usar *ir procurar* nas seguintes seções:</span><span class="sxs-lookup"><span data-stu-id="34ac7-111">For example, you can use *go hunt* from the following sections:</span></span>

- <span data-ttu-id="34ac7-112">Na página [incidente,](investigate-incidents.md#summary)você pode revisar detalhes sobre usuários, dispositivos e muitas outras entidades associadas a um incidente.</span><span class="sxs-lookup"><span data-stu-id="34ac7-112">In the [incident page](investigate-incidents.md#summary), you can review details about users, devices, and many other entities associated with an incident.</span></span> <span data-ttu-id="34ac7-113">Ao selecionar uma entidade, você obterá informações adicionais, bem como várias ações que poderia tomar nessa entidade.</span><span class="sxs-lookup"><span data-stu-id="34ac7-113">As you select an entity, you get additional information as well as various actions you could take on that entity.</span></span> <span data-ttu-id="34ac7-114">No exemplo abaixo, uma caixa de correio é selecionada, mostrando detalhes sobre a caixa de correio, bem como a opção de procurar mais informações sobre a caixa de correio.</span><span class="sxs-lookup"><span data-stu-id="34ac7-114">In the example below, a mailbox is selected, showing details about the mailbox as well the option to hunt for more information about the mailbox.</span></span>

    ![Imagem mostrando detalhes da caixa de correio com a opção ir buscar](../../media/mtp-ah/go-hunt-email.png)

- <span data-ttu-id="34ac7-116">Na página incidente, você também pode acessar uma lista de entidades na guia evidências. Selecionar uma dessas entidades fornece uma opção para procurar rapidamente informações sobre essa entidade.</span><span class="sxs-lookup"><span data-stu-id="34ac7-116">In the incident page, you can also access a list of entities under the evidence tab. Selecting one of those entities provides an option to quickly hunt for information about that entity.</span></span>

    ![Imagem mostrando o arquivo selecionado com a opção ir buscar na guia Evidências](../../media/mtp-ah/go-hunt-evidence-file.png)


- <span data-ttu-id="34ac7-118">Ao exibir a linha do tempo de um dispositivo, você pode selecionar um evento na linha do tempo para exibir informações adicionais sobre esse evento.</span><span class="sxs-lookup"><span data-stu-id="34ac7-118">When viewing the timeline for a device, you can select an event in the timeline to view additional information about that event.</span></span> <span data-ttu-id="34ac7-119">Depois que um evento é selecionado, você tem a opção de procurar outros eventos relevantes na busca avançada.</span><span class="sxs-lookup"><span data-stu-id="34ac7-119">Once an event is selected, you get the option to hunt for other relevant events in advanced hunting.</span></span>

    ![Imagem mostrando detalhes do evento com a opção ir buscar](../../media/mtp-ah/go-hunt-event.png)

<span data-ttu-id="34ac7-121">Selecionar **Ir procurar** ou procurar **eventos** relacionados passa por diferentes consultas, dependendo se você selecionou uma entidade ou um evento.</span><span class="sxs-lookup"><span data-stu-id="34ac7-121">Selecting **Go hunt** or **Hunt for related events** passes different queries, depending on whether you've selected an entity or an event.</span></span>

## <a name="query-for-entity-information"></a><span data-ttu-id="34ac7-122">Consulta para informações da entidade</span><span class="sxs-lookup"><span data-stu-id="34ac7-122">Query for entity information</span></span>
<span data-ttu-id="34ac7-123">Ao usar *o go hunt* to query for information about a user, device, or any other type of entity, the query checks all relevant schema tables for any events involving that entity.</span><span class="sxs-lookup"><span data-stu-id="34ac7-123">When using *go hunt* to query for information about a user, device, or any other type of entity, the query checks all relevant schema tables for any events involving that entity.</span></span> <span data-ttu-id="34ac7-124">Para manter os resultados gerenciáveis, a consulta tem escopo para o mesmo período de tempo que a atividade mais antiga nos últimos 30 dias que envolve a entidade e está associada ao incidente.</span><span class="sxs-lookup"><span data-stu-id="34ac7-124">To keep the results manageable, the query is scoped to around the same time period as the earliest activity in the past 30 days that involves the entity and is associated with the incident.</span></span>

<span data-ttu-id="34ac7-125">Aqui está um exemplo da consulta go hunt para um dispositivo:</span><span class="sxs-lookup"><span data-stu-id="34ac7-125">Here is an example of the go hunt query for a device:</span></span>

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
### <a name="supported-entity-types"></a><span data-ttu-id="34ac7-126">Tipos de entidade com suporte</span><span class="sxs-lookup"><span data-stu-id="34ac7-126">Supported entity types</span></span>
<span data-ttu-id="34ac7-127">Você pode usar *ir procurar depois* de selecionar qualquer um desses tipos de entidade:</span><span class="sxs-lookup"><span data-stu-id="34ac7-127">You can use *go hunt* after selecting any of these entity types:</span></span>

- <span data-ttu-id="34ac7-128">Arquivos</span><span class="sxs-lookup"><span data-stu-id="34ac7-128">Files</span></span>
- <span data-ttu-id="34ac7-129">Emails</span><span class="sxs-lookup"><span data-stu-id="34ac7-129">Emails</span></span>
- <span data-ttu-id="34ac7-130">Clusters de email</span><span class="sxs-lookup"><span data-stu-id="34ac7-130">Email clusters</span></span>
- <span data-ttu-id="34ac7-131">Caixas de correio</span><span class="sxs-lookup"><span data-stu-id="34ac7-131">Mailboxes</span></span>
- <span data-ttu-id="34ac7-132">Usuários</span><span class="sxs-lookup"><span data-stu-id="34ac7-132">Users</span></span>
- <span data-ttu-id="34ac7-133">Dispositivos</span><span class="sxs-lookup"><span data-stu-id="34ac7-133">Devices</span></span>
- <span data-ttu-id="34ac7-134">Endereços IP</span><span class="sxs-lookup"><span data-stu-id="34ac7-134">IP addresses</span></span>
- <span data-ttu-id="34ac7-135">URLs</span><span class="sxs-lookup"><span data-stu-id="34ac7-135">URLs</span></span>

## <a name="query-for-event-information"></a><span data-ttu-id="34ac7-136">Consulta para informações do evento</span><span class="sxs-lookup"><span data-stu-id="34ac7-136">Query for event information</span></span>
<span data-ttu-id="34ac7-137">Ao usar *o go hunt* to query for information about a timeline event, the query checks all relevant schema tables for other events around the time of the selected event.</span><span class="sxs-lookup"><span data-stu-id="34ac7-137">When using *go hunt* to query for information about a timeline event, the query checks all relevant schema tables for other events around the time of the selected event.</span></span> <span data-ttu-id="34ac7-138">Por exemplo, a consulta a seguir lista eventos em várias tabelas de esquema que ocorreram ao redor do mesmo período de tempo no mesmo dispositivo:</span><span class="sxs-lookup"><span data-stu-id="34ac7-138">For example, the following query lists events in various schema tables that occurred around the same time period on the same device:</span></span>

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

## <a name="adjust-the-query"></a><span data-ttu-id="34ac7-139">Ajustar a consulta</span><span class="sxs-lookup"><span data-stu-id="34ac7-139">Adjust the query</span></span>
<span data-ttu-id="34ac7-140">Com algum conhecimento do [idioma de consulta,](advanced-hunting-query-language.md)você pode ajustar a consulta à sua preferência.</span><span class="sxs-lookup"><span data-stu-id="34ac7-140">With some knowledge of the [query language](advanced-hunting-query-language.md), you can adjust the query to your preference.</span></span> <span data-ttu-id="34ac7-141">Por exemplo, você pode ajustar essa linha, que determina o tamanho da janela de tempo:</span><span class="sxs-lookup"><span data-stu-id="34ac7-141">For example, you can adjust this line, which determines the size of the time window:</span></span>

```kusto
Timestamp between ((selectedTimestamp - 1h) .. (selectedTimestamp + 1h))
```

<span data-ttu-id="34ac7-142">Além de modificar a consulta para obter resultados mais relevantes, você também pode:</span><span class="sxs-lookup"><span data-stu-id="34ac7-142">In addition to modifying the query to get more relevant results, you can also:</span></span>
- [<span data-ttu-id="34ac7-143">Exibir os resultados como gráficos</span><span class="sxs-lookup"><span data-stu-id="34ac7-143">View the results as charts</span></span>](advanced-hunting-query-results.md#view-query-results-as-a-table-or-chart)
- [<span data-ttu-id="34ac7-144">Criar uma regra de detecção personalizada</span><span class="sxs-lookup"><span data-stu-id="34ac7-144">Create a custom detection rule</span></span>](custom-detection-rules.md)

>[!NOTE]
><span data-ttu-id="34ac7-145">Algumas tabelas neste artigo podem não estar disponíveis no Microsoft Defender para Ponto de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="34ac7-145">Some tables in this article might not be available in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="34ac7-146">[A Microsoft 365 Defender para](m365d-enable.md) procurar ameaças usando mais fontes de dados.</span><span class="sxs-lookup"><span data-stu-id="34ac7-146">[Turn on Microsoft 365 Defender](m365d-enable.md) to hunt for threats using more data sources.</span></span> <span data-ttu-id="34ac7-147">Você pode mover seus fluxos de trabalho de busca avançados do Microsoft Defender para o Endpoint para o Microsoft 365 Defender seguindo as etapas em Migrar consultas de busca avançadas do Microsoft Defender para o Ponto de [Extremidade.](advanced-hunting-migrate-from-mde.md)</span><span class="sxs-lookup"><span data-stu-id="34ac7-147">You can move your advanced hunting workflows from Microsoft Defender for Endpoint to Microsoft 365 Defender by following the steps in [Migrate advanced hunting queries from Microsoft Defender for Endpoint](advanced-hunting-migrate-from-mde.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="34ac7-148">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="34ac7-148">Related topics</span></span>
- [<span data-ttu-id="34ac7-149">Visão geral da busca avançada</span><span class="sxs-lookup"><span data-stu-id="34ac7-149">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="34ac7-150">Aprender a linguagem de consulta</span><span class="sxs-lookup"><span data-stu-id="34ac7-150">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="34ac7-151">Trabalhar com os resultados da consulta</span><span class="sxs-lookup"><span data-stu-id="34ac7-151">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="34ac7-152">Regras de detecção personalizadas</span><span class="sxs-lookup"><span data-stu-id="34ac7-152">Custom detection rules</span></span>](custom-detection-rules.md)
