---
title: APIs de proteção de ameaças da Microsoft compatíveis
description: APIs de proteção de ameaças da Microsoft compatíveis
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
ms.openlocfilehash: 49fa182a6142748ca7769411fe74389f365ba75f
ms.sourcegitcommit: 9a275a13af3e063e80ce1bd3cd8142a095db92d2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/14/2020
ms.locfileid: "47650102"
---
# <a name="supported-microsoft-threat-protection-apis"></a>APIs de proteção de ameaças da Microsoft compatíveis 
**Aplica-se a:**
- Proteção contra Ameaças da Microsoft

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
[API de busca avançada](api-advanced-hunting.md) | Executar consultas de busca avançada da API.
[APIs de incidente](api-incident.md) | Executar chamadas de API relacionadas a incidentes, como: listar incidentes, atualizar incidente e mais.
