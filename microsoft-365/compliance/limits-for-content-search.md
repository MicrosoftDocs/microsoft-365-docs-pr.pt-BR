---
title: Limites para pesquisa de conteúdo e Descoberta Principal no centro de conformidade
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
description: Saiba mais sobre os limites em vigor para o recurso de pesquisa de conteúdo no centro de conformidade Microsoft 365, como o número máximo de pesquisas simultâneas. Esses limites de pesquisa também se aplicam às pesquisas associadas aos principais casos de Descoberta eDiscovery.
ms.openlocfilehash: e4cfc79d35b4dc6a22e8e7a872699d906b39a901
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52244315"
---
# <a name="limits-for-content-search"></a>Limites para pesquisa de conteúdo 
Vários limites são aplicados à ferramenta de pesquisa de conteúdo no centro Microsoft 365 conformidade. Isso inclui pesquisas executados  na página De pesquisa de conteúdo e pesquisas associadas a um caso de Descoberta De eDiscovery na página **Descoberta Principal.** Esses limites ajudam a manter a saúde e a qualidade dos serviços fornecidos às organizações. Também há limites relacionados à indexação de mensagens de email Exchange Online pesquisa. Você não pode modificar os limites da Pesquisa de Conteúdo ou indexação de email, mas deve estar ciente deles para que possa levar esses limites em consideração ao planejar, executar e solucionar problemas de pesquisas de conteúdo.
  
## <a name="search-limits"></a>Limites da pesquisa

A tabela a seguir lista os limites de pesquisa ao usar a ferramenta de pesquisa de conteúdo no centro de conformidade Microsoft 365 e para pesquisas associadas a um caso de Descoberta Principal de Descoberta Digital.
  
| Descrição do limite | Limite |
|:-----|:-----|
|O número máximo de caixas de correio ou sites que podem ser pesquisados em uma única pesquisa  <br/> |Sem limite <sup>1</sup> <br/> |
|O número máximo de pesquisas que podem ser executados ao mesmo tempo em sua organização.  <br/> |30  <br/> |
|O número máximo de pesquisas em toda a organização que podem ser executados ao mesmo tempo. <br/> |3  <br/> |
|O número máximo de pesquisas que um único usuário pode iniciar ao mesmo tempo. Esse limite é provavelmente atingido quando o usuário tenta iniciar várias pesquisas usando o comando **Get-ComplianceSearch \| Start-ComplianceSearch** no Centro de Conformidade e Segurança & do PowerShell.  <br/> |10   <br/> |
|O número máximo de itens por caixa de correio de usuário que são exibidos na página de visualização ao visualizar os resultados da Pesquisa de Conteúdo.  <br/> |100  <br/> |
|O número máximo de itens encontrados em todas as caixas de correio de usuário exibidas na página de visualização ao visualizar os resultados da pesquisa. Os itens mais novos são exibidos.  <br/> |1.000  <br/> |
|O número máximo de caixas de correio de usuário que podem ser visualizadas para resultados de pesquisa. Se houver mais de 1.000 caixas de correio que contenham conteúdo que corresponde à consulta de pesquisa, apenas as 1000 caixas de correio mais importantes com mais resultados de pesquisa estarão disponíveis para visualização.  <br/> |1.000  <br/> |
|O número máximo de itens encontrados em sites SharePoint e OneDrive for Business que são exibidos na página de visualização ao visualizar os resultados da pesquisa. Os itens mais novos são exibidos.  <br/> |200  <br/> |
|O número máximo de sites (em SharePoint e OneDrive for Business) que podem ser visualizados para resultados de pesquisa. Se houver mais de 200 sites totais que contenham conteúdo que corresponde à consulta de pesquisa, somente os 200 sites principais com mais resultados de pesquisa estarão disponíveis para visualização.  <br/> |200  <br/> |
|O número máximo de itens por caixa de correio de pasta pública exibida na página de visualização ao visualizar os resultados da pesquisa de conteúdo.  <br/> |100  <br/> |
|O número máximo de itens encontrados em todas as caixas de correio de pasta pública exibidas na página de visualização ao visualizar os resultados da pesquisa de conteúdo.  <br/> |200  <br/> |
|O número máximo de caixas de correio públicas que podem ser visualizadas para resultados de pesquisa. Se houver mais de 500 caixas de correio de pasta pública que contêm conteúdo que corresponde à consulta de pesquisa, somente as 500 caixas de correio de pasta pública mais importantes com a maioria dos resultados da pesquisa estarão disponíveis para visualização.  <br/> |500  <br/> |
|O número máximo de caracteres para a consulta de pesquisa (incluindo operadores e condições) para uma pesquisa.  <br/><br/> **Observação:** Esse limite entra em vigor depois que a consulta é expandida e inclui caracteres da consulta de palavra-chave, quaisquer filtros de permissões de pesquisa aplicados ao usuário e URLs de todos os locais do site. Isso significa que a consulta será expandida em cada uma das palavras-chave. Por exemplo, se uma consulta de pesquisa tiver 15 palavras-chave e parâmetros e condições adicionais, a consulta será expandida 15 vezes, cada uma com os outros parâmetros e condições na consulta. Portanto, mesmo que o número de caracteres na consulta de pesquisa possa estar abaixo do limite, é a consulta expandida que pode contribuir para exceder esse limite.  <br/> |**Caixas de correio:** 10.000  <br/> **Sites:** 4.000 ao pesquisar todos os sites ou 2.000 ao pesquisar até 20 sites <sup>2</sup> <br/> |
|Número máximo de variantes retornadas ao usar um caractere curinga de prefixo para pesquisar uma frase exata em uma consulta de pesquisa ou ao usar um caractere curinga de prefixo e o **operador booleano NEAR.**  <br/> |10.000 <sup>3</sup> <br/> |
|O número mínimo de caracteres alfa para caracteres curinga de prefixo; por exemplo,  `time*`  `one*` , ou  `set*` .  <br/> |3  <br/> |
|O número máximo de caixas de correio em uma pesquisa em que você pode excluir itens fazendo uma ação de "pesquisa e limpeza" (usando o comando **New-ComplianceSearchAction -Purge).** Se a pesquisa que você está fazendo uma ação de limpeza tiver mais caixas de correio de origem do que esse limite, a ação de limpeza falhará. Para obter mais informações sobre pesquisa e limpeza, consulte Pesquisar e excluir mensagens [de email em sua organização](search-for-and-delete-messages-in-your-organization.md).  <br/> |50.000  <br/> |
|O número máximo de locais em uma pesquisa de onde você pode exportar itens. Se a pesquisa que você está exportando tiver mais locais do que esse limite, a exportação falhará. Para obter mais informações, consulte [Exportar resultados da pesquisa de conteúdo](export-search-results.md).  <br/> |100.000  <br/> |
|||

> [!NOTE]
> <sup>1</sup> Embora você possa pesquisar um número ilimitado de caixas de correio em uma única pesquisa, você só pode baixar os resultados de pesquisa exportados de no máximo 100.000 caixas de correio usando a Ferramenta de Exportação de Descoberta Eletrônico no centro de conformidade do Microsoft 365. <br/><br/> <sup>2</sup> Ao pesquisar SharePoint e OneDrive for Business locais, os caracteres nas URLs dos sites que estão sendo pesquisados são contados em relação a esse limite. <br/><br/> <sup>3 Para</sup> consultas que não são frases (um valor de palavra-chave que não usa aspas duplas), usamos um índice de prefixo especial. Isso nos diz que uma palavra ocorre em um documento, mas não onde ela ocorre no documento. Para fazer uma consulta de frase (um valor de palavra-chave com aspas duplas), precisamos comparar a posição dentro do documento para as palavras na frase. Isso significa que não podemos usar o índice de prefixo para consultas de frase. Nesse caso, expandimos internamente a consulta com todas as palavras possíveis às quais o prefixo se expande; por exemplo,  `"time*"` pode expandir para  `"time OR timer OR times OR timex OR timeboxed OR …"` . 10.000 é o número máximo de variantes que a palavra pode expandir, não o número de documentos correspondentes à consulta. Não há limite superior para termos que não são frases. 
  
## <a name="search-times"></a>Tempos de pesquisa
A Microsoft coleta informações de desempenho para pesquisas executados por todas as organizações. Embora a complexidade da consulta de pesquisa possa afetar os tempos de pesquisa, o maior fator que afeta o tempo de duração das pesquisas é o número de caixas de correio pesquisadas. Embora a Microsoft não forneça um Contrato de Nível de Serviço para tempos de pesquisa, a tabela a seguir lista os tempos médios de pesquisa para pesquisas de coleção com base no número de caixas de correio incluídas na pesquisa.

|Número de caixas de correio|Tempo médio de pesquisa|
|:-----|:-----|
|100|30 segundos|
|1.000|45 segundos|
|10.000|4 minutos|
|25.000|10 minutos|
|50.000|20 minutos|
|100.000|25 minutos|
|||

## <a name="export-limits"></a>Limites de exportação
A tabela a seguir lista os limites ao exportar os resultados de uma pesquisa de conteúdo. Esses limites também se aplicam quando você exporta conteúdo de um caso de Descoberta Principal.

|Descrição do limite|Limite|
|:-----|:-----|
|Quantidade máxima de dados exportáveis de uma única pesquisa  <br/><br/> **Observação:** Se os resultados da pesquisa são maiores que 2 TB, considere usar intervalos de datas ou outros tipos de filtros para diminuir o tamanho total dos resultados da pesquisa. <br/>  |2 TB  <br/> | 
|Máximo que uma organização pode exportar em um único dia <br/><br/> **Observação:** Esse limite é redefinido diariamente às 12:00 UTC <br/> |2 TB <br/> |
|Máximo de exportações simultâneas que podem ser usadas ao mesmo tempo em sua organização <br/><br/> **Observação:** Executar um **Relatório Somente exportação** contagens em relação ao total de exportações simultâneas para sua organização. Se três usuários estão executando 3 exportações cada, apenas um outro export pode ser executado. Se ele está exportando um relatório ou resultados de pesquisa, nenhuma outra exportação pode ser executada até que um seja concluído.   <br/> |10  <br/> |
|Exportações máximas que um único usuário pode executar a qualquer momento <br/> |3 <br/> |
|Número máximo de caixas de correio para resultados de pesquisa que podem ser baixadas usando a Ferramenta de Exportação de Descoberta Eletrônico <br/>| 100.000 <br/>|
|Tamanho máximo do arquivo PST que pode ser exportado <br/><br/> **Observação:** Se os resultados da pesquisa da caixa de correio de um usuário são maiores do que 10 GB, os resultados da pesquisa para a caixa de correio serão exportados em dois (ou mais) arquivos PST separados. Se você optar por exportar todos os resultados da pesquisa em um único arquivo PST, o arquivo PST será spiltado em arquivos PST adicionais se o tamanho total dos resultados da pesquisa for maior que 10 GB. Se você quiser alterar esse tamanho padrão, poderá editar o registro Windows no computador que você usa para exportar os resultados da pesquisa. Consulte [Alterar o tamanho dos arquivos PST ao exportar](change-the-size-of-pst-files-when-exporting-results.md)resultados da pesquisa de Descoberta e. Os resultados da pesquisa de uma caixa de correio específica não serão divididos entre vários arquivos PST, a menos que o conteúdo de uma única caixa de correio seja maior que 10 GB. Se você optou por exportar os resultados da pesquisa em um arquivo PST para o qual contém todas as mensagens em uma única pasta e os resultados da pesquisa são maiores que 10 GB, os itens ainda são organizados em ordem cronológica, para que eles sejam lançados em arquivos PST adicionais com base na data enviada.<br/> | 10 GB <br/> |
|Taxa na qual os resultados da pesquisa de caixas de correio e sites são carregados em um local do Azure Armazenamento fornecido pela Microsoft. |Máximo de 2 GB por hora|
|||

## <a name="indexing-limits-for-email-messages"></a>Limites de indexação para mensagens de email

A tabela a seguir descreve os limites de indexação que podem resultar em uma mensagem de email sendo retornada como um item não indexado ou um item parcialmente indexado nos resultados de uma pesquisa de conteúdo.
  
| Limite de indexação | Valor máximo | Descrição |
|:-----|:-----|:-----|
|Tamanho máximo do anexo|150 MB  <br/> |O tamanho máximo de um anexo de email que será analisado para indexação. Qualquer anexo maior que esse limite não será analisado para indexação, e a mensagem com o anexo será marcada como parcialmente indexada.  <br/> <br/>**Observação:** A análise é o processo em que o serviço de indexação extrai texto do anexo, remove caracteres desnecessários, como pontuação e espaços, e divide o texto em palavras (em um processo chamado tokenização), que são armazenados no índice.           |
|Número máximo de anexos  <br/> |250  <br/> |O número máximo de arquivos anexados a uma mensagem de email que será analisado para indexação. Se uma mensagem tiver mais de 250 anexos, os primeiros 250 anexos serão analisados e indexados, e a mensagem será marcada como parcialmente indexada porque tinha anexos adicionais que não foram analisados.  <br/> |
|Profundidade máxima do anexo  <br/> |30  <br/> |O número máximo de anexos aninhados analisados. Por exemplo, se uma mensagem de email tiver outra mensagem anexada a ela e a mensagem anexada tiver um documento do Word anexado, o documento do Word e a mensagem anexada serão indexados. Esse comportamento continuará para até 30 anexos aninhados.  <br/> |
|Número máximo de imagens anexadas  <br/> |0  <br/> |Uma imagem anexada a uma mensagem de email é ignorada pelo analisador e não indexada.  <br/> |
|Tempo máximo gasto para analisar um item  <br/> |30 segundos  <br/> |Um máximo de 30 segundos é gasto ao analisar um item para indexação. Se o tempo de análise exceder 30 segundos, o item será marcado como parcialmente indexado.  <br/> |
|Saída máxima do analisador  <br/> |2 milhões de caracteres  <br/> |A quantidade máxima de saída de texto do analisador indexado. Por exemplo, se o analisador extraiu 8 milhões de caracteres de um documento, apenas os primeiros 2 milhões de caracteres serão indexados.  <br/> |
|Tokens máximos de anotação  <br/> |2 milhões  <br/> |Quando uma mensagem de email é indexada, cada palavra é anotada com instruções de processamento diferentes que especificam como essa palavra deve ser indexada. Cada conjunto de instruções de processamento é chamado de token de anotação. Para manter a qualidade do serviço Office 365, há um limite de 2 milhões de tokens de anotação para uma mensagem de email.  <br/> |
|Tamanho máximo do corpo no índice  <br/> |67 milhões de caracteres  <br/> |O número total de caracteres no corpo de uma mensagem de email e todos os seus anexos. Quando uma mensagem de email é indexada, todo o texto no corpo da mensagem e em todos os anexos é concatenado em uma única cadeia de caracteres. O tamanho máximo dessa cadeia de caracteres indexada é de 67 milhões de caracteres.  <br/> |
|Máximo de tokens exclusivos no corpo  <br/> |1 milhão  <br/> |Conforme explicado anteriormente, os tokens são o resultado da extração de texto do conteúdo, da remoção da pontuação e dos espaços e da divisão em palavras (chamadas tokens) armazenadas no índice. Por exemplo, a frase  `"cat, mouse, bird, dog, dog"` contém 5 tokens. Mas apenas 4 deles são tokens exclusivos. Há um limite de 1 milhão de tokens exclusivos por mensagem de email, o que ajuda a impedir que o índice seja muito grande com tokens aleatórios.  <br/> |
|||
  
## <a name="more-information"></a>Mais informações

Há limites adicionais relacionados a diferentes aspectos da pesquisa de conteúdo, como indexação de conteúdo. Para obter mais informações sobre esses limites, consulte os seguintes tópicos:

- [Itens parcialmente indexados na Pesquisa de Conteúdo](partially-indexed-items-in-content-search.md)

- [Investigando itens parcialmente indexados na Descoberta eDiscovery](investigating-partially-indexed-items-in-ediscovery.md)

- [Limites de pesquisa para SharePoint Online](/sharepoint/search-limits)

Para obter informações sobre pesquisas de conteúdo, consulte:
  
- [Pesquisa de conteúdo em Microsoft 365](content-search.md)

- [Pesquisar conteúdo em um caso core de Descoberta eDiscovery](search-for-content-in-core-ediscovery.md)

- [Consultas de palavra-chave e condições de pesquisa para pesquisa de conteúdo](keyword-queries-and-search-conditions.md)

Para limites de caso relacionados à Descoberta Básica e Advanced eDiscovery, consulte:

- [Limites na Descoberta Principal da Descoberta](limits-core-ediscovery.md)

- [Limites da Descoberta Eletrônica Avançada](limits-ediscovery20.md)
