---
title: Investigar itens parcialmente indexados na descoberta eletrônica
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 1/26/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 4e8ff113-6361-41e2-915a-6338a7e2a1ed
ms.custom:
- seo-marvel-apr2020
description: Saiba como gerenciar itens parcialmente indexados (ou não indexados) do Exchange, SharePoint e OneDrive em sua organização.
ms.openlocfilehash: ed85a9351aad340c5840b6b9b9ea6e55833ed527
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/19/2020
ms.locfileid: "44817520"
---
# <a name="investigating-partially-indexed-items-in-ediscovery"></a>Investigar itens parcialmente indexados na descoberta eletrônica

Uma pesquisa de conteúdo que você executa a partir do centro de conformidade & segurança inclui automaticamente itens parcialmente indexados nos resultados estimados da pesquisa quando você executa uma pesquisa. Itens parcialmente indexados são itens de caixa de correio do Exchange e documentos em sites do SharePoint e do OneDrive for Business que por algum motivo não foram completamente indexados para pesquisa. A maioria das mensagens de email e documentos de site são indexados com êxito porque estão dentro dos [limites de indexação para mensagens de email](limits-for-content-search.md#indexing-limits-for-email-messages). No entanto, alguns itens podem exceder esses limites de indexação e serão parcialmente indexados. Aqui estão outras razões pelas quais os itens não podem ser indexados para pesquisa e são retornados como itens parcialmente indexados quando você executa uma pesquisa de conteúdo:
  
- As mensagens de email têm um arquivo anexado de um tipo de arquivo que não pode ser indexado; na maioria dos casos, o tipo de arquivo é [não reconhecido ou não tem suporte para indexação](partially-indexed-items-in-content-search.md#file-types-not-indexed-for-search)
    
- As mensagens de email têm um arquivo anexado sem um manipulador válido, como arquivos de imagem; Esta é a causa mais comum de itens de email parcialmente indexados
    
- Muitos arquivos anexados a uma mensagem de email
    
- Um arquivo anexado a uma mensagem de email é muito grande
    
- O tipo de arquivo tem suporte para indexação, mas ocorreu um erro de indexação para um arquivo específico
    
Embora varie, a maioria dos clientes da organização tem menos de 1% do conteúdo por volume e menos de 12% do conteúdo por tamanho parcialmente indexado. O motivo para a diferença entre o volume versus o tamanho é que os arquivos maiores têm uma maior probabilidade de conteúdo que não pode ser completamente indexado.
  
## <a name="why-does-the-partially-indexed-item-count-change-for-a-search"></a>Por que a contagem de itens parcialmente indexados é alterada para uma pesquisa?

Após executar uma pesquisa de conteúdo no centro de conformidade de & de segurança, o número total e o tamanho de itens parcialmente indexados nos locais que foram pesquisados são listados nas estatísticas de resultados de pesquisa que são exibidas nas estatísticas detalhadas da pesquisa. Observe que são chamados de *itens não indexados* nas estatísticas de pesquisa. Veja algumas coisas que afetarão o número de itens parcialmente indexados retornados nos resultados da pesquisa: 
  
- Se um item for parcialmente indexado e corresponder à consulta de pesquisa, ele será incluído na contagem (e no tamanho) dos itens de resultado de pesquisa e dos itens parcialmente indexados. No entanto, quando os resultados da mesma pesquisa são exportados, o item é incluído somente com o conjunto de resultados de pesquisa; Ele não está incluído como um item parcialmente indexado.
    
- Se você especificar um intervalo de datas para uma consulta de pesquisa (incluindo-a na consulta de palavra-chave ou usando uma condição), qualquer item parcialmente indexado que não coincida com o intervalo de datas não será incluído na contagem de itens parcialmente indexados. Somente os itens parcialmente indexados que estão no intervalo de datas são incluídos na contagem de itens parcialmente indexados.
    
 **Observação:** Os itens parcialmente indexados localizados nos sites do SharePoint e do OneDrive *não são* incluídos na estimativa de itens parcialmente indexados que são exibidos nas estatísticas detalhadas da pesquisa. No entanto, os itens parcialmente indexados podem ser exportados quando você exporta os resultados de uma pesquisa de conteúdo. Por exemplo, se você só pesquisa sites em uma pesquisa de conteúdo, o número estimado de itens parcialmente indexados será zero. 
  
## <a name="calculating-the-ratio-of-partially-indexed-items-in-your-organization"></a>Calculando a taxa de itens parcialmente indexados em sua organização

Para entender a exposição da sua organização a itens parcialmente indexados, você pode executar uma pesquisa de todo o conteúdo em todas as caixas de correio (usando uma consulta de palavra-chave em branco). No exemplo a seguir, há itens totalmente indexados de 56.208 (4.830 MB) e 470 (316 MB) parcialmente indexados.
  
![Exemplo de estatísticas de pesquisa mostrando itens parcialmente indexados](../media/0f6a5cf7-4c98-44a0-a0dd-5aed67124641.png)
  
Você pode determinar a porcentagem de itens parcialmente indexados usando os seguintes cálculos.
  
 **Para calcular a taxa de itens parcialmente indexados em sua organização:**

`(Total number of partially indexed items/Total number of items) x 100`


`(470/56,208) x 100 = 0.84%`
 
Usando os resultados da pesquisa do exemplo anterior,. 84% de todos os itens de caixas de correio são parcialmente indexados.
  
 **Para calcular a porcentagem do tamanho de itens parcialmente indexados em sua organização:**

`(Size of all partially indexed items/Size of all items) x 100`

`(316 MB/4830 MB) x 100 = 6.54%`

Portanto, no exemplo anterior, 6,54% do tamanho total dos itens de caixa de correio são de itens parcialmente indexados. Conforme mencionado anteriormente, a maioria das organizações tem menos de 1% de conteúdo por volume e menos de 12% de conteúdo por tamanho parcialmente indexado.

## <a name="working-with-partially-indexed-items"></a>Trabalhar com itens parcialmente indexados

Em casos em que você precisa examinar itens parcialmente para validar que eles não contêm informações relevantes, é possível [exportar um relatório de pesquisa de conteúdo](export-a-content-search-report.md) que contenha informações sobre itens parcialmente indexados. Ao exportar um relatório de pesquisa de conteúdo, certifique-se de escolher uma das opções de exportação que inclui itens parcialmente indexados. 
  
![Escolha a segunda ou terceira opção para exportar itens parcialmente indexados](../media/624a62b4-78f7-4329-ab5d-e62e3b369885.png)
  
Quando você exporta resultados de pesquisa de conteúdo ou um relatório de pesquisa de conteúdo usando uma destas opções, a exportação inclui um relatório chamado Items.csv não indexado. Este relatório inclui a maioria das mesmas informações que o arquivo de ResultsLog.csv; no entanto, o arquivo Items.csv não indexado também inclui dois campos relacionados a itens parcialmente indexados: **marcas de erro** e **Propriedades de erro**. Esses campos contêm informações sobre o erro de indexação para cada item parcialmente indexado. O uso das informações nesses dois campos pode ajudá-lo a determinar se o erro de indexação para um determinado impacto em sua investigação. Se isso acontecer, você poderá executar uma pesquisa de conteúdo direcionado e recuperar e exportar mensagens de email específicas e documentos do SharePoint ou do OneDrive para que possa examiná-las para determinar se elas são relevantes para a investigação. Para obter instruções passo a passo, consulte [preparar um arquivo CSV para uma pesquisa de conteúdo direcionado no Office 365](csv-file-for-an-id-list-content-search.md).
  
 **Observação:** O arquivo Items.csv não indexado também contém campos chamados de **tipo de erro** e mensagem de **erro**. Estes são campos herdados que contêm informações semelhantes às informações nos campos marcas de **erro** e **Propriedades de erro** , mas com informações menos detalhadas. Você pode ignorar com segurança esses campos herdados. 
  
## <a name="errors-related-to-partially-indexed-items"></a>Erros relacionados a itens parcialmente indexados

Marcas de erro são comparadas de duas partes de informação, o erro e o tipo de arquivo. Por exemplo, neste par erro/filetype:

```text
 parseroutputsize_xls
```

   
 `parseroutputsize`é o erro e `xls` é o tipo de arquivo do arquivo no qual o erro ocorreu. Nos casos em que o tipo de arquivo não foi reconhecido ou o tipo de arquivo não se aplica ao erro, você verá o valor `noformat` no lugar do tipo de arquivo. 
  
Veja a seguir uma lista de erros de indexação e uma descrição da possível causa do erro.
  
|**Marca de erro**|**Descrição**|
|:-----|:-----|
| `attachmentcount` <br/> |Uma mensagem de email tinha muitos anexos e alguns desses anexos não foram processados.  <br/> |
| `attachmentdepth` <br/> |O recuperador de conteúdo e o analisador de documentos encontraram muitos níveis de anexos aninhados dentro de outros anexos. Alguns desses anexos não foram processados.  <br/> |
| `attachmentrms` <br/> |Um anexo falhou ao decodificar porque estava protegido por RMS.  <br/> |
| `attachmentsize` <br/> |Um arquivo anexado a uma mensagem de email era muito grande e não pôde ser processado.  <br/> |
| `indexingtruncated` <br/> |Ao gravar a mensagem de email processada no índice, uma das propriedades indexáveis era muito grande e estava truncada. As propriedades truncadas estão listadas no campo Propriedades do erro.  <br/> |
| `invalidunicode` <br/> |Uma mensagem de email continha texto que não pôde ser processado como Unicode válido. A indexação deste item pode estar incompleta.  <br/> |
| `parserencrypted` <br/> |O conteúdo do anexo ou da mensagem de email é criptografado, e o Microsoft 365 não pôde decodificar o conteúdo.  <br/> |
| `parsererror` <br/> |Ocorreu um erro desconhecido durante a análise. Isso normalmente resulta de um bug de software ou uma falha de serviço.  <br/> |
| `parserinputsize` <br/> |Um anexo era muito grande para o analisador manipular, e a análise desse anexo não aconteceu ou não foi concluída.  <br/> |
| `parsermalformed` <br/> |Um anexo foi malformado e não pôde ser manipulado pelo analisador. Esse resultado pode ser de formatos de arquivo antigos, arquivos criados por software incompatível ou vírus que fingim ser algo diferente de alegado.  <br/> |
| `parseroutputsize` <br/> |A saída da análise de um anexo era muito grande e teve de ser truncada.  <br/> |
| `parserunknowntype` <br/> |Um anexo tinha um tipo de arquivo que o Microsoft 365 não pôde detectar.  <br/> |
| `parserunsupportedtype` <br/> |Um anexo tinha um tipo de arquivo que o Office 365could detectou, mas não há suporte para a análise desse tipo de arquivo.  <br/> |
| `propertytoobig` <br/> |O valor de uma propriedade de email no repositório do Exchange era muito grande para ser recuperado e a mensagem não pôde ser processada. Isso geralmente ocorre apenas na Propriedade Body de uma mensagem de email.  <br/> |
| `retrieverrms` <br/> |O recuperador de conteúdo falhou ao decodificar uma mensagem protegida por RMS.  <br/> |
| `wordbreakertruncated` <br/> |Muitas palavras foram identificadas no documento durante a indexação. Processamento da propriedade parado ao atingir o limite, e a propriedade será truncada.  <br/> |
   
Os campos de erro descrevem quais campos são afetados pelo erro de processamento listado no campo marcas de erro. Se você estiver pesquisando uma propriedade como `subject` ou `participants` , os erros no corpo da mensagem não afetarão os resultados da pesquisa. Isso pode ser útil ao determinar exatamente quais itens parcialmente indexados você talvez precise investigar.
  
## <a name="using-a-powershell-script-to-determine-your-organizations-exposure-to-partially-indexed-email-items"></a>Usando um script do PowerShell para determinar a exposição da sua organização a itens de email parcialmente indexados

As etapas a seguir mostram como executar um script do PowerShell que pesquisa todos os itens em todas as caixas de correio do Exchange e, em seguida, gera um relatório sobre a taxa da organização de itens de email parcialmente indexados (por contagem e por tamanho) e exibe o número de itens (e o tipo de arquivo) para cada erro de indexação que ocorre. Use as descrições de marcas de erro na seção anterior para identificar o erro de indexação.
  
1. Salve o seguinte texto em um arquivo de script do Windows PowerShell usando um sufixo de nome de arquivo. ps1; por exemplo, `PartiallyIndexedItems.ps1` .

```powershell
  write-host "**************************************************"
  write-host "     Security & Compliance Center      " -foregroundColor yellow -backgroundcolor darkgreen
  write-host "   eDiscovery Partially Indexed Item Statistics   " -foregroundColor yellow -backgroundcolor darkgreen
  write-host "**************************************************"
  " " 
  # Create a search with Error Tags Refinders enabled
  Remove-ComplianceSearch "RefinerTest" -Confirm:$false -ErrorAction 'SilentlyContinue'
  New-ComplianceSearch -Name "RefinerTest" -ContentMatchQuery "size>0" -RefinerNames ErrorTags -ExchangeLocation ALL
  Start-ComplianceSearch "RefinerTest"
  # Loop while search is in progress
  do{
      Write-host "Waiting for search to complete..."
      Start-Sleep -s 5
      $complianceSearch = Get-ComplianceSearch "RefinerTest"
  }while ($complianceSearch.Status -ne 'Completed')
  $refiners = $complianceSearch.Refiners | ConvertFrom-Json
  $errorTagProperties = $refiners.Entries | Get-Member -MemberType NoteProperty
  $partiallyIndexedRatio = $complianceSearch.UnindexedItems / $complianceSearch.Items
  $partiallyIndexedSizeRatio = $complianceSearch.UnindexedSize / $complianceSearch.Size
  " "
  "===== Partially indexed items ====="
  "         Total          Ratio"
  "Count    {0:N0}{1:P2}" -f $complianceSearch.Items.ToString("N0").PadRight(15, " "), $partiallyIndexedRatio
  "Size(GB) {0:N2}{1:P2}" -f ($complianceSearch.Size / 1GB).ToString("N2").PadRight(15, " "), $partiallyIndexedSizeRatio
  " "
  Write-Host ===== Reasons for partially indexed items =====
  foreach($errorTagProperty in $errorTagProperties)
  {
      $name = $refiners.Entries.($errorTagProperty.Name).Name
      $count = $refiners.Entries.($errorTagProperty.Name).TotalCount
      $frag = $name.Split("{_}")
      $errorTag = $frag[0]
      $fileType = $frag[1]
      if ($errorTag -ne $lastErrorTag)
      {
          $errorTag
      }
      "    " + $fileType + " => " + $count
      $lastErrorTag = $errorTag
  }
  
```

2. [Conectar-se ao PowerShell do Centro de Conformidade e Segurança](https://go.microsoft.com/fwlink/p/?linkid=627084).
    
3. Em segurança & centro de conformidade do PowerShell, vá para a pasta onde você salvou o script na etapa 1 e execute o script; por exemplo:

    ```powershell
    .\PartiallyIndexedItems.ps1
    ```

Aqui está um exemplo de saída retornada pelo script.
  
![Exemplo de saída do script que gera um relatório sobre a exposição da sua organização para itens de email parcialmente indexados](../media/aeab5943-c15d-431a-bdb2-82f135abc2f3.png)
  
Observe o seguinte:
  
1. O número total e o tamanho dos itens de email e a taxa da sua organização de itens de email parcialmente indexados (por contagem e por tamanho)
    
2. Uma lista de marcas de erro e os tipos de arquivo correspondentes para os quais o erro ocorreu.
  
## <a name="see-also"></a>Confira também

[Itens parcialmente indexados na Pesquisa de Conteúdo do Office 365](partially-indexed-items-in-content-search.md)
