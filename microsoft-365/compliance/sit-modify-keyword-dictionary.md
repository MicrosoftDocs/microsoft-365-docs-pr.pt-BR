---
title: Modificar um dicionário de palavras-chave
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.date: ''
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
description: Saiba como modificar um dicionário de palavras-chave no Centro Microsoft 365 Conformidade.
ms.openlocfilehash: 93357d153d9c6a2a4521d1604b2a1cb8cbcec48c
ms.sourcegitcommit: a6fb731fdf726d7d9fe4232cf69510013f2b54ce
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/27/2021
ms.locfileid: "52685196"
---
# <a name="modify-a-keyword-dictionary"></a><span data-ttu-id="81938-103">Modificar um dicionário de palavras-chave</span><span class="sxs-lookup"><span data-stu-id="81938-103">Modify a keyword dictionary</span></span>

<span data-ttu-id="81938-104">Talvez seja necessário modificar palavras-chave em um de seus dicionários de palavras-chave ou modificar um dos dicionários internos.</span><span class="sxs-lookup"><span data-stu-id="81938-104">You might need to modify keywords in one of your keyword dictionaries, or modify one of the built-in dictionaries.</span></span> <span data-ttu-id="81938-105">Você pode fazer isso por meio do PowerShell ou por meio do Centro de Conformidade.</span><span class="sxs-lookup"><span data-stu-id="81938-105">You can do this through PowerShell or through the Compliance center.</span></span>

## <a name="modify-a-keyword-dictionary-in-compliance-center"></a><span data-ttu-id="81938-106">Modificar um dicionário de palavras-chave no Centro de Conformidade</span><span class="sxs-lookup"><span data-stu-id="81938-106">Modify a keyword dictionary in Compliance center</span></span>

<span data-ttu-id="81938-107">Os dicionários de palavras-chave podem ser usados como `Primary elements` ou em padrões de tipo de informação confidenciais `Supporting elements` (SIT).</span><span class="sxs-lookup"><span data-stu-id="81938-107">Keyword dictionaries can be used as `Primary elements` or `Supporting elements` in sensitive information type (SIT) patterns.</span></span> <span data-ttu-id="81938-108">Você pode editar um dicionário de palavras-chave ao criar um SIT ou em um SIT existente.</span><span class="sxs-lookup"><span data-stu-id="81938-108">You can edit a keyword dictionary while creating a SIT or in an existing SIT.</span></span> <span data-ttu-id="81938-109">Por exemplo, para editar um dicionário de palavras-chave existente:</span><span class="sxs-lookup"><span data-stu-id="81938-109">For example to edit an existing keyword dictionary:</span></span>

1. <span data-ttu-id="81938-110">Abra o padrão que tem o dicionário de palavras-chave que você deseja atualizar.</span><span class="sxs-lookup"><span data-stu-id="81938-110">Open the pattern that has the keyword dictionary you want to update.</span></span>
2. <span data-ttu-id="81938-111">Encontre o dicionário de palavras-chave que você deseja atualizar e escolha editar.</span><span class="sxs-lookup"><span data-stu-id="81938-111">Find the keyword dictionary you want to update and choose edit.</span></span> 
3.  <span data-ttu-id="81938-112">Faça suas edições usando uma palavra-chave por linha.</span><span class="sxs-lookup"><span data-stu-id="81938-112">Make your edits, using one keyword per line.</span></span>

![palavras-chave de edição de captura de tela](../media/edit-keyword-dictionary.png)

4. <span data-ttu-id="81938-114">Escolha `Done` .</span><span class="sxs-lookup"><span data-stu-id="81938-114">Choose `Done`.</span></span>

## <a name="modify-a-keyword-dictionary-using-powershell"></a><span data-ttu-id="81938-115">Modificar um dicionário de palavras-chave usando o PowerShell</span><span class="sxs-lookup"><span data-stu-id="81938-115">Modify a keyword dictionary using PowerShell</span></span> 

<span data-ttu-id="81938-116">Por exemplo, modificaremos alguns termos no PowerShell, salvaremos os termos em um local onde você poderá modificá-los em um editor e atualizaremos os termos anteriores no local.</span><span class="sxs-lookup"><span data-stu-id="81938-116">For example, we'll modify some terms in PowerShell, save the terms locally where you can modify them in an editor, and then update the previous terms in place.</span></span> 

<span data-ttu-id="81938-117">Primeiro, recupere o objeto de dicionário:</span><span class="sxs-lookup"><span data-stu-id="81938-117">First, retrieve the dictionary object:</span></span>
  
```powershell
$dict = Get-DlpKeywordDictionary -Name "Diseases"
```

<span data-ttu-id="81938-118">A impressão do `$dict` exibirá as diversas variáveis.</span><span class="sxs-lookup"><span data-stu-id="81938-118">Printing  `$dict` will show the various variables.</span></span> <span data-ttu-id="81938-119">As palavras-chave são armazenadas em um objeto no back-end, mas o `$dict.KeywordDictionary` contém uma representação de cadeia de caracteres delas, que você usará para modificar o dicionário.</span><span class="sxs-lookup"><span data-stu-id="81938-119">The keywords themselves are stored in an object on the backend, but  `$dict.KeywordDictionary` contains a string representation of them, which you'll use to modify the dictionary.</span></span> 

<span data-ttu-id="81938-120">Antes de modificar o dicionário, você precisa transformar a cadeia de caracteres de termos novamente em uma matriz usando o método `.split(',')`.</span><span class="sxs-lookup"><span data-stu-id="81938-120">Before you modify the dictionary, you need to turn the string of terms back into an array using the  `.split(',')` method.</span></span> <span data-ttu-id="81938-121">Em seguida, você limpará os espaços indesejados entre as palavras-chave com o método `.trim()`, deixando apenas as palavras-chave com as quais trabalhar.</span><span class="sxs-lookup"><span data-stu-id="81938-121">Then you'll clean up the unwanted spaces between the keywords with the  `.trim()` method, leaving just the keywords to work with.</span></span> 
  
```powershell
$terms = $dict.KeywordDictionary.split(',').trim()
```

<span data-ttu-id="81938-p105">Agora, você removerá alguns termos do dicionário. Como o dicionário de exemplo tem algumas palavras-chave, você poderá ignorar facilmente para exportar o dicionário e editá-lo no Bloco de Notas, mas os dicionários geralmente contêm uma grande quantidade de texto, então você vai aprender primeiro assim para editá-los facilmente no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="81938-p105">Now you'll remove some terms from the dictionary. Because the example dictionary has only a few keywords, you could as easily skip to exporting the dictionary and editing it in Notepad, but dictionaries generally contain a large amount of text, so you'll first learn this way to edit them easily in PowerShell.</span></span>
  
<span data-ttu-id="81938-p106">Na última etapa, você salvou as palavras-chave em uma matriz. Há várias maneiras de [remover itens de uma matriz](/previous-versions/windows/it-pro/windows-powershell-1.0/ee692802(v=technet.10)), mas como uma abordagem simples, você criará uma matriz de termos que deseja remover do dicionário e, em seguida, copia apenas os termos de dicionário para que ele não esteja na lista de termos para remover.</span><span class="sxs-lookup"><span data-stu-id="81938-p106">In the last step, you saved the keywords to an array. There are several ways to [remove items from an array](/previous-versions/windows/it-pro/windows-powershell-1.0/ee692802(v=technet.10)), but as a straightforward approach, you'll create an array of the terms you want to remove from the dictionary, and then copy only the dictionary terms to it that aren't in the list of terms to remove.</span></span>
  
<span data-ttu-id="81938-p107">Execute o comando `$terms` para mostrar a lista atual de termos. A saída do comando tem esta aparência:</span><span class="sxs-lookup"><span data-stu-id="81938-p107">Run the command  `$terms` to show the current list of terms. The output of the command looks like this:</span></span> 
  
`aarskog's syndrome`
`abandonment`
`abasia`
`abderhalden-kaufmann-lignac`
`abdominalgia`
`abduction contracture`
`abetalipoproteinemia`
`abiotrophy`
`ablatio`
`ablation`
`ablepharia`
`abocclusion`
`abolition`
`aborter`
`abortion`
`abortus`
`aboulomania`
`abrami's disease`

<span data-ttu-id="81938-128">Execute este comando para especificar os termos que você deseja remover:</span><span class="sxs-lookup"><span data-stu-id="81938-128">Run this command to specify the terms that you want to remove:</span></span>
  
```powershell
$termsToRemove = @('abandonment', 'ablatio')
```

<span data-ttu-id="81938-129">Execute este comando para remover os termos realmente da lista:</span><span class="sxs-lookup"><span data-stu-id="81938-129">Run this command to actually remove the terms from the list:</span></span>
  
```powershell
$updatedTerms = $terms | Where-Object{ $_ -notin $termsToRemove }
```

<span data-ttu-id="81938-p108">Execute o comando `$updatedTerms` para mostrar a lista atualizada de termos. A saída do comando tem esta aparência (os termos especificados foram removidos):</span><span class="sxs-lookup"><span data-stu-id="81938-p108">Run the command  `$updatedTerms` to show the updated list of terms. The output of the command looks like this (the specified terms have been removed):</span></span> 
  
`aarskog's syndrome`
`abasia`
`abderhalden-kaufmann-lignac`
`abdominalgia`
`abduction contracture`
`abetalipo proteinemia`
`abiotrophy`
`ablation`
`ablepharia`
`abocclusion`
`abolition`
`aborter`
`abortion`
`abortus`
`aboulomania`
`abrami's disease`
```

Now save the dictionary locally and add a few more terms. You could add the terms right here in PowerShell, but you'll still need to export the file locally to ensure it's saved with Unicode encoding and contains the BOM.
  
Save the dictionary locally by running the following:
  
```powershell
Set-Content $updatedTerms -Path "C:\myPath\terms.txt"
```

<span data-ttu-id="81938-p109">Agora abra o arquivo, acrescente seus outros termos e salve com codificação Unicode (UTF-16). Agora, você carregará os termos atualizados e atualizará o dicionário no lugar.</span><span class="sxs-lookup"><span data-stu-id="81938-p109">Now open the file, add your other terms, and save with Unicode encoding (UTF-16). Now you'll upload the updated terms and update the dictionary in place.</span></span>
  
```powershell
PS> Set-DlpKeywordDictionary -Identity "Diseases" -FileData (Get-Content -Path "C:myPath\terms.txt" -Encoding Byte -ReadCount 0)
```

<span data-ttu-id="81938-134">Agora o dicionário foi atualizado.</span><span class="sxs-lookup"><span data-stu-id="81938-134">Now the dictionary has been updated in place.</span></span> <span data-ttu-id="81938-135">O campo `Identity` leva o nome do dicionário.</span><span class="sxs-lookup"><span data-stu-id="81938-135">The  `Identity` field takes the name of the dictionary.</span></span> <span data-ttu-id="81938-136">Se você também quiser mudar o nome de seu dicionário usando o cmdlet `set-`, basta adicionar o parâmetro `-Name` ao que está acima com seu novo nome de dicionário.</span><span class="sxs-lookup"><span data-stu-id="81938-136">If you wanted to also change the name of your dictionary using the  `set-` cmdlet, you would just need to add the  `-Name` parameter to what's above with your new dictionary name.</span></span> 

<span data-ttu-id="81938-137">Confira também</span><span class="sxs-lookup"><span data-stu-id="81938-137">See Also</span></span>
- [<span data-ttu-id="81938-138">Criar um dicionário de palavras-chave</span><span class="sxs-lookup"><span data-stu-id="81938-138">Create a keyword dictionary</span></span>](create-a-keyword-dictionary.md)
- [<span data-ttu-id="81938-139">Criar um tipo de informação confidencial personalizado</span><span class="sxs-lookup"><span data-stu-id="81938-139">Create a custom sensitive information type</span></span>](create-a-custom-sensitive-information-type.md)
