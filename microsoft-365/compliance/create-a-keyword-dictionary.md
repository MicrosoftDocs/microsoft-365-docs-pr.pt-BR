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
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
description: Aprenda as etapas básicas para criar um dicionário de palavras-chave no Centro de Segurança e Conformidade do Office 365.
ms.openlocfilehash: e6f6043efd4c5f38b7e9fa2a92c4fcb7ceb91e45
ms.sourcegitcommit: 554755bc9ce40228ce6e34bde6fc6e226869b6a1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/22/2020
ms.locfileid: "48681631"
---
# <a name="create-a-keyword-dictionary"></a>Criar um dicionário de palavras-chave

A DLP (prevenção contra perda de dados) pode identificar, monitorar e proteger seus itens confidenciais. Às vezes, a identificação de itens confidenciais requer a procura de palavras-chave, principalmente ao identificar conteúdos genéricos (como comunicações relacionadas à assistência médica), ou linguagem inadequada ou explícita. Embora seja possível criar listas de palavras-chave em tipos de informações confidenciais, as listas de palavras-chave têm tamanho limitado e exigem a modificação do XML para criá-las ou editá-las. Os dicionários de palavras-chave oferecem gerenciamento mais simples de palavras-chave e em uma escala muito maior, suportando até 100KB de termos (pós compactação) no dicionário e qualquer idioma. O limite do locatário também é de 100KB após a compactação.
  
> [!NOTE]
> A Proteção de Informações do Microsoft 365 agora oferece suporte a idiomas de conjunto de caracteres de byte duplo de visualização:
> - Chinês (simplificado)
> - Chinês (tradicional)
> - Coreano
> - Japonês
>
>Este suporte está disponível para tipos de informações confidenciais. Para obter mais informações, confira [Suporte à proteção de informações para notas de versão de conjuntos de caracteres de byte duplo (visualização)](mip-dbcs-relnotes.md).

## <a name="basic-steps-to-creating-a-keyword-dictionary"></a>Etapas básicas para criar um dicionário de palavra-chave

As palavras-chave para o seu dicionário podem vir de uma variedade de fontes, mais comumente de um arquivo (como uma lista .csv ou .txt), importada no serviço ou pelo cmdlet do PowerShell de uma lista que você insere diretamente no cmdlet do PowerShell ou de um dicionário existente. Quando você cria um dicionário de palavras-chave, siga as mesmas etapas principais:
  
1. Use o **Centro de Conformidade e Segurança** ([https://protection.office.com](https://protection.office.com)) ou conecte-se ao **Centro &amp; de Conformidade e Segurança do PowerShell**.
    
2. **Defina ou carregue suas palavras-chave da fonte pretendida**. O assistente e o cmdlet aceitam uma lista separada por vírgulas de palavras-chave para criar um dicionário de palavras-chave personalizado, de modo que esta etapa irá variar um pouco dependendo da origem das palavras-chave. Uma vez carregadas, elas são codificadas e convertidas em uma matriz bytes antes de serem importadas.
    
3. **Crie seu dicionário**. Escolha um nome e uma descrição, e crie seu dicionário.

## <a name="create-a-keyword-dictionary-using-the-security--compliance-center"></a>Criar um dicionário de palavras-chave usando o Centro de Conformidade e Segurança

Use as etapas a seguir para criar e importar palavras-chave para um dicionário personalizado:

1. Conectar-se ao Centro de Conformidade e Segurança ([https://protection.office.com](https://protection.office.com)).

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

Frequentemente, quando você precisa criar um dicionário grande, é para usar palavras-chave de um arquivo ou lista exportada de alguma outra fonte. Nesse caso, você criará um dicionário de palavras-chave contendo uma lista de linguagem imprópria para exibir em email externo. Primeiro você deve [conectar-se ao Centro &amp; de Conformidade e Segurança do PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).
  
1. Copie as palavras-chave para um arquivo de texto e verifique se cada palavra-chave está em uma linha separada.
    
2. Salve o arquivo de texto com codificação Unicode. No Bloco de Notas \> **Salvar como** \> **Codificação** \> **Unicode**.
    
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

Agora, você removerá alguns termos do dicionário. Como o dicionário de exemplo tem apenas alguns as palavras-chave, você poderá ignorar facilmente para exportar o dicionário e editá-lo no Bloco de Notas, mas os dicionários geralmente contêm uma grande quantidade de texto, então você vai aprender primeiro assim para editá-los facilmente no PowerShell.
  
Na última etapa, você salvou as palavras-chave em uma matriz. Há várias maneiras de [remover itens de uma matriz](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-powershell-1.0/ee692802(v=technet.10)), mas como uma abordagem simples, você criará uma matriz de termos que deseja remover do dicionário e, em seguida, copia apenas os termos de dicionário para que ele não esteja na lista de termos para remover.
  
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

Agora basta abrir o arquivo, adicionar os termos adicionais e salvar a codificação Unicode (UTF-16). Agora você carregará os termos atualizados e atualizará o dicionário no local.
  
```powershell
PS> Set-DlpKeywordDictionary -Identity "Diseases" -FileData (Get-Content -Path "C:myPath\terms.txt" -Encoding Byte -ReadCount 0)
```

Agora, o dicionário foi atualizado no local. Observe que o campo `Identity` leva o nome do dicionário. Se você também quiser alterar o nome do dicionário usando o cmdlet `set-`, basta adicionar o parâmetro `-Name` para o que está acima com o novo nome do dicionário. 
  
## <a name="using-keyword-dictionaries-in-custom-sensitive-information-types-and-dlp-policies"></a>Usar dicionários de palavras-chave em tipos de informação confidencial personalizados e as políticas DLP

Os dicionários de palavras-chave podem ser usados como parte dos requisitos de correspondência para um tipo de informação confidencial personalizado ou como um tipo de informação confidencial próprio. Ambos exigem que você crie um [tipo de informação confidencial personalizado](create-a-custom-sensitive-information-type-in-scc-powershell.md). Siga as instruções no artigo vinculado para criar um tipo de informação confidencial. Assim que tiver o XML, você precisará do identificador de GUID do dicionário para usá-lo.
  
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


Cole a identidade no XML do seu tipo de informação confidencial personalizado e carregue-a. Agora seu dicionário aparecerá na sua lista de tipos de informação confidencial e você poderá usá-lo direto em sua política, especificando o número de palavras-chave necessário para corresponder.
  
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
