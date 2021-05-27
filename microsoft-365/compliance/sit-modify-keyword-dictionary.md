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
# <a name="modify-a-keyword-dictionary"></a>Modificar um dicionário de palavras-chave

Talvez seja necessário modificar palavras-chave em um de seus dicionários de palavras-chave ou modificar um dos dicionários internos. Você pode fazer isso por meio do PowerShell ou por meio do Centro de Conformidade.

## <a name="modify-a-keyword-dictionary-in-compliance-center"></a>Modificar um dicionário de palavras-chave no Centro de Conformidade

Os dicionários de palavras-chave podem ser usados como `Primary elements` ou em padrões de tipo de informação confidenciais `Supporting elements` (SIT). Você pode editar um dicionário de palavras-chave ao criar um SIT ou em um SIT existente. Por exemplo, para editar um dicionário de palavras-chave existente:

1. Abra o padrão que tem o dicionário de palavras-chave que você deseja atualizar.
2. Encontre o dicionário de palavras-chave que você deseja atualizar e escolha editar. 
3.  Faça suas edições usando uma palavra-chave por linha.

![palavras-chave de edição de captura de tela](../media/edit-keyword-dictionary.png)

4. Escolha `Done` .

## <a name="modify-a-keyword-dictionary-using-powershell"></a>Modificar um dicionário de palavras-chave usando o PowerShell 

Por exemplo, modificaremos alguns termos no PowerShell, salvaremos os termos em um local onde você poderá modificá-los em um editor e atualizaremos os termos anteriores no local. 

Primeiro, recupere o objeto de dicionário:
  
```powershell
$dict = Get-DlpKeywordDictionary -Name "Diseases"
```

A impressão do `$dict` exibirá as diversas variáveis. As palavras-chave são armazenadas em um objeto no back-end, mas o `$dict.KeywordDictionary` contém uma representação de cadeia de caracteres delas, que você usará para modificar o dicionário. 

Antes de modificar o dicionário, você precisa transformar a cadeia de caracteres de termos novamente em uma matriz usando o método `.split(',')`. Em seguida, você limpará os espaços indesejados entre as palavras-chave com o método `.trim()`, deixando apenas as palavras-chave com as quais trabalhar. 
  
```powershell
$terms = $dict.KeywordDictionary.split(',').trim()
```

Agora, você removerá alguns termos do dicionário. Como o dicionário de exemplo tem algumas palavras-chave, você poderá ignorar facilmente para exportar o dicionário e editá-lo no Bloco de Notas, mas os dicionários geralmente contêm uma grande quantidade de texto, então você vai aprender primeiro assim para editá-los facilmente no PowerShell.
  
Na última etapa, você salvou as palavras-chave em uma matriz. Há várias maneiras de [remover itens de uma matriz](/previous-versions/windows/it-pro/windows-powershell-1.0/ee692802(v=technet.10)), mas como uma abordagem simples, você criará uma matriz de termos que deseja remover do dicionário e, em seguida, copia apenas os termos de dicionário para que ele não esteja na lista de termos para remover.
  
Execute o comando `$terms` para mostrar a lista atual de termos. A saída do comando tem esta aparência: 
  
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

Execute este comando para especificar os termos que você deseja remover:
  
```powershell
$termsToRemove = @('abandonment', 'ablatio')
```

Execute este comando para remover os termos realmente da lista:
  
```powershell
$updatedTerms = $terms | Where-Object{ $_ -notin $termsToRemove }
```

Execute o comando `$updatedTerms` para mostrar a lista atualizada de termos. A saída do comando tem esta aparência (os termos especificados foram removidos): 
  
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

Agora abra o arquivo, acrescente seus outros termos e salve com codificação Unicode (UTF-16). Agora, você carregará os termos atualizados e atualizará o dicionário no lugar.
  
```powershell
PS> Set-DlpKeywordDictionary -Identity "Diseases" -FileData (Get-Content -Path "C:myPath\terms.txt" -Encoding Byte -ReadCount 0)
```

Agora o dicionário foi atualizado. O campo `Identity` leva o nome do dicionário. Se você também quiser mudar o nome de seu dicionário usando o cmdlet `set-`, basta adicionar o parâmetro `-Name` ao que está acima com seu novo nome de dicionário. 

Confira também
- [Criar um dicionário de palavras-chave](create-a-keyword-dictionary.md)
- [Criar um tipo de informação confidencial personalizado](create-a-custom-sensitive-information-type.md)
