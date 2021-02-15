---
title: Itens parcialmente indexados na Pesquisa de Conteúdo e em outras ferramentas de Descoberta
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
f1_keywords:
- ms.o365.cc.UnindexedItemsLearnMore
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- SPO160
- MOE150
- MET150
ms.assetid: d1691de4-ca0d-446f-a0d0-373a4fc8487b
description: Saiba mais sobre os itens não índicedos no Exchange e no SharePoint que você pode incluir em uma pesquisa de Descoberta eDiscovery que você executar no centro de conformidade do Microsoft 365.
ms.openlocfilehash: 34758ae904678d194e889a4f1b65606d2420a3c7
ms.sourcegitcommit: d7975c391e03eeb96e29c1d02e77d2a1433ea67c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/05/2020
ms.locfileid: "48920295"
---
# <a name="partially-indexed-items-in-ediscovery"></a>Itens parcialmente indexados na Descoberta e

Uma pesquisa de Descoberta Automática que você executar no centro de conformidade do Microsoft 365 inclui automaticamente itens parcialmente indexados nos resultados estimados da pesquisa quando você executar uma pesquisa. Itens parcialmente indexados são documentos e itens de caixa de correio do Exchange em sites do SharePoint e do OneDrive for Business que, por algum motivo, não foram completamente indexados para pesquisa. No Exchange, um item parcialmente indexado normalmente contém um arquivo (de um tipo de arquivo que não pode ser indexado) anexado a uma mensagem de email. Aqui estão alguns outros motivos pelos quais os itens não podem ser indexados para pesquisa e são retornados como itens parcialmente indexados quando você executar uma pesquisa de Descoberta e:
  
- O tipo de arquivo não é reconhecido ou não tem suporte para indexação. 

- As mensagens têm um arquivo anexado sem um manipulador válido, como arquivos de imagem; essa é a causa mais comum de itens de email parcialmente indexados.

- O tipo de arquivo é compatível com a indexação, mas ocorreu um erro de indexação com um arquivo específico.

- Muitos arquivos anexados a uma mensagem de email.

- Um arquivo anexado a uma mensagem de email é muito grande.

- Um arquivo foi criptografado com tecnologias que não são da Microsoft.

- Um arquivo está protegido por senha.

> [!NOTE]
> A maioria das organizações tem menos de 1% do conteúdo por volume e menos de 12% por tamanho parcialmente indexado. O motivo para a diferença entre volume e tamanho é que arquivos maiores têm uma maior probabilidade de conter conteúdo que não pode ser completamente indexado.
  
Para investigações legais, sua organização pode ser obrigada a revisar itens parcialmente indexados. Você também pode especificar se incluirá itens parcialmente indexados quando exportar resultados de pesquisa para um computador local ou quando preparar os resultados para análise com a Descoberta Avançada. Para obter mais informações, [consulte Investigando itens parcialmente indexados na Descoberta eDiscovery](investigating-partially-indexed-items-in-ediscovery.md).
  
## <a name="file-types-not-indexed-for-search"></a>Tipos de arquivo não indexados para pesquisa

Determinados tipos de arquivos, como arquivos Bitmap ou MP3, não têm conteúdo que possa ser indexado. Como resultado, os servidores de indexação de pesquisa no Exchange e no SharePoint não executam indexação de texto completo nesses tipos de arquivos. Estes tipos de arquivo são considerados como tipos de arquivo incompatíveis. Também existem tipos de arquivo para os quais a indexação de texto completo foi desabilitada, por padrão ou por um administrador. Os tipos de arquivo sem suporte e desabilitado são rotulados como itens não índicedos nas Pesquisas de Conteúdo. Conforme mencionado anteriormente, itens parcialmente indexados podem ser incluídos no conjunto de resultados de pesquisa quando você executar uma pesquisa, exportar os resultados da pesquisa para um computador local ou preparar os resultados da pesquisa para a Descoberta Avançada.
  
Para obter uma lista de formatos de arquivo com suporte ou desabilitados, confira os tópicos a seguir:
  
- **Exchange**  -  [Formatos de arquivo indexados pela Pesquisa do Exchange](https://go.microsoft.com/fwlink/p/?LinkID=386618)

- **Exchange**  -  [Get-SearchDocumentFormat](https://go.microsoft.com/fwlink/p/?LinkID=724037)

- **SharePoint**  -  [Extensões de nome de arquivo rastreado e tipos de arquivo analisados padrão no SharePoint](https://go.microsoft.com/fwlink/p/?LinkID=404033)
  
## <a name="messages-and-documents-with-partially-indexed-file-types-can-be-returned-in-search-results"></a>Mensagens e documentos com tipos de arquivo parcialmente indexados podem ser retornados nos resultados da pesquisa

Nem todas as mensagens de email com um anexo de arquivo parcialmente indexado ou cada documento do SharePoint parcialmente indexado são automaticamente retornados como um item parcialmente indexado. Isso porque outras propriedades de documento ou mensagem, como a propriedade  **Assunto** em mensagens de email e as propriedades **Título** ou Autor de documentos são indexadas e estão disponíveis para serem pesquisadas. Por exemplo, uma pesquisa de palavra-chave por "financeiro" retornará itens com um anexo de arquivo parcialmente indexado se essa palavra-chave aparecer no assunto de uma mensagem de email ou no nome de arquivo ou título de um documento. No entanto, se a palavra-chave aparecer somente no corpo do arquivo, a mensagem ou o documento será retornado como um item parcialmente indexado.
  
Da mesma forma, as mensagens com anexos de arquivo parcialmente indexados e documentos de um tipo de arquivo parcialmente indexado são incluídas nos resultados da pesquisa quando outras propriedades de documento ou mensagem, que são indexadas e pesquisáveis, atendem aos critérios de pesquisa. Propriedades de mensagem indexadas para pesquisa incluem datas enviadas e recebidas, remetente e destinatário, o nome do arquivo de um anexo e o texto no corpo da mensagem. Propriedades do documento indexadas para pesquisa incluem datas criadas e modificadas. Portanto, mesmo que um anexo de mensagem possa ser um item parcialmente indexado, a mensagem será incluída nos resultados da pesquisa regular se o valor de outras propriedades de mensagem ou documento corresponde aos critérios de pesquisa.
  
Para uma lista de propriedades de email e documento que você pode pesquisar usando o recurso de Pesquisa no Centro de Conformidade de segurança &, consulte Consultas de palavra-chave e condições de pesquisa para [eDiscovery](keyword-queries-and-search-conditions.md).
  
## <a name="partially-indexed-items-included-in-the-search-results"></a>Itens parcialmente indexados incluídos nos resultados da pesquisa

Sua organização pode ser obrigada a identificar e executar análises adicionais em itens parcialmente indexados para determinar o que são, o que eles contêm e se são relevantes para uma investigação específica. Conforme explicado anteriormente, os itens parcialmente indexados nos locais de conteúdo pesquisados são incluídos automaticamente nos resultados estimados da pesquisa. Você tem a opção de incluir esses itens parcialmente indexados ao exportar resultados de pesquisa ou preparar os resultados da pesquisa para a Descoberta Avançada.
  
Lembre-se do seguinte sobre itens parcialmente indexados:
  
- Quando você executar uma pesquisa de Descoberta eDiscovery, o número total e o tamanho de itens do Exchange parcialmente indexados (retornados pela consulta de pesquisa) serão exibidos nas estatísticas de pesquisa no painel de detalhes e rotulados como itens **indexados.** As estatísticas sobre itens parcialmente indexados exibidos no painel de detalhes não incluem itens parcialmente indexados no SharePoint ou no OneDrive.

- Se a pesquisa de onde você está exportando resultados foi uma pesquisa de locais de conteúdo específicos ou de todos os locais de conteúdo em sua organização, apenas os itens não índicedos de locais de conteúdo que contêm itens que corresponderem aos critérios de pesquisa serão exportados. In other words, if no search results are found in a mailbox or site, then any unindexed items in that mailbox or site won't be exported. O motivo para isso é que exportar itens parcialmente indexados de muitos locais na organização pode aumentar a probabilidade de erros de exportação e aumentar o tempo necessário para exportar e baixar os resultados da pesquisa.

    Para exportar itens parcialmente indexados de todos os locais de conteúdo para uma pesquisa, configure a pesquisa para retornar todos os itens (removendo todas as palavras-chave da consulta de pesquisa) e exporte apenas itens parcialmente indexados quando você exportar os resultados da pesquisa (clicando em Apenas itens que têm um formato não reconhecedo, são criptografados ou não **foram indexados** por outros motivos em opções de saída **).**

- Se você optar por incluir todos os itens de caixa de correio nos resultados da pesquisa ou se uma consulta de pesquisa não especificar nenhuma palavra-chave ou apenas especificar um intervalo de datas, os itens parcialmente indexados podem não ser copiados para o arquivo PST que contém os itens parcialmente indexados. Isso acontece porque todos os itens, incluindo todos os itens parcialmente indexados, serão automaticamente incluídos nos resultados regulares da pesquisa.

- Itens parcialmente indexados não estão disponíveis para visualização. Você precisa exportar os resultados da pesquisa para exibir itens parcialmente indexados retornados pela pesquisa.

Além disso, quando você exporta os resultados da pesquisa e inclui itens parcialmente indexados na exportação, itens parcialmente indexados de itens do SharePoint são exportados para uma pasta chamada **Uncrawlable**. Quando você exporta itens do Exchange parcialmente indexados, eles são exportados de forma diferente, dependendo se os itens parcialmente indexados corresponderam à consulta de pesquisa e à configuração das configurações de exportação. 

A tabela a seguir mostra o comportamento de exportação de itens indexados e parcialmente indexados e se cada um deles está incluído nas diferentes definições de configuração de exportação.

|**Configuração de exportação**|**Itens indexados que corresponderem à consulta de pesquisa**|**Itens parcialmente indexados que corresponderem à consulta de pesquisa**|**Itens parcialmente indexados que não corresponderem à consulta de pesquisa**|
|:-----|:-----|:-----|:-----|
|Exportar somente itens indexados  <br/> |Exported<br/> |Exported (included with the indexed items that are exported)<br/>  |Não exportado <br/>|
|Exportar apenas itens parcialmente indexados  <br/> |Não exportado  <br/> |Exportado (como itens parcialmente indexados)<br/> |Exportado (como itens parcialmente indexados)|
|Exportar itens indexados e parcialmente indexados  <br/> |Exported<br/> |Exported (included with the indexed items that are exported)<br/>  |Exportado (como itens parcialmente indexados)<br/>|
||||

## <a name="partially-indexed-items-excluded-from-the-search-results"></a>Itens parcialmente indexados excluídos dos resultados da pesquisa

Se um item for parcialmente indexado, mas não atender aos critérios de consulta de pesquisa, ele não será incluído como um item parcialmente indexado nos resultados da pesquisa. Em outras palavras, o item é excluído nos resultados da pesquisa. Por exemplo, digamos que você executa uma pesquisa e não inclui quaisquer palavras-chave ou propriedades porque você deseja incluir todo o conteúdo. Mas você inclui uma condição de intervalo de data para a consulta. Se um item parcialmente indexado ficar fora desse intervalo de datas, ele não será incluído como um item parcialmente indexado. Intervalos de datas são uma maneira eficaz de excluir itens parcialmente indexados dos resultados da pesquisa.
  
Da mesma forma, se você optar por incluir itens parcialmente indexados ao exportar os resultados de uma pesquisa, os itens parcialmente indexados que foram excluídos dos resultados da pesquisa não serão exportados.
  
Uma exceção a essa regra é quando você cria uma isenção baseada em consulta que está associada a um caso de Descoberta eDiscovery. Se você criar uma espera de Descoberta e Baseada em Consulta, todos os itens parcialmente indexados serão colocados em espera. Isso inclui itens parcialmente indexados que não corresponderem aos critérios de consulta de pesquisa e itens parcialmente indexados que podem estar fora de uma condição de intervalo de datas. Para obter mais informações sobre a criação de retém de Descoberta e baseada em consulta, consulte [Create an eDiscovery hold](create-ediscovery-holds.md).
  
## <a name="indexing-limits-for-messages"></a>Limites de indexação para mensagens

A tabela a seguir descreve os limites de indexação que podem resultar no retorno de uma mensagem de email como um item parcialmente indexado em uma pesquisa de Descoberta Eletrônico no Microsoft 365.
  
Para uma lista de limites de indexação para documentos do SharePoint, confira [Limites de pesquisa do SharePoint Online.](https://docs.microsoft.com/sharepoint/search-limits)
  
|**Limite de indexação**|**Observações**|**Descrição**|
|:-----|:-----|:-----|
|Tamanho máximo do anexo (excluindo arquivos do Excel)  <br/> |150 MB  <br/> |O tamanho máximo de um anexo de email que será analisado para indexação. Qualquer anexo maior do que esse limite não será analisado para indexação, e a mensagem com o anexo será marcada como parcialmente indexada.  <br/><br/> **Observação:** Análise é o processo em que o serviço de indexação extrai texto do anexo, remove caracteres desnecessários, como pontuação e espaços, e divide o texto em palavras (em um processo chamado tokenização), que são armazenadas no índice.           |
|Tamanho máximo de arquivos do Excel  <br/> |4 MB  <br/> |O tamanho máximo de um arquivo do Excel localizado em um site ou anexado a uma mensagem de email que será analisado para indexação. Qualquer arquivo do Excel maior que esse limite não será analisado e o arquivo ou o email da mensagem com o anexo de arquivo será marcado como não-índicedo.  <br/> |
|Número máximo de anexos  <br/> |250  <br/> |O número máximo de arquivos anexados a uma mensagem de email que serão analisados para indexação. Se uma mensagem tiver mais de 250 anexos, os primeiros 250 anexos serão analisados e indexados, e a mensagem será marcada como parcialmente indexada porque tinha anexos adicionais que não foram analisados.  <br/> |
|Profundidade máxima do anexo  <br/> |30  <br/> |O número máximo de anexos aninhados analisados. Por exemplo, se uma mensagem de email tiver outra mensagem anexada a ela e a mensagem anexada tiver um documento do Word anexado, o documento do Word e a mensagem anexada serão indexados. Esse comportamento continuará para até 30 anexos aninhados.  <br/> |
|Número máximo de imagens anexadas  <br/> |0  <br/> |Uma imagem anexada a uma mensagem de email é ignorada pelo analisador e não indexada.  <br/> |
|Tempo máximo gasto na análise de um item  <br/> |30 segundos  <br/> |Um máximo de 30 segundos é gasto na análise de um item para indexação. Se o tempo de análise exceder 30 segundos, o item será marcado como parcialmente indexado.  <br/> |
|Saída máxima do analisador  <br/> |2 milhões de caracteres  <br/> |A quantidade máxima de saída de texto do analisador indexado. Por exemplo, se o analisador extraiu 8 milhões de caracteres de um documento, somente os primeiros 2 milhões de caracteres são indexados.  <br/> |
|Tokens de anotação máximo  <br/> |2 milhões  <br/> |Quando uma mensagem de email é indexada, cada palavra é anotada com diferentes instruções de processamento que especificam como essa palavra deve ser indexada. Cada conjunto de instruções de processamento é chamado de token de anotação. Para manter a qualidade do serviço no Office 365, há um limite de 2 milhões de tokens de anotação para uma mensagem de email.  <br/> |
|Tamanho máximo do corpo no índice  <br/> |67 milhões de caracteres  <br/> |O número total de caracteres no corpo de uma mensagem de email e todos os seus anexos. Quando uma mensagem de email é indexada, todo o texto no corpo da mensagem e em todos os anexos é concatenado em uma única cadeia de caracteres. O tamanho máximo dessa cadeia de caracteres indexada é de 67 milhões de caracteres.  <br/> |
|Máximo de tokens exclusivos no corpo  <br/> |1 milhão  <br/> |Conforme explicado anteriormente, os tokens são o resultado da extração de texto do conteúdo, da remoção da pontuação e dos espaços e da divisão em palavras (chamadas tokens) armazenadas no índice. Por exemplo, a frase  `"cat, mouse, bird, dog, dog"` contém 5 tokens. Mas apenas 4 desses são tokens exclusivos. Há um limite de 1 milhão de tokens exclusivos por mensagem de email, o que ajuda a impedir que o índice se mantenha muito grande com tokens aleatórios.  <br/> |

## <a name="more-information-about-partially-indexed-items"></a>Mais informações sobre itens parcialmente indexados

- Conforme mencionado anteriormente, como as propriedades da mensagem e do documento e seus metadados são indexados, uma pesquisa de palavra-chave pode retornar resultados se essa palavra-chave aparecer nos metadados indexados. No entanto, essa mesma pesquisa de palavra-chave poderá não retornar o mesmo item se a palavra-chave só aparece no conteúdo de um item com um tipo de arquivo sem suporte. Nesse caso, o item seria retornado como um item parcialmente indexado.

- Se um item parcialmente indexado for incluído nos resultados da pesquisa porque atendeu aos critérios de consulta de pesquisa (e não foi excluído), ele não será incluído como um item parcialmente indexado nas estatísticas de pesquisa estimadas. Além disso, ele não será incluído com itens parcialmente indexados quando você exportar resultados de pesquisa.

- Embora um tipo de arquivo seja suportado para indexação e seja indexado, pode haver erros de indexação ou pesquisa que fará com que um arquivo seja retornado como um item parcialmente indexado. Por exemplo, pesquisar um arquivo muito grande do Excel pode ser parcialmente bem-sucedido (porque os primeiros 4 MB são indexados), mas depois falha porque o limite de tamanho do arquivo foi excedido. Nesse caso, é possível que o mesmo arquivo seja retornado com os resultados da pesquisa e como um item parcialmente indexado.

- Arquivos criptografados com tecnologias de criptografia da [Microsoft](encryption.md) e anexados a uma mensagem de email que corresponde aos critérios de uma pesquisa podem ser visualizados e descriptografados quando exportados. No momento, os arquivos criptografados com tecnologias de criptografia da Microsoft (e armazenados no SharePoint ou no OneDrive for Business) são parcialmente indexados.

- As mensagens de email criptografadas com S/MIME são parcialmente indexadas. Isso inclui mensagens criptografadas com ou sem anexos de arquivo.

- As mensagens de email protegidas usando o Azure Rights Management são indexadas e serão incluídas nos resultados da pesquisa se corresponderem à consulta de pesquisa. As mensagens de email protegidas por direitos são descriptografadas e podem ser visualizadas e exportadas. Essa funcionalidade exige que você seja atribuído à função Descriptografar RMS, que é atribuída por padrão ao grupo de funções Do Gerenciador de Descobertas.

## <a name="see-also"></a>Confira também

[Investigando itens parcialmente indexados na Descoberta eDiscovery](investigating-partially-indexed-items-in-ediscovery.md)
