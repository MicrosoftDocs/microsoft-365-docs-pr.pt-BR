---
title: APIs do Microsoft 365 defender com suporte
description: APIs do Microsoft 365 defender com suporte
keywords: MTP, APIs, API
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: b7c0accf2d649d4ad6177260294922ee17783f2c
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/03/2020
ms.locfileid: "48844955"
---
# <a name="supported-microsoft-365-defender-apis"></a>APIs do Microsoft 365 defender com suporte 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Aplica-se a:**
- Microsoft 365 defender

>[!IMPORTANT] 
>Algumas informações estão relacionadas ao produto já publicado que pode ser modificado substancialmente antes de ser lançado comercialmente. Microsoft makes no warranties, express or implied, with respect to the information provided here.


### <a name="end-point-uris"></a>URIs de ponto de extremidade:

- O URI da base de serviço é: https://api.security.microsoft.com <br>

>[!NOTE]
>Para melhorar o desempenho, você pode usar o servidor mais próximo do local geográfico:
> - api-us.security.microsoft.com
> - api-eu.security.microsoft.com
> - api-uk.security.microsoft.com

 - O recurso para aquisição de token deve ser: https://api.security.microsoft.com

 - Todas as APIs em ```/api``` Path são APIs OData. exemplo. ```https://api.security.microsoft.com/api/incidents```

## <a name="list-of-available-apis"></a>Lista de APIs disponíveis:

Tópico | Descrição
:---|:---
[API de Busca Avançada](api-advanced-hunting.md) | Executar consultas de busca avançada da API.
[APIs de Incidente](api-incident.md) | Executar chamadas de API relacionadas a incidentes, como: listar incidentes, atualizar incidente e mais.
