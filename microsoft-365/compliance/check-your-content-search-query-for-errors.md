---
title: Verifique se há erros na sua consulta da Pesquisa de Conteúdo
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 11/30/2016
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 88898874-e262-4c5c-b6d2-4e697497fc74
ms.custom: seo-marvel-apr2020
description: Saiba como detectar erros e erros de digitação em sua consulta de palavra-chave para pesquisa de conteúdo, antes de executar a pesquisa.
ms.openlocfilehash: 296f30f5332165017f5c7ccebc35c0663041718d
ms.sourcegitcommit: d4604e333507c6f57d5bf327531a241b649052de
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "51470440"
---
# <a name="check-your-content-search-query-for-errors"></a>Verifique se há erros na sua consulta da Pesquisa de Conteúdo
  
Aqui está uma lista dos caracteres sem suporte que verificamos. Caracteres sem suporte geralmente são ocultos e normalmente causam um erro de pesquisa ou retornam resultados não intencionados.
  
- **Aspas inteligentes** - Aspas simples e duplas inteligentes (também chamadas de aspas curly) não são suportadas. Somente aspas retas podem ser usadas em uma consulta de pesquisa. 

- **Caracteres não imprimíveis** e de controle - Caracteres não imprimíveis e de controle não representam um símbolo escrito, como um caractere alfanumérico. Exemplos de caracteres não imprimíveis e de controle incluem caracteres que formatam texto ou linhas separadas de texto. 

- **Marcas da** esquerda para a direita e da direita para a esquerda - Essas marcas são caracteres de controle usados para indicar a direção de texto para idiomas da esquerda para a direita (como inglês e espanhol) e idiomas da direita para a esquerda (como árabe e hebraico).

- **Operadores Boolean minúsculos** - Se você usar um operador Boolean, como **AND**, **OR** e **NOT** em uma consulta de pesquisa, ele deve ser maiúscula. Quando verificamos uma consulta para erros de digitação, a sintaxe de consulta geralmente indica que um operador Boolean está sendo usado, mesmo que operadores minúsculos possam ser usados; por exemplo,  `(WordA or WordB) and (WordC or WordD)` .

## <a name="what-happens-if-a-query-has-an-unsupported-character"></a>O que acontece se uma consulta tiver um caractere sem suporte?

Se caracteres sem suporte são encontrados em sua consulta, uma mensagem de aviso é exibida informando que caracteres sem suporte foram encontrados e sugere uma alternativa. Em seguida, você tem a opção de manter a consulta original ou substituí-la pela consulta revisada sugerida.

Veja um exemplo da mensagem de aviso exibida depois  de clicar em Verificar se há erros de digitação na consulta de pesquisa na captura de tela anterior. Observe que a consulta original usou aspas inteligentes e operadores booleano minúsculos.
  
![Uma mensagem de aviso é exibida com uma revisão sugerida para sua consulta](../media/23214b30-8e52-412c-bd80-63fb1b3ed52d.png)
  
## <a name="how-to-prevent-unsupported-characters-in-your-search-queries"></a>Como evitar caracteres sem suporte em suas consultas de pesquisa

Caracteres sem suporte geralmente são adicionados a uma consulta quando você copia a consulta ou partes da consulta de outros aplicativos (como o Microsoft Word ou o Microsoft Excel) e os colar na caixa de palavra-chave na página de consulta de uma Pesquisa de Conteúdo. A melhor maneira de evitar caracteres sem suporte é apenas digitar a consulta na caixa de palavra-chave. Ou você pode copiar uma consulta do Word ou excel e, em seguida, colar em um editor de texto simples, como o Bloco de Notas da Microsoft. Salve o arquivo de texto e selecione **ANSI** **na** lista drop-down de Codificação. Isso removerá qualquer formatação e caracteres sem suporte. Em seguida, você pode copiar e colar a consulta do arquivo de texto para a caixa de consulta de palavra-chave. 
