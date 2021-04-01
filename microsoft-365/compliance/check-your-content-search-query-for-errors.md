---
title: Verifique se há erros na sua consulta da Pesquisa de Conteúdo
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
search.appverid:
- MOE150
- MET150
ms.assetid: 88898874-e262-4c5c-b6d2-4e697497fc74
ms.custom: seo-marvel-apr2020
description: Saiba como detectar erros e erros de digitação em sua consulta de palavra-chave para pesquisa de conteúdo, antes de executar a pesquisa.
ms.openlocfilehash: 939ac3d227f176a0b74138107ced5dd5b7142bcd
ms.sourcegitcommit: 7ebed5810480d7c49f8ca03207b5ea84993d253f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "51488208"
---
# <a name="check-your-content-search-query-for-errors"></a><span data-ttu-id="47d41-103">Verifique se há erros na sua consulta da Pesquisa de Conteúdo</span><span class="sxs-lookup"><span data-stu-id="47d41-103">Check your Content Search query for errors</span></span>
  
<span data-ttu-id="47d41-104">Aqui está uma lista dos caracteres sem suporte que verificamos.</span><span class="sxs-lookup"><span data-stu-id="47d41-104">Here's a list of the unsupported characters that we check for.</span></span> <span data-ttu-id="47d41-105">Caracteres sem suporte geralmente são ocultos e normalmente causam um erro de pesquisa ou retornam resultados não intencionados.</span><span class="sxs-lookup"><span data-stu-id="47d41-105">Unsupported characters are often hidden, and they typically cause a search error or return unintended results.</span></span>
  
- <span data-ttu-id="47d41-106">**Aspas inteligentes** - Aspas simples e duplas inteligentes (também chamadas de aspas curly) não são suportadas.</span><span class="sxs-lookup"><span data-stu-id="47d41-106">**Smart quotation marks** - Smart single and double quotation marks (also called curly quotes) aren't supported.</span></span> <span data-ttu-id="47d41-107">Somente aspas retas podem ser usadas em uma consulta de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="47d41-107">Only straight quotation marks can be used in a search query.</span></span> 

- <span data-ttu-id="47d41-108">**Caracteres não imprimíveis** e de controle - Caracteres não imprimíveis e de controle não representam um símbolo escrito, como um caractere alfanumérico.</span><span class="sxs-lookup"><span data-stu-id="47d41-108">**Non-printable and control characters** - Non-printable and control characters don't represent a written symbol, such as an alpha-numeric character.</span></span> <span data-ttu-id="47d41-109">Exemplos de caracteres não imprimíveis e de controle incluem caracteres que formatam texto ou linhas separadas de texto.</span><span class="sxs-lookup"><span data-stu-id="47d41-109">Examples of non-printable and control characters include characters that format text or separate lines of text.</span></span> 

- <span data-ttu-id="47d41-110">**Marcas da** esquerda para a direita e da direita para a esquerda - Essas marcas são caracteres de controle usados para indicar a direção de texto para idiomas da esquerda para a direita (como inglês e espanhol) e idiomas da direita para a esquerda (como árabe e hebraico).</span><span class="sxs-lookup"><span data-stu-id="47d41-110">**Left-to-right and right-to-left marks** - These marks are control characters used to indicate text direction for left-to-right languages (such as English and Spanish) and right-to-left languages (such as Arabic and Hebrew).</span></span>

- <span data-ttu-id="47d41-111">**Operadores Boolean minúsculos** - Se você usar um operador Boolean, como **AND**, **OR** e **NOT** em uma consulta de pesquisa, ele deve ser maiúscula.</span><span class="sxs-lookup"><span data-stu-id="47d41-111">**Lowercase Boolean operators** - If you use a Boolean operator, such as **AND**, **OR**, and **NOT** in a search query, it must be uppercase.</span></span> <span data-ttu-id="47d41-112">Quando verificamos uma consulta para erros de digitação, a sintaxe de consulta geralmente indica que um operador Boolean está sendo usado, mesmo que operadores minúsculos possam ser usados; por exemplo,  `(WordA or WordB) and (WordC or WordD)` .</span><span class="sxs-lookup"><span data-stu-id="47d41-112">When we check a query for typos, the query syntax will often indicate that a Boolean operator is being used even though lowercase operators might be used; for example,  `(WordA or WordB) and (WordC or WordD)`.</span></span>

## <a name="what-happens-if-a-query-has-an-unsupported-character"></a><span data-ttu-id="47d41-113">O que acontece se uma consulta tiver um caractere sem suporte?</span><span class="sxs-lookup"><span data-stu-id="47d41-113">What happens if a query has an unsupported character?</span></span>

<span data-ttu-id="47d41-114">Se caracteres sem suporte são encontrados em sua consulta, uma mensagem de aviso é exibida informando que caracteres sem suporte foram encontrados e sugere uma alternativa.</span><span class="sxs-lookup"><span data-stu-id="47d41-114">If unsupported characters are found in your query, a warning message is displayed that says unsupported characters were found and suggests an alternative.</span></span> <span data-ttu-id="47d41-115">Em seguida, você tem a opção de manter a consulta original ou substituí-la pela consulta revisada sugerida.</span><span class="sxs-lookup"><span data-stu-id="47d41-115">You then have the option keep the original query or replace it with the suggested revised query.</span></span>

<span data-ttu-id="47d41-116">Veja um exemplo da mensagem de aviso exibida depois  de clicar em Verificar se há erros de digitação na consulta de pesquisa na captura de tela anterior.</span><span class="sxs-lookup"><span data-stu-id="47d41-116">Here's an example of the warning message that's displayed after you click **Check query for typos** for the search query in the previous screenshot.</span></span> <span data-ttu-id="47d41-117">Observe que a consulta original usou aspas inteligentes e operadores booleano minúsculos.</span><span class="sxs-lookup"><span data-stu-id="47d41-117">Note the original query used smart quotes and lowercase Boolean operators.</span></span>
  
![Uma mensagem de aviso é exibida com uma revisão sugerida para sua consulta](../media/23214b30-8e52-412c-bd80-63fb1b3ed52d.png)
  
## <a name="how-to-prevent-unsupported-characters-in-your-search-queries"></a><span data-ttu-id="47d41-119">Como evitar caracteres sem suporte em suas consultas de pesquisa</span><span class="sxs-lookup"><span data-stu-id="47d41-119">How to prevent unsupported characters in your search queries</span></span>

<span data-ttu-id="47d41-120">Caracteres sem suporte geralmente são adicionados a uma consulta quando você copia a consulta ou partes da consulta de outros aplicativos (como o Microsoft Word ou o Microsoft Excel) e os colar na caixa de palavra-chave na página de consulta de uma Pesquisa de Conteúdo.</span><span class="sxs-lookup"><span data-stu-id="47d41-120">Unsupported characters are typically added to a query when you copy the query or parts of the query from other applications (such as Microsoft Word or Microsoft Excel) and paste them in the keyword box on the query page of a Content Search.</span></span> <span data-ttu-id="47d41-121">A melhor maneira de evitar caracteres sem suporte é apenas digitar a consulta na caixa de palavra-chave.</span><span class="sxs-lookup"><span data-stu-id="47d41-121">The best way to prevent unsupported characters is to just type the query in the keyword box.</span></span> <span data-ttu-id="47d41-122">Ou você pode copiar uma consulta do Word ou excel e, em seguida, colar em um editor de texto simples, como o Bloco de Notas da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="47d41-122">Or you can copy a query from Word or Excel, and then paste it in a plain text editor, such as Microsoft Notepad.</span></span> <span data-ttu-id="47d41-123">Salve o arquivo de texto e selecione **ANSI** **na** lista drop-down de Codificação.</span><span class="sxs-lookup"><span data-stu-id="47d41-123">Save the text file and select **ANSI** in the **Encoding** drop-down list.</span></span> <span data-ttu-id="47d41-124">Isso removerá qualquer formatação e caracteres sem suporte.</span><span class="sxs-lookup"><span data-stu-id="47d41-124">This will remove any formatting and unsupported characters.</span></span> <span data-ttu-id="47d41-125">Em seguida, você pode copiar e colar a consulta do arquivo de texto para a caixa de consulta de palavra-chave.</span><span class="sxs-lookup"><span data-stu-id="47d41-125">Then you can copy and paste the query from the text file to the keyword query box.</span></span> 
