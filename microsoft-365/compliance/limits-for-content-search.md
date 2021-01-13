---
title: Limites para a pesquisa de conteúdo e a Descoberta Principal no centro de conformidade
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 78fe3147-1979-4c41-83bb-aeccf244368d
description: Saiba mais sobre os limites em vigor para o recurso de pesquisa de conteúdo no centro de conformidade do Microsoft 365, como o número máximo de pesquisas simultâneas. Esses limites de pesquisa também se aplicam às pesquisas associadas aos principais casos de Descoberta eDiscovery.
ms.openlocfilehash: 23751fd62b2d96400d8184faa0d8d74b06b68906
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/13/2021
ms.locfileid: "49840488"
---
# <a name="limits-for-content-search"></a>Limites da pesquisa de conteúdo 
Vários limites são aplicados à ferramenta pesquisa de conteúdo no centro de conformidade do Microsoft 365. Isso inclui pesquisas que  são executados na página Pesquisa de conteúdo e pesquisas associadas a um caso de Descoberta eDiscovery na página **Principal descoberta eDiscovery.** Esses limites ajudam a manter a saúde e a qualidade dos serviços fornecidos às organizações. Também há limites relacionados à indexação de mensagens de email no Exchange Online para pesquisa. Não é possível modificar os limites da Pesquisa de Conteúdo ou da indexação de email, mas você deve estar ciente deles para que possa levar esses limites em consideração ao planejar, executar e solucionar problemas de pesquisas de conteúdo.
  
## <a name="search-limits"></a>Limites da pesquisa

A tabela a seguir lista os limites de pesquisa ao usar a ferramenta de pesquisa de conteúdo no centro de conformidade do Microsoft 365 e para pesquisas que estão associadas a um caso de Descoberta Online Principal.
  
| Descrição do limite | Limite |
|:-----|:-----|
|O número máximo de caixas de correio ou sites que podem ser pesquisados em uma única pesquisa  <br/> |Sem limite <sup>1</sup> <br/> |
|O número máximo de pesquisas que podem ser executados ao mesmo tempo em sua organização.  <br/> |30  <br/> |
|O número máximo de pesquisas que um único usuário pode iniciar ao mesmo tempo. Esse limite é mais provável quando o usuário tenta iniciar várias pesquisas usando o comando **Get-ComplianceSearch \| Start-ComplianceSear & ch** no PowerShell do Centro de Conformidade e Segurança.  <br/> |10   <br/> |
|O número máximo de itens por caixa de correio de usuário que são exibidos na página de visualização ao visualizar os resultados da Pesquisa de Conteúdo.  <br/> |100  <br/> |
|O número máximo de itens encontrados em todas as caixas de correio de usuário exibidas na página de visualização ao visualizar os resultados da pesquisa. Os itens mais novos são exibidos.  <br/> |1.000  <br/> |
|O número máximo de caixas de correio de usuário que podem ser visualizadas para resultados de pesquisa. Se houver mais de 1.000 caixas de correio que contenham conteúdo que corresponde à consulta de pesquisa, somente as 1.000 caixas de correio com mais resultados de pesquisa estarão disponíveis para visualização.  <br/> |1.000  <br/> |
|O número máximo de itens encontrados nos sites do SharePoint e do OneDrive for Business que são exibidos na página de visualização ao visualizar os resultados da pesquisa. Os itens mais novos são exibidos.  <br/> |200  <br/> |
|O número máximo de sites (no SharePoint e no OneDrive for Business) que podem ser visualizados para resultados de pesquisa. Se houver mais de 200 sites no total que contenham conteúdo que corresponde à consulta de pesquisa, somente os 200 sites com mais resultados de pesquisa estarão disponíveis para visualização.  <br/> |200  <br/> |
|O número máximo de itens por caixa de correio de pasta pública que são exibidos na página de visualização ao visualizar os resultados da pesquisa de conteúdo.  <br/> |100  <br/> |
|O número máximo de itens encontrados em todas as caixas de correio de pasta pública que são exibidos na página de visualização ao visualizar os resultados da pesquisa de conteúdo.  <br/> |200  <br/> |
|O número máximo de caixas de correio públicas que podem ser visualizadas para resultados de pesquisa. Se houver mais de 500 caixas de correio de pasta pública que contenham conteúdo que corresponde à consulta de pesquisa, somente as 500 caixas de correio de pasta pública com mais resultados de pesquisa estarão disponíveis para visualização.  <br/> |500  <br/> |
|O número máximo de caracteres para a consulta de pesquisa (incluindo operadores e condições) de uma pesquisa.  <br/><br/> **Observação:** Esse limite entra em vigor depois que a consulta é expandida, o que significa que a consulta será expandida em relação a cada uma das palavras-chave. Por exemplo, se uma consulta de pesquisa tiver 15 palavras-chave e parâmetros e condições adicionais, a consulta será expandida 15 vezes, cada uma com os outros parâmetros e condições na consulta. Portanto, mesmo que o número de caracteres na consulta de pesquisa possa estar abaixo do limite, é a consulta expandida que pode contribuir para exceder esse limite.  <br/> |**Caixas de correio:** 10.000  <br/> **Sites:** 4.000 ao pesquisar em todos os sites ou 2.000 ao pesquisar até 20 sites <sup>2</sup> <br/> |
|Número máximo de variantes retornadas ao usar um caractere curinga de prefixo para pesquisar uma frase exata em uma consulta de pesquisa ou ao usar um caractere curinga de prefixo e o operador booleano **NEAR.**  <br/> |10.000 <sup>3</sup> <br/> |
|O número mínimo de caracteres alfa para caracteres curinga de prefixo; por exemplo,  `time*`  `one*` , ou  `set*` .  <br/> |3   <br/> |
|O número máximo de caixas de correio em uma pesquisa em que você pode excluir itens realizando uma ação de "pesquisar e limpar" (usando o comando **New-ComplianceSearchAction -Purge).** Se a pesquisa que você está realizando uma ação de limpeza tiver mais caixas de correio de origem do que esse limite, a ação de limpeza falhará. Para obter mais informações sobre pesquisa e limpeza, consulte [Pesquisar e excluir mensagens de email em sua organização.](search-for-and-delete-messages-in-your-organization.md)  <br/> |50.000  <br/> |
|O número máximo de locais em uma pesquisa dos que você pode exportar itens. Se a pesquisa que você está exportando tiver mais locais do que esse limite, a exportação falhará. Para obter mais informações, consulte [Exportar resultados de pesquisa de conteúdo.](export-search-results.md)  <br/> |100.000  <br/> |
|||

> [!NOTE]
> <sup>1</sup> Embora seja possível pesquisar um número ilimitado de caixas de correio em uma única pesquisa, você só pode baixar os resultados de pesquisa exportados de um máximo de 100.000 caixas de correio usando a Ferramenta de Exportação de Descoberta Eletrônico no centro de conformidade do Microsoft 365. Para baixar os resultados da pesquisa de mais de 100.000 caixas de correio &, você precisa usar o PowerShell do Centro de Conformidade e Segurança. Para obter mais informações e um script de exemplo, consulte Exportando resultados de mais de [100.000 caixas de correio.](export-search-results.md#exporting-results-from-more-than-100000-mailboxes) <br/><br/> <sup>2</sup> Ao pesquisar locais do SharePoint e do OneDrive for Business, os caracteres nas URLs dos sites que estão sendo pesquisados são contados em relação a esse limite. <br/><br/> <sup>3</sup> Para consultas sem frase (um valor de palavra-chave que não usa aspas duplas), usamos um índice de prefixo especial. Isso nos informa que uma palavra ocorre em um documento, mas não onde ela ocorre no documento. Para fazer uma consulta de frase (um valor de palavra-chave com aspas duplas), precisamos comparar a posição no documento com as palavras na frase. Isso significa que não podemos usar o índice de prefixo para consultas de frase. Nesse caso, expandimos internamente a consulta com todas as palavras possíveis para as quais o prefixo se expande; por exemplo,  `"time*"` pode expandir para  `"time OR timer OR times OR timex OR timeboxed OR …"` . 10.000 é o número máximo de variantes para as que a palavra pode se expandir, não o número de documentos correspondentes à consulta. Não há limite superior para termos sem frase. 
  
## <a name="export-limits"></a>Limites de exportação
A tabela a seguir lista os limites ao exportar os resultados de uma pesquisa de conteúdo. Esses limites também se aplicam quando você exporta o conteúdo de um caso de Descoberta e Principal.

|Descrição do limite|Limite|
|:-----|:-----|
|Quantidade máxima de dados exportáveis de uma única pesquisa  <br/><br/> **Observação:** Se os resultados da pesquisa são maiores do que 2 TB, considere usar intervalos de datas ou outros tipos de filtros para diminuir o tamanho total dos resultados da pesquisa. <br/>  |2 TB  <br/> | 
|Máximo que uma organização pode exportar em um único dia <br/><br/> **Observação:** Esse limite é redefinido diariamente às 12:00 UTC <br/> |2 TB <br/> |
|Máximo de exportações simultâneas que podem ser usadas ao mesmo tempo em sua organização <br/><br/> **Observação:** A execução **de uma exportação Somente** Relatório conta contra o total de exportações simultâneas para sua organização. Se três usuários estão executando 3 exportações cada, apenas uma outra exportação pode ser executada. Se ele está exportando um relatório ou resultados de pesquisa, nenhuma outra exportação pode ser executada até que uma seja concluída.   <br/> |10  <br/> |
|Exportações máximas que um único usuário pode executar a qualquer momento <br/> |3  <br/> |
|Número máximo de caixas de correio para resultados de pesquisa que podem ser baixados usando a Ferramenta de Exportação de Descoberta Eletrônico <br/><br/> **Observação:** Para baixar os resultados da pesquisa de mais de 100.000 caixas de correio &, você precisa usar o PowerShell do Centro de Conformidade e Segurança. Para obter instruções, [consulte Exportando resultados de mais de 100.000 caixas de correio.](export-search-results.md#exporting-results-from-more-than-100000-mailboxes) <br/> | 100.000 <br/>|
|Tamanho máximo do arquivo PST que pode ser exportado <br/><br/> **Observação:** Se os resultados da pesquisa da caixa de correio de um usuário são maiores do que 10 GB, os resultados da pesquisa para a caixa de correio serão exportados em dois (ou mais) arquivos PST separados. Se você optar por exportar todos os resultados da pesquisa em um único arquivo PST, o arquivo PST será spilt em arquivos PST adicionais se o tamanho total dos resultados da pesquisa for maior do que 10 GB. Se quiser alterar esse tamanho padrão, você pode editar o Registro do Windows no computador usado para exportar os resultados da pesquisa. Consulte [Alterar o tamanho dos arquivos PST ao exportar resultados de pesquisa de Descobertas eDiscovery.](change-the-size-of-pst-files-when-exporting-results.md) Os resultados da pesquisa de uma caixa de correio específica não serão divididos entre vários arquivos PST, a menos que o conteúdo de uma única caixa de correio seja maior que 10 GB. Se você optar por exportar os resultados da pesquisa em um arquivo PST para que contenha todas as mensagens em uma única pasta e os resultados da pesquisa são maiores do que 10 GB, os itens ainda são organizados em ordem cronológica, portanto, eles serão spilt em arquivos PST adicionais com base na data enviada.<br/> | 10 GB <br/> |
|Taxa na qual os resultados da pesquisa de caixas de correio e sites são carregados em um local de armazenamento do Azure fornecido pela Microsoft. |Máximo de 2 GB por hora|
|||

## <a name="indexing-limits-for-email-messages"></a>Limites de indexação para mensagens de email

A tabela a seguir descreve os limites de indexação que podem resultar no retorno de uma mensagem de email como um item não indexado ou um item parcialmente indexado nos resultados de uma pesquisa de conteúdo.
  
| Limite de indexação | Valor máximo | Descrição |
|:-----|:-----|:-----|
|Tamanho máximo do anexo|150 MB  <br/> |O tamanho máximo de um anexo de email que será analisado para indexação. Qualquer anexo maior do que esse limite não será analisado para indexação, e a mensagem com o anexo será marcada como parcialmente indexada.  <br/> <br/>**Observação:** Análise é o processo em que o serviço de indexação extrai texto do anexo, remove caracteres desnecessários, como pontuação e espaços, e divide o texto em palavras (em um processo chamado tokenização), que são armazenadas no índice.           |
|Número máximo de anexos  <br/> |250  <br/> |O número máximo de arquivos anexados a uma mensagem de email que serão analisados para indexação. Se uma mensagem tiver mais de 250 anexos, os primeiros 250 anexos serão analisados e indexados, e a mensagem será marcada como parcialmente indexada porque tinha anexos adicionais que não foram analisados.  <br/> |
|Profundidade máxima do anexo  <br/> |30  <br/> |O número máximo de anexos aninhados analisados. Por exemplo, se uma mensagem de email tiver outra mensagem anexada a ela e a mensagem anexada tiver um documento do Word anexado, o documento do Word e a mensagem anexada serão indexados. Esse comportamento continuará para até 30 anexos aninhados.  <br/> |
|Número máximo de imagens anexadas  <br/> |0  <br/> |Uma imagem anexada a uma mensagem de email é ignorada pelo analisador e não indexada.  <br/> |
|Tempo máximo gasto na análise de um item  <br/> |30 segundos  <br/> |Um máximo de 30 segundos é gasto na análise de um item para indexação. Se o tempo de análise exceder 30 segundos, o item será marcado como parcialmente indexado.  <br/> |
|Saída máxima do analisador  <br/> |2 milhões de caracteres  <br/> |A quantidade máxima de saída de texto do analisador indexado. Por exemplo, se o analisador extraiu 8 milhões de caracteres de um documento, somente os primeiros 2 milhões de caracteres são indexados.  <br/> |
|Tokens de anotação máximo  <br/> |2 milhões  <br/> |Quando uma mensagem de email é indexada, cada palavra é anotada com diferentes instruções de processamento que especificam como essa palavra deve ser indexada. Cada conjunto de instruções de processamento é chamado de token de anotação. Para manter a qualidade do serviço no Office 365, há um limite de 2 milhões de tokens de anotação para uma mensagem de email.  <br/> |
|Tamanho máximo do corpo no índice  <br/> |67 milhões de caracteres  <br/> |O número total de caracteres no corpo de uma mensagem de email e todos os seus anexos. Quando uma mensagem de email é indexada, todo o texto no corpo da mensagem e em todos os anexos é concatenado em uma única cadeia de caracteres. O tamanho máximo dessa cadeia de caracteres indexada é de 67 milhões de caracteres.  <br/> |
|Máximo de tokens exclusivos no corpo  <br/> |1 milhão  <br/> |Conforme explicado anteriormente, os tokens são o resultado da extração de texto do conteúdo, da remoção da pontuação e dos espaços e da divisão em palavras (chamadas tokens) armazenadas no índice. Por exemplo, a frase  `"cat, mouse, bird, dog, dog"` contém 5 tokens. Mas apenas 4 desses são tokens exclusivos. Há um limite de 1 milhão de tokens exclusivos por mensagem de email, o que ajuda a impedir que o índice se mantenha muito grande com tokens aleatórios.  <br/> |
|||
  
## <a name="more-information"></a>Mais informações

Há limites adicionais relacionados a diferentes aspectos da pesquisa de conteúdo, como a indexação de conteúdo. Para obter mais informações sobre esses limites, consulte os seguintes tópicos:

- [Itens parcialmente indexados na Pesquisa de Conteúdo](partially-indexed-items-in-content-search.md)

- [Investigando itens parcialmente indexados na Descoberta eDiscovery](investigating-partially-indexed-items-in-ediscovery.md)

- [Limites de pesquisa para o SharePoint Online](https://docs.microsoft.com/sharepoint/search-limits)

Para obter informações sobre pesquisas de conteúdo, consulte:
  
- [Pesquisa de conteúdo no Microsoft 365](content-search.md)

- [Pesquisar conteúdo em um caso principal de Descoberta eDiscovery](search-for-content-in-core-ediscovery.md)

- [Consultas de palavra-chave e condições de pesquisa para pesquisa de conteúdo](keyword-queries-and-search-conditions.md)

Para limites de caso relacionados à Descoberta Principal e Descoberta Avançada, consulte:

- [Limites na Descoberta eDiscovery Principal](limits-core-ediscovery.md)

- [Limites da Descoberta Eletrônica Avançada](limits-ediscovery20.md)
