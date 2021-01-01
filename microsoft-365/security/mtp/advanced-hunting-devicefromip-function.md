---
title: Função DeviceFromIP () em busca avançada no Microsoft 365 defender
description: Saiba como usar a função DeviceFromIP () para obter os dispositivos aos quais foram atribuídos um endereço IP específico
keywords: caça avançada, busca de ameaças, caça à Cyber Threat, proteção de ameaças da Microsoft, Microsoft 365, MTP, M365, pesquisa, consulta, telemetria, referência de esquema, Kusto, dispositivo, devicefromIP, função, enriquecimento
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: 65409dd93f3703f1af115178c4cd9fa470fb7497
ms.sourcegitcommit: 25ac2736a66bb72c0d574c3fbde7472ac98d5321
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/31/2020
ms.locfileid: "49741100"
---
# <a name="devicefromip"></a><span data-ttu-id="b985c-104">DeviceFromIP()</span><span class="sxs-lookup"><span data-stu-id="b985c-104">DeviceFromIP()</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="b985c-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="b985c-105">**Applies to:**</span></span>
- <span data-ttu-id="b985c-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b985c-106">Microsoft 365 Defender</span></span>


[!INCLUDE [Prerelease information](../includes/prerelease.md)]


<span data-ttu-id="b985c-107">Use a `DeviceFromIP()` função nas suas consultas de [busca avançada](advanced-hunting-overview.md) para obter rapidamente a lista de dispositivos que foram atribuídos a um determinado endereço IP em um determinado momento.</span><span class="sxs-lookup"><span data-stu-id="b985c-107">Use the `DeviceFromIP()` function in your [advanced hunting](advanced-hunting-overview.md) queries to quickly obtain the list of devices that have been assigned to a certain IP address at a given point in time.</span></span> 

<span data-ttu-id="b985c-108">Essa função retorna uma tabela com as seguintes colunas:</span><span class="sxs-lookup"><span data-stu-id="b985c-108">This function returns a table with the following columns:</span></span>

| <span data-ttu-id="b985c-109">Coluna</span><span class="sxs-lookup"><span data-stu-id="b985c-109">Column</span></span> | <span data-ttu-id="b985c-110">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="b985c-110">Data type</span></span> | <span data-ttu-id="b985c-111">Descrição</span><span class="sxs-lookup"><span data-stu-id="b985c-111">Description</span></span> |
|------------|-------------|-------------|
| `IP` | <span data-ttu-id="b985c-112">string</span><span class="sxs-lookup"><span data-stu-id="b985c-112">string</span></span> | <span data-ttu-id="b985c-113">Endereço IP</span><span class="sxs-lookup"><span data-stu-id="b985c-113">IP address</span></span>  |
| `DeviceId` | <span data-ttu-id="b985c-114">string</span><span class="sxs-lookup"><span data-stu-id="b985c-114">string</span></span> | <span data-ttu-id="b985c-115">Identificador exclusivo do dispositivo no serviço</span><span class="sxs-lookup"><span data-stu-id="b985c-115">Unique identifier for the device in the service</span></span> |


## <a name="syntax"></a><span data-ttu-id="b985c-116">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="b985c-116">Syntax</span></span>

```kusto
invoke DeviceFromIP()
```

## <a name="arguments"></a><span data-ttu-id="b985c-117">Argumentos</span><span class="sxs-lookup"><span data-stu-id="b985c-117">Arguments</span></span>

<span data-ttu-id="b985c-118">Essa função é chamada como parte de uma consulta.</span><span class="sxs-lookup"><span data-stu-id="b985c-118">This function is invoked as part of a query.</span></span>

- <span data-ttu-id="b985c-119">**x**— o primeiro parâmetro normalmente já é uma coluna na consulta.</span><span class="sxs-lookup"><span data-stu-id="b985c-119">**x**—The first parameter is typically already a column in the query.</span></span> <span data-ttu-id="b985c-120">Nesse caso, é a coluna chamada `IP` , o endereço IP para o qual você deseja ver uma lista de dispositivos que foram atribuídos a ele.</span><span class="sxs-lookup"><span data-stu-id="b985c-120">In this case, it is the column named `IP`, the IP address for which you want to see a list of devices that have been assigned to it.</span></span> <span data-ttu-id="b985c-121">Deve ser um endereço IP local.</span><span class="sxs-lookup"><span data-stu-id="b985c-121">It should be a local IP address.</span></span> <span data-ttu-id="b985c-122">Não há suporte para endereços IP externos.</span><span class="sxs-lookup"><span data-stu-id="b985c-122">External IP addresses are not supported.</span></span>
- <span data-ttu-id="b985c-123">**y**— um segundo parâmetro opcional é o `Timestamp` , que instrui a função a obter os dispositivos atribuídos mais recentes de uma hora específica.</span><span class="sxs-lookup"><span data-stu-id="b985c-123">**y**—A second optional parameter is the `Timestamp`, which instructs the function to obtain the most recent assigned devices from a specific time.</span></span> <span data-ttu-id="b985c-124">Se não for especificado, a função retornará os registros mais recentes disponíveis.</span><span class="sxs-lookup"><span data-stu-id="b985c-124">If not specified, the function returns the latest available records.</span></span>

## <a name="example"></a><span data-ttu-id="b985c-125">Exemplo</span><span class="sxs-lookup"><span data-stu-id="b985c-125">Example</span></span>


### <a name="get-the-latest-devices-that-have-been-assigned-specific-ip-addresses"></a><span data-ttu-id="b985c-126">Obter os dispositivos mais recentes que foram atribuídos a endereços IP específicos</span><span class="sxs-lookup"><span data-stu-id="b985c-126">Get the latest devices that have been assigned specific IP addresses</span></span>

```kusto
DeviceNetworkEvents 
| limit 100 
| project IP = LocalIP 
| invoke DeviceFromIP()
```

## <a name="related-topics"></a><span data-ttu-id="b985c-127">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="b985c-127">Related topics</span></span>
- [<span data-ttu-id="b985c-128">Visão geral da busca avançada</span><span class="sxs-lookup"><span data-stu-id="b985c-128">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="b985c-129">Aprender a linguagem de consulta</span><span class="sxs-lookup"><span data-stu-id="b985c-129">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="b985c-130">Compreender o esquema</span><span class="sxs-lookup"><span data-stu-id="b985c-130">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
