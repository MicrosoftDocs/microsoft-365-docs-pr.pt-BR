---
title: Detecção de duplicata próxima
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
description: ''
ms.openlocfilehash: 7ae5e695091d140089f979f28793876a2df77251
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/20/2019
ms.locfileid: "37073473"
---
# <a name="near-duplicate-detection"></a>Detecção de duplicata próxima

Considere um conjunto de documentos para ser revisado no qual um subconjunto é baseado no mesmo modelo e tem principalmente o mesmo idioma clichê, com algumas diferenças aqui e ali. Se um revisor pudesse identificar esse subconjunto, revise um deles cuidadosamente e revise as diferenças para o resto, eles não teriam informações exclusivas e, ao mesmo tempo, levaria apenas uma fração de tempo que teria levado em vista para ler todos os documentos na capa. Um grupo de detecção de duplicidades próximo agrupa documentos semelhantes para ajudá-lo a tornar seu processo de revisão mais eficiente.

## <a name="how-does-it-work"></a>Como funciona?

Quando a detecção próxima duplicação é executada, o sistema analisa todos os documentos com texto. Em seguida, ele compara todos os documentos entre si para determinar se sua similaridade é maior do que o limite definido. Se for, os documentos serão agrupados. Depois que todos os documentos forem comparados e agrupados, um documento de cada grupo será marcado como "pivô"; ao revisar seus documentos, você pode revisar uma tabela dinâmica primeiro e revisar os outros documentos no mesmo conjunto próximo duplicado, concentrando-se na diferença entre a tabela dinâmica e o documento que está em revisão.