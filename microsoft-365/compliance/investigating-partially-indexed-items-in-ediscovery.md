---
title: Investigando itens parcialmente indexados na Descoberta eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 4e8ff113-6361-41e2-915a-6338a7e2a1ed
ms.custom:
- seo-marvel-apr2020
description: Saiba como gerenciar itens parcialmente indexados (também chamados de itens não indexados) Exchange, SharePoint e OneDrive for Business dentro da sua organização.
ms.openlocfilehash: c24fb2d9b633181538d76cf35e27dae1824b311d
ms.sourcegitcommit: f000358c01a8006e5749a86b256300ee3a73174c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/24/2021
ms.locfileid: "51994800"
---
# <a name="investigating-partially-indexed-items-in-ediscovery"></a>Investigando itens parcialmente indexados na Descoberta eDiscovery

Uma pesquisa de Descoberta Automática que você executar do centro de conformidade Microsoft 365 inclui automaticamente itens parcialmente indexados nos resultados estimados da pesquisa ao executar uma pesquisa. Itens parcialmente indexados são Exchange de caixa de correio e documentos em sites SharePoint e OneDrive for Business que, por algum motivo, não foram totalmente indexados para pesquisa. A maioria das mensagens de email e documentos de site são indexadas com êxito porque estão dentro dos [limites de indexação para mensagens de email.](limits-for-content-search.md#indexing-limits-for-email-messages) No entanto, alguns itens podem exceder esses limites de indexação e serão parcialmente indexados. Aqui estão outros motivos pelos quais os itens não podem ser indexados para pesquisa e são retornados como itens parcialmente indexados quando você executar uma pesquisa de Descoberta E:
  
- As mensagens de email têm um arquivo anexado sem um manipulador válido, como arquivos de imagem; essa é a causa mais comum de itens de email parcialmente indexados.

- Muitos arquivos anexados a uma mensagem de email.

- Um arquivo anexado a uma mensagem de email é muito grande.

- O tipo de arquivo é compatível com a indexação, mas ocorreu um erro de indexação com um arquivo específico.

Embora varie, a maioria dos clientes de organizações tem menos de 1% do conteúdo por volume e menos de 12% do conteúdo por tamanho parcialmente indexado. O motivo da diferença entre o volume e o tamanho é que arquivos maiores têm uma maior probabilidade de conter conteúdo que não pode ser totalmente indexado.
  
## <a name="why-does-the-partially-indexed-item-count-change-for-a-search"></a>Por que a contagem de itens parcialmente indexada muda para uma pesquisa?

Depois que você executar uma pesquisa de Descobertas E, o número total e o tamanho de itens parcialmente indexados nos locais pesquisados são listados nas estatísticas de resultados da pesquisa exibidas nas estatísticas detalhadas da pesquisa. Observe que eles são chamados de itens  *não índicedos*  nas estatísticas de pesquisa. Aqui estão algumas coisas que afetarão o número de itens parcialmente indexados que são retornados nos resultados da pesquisa:
  
- Se um item for parcialmente indexado e corresponde à consulta de pesquisa, ele será incluído na contagem (e no tamanho) dos itens de resultado da pesquisa e itens parcialmente indexados. No entanto, quando os resultados dessa mesma pesquisa são exportados, o item é incluído apenas com o conjunto de resultados da pesquisa; ele não está incluído como um item parcialmente indexado.

- Os itens parcialmente indexados localizados em sites SharePoint e OneDrive *não* estão incluídos na estimativa de itens parcialmente indexados exibidos nas estatísticas detalhadas da pesquisa. No entanto, itens parcialmente indexados podem ser exportados quando você exporta os resultados de uma pesquisa de Descoberta e. Por exemplo, se você pesquisar apenas sites, o número estimado parcialmente indexado itens será zero.
  
## <a name="calculating-the-ratio-of-partially-indexed-items-in-your-organization"></a>Calculando a proporção de itens parcialmente indexados em sua organização

Para entender a exposição da sua organização a itens parcialmente indexados, você pode executar uma pesquisa de todo o conteúdo em todas as caixas de correio (usando uma consulta de palavra-chave em branco). No exemplo a seguir, há 56.208 (4.830 MB) itens totalmente indexados e 470 (316 MB) parcialmente indexados.
  
![Exemplo de estatísticas de pesquisa mostrando itens parcialmente indexados](../media/0f6a5cf7-4c98-44a0-a0dd-5aed67124641.png)
  
Você pode determinar a porcentagem de itens parcialmente indexados usando os cálculos a seguir.
  
 **Para calcular a proporção de itens parcialmente indexados em sua organização:**

`(Total number of partially indexed items/Total number of items) x 100`

`(470/56,208) x 100 = 0.84%`

Usando os resultados da pesquisa do exemplo anterior, 0,84% de todos os itens de caixas de correio são parcialmente indexados.
  
 **Para calcular a porcentagem do tamanho de itens parcialmente indexados em sua organização:**

`(Size of all partially indexed items/Size of all items) x 100`

`(316 MB/4830 MB) x 100 = 6.54%`

Portanto, no exemplo anterior, 6,54% do tamanho total de itens de caixa de correio são de itens parcialmente indexados. Como mencionado anteriormente, a maioria dos clientes de organizações tem menos de 1% do conteúdo por volume e menos de 12% do conteúdo por tamanho parcialmente indexado.

## <a name="working-with-partially-indexed-items"></a>Trabalhando com itens parcialmente indexados

Nos casos em que você precisa examinar parcialmente itens para validar que eles não contêm informações relevantes, você pode [exportar](export-a-content-search-report.md) um relatório de pesquisa de conteúdo que contém informações sobre itens parcialmente indexados. Ao exportar um relatório de pesquisa de conteúdo, certifique-se de escolher uma das opções de exportação que inclui itens parcialmente indexados.
  
![Escolha a segunda ou a terceira opção para exportar itens parcialmente indexados](../media/624a62b4-78f7-4329-ab5d-e62e3b369885.png)
  
Quando você exporta resultados de pesquisa de Descoberta Items.csv. Este relatório inclui a maioria das mesmas informações que o arquivo ResultsLog.csv arquivo; no entanto, o arquivo Items.csv também inclui dois campos relacionados a itens parcialmente **indexados:** **Marcas** de Erro e Propriedades de Erro . Esses campos contêm informações sobre o erro de indexação para cada item parcialmente indexado. O uso das informações nesses dois campos pode ajudá-lo a determinar se o erro de indexação de um determinado afeta ou não sua investigação. Se isso acontecer, você poderá executar uma pesquisa direcionada e recuperar e exportar mensagens de email específicas e documentos SharePoint ou OneDrive para que você possa examiná-los para determinar se elas são relevantes para sua investigação. Para obter instruções passo a passo, consulte [Prepare a CSV file for a targeted search in Office 365](csv-file-for-an-id-list-content-search.md).

> [!NOTE]
> O arquivo Items.csv não Items.csv também contém campos denominados **Tipo de** Erro e Mensagem **de Erro.** Esses são campos herdados que contêm informações semelhantes  às informações nos campos **Marcas** de Erro e Propriedades de Erro, mas com informações menos detalhadas. Você pode ignorar com segurança esses campos herddos.
  
## <a name="errors-related-to-partially-indexed-items"></a>Erros relacionados a itens parcialmente indexados

As marcas de erro são feitas de duas informações, o erro e o tipo de arquivo. Por exemplo, neste par de erro/tipo de arquivo:

```text
 parseroutputsize_xls
```

 `parseroutputsize` é o erro e `xls` é o tipo de arquivo do arquivo em que o erro ocorreu. Nos casos em que o tipo de arquivo não foi reconhecido ou o tipo de arquivo não se aplica ao erro, você verá o valor no lugar do tipo `noformat` de arquivo.
  
Veja a seguir uma lista de erros de indexação e uma descrição da possível causa do erro.
  
| Marca de erro | Descrição |
|:-----|:-----|
| `attachmentcount` <br/> |Uma mensagem de email tinha muitos anexos e alguns desses anexos não foram processados.  <br/> |
| `attachmentdepth` <br/> |O recuperador de conteúdo e o analisador de documentos encontraram muitos níveis de anexos aninhados dentro de outros anexos. Alguns desses anexos não foram processados.  <br/> |
| `attachmentrms` <br/> |Falha na decodificação de um anexo porque estava protegido por RMS.  <br/> |
| `attachmentsize` <br/> |Um arquivo anexado a uma mensagem de email era muito grande e não podia ser processado.  <br/> |
| `indexingtruncated` <br/> |Ao escrever a mensagem de email processada no índice, uma das propriedades indexáveis era muito grande e foi truncada. As propriedades truncadas estão listadas no campo Propriedades de Erro.  <br/> |
| `invalidunicode` <br/> |Uma mensagem de email continha texto que não poderia ser processado como Unicode válido. A indexação para este item pode estar incompleta.  <br/> |
| `parserencrypted` <br/> |O conteúdo do anexo ou da mensagem de email é criptografado e Microsoft 365 não pôde decodificar o conteúdo.  <br/> |
| `parsererror` <br/> |Ocorreu um erro desconhecido durante a análise. Isso normalmente resulta de um bug de software ou de uma falha de serviço.  <br/> |
| `parserinputsize` <br/> |Um anexo era muito grande para o analisador manipular, e a análise desse anexo não aconteceu ou não foi concluída.  <br/> |
| `parsermalformed` <br/> |Um anexo foi malformado e não pôde ser manipulado pelo analisador. Esse resultado pode ser devido a formatos de arquivo antigos, arquivos criados por software incompatível ou vírus que fingem ser algo diferente de reivindicado.  <br/> |
| `parseroutputsize` <br/> |A saída da análise de um anexo era muito grande e precisava ser truncada.  <br/> |
| `parserunknowntype` <br/> |Um anexo tinha um tipo de arquivo Microsoft 365 não era detectado.  <br/> |
| `parserunsupportedtype` <br/> |Um anexo tinha um tipo de arquivo que Office 365 poderia detectar, mas não há suporte para analisar esse tipo de arquivo.  <br/> |
| `propertytoobig` <br/> |O valor de uma propriedade de email no Exchange Store era muito grande para ser recuperado e a mensagem não pôde ser processada. Normalmente, isso só acontece com a propriedade body de uma mensagem de email.  <br/> |
| `retrieverrms` <br/> |O recuperador de conteúdo falhou ao decodificar uma mensagem protegida por RMS.  <br/> |
| `wordbreakertruncated` <br/> |Muitas palavras foram identificadas no documento durante a indexação. O processamento da propriedade parou ao atingir o limite e a propriedade é truncada.  <br/> |

Os campos de erro descrevem quais campos são afetados pelo erro de processamento listado no campo Marcas de Erro. Se você estiver pesquisando uma propriedade como ou , erros no corpo da mensagem não afetarão os  `subject`  `participants` resultados da pesquisa. Isso pode ser útil ao determinar exatamente quais itens parcialmente indexados você pode precisar investigar mais.
  
## <a name="using-a-powershell-script-to-determine-your-organizations-exposure-to-partially-indexed-email-items"></a>Usando um script do PowerShell para determinar a exposição da sua organização a itens de email parcialmente indexados

As etapas a seguir mostram como executar um script do PowerShell que pesquisa todos os itens em todas as caixas de correio do Exchange e, em seguida, gera um relatório sobre a proporção da sua organização de itens de email parcialmente indexados (por contagem e por tamanho) e exibe o número de itens (e seu tipo de arquivo) para cada erro de indexação que ocorre. Use as descrições da marca de erro na seção anterior para identificar o erro de indexação.
  
1. Salve o texto a seguir em um arquivo Windows PowerShell script usando um sufixo de nome de arquivo de .ps1; por exemplo, `PartiallyIndexedItems.ps1` .

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

2. [Conectar ao Centro de Conformidade e Segurança do PowerShell](/powershell/exchange/exchange-online-powershell).

3. No Centro de Conformidade & Segurança do PowerShell, vá para a pasta onde você salvou o script na etapa 1 e execute o script; por exemplo:

   ```powershell
   .\PartiallyIndexedItems.ps1
   ```

Veja um exemplo para a saída retornada pelo script.
  
![Exemplo de saída do script que gera um relatório sobre a exposição da sua organização a itens de email parcialmente indexados](../media/aeab5943-c15d-431a-bdb2-82f135abc2f3.png)

> [!NOTE]
> Observe o seguinte:
>  
> - O número total e o tamanho dos itens de email e a taxa de itens de email parcialmente indexados da sua organização (por contagem e por tamanho).
> 
> - Uma lista de marcas de erro e os tipos de arquivo correspondentes para os quais o erro ocorreu.
  
## <a name="see-also"></a>Confira também

[Itens parcialmente indexados na Descoberta eDiscovery](partially-indexed-items-in-content-search.md)