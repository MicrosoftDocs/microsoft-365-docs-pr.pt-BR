---
title: APIs com suporte do Microsoft 365 Defender
description: APIs com suporte do Microsoft 365 Defender
keywords: Microsoft 365 Defender, APIs, api
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: c10b2863503a5bda829cbf67379a606b687ac2e3
ms.sourcegitcommit: e8f5d88f0fe54620308d3bec05263568f9da2931
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2021
ms.locfileid: "52730937"
---
# <a name="supported-microsoft-365-defender-apis"></a>APIs com suporte do Microsoft 365 Defender 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Aplica-se a:**
- Microsoft 365 Defender

> [!IMPORTANT]
> Algumas informações estão relacionadas a produtos pré-lançados que podem ser substancialmente modificados antes de seu lançamento comercial. A Microsoft não faz garantias, expressas ou implícitas, quanto às informações fornecidas aqui.

## <a name="list-of-available-apis"></a>Lista de APIs disponíveis

Artigo | Descrição
-|-
[API de Busca Avançada](api-advanced-hunting.md) | Execute consultas de Busca Avançada.
[APIs de Incidente](api-incident.md) | Listar e atualizar incidentes, juntamente com outras tarefas práticas.
[API de streaming](../defender-endpoint/raw-data-export.md) (Visualização) | Enviar eventos e alertas em tempo real conforme eles ocorrem em um único fluxo de dados.

### <a name="endpoint-uris"></a>URIs de ponto de extremidade

O URI base para ambas as APIs principais é: https://api.security.microsoft.com . Para melhorar o desempenho, use um servidor mais próximo de sua localização geográfica:

- Estados Unidos: api-us.security.microsoft.com
- Europa: api-eu.security.microsoft.com
- Reino Unido: api-uk.security.microsoft.com

Tokens podem ser adquiridos acessando https://api.security.microsoft.com .

Todas as APIs ao longo `/api` do caminho usam o Protocolo [OData;](/odata/overview) por exemplo, https://api.security.microsoft.com/api/incidents .

## <a name="related-articles"></a>Artigos relacionados

- [Microsoft 365 Visão geral das APIs do Defender](api-overview.md)
- [Acessar as APIs Microsoft 365 Defender](api-access.md)
- [Streaming API](../defender-endpoint/raw-data-export.md)
- [Saiba mais sobre limites de API e licenciamento](api-terms.md)
- [Compreender códigos de erro](api-error-codes.md)
