---
title: Função DeviceFromIP() em busca avançada do Microsoft 365 Defender
description: Saiba como usar a função DeviceFromIP() para obter os dispositivos aos quais foi atribuído um endereço IP específico
keywords: busca avançada, busca de ameaças, busca de ameaças cibernéticas, proteção contra ameaças da Microsoft, microsoft 365, mtp, m365, pesquisa, consulta, telemetria, referência de esquema, kusto, dispositivo, devicefromIP, função, enriquecimento
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
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 86373c903252fde4ab71c80a81404428a7366da7
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49931297"
---
# <a name="devicefromip"></a><span data-ttu-id="91cd0-104">DeviceFromIP()</span><span class="sxs-lookup"><span data-stu-id="91cd0-104">DeviceFromIP()</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="91cd0-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="91cd0-105">**Applies to:**</span></span>
- <span data-ttu-id="91cd0-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="91cd0-106">Microsoft 365 Defender</span></span>


[!INCLUDE [Prerelease information](../includes/prerelease.md)]


<span data-ttu-id="91cd0-107">Use a função em suas consultas de busca avançada para obter rapidamente a lista de dispositivos que foram atribuídos a um determinado endereço IP em `DeviceFromIP()` um determinado momento. [](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="91cd0-107">Use the `DeviceFromIP()` function in your [advanced hunting](advanced-hunting-overview.md) queries to quickly obtain the list of devices that have been assigned to a certain IP address at a given point in time.</span></span> 

<span data-ttu-id="91cd0-108">Esta função retorna uma tabela com as seguintes colunas:</span><span class="sxs-lookup"><span data-stu-id="91cd0-108">This function returns a table with the following columns:</span></span>

| <span data-ttu-id="91cd0-109">Coluna</span><span class="sxs-lookup"><span data-stu-id="91cd0-109">Column</span></span> | <span data-ttu-id="91cd0-110">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="91cd0-110">Data type</span></span> | <span data-ttu-id="91cd0-111">Descrição</span><span class="sxs-lookup"><span data-stu-id="91cd0-111">Description</span></span> |
|------------|-------------|-------------|
| `IP` | <span data-ttu-id="91cd0-112">string</span><span class="sxs-lookup"><span data-stu-id="91cd0-112">string</span></span> | <span data-ttu-id="91cd0-113">Endereço IP</span><span class="sxs-lookup"><span data-stu-id="91cd0-113">IP address</span></span>  |
| `DeviceId` | <span data-ttu-id="91cd0-114">string</span><span class="sxs-lookup"><span data-stu-id="91cd0-114">string</span></span> | <span data-ttu-id="91cd0-115">Identificador exclusivo do dispositivo no serviço</span><span class="sxs-lookup"><span data-stu-id="91cd0-115">Unique identifier for the device in the service</span></span> |


## <a name="syntax"></a><span data-ttu-id="91cd0-116">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="91cd0-116">Syntax</span></span>

```kusto
invoke DeviceFromIP()
```

## <a name="arguments"></a><span data-ttu-id="91cd0-117">Argumentos</span><span class="sxs-lookup"><span data-stu-id="91cd0-117">Arguments</span></span>

<span data-ttu-id="91cd0-118">Essa função é invocada como parte de uma consulta.</span><span class="sxs-lookup"><span data-stu-id="91cd0-118">This function is invoked as part of a query.</span></span>

- <span data-ttu-id="91cd0-119">**x**— O primeiro parâmetro geralmente já é uma coluna na consulta.</span><span class="sxs-lookup"><span data-stu-id="91cd0-119">**x**—The first parameter is typically already a column in the query.</span></span> <span data-ttu-id="91cd0-120">Nesse caso, é a coluna chamada , o endereço IP para o qual você deseja ver uma lista de dispositivos que `IP` foram atribuídos a ela.</span><span class="sxs-lookup"><span data-stu-id="91cd0-120">In this case, it is the column named `IP`, the IP address for which you want to see a list of devices that have been assigned to it.</span></span> <span data-ttu-id="91cd0-121">Deve ser um endereço IP local.</span><span class="sxs-lookup"><span data-stu-id="91cd0-121">It should be a local IP address.</span></span> <span data-ttu-id="91cd0-122">Não há suporte para endereços IP externos.</span><span class="sxs-lookup"><span data-stu-id="91cd0-122">External IP addresses are not supported.</span></span>
- <span data-ttu-id="91cd0-123">**y**— Um segundo parâmetro opcional é o , que instrui a função a obter os dispositivos atribuídos mais recentes `Timestamp` de um horário específico.</span><span class="sxs-lookup"><span data-stu-id="91cd0-123">**y**—A second optional parameter is the `Timestamp`, which instructs the function to obtain the most recent assigned devices from a specific time.</span></span> <span data-ttu-id="91cd0-124">Se não for especificada, a função retornará os registros disponíveis mais recentes.</span><span class="sxs-lookup"><span data-stu-id="91cd0-124">If not specified, the function returns the latest available records.</span></span>

## <a name="example"></a><span data-ttu-id="91cd0-125">Exemplo</span><span class="sxs-lookup"><span data-stu-id="91cd0-125">Example</span></span>


### <a name="get-the-latest-devices-that-have-been-assigned-specific-ip-addresses"></a><span data-ttu-id="91cd0-126">Obter os dispositivos mais recentes que foram atribuídos a endereços IP específicos</span><span class="sxs-lookup"><span data-stu-id="91cd0-126">Get the latest devices that have been assigned specific IP addresses</span></span>

```kusto
DeviceNetworkEvents 
| limit 100 
| project IP = LocalIP 
| invoke DeviceFromIP()
```

## <a name="related-topics"></a><span data-ttu-id="91cd0-127">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="91cd0-127">Related topics</span></span>
- [<span data-ttu-id="91cd0-128">Visão geral da busca avançada</span><span class="sxs-lookup"><span data-stu-id="91cd0-128">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="91cd0-129">Aprender a linguagem de consulta</span><span class="sxs-lookup"><span data-stu-id="91cd0-129">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="91cd0-130">Compreender o esquema</span><span class="sxs-lookup"><span data-stu-id="91cd0-130">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
