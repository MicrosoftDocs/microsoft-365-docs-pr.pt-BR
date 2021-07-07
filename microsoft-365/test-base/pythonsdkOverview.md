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
# <a name="test-base-sdk-for-python"></a>SDK base de teste para Python

## <a name="overview"></a>Visão geral
O SDK base de teste pode ser usado para interagir com o recurso base de teste do Azure. (ou seja, gerenciar seu pacote de aplicativos, incluir criar pacote, editar pacote e excluir pacote)

Com o SDK, o resumo de teste e o Resultado de Análise que podem ser obtidos incluem : scriptExecution, confiabilidade, memoryUtilization, cpuUtilization, memoryRegression, cpuRegression.

Com o SDK base de teste, você pode integrar a base de teste no pipeline ci/CD.

## <a name="client-library"></a>Biblioteca do Cliente

Instale o pacote base de teste com pip.

~~~
pip install  Microsoft.Testbase
~~~
 
## <a name="example"></a>Exemplo
