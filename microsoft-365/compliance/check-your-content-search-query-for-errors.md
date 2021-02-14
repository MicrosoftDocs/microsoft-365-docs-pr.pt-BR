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
ms.openlocfilehash: 250db272014d5801bfb3927d14072eea94bd635f
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/19/2020
ms.locfileid: "44818090"
---
# <a name="check-your-content-search-query-for-errors"></a><span data-ttu-id="eca44-103">Verifique se há erros na sua consulta da Pesquisa de Conteúdo</span><span class="sxs-lookup"><span data-stu-id="eca44-103">Check your Content Search query for errors</span></span>

<span data-ttu-id="eca44-104">Ao criar ou editar uma Pesquisa de Conteúdo, você pode fazer com que o Microsoft 365 verifique sua consulta em busca de caracteres sem suporte e operadores Boolean minúsculos.</span><span class="sxs-lookup"><span data-stu-id="eca44-104">When you create or edit a Content Search, you can have Microsoft 365 check your query for unsupported characters and lowercase Boolean operators.</span></span> <span data-ttu-id="eca44-105">Como?</span><span class="sxs-lookup"><span data-stu-id="eca44-105">How?</span></span> <span data-ttu-id="eca44-106">Basta clicar **em Verificar consulta para erros de digitação** na página de consulta de uma Pesquisa de Conteúdo.</span><span class="sxs-lookup"><span data-stu-id="eca44-106">Just click **Check query for typos** on the query page of a Content Search.</span></span> 
  
![Clique em "Verificar se há erros de digitação" para verificar se há caracteres sem suporte na consulta de pesquisa](../media/e5314306-cfb2-481d-9b5c-13ce658156e7.png)
  
<span data-ttu-id="eca44-108">Aqui está uma lista dos caracteres sem suporte que verificamos.</span><span class="sxs-lookup"><span data-stu-id="eca44-108">Here's a list of the unsupported characters that we check for.</span></span> <span data-ttu-id="eca44-109">Os caracteres sem suporte geralmente ficam ocultos e normalmente causam um erro de pesquisa ou retornam resultados não intencionais.</span><span class="sxs-lookup"><span data-stu-id="eca44-109">Unsupported characters are often hidden, and they typically cause a search error or return unintended results.</span></span>
  
- <span data-ttu-id="eca44-110">**Aspas inteligentes** - Aspas simples e duplas inteligentes (também chamadas de aspas duplas) não são suportadas.</span><span class="sxs-lookup"><span data-stu-id="eca44-110">**Smart quotation marks** - Smart single and double quotation marks (also called curly quotes) aren't supported.</span></span> <span data-ttu-id="eca44-111">Somente aspas retas podem ser usadas em uma consulta de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="eca44-111">Only straight quotation marks can be used in a search query.</span></span> 
    
- <span data-ttu-id="eca44-112">**Caracteres não imprimíveis** e de controle - Caracteres de controle e não imprimíveis não representam um símbolo escrito, como um caractere alfanumérico.</span><span class="sxs-lookup"><span data-stu-id="eca44-112">**Non-printable and control characters** - Non-printable and control characters don't represent a written symbol, such as an alpha-numeric character.</span></span> <span data-ttu-id="eca44-113">Exemplos de caracteres não imprimíveis e de controle incluem caracteres que formatam texto ou linhas separadas de texto.</span><span class="sxs-lookup"><span data-stu-id="eca44-113">Examples of non-printable and control characters include characters that format text or separate lines of text.</span></span> 
    
- <span data-ttu-id="eca44-114">**Marcas da** esquerda para a direita e da direita para a esquerda - Essas marcas são caracteres de controle usados para indicar a direção do texto para idiomas da esquerda para a direita (como inglês e espanhol) e idiomas da direita para a esquerda (como árabe e hebraico).</span><span class="sxs-lookup"><span data-stu-id="eca44-114">**Left-to-right and right-to-left marks** - These marks are control characters used to indicate text direction for left-to-right languages (such as English and Spanish) and right-to-left languages (such as Arabic and Hebrew).</span></span>
    
- <span data-ttu-id="eca44-115">**Operadores Boolianas** minúsculos - Se você usar um operador Booliana, como **AND**, **OR** e **NOT** em uma consulta de pesquisa, ele deverá estar em maiúsculas.</span><span class="sxs-lookup"><span data-stu-id="eca44-115">**Lowercase Boolean operators** - If you use a Boolean operator, such as **AND**, **OR**, and **NOT** in a search query, it must be uppercase.</span></span> <span data-ttu-id="eca44-116">Quando verificamos se há erros de digitação em uma consulta, a sintaxe da consulta geralmente indica que um operador booliana está sendo usado, mesmo que operadores minúsculos possam ser usados; por exemplo,  `(WordA or WordB) and (WordC or WordD)` .</span><span class="sxs-lookup"><span data-stu-id="eca44-116">When we check a query for typos, the query syntax will often indicate that a Boolean operator is being used even though lowercase operators might be used; for example,  `(WordA or WordB) and (WordC or WordD)`.</span></span>
    
## <a name="what-happens-if-a-query-has-an-unsupported-character"></a><span data-ttu-id="eca44-117">O que acontece se uma consulta tiver um caractere sem suporte?</span><span class="sxs-lookup"><span data-stu-id="eca44-117">What happens if a query has an unsupported character?</span></span>

<span data-ttu-id="eca44-118">Se caracteres sem suporte são encontrados em sua consulta, uma mensagem de aviso é exibida informando que caracteres sem suporte foram encontrados e sugere uma alternativa.</span><span class="sxs-lookup"><span data-stu-id="eca44-118">If unsupported characters are found in your query, a warning message is displayed that says unsupported characters were found and suggests an alternative.</span></span> <span data-ttu-id="eca44-119">Em seguida, você tem a opção de manter a consulta original ou substituí-la pela consulta revisada sugerida.</span><span class="sxs-lookup"><span data-stu-id="eca44-119">You then have the option keep the original query or replace it with the suggested revised query.</span></span> <span data-ttu-id="eca44-120">Aqui está um exemplo da mensagem de aviso que  é exibida depois que você clica em Verificar consulta para erros de digitação para a consulta de pesquisa na captura de tela anterior.</span><span class="sxs-lookup"><span data-stu-id="eca44-120">Here's an example of the warning message that's displayed after you click **Check query for typos** for the search query in the previous screenshot.</span></span> <span data-ttu-id="eca44-121">Observe que a consulta original contém aspas inteligentes e operadores boolianas minúsculos.</span><span class="sxs-lookup"><span data-stu-id="eca44-121">Notice that the original query contains smart quotes and lowercase Boolean operators.</span></span> 
  
![Uma mensagem de aviso é exibida com uma revisão sugerida para sua consulta](../media/23214b30-8e52-412c-bd80-63fb1b3ed52d.png)
  
## <a name="how-to-prevent-unsupported-characters-in-your-search-queries"></a><span data-ttu-id="eca44-123">Como impedir caracteres sem suporte em suas consultas de pesquisa</span><span class="sxs-lookup"><span data-stu-id="eca44-123">How to prevent unsupported characters in your search queries</span></span>

<span data-ttu-id="eca44-124">Caracteres sem suporte são normalmente adicionados a uma consulta quando você copia a consulta ou partes da consulta de outros aplicativos (como o Microsoft Word ou o Microsoft Excel) e os colar na caixa de palavra-chave na página de consulta de uma Pesquisa de Conteúdo.</span><span class="sxs-lookup"><span data-stu-id="eca44-124">Unsupported characters are typically added to a query when you copy the query or parts of the query from other applications (such as Microsoft Word or Microsoft Excel) and paste them in the keyword box on the query page of a Content Search.</span></span> <span data-ttu-id="eca44-125">A melhor maneira de evitar caracteres sem suporte é apenas digitar a consulta na caixa de palavra-chave.</span><span class="sxs-lookup"><span data-stu-id="eca44-125">The best way to prevent unsupported characters is to just type the query in the keyword box.</span></span> <span data-ttu-id="eca44-126">Ou você pode copiar uma consulta do Word ou excel e, em seguida, colar em um editor de texto sem texto, como o Bloco de Notas da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="eca44-126">Or you can copy a query from Word or Excel, and then paste it in a plain text editor, such as Microsoft Notepad.</span></span> <span data-ttu-id="eca44-127">Salve o arquivo de texto **e selecione ANSI** na lista de **codificação.**</span><span class="sxs-lookup"><span data-stu-id="eca44-127">Save the text file and select **ANSI** in the **Encoding** drop-down list.</span></span> <span data-ttu-id="eca44-128">Isso removerá qualquer formatação e caracteres sem suporte.</span><span class="sxs-lookup"><span data-stu-id="eca44-128">This will remove any formatting and unsupported characters.</span></span> <span data-ttu-id="eca44-129">Em seguida, você pode copiar e colar a consulta do arquivo de texto para a caixa de consulta de palavra-chave.</span><span class="sxs-lookup"><span data-stu-id="eca44-129">Then you can copy and paste the query from the text file to the keyword query box.</span></span> 
