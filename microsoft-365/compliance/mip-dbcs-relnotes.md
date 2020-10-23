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
ms.openlocfilehash: 1c2244c49a92aa2c00fad06caa8194cf7e32220e
ms.sourcegitcommit: 554755bc9ce40228ce6e34bde6fc6e226869b6a1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/22/2020
ms.locfileid: "48681497"
---
# <a name="support-for-double-byte-character-set-release-notes-preview"></a>Suporte para as notas de versão do conjunto de caracteres de dois bytes (visualização)

 A Proteção de Informações do Microsoft 365 agora oferece suporte a idiomas de conjunto de caracteres de byte duplo de visualização:

- Chinês (simplificado)
- Chinês (tradicional)
- Coreano
- Japonês

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
