---
title: SDK base de teste para Python
description: Detalhes sobre como entender o SDK da Base de Teste para Python
search.appverid: MET150
author: mansipatel-usl
ms.author: mapatel
manager: rshastri
audience: Software-Vendor
ms.topic: article
ms.date: 07/06/2021
ms.service: virtual-desktop
localization_priority: Normal
ms.collection: TestBase-M365
ms.custom: ''
ms.reviewer: mapatel
f1.keywords: NOCSH
ms.openlocfilehash: c7f2d4b7b600e84b2ed35cce320dcb7d7191ecfc
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2021
ms.locfileid: "53322465"
---
# <a name="test-base-sdk-for-python"></a><span data-ttu-id="b61c3-103">SDK base de teste para Python</span><span class="sxs-lookup"><span data-stu-id="b61c3-103">Test Base SDK for Python</span></span>

## <a name="overview"></a><span data-ttu-id="b61c3-104">Visão geral</span><span class="sxs-lookup"><span data-stu-id="b61c3-104">Overview</span></span>
<span data-ttu-id="b61c3-105">O SDK base de teste pode ser usado para interagir com o recurso base de teste do Azure.</span><span class="sxs-lookup"><span data-stu-id="b61c3-105">The Test Base SDK can be used to interact with the Azure test base resource.</span></span> <span data-ttu-id="b61c3-106">(ou seja, gerenciar seu pacote de aplicativos, incluir criar pacote, editar pacote e excluir pacote)</span><span class="sxs-lookup"><span data-stu-id="b61c3-106">(i.e. manage your application package, include create package, edit package and delete package)</span></span>

<span data-ttu-id="b61c3-107">Com o SDK, o resumo de teste e o Resultado de Análise que podem ser obtidos incluem : scriptExecution, confiabilidade, memoryUtilization, cpuUtilization, memoryRegression, cpuRegression.</span><span class="sxs-lookup"><span data-stu-id="b61c3-107">With the SDK, the test summary and Analysis Result which can be gotten include : scriptExecution, reliability, memoryUtilization, cpuUtilization, memoryRegression, cpuRegression.</span></span>

<span data-ttu-id="b61c3-108">Com o SDK base de teste, você pode integrar a base de teste no pipeline ci/CD.</span><span class="sxs-lookup"><span data-stu-id="b61c3-108">With the Test Base SDK, you can integrate test base in your CI/CD pipeline.</span></span>

## <a name="client-library"></a><span data-ttu-id="b61c3-109">Biblioteca do Cliente</span><span class="sxs-lookup"><span data-stu-id="b61c3-109">Client Library</span></span>

<span data-ttu-id="b61c3-110">Instale o pacote base de teste com pip.</span><span class="sxs-lookup"><span data-stu-id="b61c3-110">Install the test base package with pip.</span></span>

~~~
pip install  Microsoft.Testbase
~~~
 
## <a name="example"></a><span data-ttu-id="b61c3-111">Exemplo</span><span class="sxs-lookup"><span data-stu-id="b61c3-111">Example</span></span>
