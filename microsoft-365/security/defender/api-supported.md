---
title: APIs com suporte do Microsoft 365 Defender
description: APIs com suporte do Microsoft 365 Defender
keywords: MTP, APIs, api
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
ms.openlocfilehash: b2239b960106d756cbd29504af05af77a553067d
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51052548"
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

### <a name="endpoint-uris"></a>URIs de ponto de extremidade

O URI base para ambas as APIs principais é: https://api.security.microsoft.com . Para melhorar o desempenho, use um servidor mais próximo de sua localização geográfica:

- Estados Unidos: api-us.security.microsoft.com
- Europa: api-eu.security.microsoft.com
- Reino Unido: api-uk.security.microsoft.com

Tokens podem ser adquiridos acessando https://api.security.microsoft.com .

Todas as APIs ao longo `/api` do caminho usam o Protocolo [OData;](/odata/overview) por exemplo, https://api.security.microsoft.com/api/incidents .

## <a name="related-articles"></a>Artigos relacionados

- [Visão geral das APIs do Microsoft 365 Defender](api-overview.md)
- [Acessar as APIs da Proteção contra Ameaças da Microsoft](api-access.md)
- [Saiba mais sobre limites de API e licenciamento](api-terms.md)
- [Compreender códigos de erro](api-error-codes.md)