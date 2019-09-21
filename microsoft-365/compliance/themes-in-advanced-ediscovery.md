---
title: Temas
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
ms.openlocfilehash: b26b031b767f23504294880f4424be5042350c71
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/20/2019
ms.locfileid: "37073745"
---
# <a name="themes"></a>Temas
Como uma pessoa escreve um documento? Geralmente, elas começam com uma ou mais ideias que desejam transmitir no documento e compor usando palavras que se alinham com as ideias. Quanto mais predominante uma ideia é, mais frequentes as palavras relacionadas a essa ideia tendem a ser. Isso informa como as pessoas consomem documentos também; o importante para a leitura de um documento é a idéia de que o documento está tentando transmitir e quais ideias aparecem onde e quais são as relações entre as idéias.

Isso pode ser estendido para a forma como uma pessoa deseja consumir um conjunto de documentos. Eles desejam ver quais ideias estão presentes nos conjuntos e quais documentos estão falando sobre essas ideias. Além disso, caso encontrem um documento de interesse específico, eles desejam poder ver documentos que discutem ideias semelhantes.

O módulo temas tenta simular a razão dos seresns de documentos, analisando os "temas" que são discutidos em um conjunto de revisão e atribuindo-os a documentos. Temas avançam um passo adiante e identificam por documento o "tema dominante"; ou seja, o tema que aparece mais.

## <a name="how-does-themes-work"></a>Como os temas funcionam?
Temas analisa documentos com texto em uma revisão definida para analisar temas comuns que aparecem nos documentos. Em seguida, ele atribui esses temas aos documentos em que eles aparecem. Ele também rotula cada um com palavras usadas nos documentos representativos do tema. Como um documento pode ser sobre mais de um assunto, em muitos casos, um documento tem mais de um temas atribuídos a ele. O tema que aparece mais proeminentemente em um documento é designado como seu tema dominante.