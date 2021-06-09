---
title: Detecção quase duplicada - Descoberta Automática
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Use a detecção quase duplicada para agrupar documentos textuamente semelhantes ao analisar dados de caso em Advanced eDiscovery.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 255531897a1706904005034c56cab00d0032b7f3
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/26/2020
ms.locfileid: "48286017"
---
# <a name="near-duplicate-detection-in-advanced-ediscovery"></a>Detecção quase duplicada no Advanced eDiscovery

Considere um conjunto de documentos a serem revisados no qual um subconjunto se baseia no mesmo modelo e tem principalmente o mesmo idioma clichê, com algumas diferenças aqui e ali. Se um revistor pudesse identificar esse subconjunto, revisar um deles completamente e revisar as diferenças para o restante, ele não teria perdido nenhuma informação exclusiva enquanto levaria apenas uma fração de tempo que os levaria a ler todos os documentos de capa a capa. Detecção de duplicata próxima agrupa documentos textualmente similares para deixar seu processo de avaliação mais eficiente.

## <a name="how-does-it-work"></a>Como funciona?

Quando a detecção de duplicatas próximas é executada, o sistema analisa cada documento com texto. Depois, ela compara os documento entre si para determinar se suas semelhanças são maiores que o limite definido.  Se forem maiores, os documentos são agrupados. Depois de todos os documentos serem comparados e agrupados, um documento de cada grupo é marcado como o “original”. Ao analisar seus documentos, você pode analisar primeiro o original e analisar os outros documentos no mesmo conjunto de duplicatas próximas, focando na diferença entre o original e o documento que está sendo analisado.
