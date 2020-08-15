---
title: Suporte ao Centro de conformidade do Microsoft 365 para as notas de versão do conjunto de caracteres de dois bytes (visualização)
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Notas de versão para suporte a conjuntos de caracteres de dois bytes.
ms.openlocfilehash: 13bac873f2ba18bc166451ea73ec0d569fb30f68
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46695227"
---
# <a name="support-for-double-byte-character-set-release-notes-preview"></a>Suporte para as notas de versão do conjunto de caracteres de dois bytes (visualização)

 A Proteção de Informações do Microsoft 365 agora oferece suporte a idiomas de conjunto de caracteres de byte duplo de visualização:

- Chinês (simplificado)
- Chinês (tradicional)
- Coreano
- Japonês

Esta visualização está apenas na nuvem comercial e a implementação está limitada para:

- Japão
- Coreia
- China
- Hong Kong
- Macau
- Taiwan

Esse suporte está disponível para tipos de informações confidenciais e dicionários de palavras-chave, e será refletido em soluções de prevenção de perda de dados, de conformidade de comunicações, do Exchange Online, do SharePoint Online, do OneDrive for Business e do Teams.

## <a name="known-issues"></a>Problemas conhecidos

- Quando um arquivo de texto anexado a um email está no formato UTF-8 sem BOM (marca de ordem de byte), o email não é detectado pela política de conformidade de comunicação.

- As políticas de conformidade de comunicação não conseguem detectar valores se uma frase for inserida na condição da política: “A mensagem contém qualquer uma destas palavras”. Se o texto especificado na política for escrito como uma palavra, ele poderá ser detectado; no entanto, se for escrito no meio de uma frase, ele não será detectado.

- As políticas de conformidade de comunicação que especificam dicionários como informações de tipo não detectam chats privados do Teams e chats de canal.

- As condições a seguir não são compatíveis com a conformidade de comunicação nesta fase (planejamos corrigir esses problemas no futuro): 
  - “A mensagem contém qualquer uma destas palavras”
  - “A mensagem não contém nenhuma destas palavras”
  - “O anexo contém qualquer uma destas palavras”
  - “O anexo contém qualquer uma destas palavras”

Em vez disso, recomendamos a criação de um SIT (tipo de informação confidencial) personalizado com dicionário de palavras-chave, que detectará padrões em mensagens e anexos, e o uso desse SIT personalizado como uma condição de política de conformidade de comunicação.
