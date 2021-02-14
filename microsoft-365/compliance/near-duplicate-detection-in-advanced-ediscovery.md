---
title: Detecção duplicada próxima - Descoberta Automática
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
description: Use a detecção quase duplicada para agrupar textually documentos semelhantes ao analisar dados de caso na Descoberta Eletrônica Avançada.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 255531897a1706904005034c56cab00d0032b7f3
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/26/2020
ms.locfileid: "48286017"
---
# <a name="near-duplicate-detection-in-advanced-ediscovery"></a>Detecção quase duplicada na Descoberta Automática Avançada

Considere um conjunto de documentos a serem revisados no qual um subconjunto é baseado no mesmo modelo e tem principalmente o mesmo idioma clichê, com algumas diferenças aqui e ali. Se um revisador puder identificar esse subconjunto, revisar um deles exaustivamente e analisar as diferenças para o restante, ele não teria perdido nenhuma informação exclusiva enquanto ocupava apenas uma fração de tempo que o levaria a ler todos os documentos decodificáveis. Documentos semelhantes textuicamente próximos a grupos de detecção duplicados para ajudar você a tornar o processo de revisão mais eficiente.

## <a name="how-does-it-work"></a>Como funciona?

Quando a detecção quase duplicada é executado, o sistema analisará cada documento com texto. Em seguida, ele compara cada documento entre si para determinar se sua semelhança é maior do que o limite definido. Se for, os documentos serão agrupados. Depois que todos os documentos são comparados e agrupados, um documento de cada grupo é marcado como o "pivô"; ao revisar seus documentos, você pode revisar um pivô primeiro e revisar os outros documentos no mesmo conjunto quase duplicado, concentrando-se na diferença entre o pivô e o documento que está em revisão.
