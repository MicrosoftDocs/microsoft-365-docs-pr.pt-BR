---
title: Criar um dicionário de palavras-chave
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
description: Saiba mais sobre as etapas básicas para criar um dicionário de palavras-chave no centro de conformidade & segurança do Office 365.
ms.openlocfilehash: 38a92aaf7e72ab79243c547ff48fa156e26b6ee6
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/19/2020
ms.locfileid: "44818050"
---
# <a name="create-a-keyword-dictionary"></a>Criar um dicionário de palavras-chave

A prevenção contra perda de dados (DLP) pode identificar, monitorar e proteger suas informações confidenciais. A identificação de informações confidenciais às vezes requer a procura de palavras-chave, particularmente ao identificar conteúdo genérico (como comunicação relacionada à assistência médica) ou linguagem inadequada ou explícita. Embora você possa criar listas de palavras-chave em tipos de informações confidenciais, as listas de palavras-chave têm tamanho limitado e exigem a modificação de XML para criá-las ou editá-las. Os dicionários de palavras-chave oferecem gerenciamento mais simples de palavras-chave e em escala muito maior, com suporte para até 100.000 termos por dicionário.
  
## <a name="basic-steps-to-creating-a-keyword-dictionary"></a>Etapas básicas para criar um dicionário de palavra-chave

The keywords for your dictionary could come from a variety of sources, most commonly from a file (such as a .csv or .txt list) imported in the service or by PowerShell cmdlet, from a list you enter directly in the PowerShell cmdlet, or from an existing dictionary. When you create a keyword dictionary, you follow the same core steps:
  
1. Use o **centro de conformidade do & de segurança** ( [https://protection.office.com](https://protection.office.com) ) ou conecte-se ao **PowerShell do centro de &amp; conformidade de segurança**.
    
2. **Defina ou carregue suas palavras-chave da fonte pretendida**. O assistente e o cmdlet aceitam uma lista separada por vírgulas de palavras-chave para criar um dicionário de palavras-chave personalizado, portanto, essa etapa variará um pouco dependendo de onde vêm suas palavras-chave. Uma vez carregadas, elas são codificadas e convertidas em uma matriz bytes antes de serem importadas.
    
3. **Crie seu dicionário**. Escolha um nome e uma descrição e crie seu dicionário.

## <a name="create-a-keyword-dictionary-using-the-security--compliance-center"></a>Criar um dicionário de palavras-chave usando o centro de conformidade de & de segurança

Use as etapas a seguir para criar e importar palavras-chave para um dicionário personalizado:

1. Conecte-se ao centro de conformidade do & de segurança ( [https://protection.office.com](https://protection.office.com) ).

2. Navegue até **Classificações > Tipos de informações confidenciais**.

3. Selecione **Criar** e insira **Nome** e **Descrição** para o tipo de informações confidenciais, em seguida, selecione **Avançar**

4. Selecione **Adicionar um elemento**e selecione **Dicionário (Palavras-chave grandes)** na lista suspensa **Detectar conteúdo que tenha**.

5. Selecione **Adicionar um dicionário**

6. Sob o controle da pesquisa, selecione **Você pode criar novos dicionários de palavras-chave**.

7. Insira um **Nome** para o dicionário personalizado.

8. Selecione **Importação**e selecione **a partir do texto** ou **a partir do csv** dependendo do tipo de arquivo de palavra-chave.

9. Na caixa de diálogo arquivo, selecione o arquivo de palavra-chave no compartilhamento de arquivos do computador ou rede local e selecione **Abrir**.

10. Selecione **Salvar**, em seguida selecione o dicionário personalizado da lista **Dicionários de palavras-chave**.

11. Selecione **Próximo**, e em seguida**Avançar**.

12. Revise e finalize as seleções de tipo de informações confidenciais e selecione **Terminar**.
    
## <a name="create-a-keyword-dictionary-from-a-file-using-powershell"></a>Criar um dicionário de palavras-chave de um arquivo usando o Power Shell

Often when you need to create a large dictionary, it's to use keywords from a file or a list exported from some other source. In this case, you'll create a keyword dictionary containing a list of inappropriate language to screen in external email. You must first [connect to Security &amp; Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).
  
1. Copie as palavras-chave para um arquivo de texto e verifique se cada palavra-chave está em uma linha separada.
    
2. Save the text file with Unicode encoding. In Notepad \> **Save As** \> **Encoding** \> **Unicode**.
    
3. Leia o arquivo em uma variável executando este cmdlet:
    
    ```powershell
    $fileData = Get-Content <filename> -Encoding Byte -ReadCount 0
    ```

4. Crie o dicionário executando este cmdlet:
    
    ```powershell
    New-DlpKeywordDictionary -Name <name> -Description <description> -FileData $fileData
    ```

## <a name="modifying-an-existing-keyword-dictionary"></a>Como modificar um dicionário de palavra-chave existente

Talvez seja necessário modificar palavras-chave em um de seus dicionários de palavras-chave ou modificar um dos dicionários internos. Atualmente, você pode atualizar somente um dicionário personalizado de palavras-chave usando o PowerShell. 

Por exemplo, modificaremos alguns termos no PowerShell, salvaremos os termos localmente, onde você poderá modificá-los em um editor e, em seguida, atualizar os termos anteriores no local. 

Primeiro, recupere o objeto dicionário:
  
```powershell
$dict = Get-DlpKeywordDictionary -Name "Diseases"
```

`$dict`A impressão mostrará várias variáveis. As palavras-chave são armazenadas em um objeto no back-end, mas `$dict.KeywordDictionary` contêm uma representação de cadeia de caracteres delas, que você usará para modificar o dicionário. 

Antes de modificar o dicionário, você precisa transformar a sequência de termos de volta em uma matriz usando o `.split(',')` método. Em seguida, você limpará os espaços indesejados entre as palavras-chave com o `.trim()` método, deixando apenas as palavras-chave com as quais trabalhar. 
  
```powershell
$terms = $dict.KeywordDictionary.split(',').trim()
```

Now you'll remove some terms from the dictionary. Because the example dictionary has only a few keywords, you could just as easily skip to exporting the dictionary and editing it in Notepad, but dictionaries generally contain a large amount of text, so you'll first learn this way to edit them easily in PowerShell.
  
In the last step, you saved the keywords to an array. There are several ways to [remove items from an array](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-powershell-1.0/ee692802(v=technet.10)), but as a straightforward approach, you'll create an array of the terms you want to remove from the dictionary, and then copy only the dictionary terms to it that aren't in the list of terms to remove.
  
Run the command  `$terms` to show the current list of terms. The output of the command looks like this: 
  
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

Run the command  `$updatedTerms` to show the updated list of terms. The output of the command looks like this (the specified terms have been removed): 
  
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

Now simply open the file, add your additional terms, and save with Unicode encoding (UTF-16). Now you'll upload the updated terms and update the dictionary in place.
  
```powershell
PS> Set-DlpKeywordDictionary -Identity "Diseases" -FileData (Get-Content -Path "C:myPath\terms.txt" -Encoding Byte -ReadCount 0)
```

Now the dictionary has been updated in place. Note that the  `Identity` field takes the name of the dictionary. If you wanted to also change the name of your dictionary using the  `set-` cmdlet, you would just need to add the  `-Name` parameter to what's above with your new dictionary name. 
  
## <a name="using-keyword-dictionaries-in-custom-sensitive-information-types-and-dlp-policies"></a>Usar dicionários de palavras-chave em tipos de informação confidencial personalizados e as políticas DLP

Os dicionários de palavras-chave podem ser usados como parte dos requisitos de correspondência para um tipo de informação confidencial personalizado ou como um tipo de informação confidencial. Ambas exigem que você crie um [tipo de informação confidencial personalizado](create-a-custom-sensitive-information-type-in-scc-powershell.md). Siga as instruções no artigo vinculado para criar um tipo de informação confidencial. Depois de usar o XML, você precisará do identificador de GUID do dicionário para usá-lo.
  
```xml
<Entity id="9e5382d0-1b6a-42fd-820e-44e0d3b15b6e" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef=". . ."/>
    </Pattern>
</Entity>
```

Para obter a identidade do seu dicionário, execute este comando e copie o valor da propriedade **Identity**: 
  
```powershell
Get-DlpKeywordDictionary -Name "Diseases"
```

A saída do comando será parecida com o seguinte:
  
`RunspaceId        : 138e55e7-ea1e-4f7a-b824-79f2c4252255`
`Identity          : 8d2d44b0-91f4-41f2-94e0-21c1c5b5fc9f`
`Name              : Diseases`
`Description       : Names of diseases and injuries from ICD-10-CM lexicon`
`KeywordDictionary : aarskog's syndrome, abandonment, abasia, abderhalden-kaufmann-lignac, abdominalgia, abduction contracture, abetalipo` `proteinemia, abiotrophy, ablatio, ablation, ablepharia, abocclusion, abolition, aborter, abortion, abortus, aboulomania,`
                    `abrami's disease, abramo`
`IsValid           : True`
`ObjectState       : Unchanged`


Paste the identity into your custom sensitive information type's XML and upload it. Now your dictionary will appear in your list of sensitive information types and you can use it right in your policy, specifying how many keywords are required to match.
  
```xml
<Entity id="d333c6c2-5f4c-4131-9433-db3ef72a89e8" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="8d2d44b0-91f4-41f2-94e0-21c1c5b5fc9f" />
      </Pattern>
    </Entity>
    <LocalizedStrings>
      <Resource idRef="d333c6c2-5f4c-4131-9433-db3ef72a89e8">
        <Name default="true" langcode="en-us">Diseases</Name>
        <Description default="true" langcode="en-us">Detects various diseases</Description>
      </Resource>
    </LocalizedStrings>
```
