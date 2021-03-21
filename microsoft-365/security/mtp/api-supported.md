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
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: a162226793cc63a9e7e4d490c721a2c488ac64fc
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50922169"
---
# <a name="supported-microsoft-365-defender-apis"></a>APIs com suporte do Microsoft 365 Defender 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Aplica-se a:**
- Microsoft 365 Defender

> [!IMPORTANT]
> Algumas informações se relacionam ao produto pré-lançamento, que pode ser substancialmente modificado antes de ser lançado comercialmente. Microsoft makes no warranties, express or implied, with respect to the information provided here.

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