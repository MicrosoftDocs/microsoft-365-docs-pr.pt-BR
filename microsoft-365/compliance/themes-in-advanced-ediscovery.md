---
title: Temas-descoberta eletrônica
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
description: Use temas em descoberta eletrônica avançada para organizar os conjuntos de análise encontrando o tema dominante em cada documento.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 3dfc0dca0c6ed62e3ce8384efa2fd3ea407c3ce8
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/26/2020
ms.locfileid: "48285527"
---
# <a name="themes-in-advanced-ediscovery"></a>Temas na descoberta eletrônica avançada

Como uma pessoa escreve um documento? Geralmente, elas começam com uma ou mais ideias que desejam transmitir no documento e compor usando palavras que se alinham com as ideias. Quanto mais predominante uma ideia é, mais frequentes as palavras relacionadas a essa ideia tendem a ser. Isso informa como as pessoas consomem documentos também. O importante a ser compreendido na leitura de um documento é as ideias que o documento está tentando transmitir, quais ideias aparecem onde e quais são as relações entre as idéias.

Isso pode ser estendido para a forma como uma pessoa deseja consumir um conjunto de documentos. Eles desejam ver quais ideias estão presentes nos conjuntos e quais documentos estão falando sobre essas ideias. Além disso, caso encontrem um documento de interesse específico, eles desejam poder ver documentos que discutem ideias semelhantes.

A funcionalidade temas em descoberta eletrônica avançada tenta simular o motivo dos seresns de documentos, analisando os *temas* que são discutidos em um conjunto de análise e atribuindo um tema a documentos no conjunto de revisão. Na descoberta eletrônica avançada, os temas vão para um passo adiante e identificam o *tema dominante* em cada documento. O tema dominante é aquele que aparece mais freqüentemente em um documento.

## <a name="how-does-themes-work"></a>Como os temas funcionam?

A funcionalidade temas analisa documentos com texto em uma revisão definida para analisar temas comuns que aparecem em todos os documentos do conjunto de revisão. A descoberta eletrônica avançada atribui esses temas aos documentos em que eles aparecem. Ele também rotula cada tema com as palavras usadas nos documentos que são representativos do tema. Como um documento pode conter vários tipos de assunto, a descoberta eletrônica avançada freqüentemente atribui vários temas a documentos. O tema que aparece mais proeminentemente em um documento é designado como seu tema dominante.
