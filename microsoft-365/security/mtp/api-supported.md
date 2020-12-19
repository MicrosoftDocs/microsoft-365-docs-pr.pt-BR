---
title: APIs com suporte do Microsoft 365 Defender
description: APIs com suporte do Microsoft 365 Defender
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
ms.openlocfilehash: dbb7613dae3755b0fb794a3d68b5b424d765cc62
ms.sourcegitcommit: d6b1da2e12d55f69e4353289e90f5ae2f60066d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/19/2020
ms.locfileid: "49719317"
---
# <a name="supported-microsoft-365-defender-apis"></a>APIs com suporte do Microsoft 365 Defender 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Aplica-se a:**
- Microsoft 365 Defender

> [!IMPORTANT]
> Algumas informações estão relacionadas ao produto já publicado que pode ser modificado substancialmente antes de ser lançado comercialmente. Microsoft makes no warranties, express or implied, with respect to the information provided here.

## <a name="list-of-available-apis"></a>Lista de APIs disponíveis

Artigo | Descrição
-|-
[API de Busca Avançada](api-advanced-hunting.md) | Executar consultas de busca avançadas.
[APIs de Incidente](api-incident.md) | Incidentes de lista e atualização, juntamente com outras tarefas práticas.

### <a name="endpoint-uris"></a>URIs de ponto de extremidade

O URI de base para ambas as APIs principais é: https://api.security.microsoft.com . Para melhorar o desempenho, use um servidor mais próximo da sua localização geográfica:

- Estados Unidos: api-us.security.microsoft.com
- Europa: api-eu.security.microsoft.com
- O Reino Unido: api-uk.security.microsoft.com

Tokens podem ser adquiridos acessando https://api.security.microsoft.com .

Todas as APIs ao longo do `/api` caminho usam o protocolo [OData](https://docs.microsoft.com/odata/overview) ; por exemplo, https://api.security.microsoft.com/api/incidents .

## <a name="related-articles"></a>Artigos relacionados

- [Visão geral das APIs do Microsoft 365 defender](api-overview.md)
- [Acessar as APIs de proteção contra ameaças da Microsoft](api-access.md)
- [Saiba mais sobre limites de API e licenciamento](api-terms.md)
- [Entender códigos de erro](api-error-codes.md)
