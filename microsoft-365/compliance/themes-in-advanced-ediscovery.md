---
title: Temas - Descoberta eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Use Temas no Advanced eDiscovery para organizar conjuntos de revisão encontrando o tema dominante em cada documento.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 3dfc0dca0c6ed62e3ce8384efa2fd3ea407c3ce8
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/26/2020
ms.locfileid: "48285527"
---
# <a name="themes-in-advanced-ediscovery"></a>Temas no Advanced eDiscovery

Como uma pessoa escreve um documento? Geralmente, eles começam com uma ou mais ideias que querem transmitir no documento e compõem usando palavras que se alinham às ideias. Quanto mais prevalente for uma ideia, mais frequentes serão as palavras relacionadas a essa ideia. Isso também informa como as pessoas consomem documentos. O importante a ser entendido na leitura de um documento são as ideias que o documento está tentando transmitir, quais ideias aparecem onde e quais são as relações entre as ideias.

Isso pode ser estendido para como uma pessoa deseja consumir um conjunto de documentos. Eles querem ver quais ideias estão presentes nos conjuntos e quais documentos estão falando sobre essas ideias. Além disso, se eles encontram um documento específico de interesse, eles querem ser capazes de ver documentos que discutem ideias semelhantes.

A funcionalidade Temas no Advanced eDiscovery tenta imitar como os humanos explicam  os documentos, analisando os temas discutidos em um conjunto de revisão e atribuindo um tema a documentos no conjunto de revisão. Em Advanced eDiscovery, Temas vão mais longe e identificam o *tema dominante* em cada documento. O tema dominante é o que aparece com mais frequência em um documento.

## <a name="how-does-themes-work"></a>Como os temas funcionam?

A funcionalidade Temas analisa documentos com texto em um conjunto de revisão para analisar temas comuns que aparecem em todos os documentos no conjunto de revisão. A Descoberta Eletrônica Avançada atribui esses temas aos documentos nos quais eles aparecem. Ela também rotula cada tema com as palavras usadas nos documentos que são representantes do tema. Como um documento pode ter vários tipos de assuntos, a Descoberta Eletrônica Avançada geralmente atribui vários temas a documentos.  O tema que mais se destaca em um documento é designado como o tema dominante.
