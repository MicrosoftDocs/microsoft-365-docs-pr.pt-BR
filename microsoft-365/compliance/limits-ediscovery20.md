---
title: Limites Descoberta Eletrônica Avançada
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
description: Saiba mais sobre os limites de caso, limites de indexação e limites de pesquisa em vigor para a solução Advanced eDiscovery no Microsoft 365.
ms.openlocfilehash: 335e40c6918fc33acc12082546b98f28c319c814
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52244571"
---
# <a name="limits-in-advanced-ediscovery"></a>Limites da Descoberta Eletrônica Avançada

Este artigo descreve os limites na solução Advanced eDiscovery no Microsoft 365.

## <a name="case-and-review-set-limits"></a>Limites de conjunto de caso e revisão

A tabela a seguir lista os limites de casos e conjuntos de revisão em Advanced eDiscovery.

| Descrição do limite | Limite |
|:-----|:-----|
|Número total de documentos que podem ser adicionados a uma ocorrência (para todos os conjuntos de revisão em um caso).  <br/> |3 milhões <br/> |
|Tamanho total do arquivo por conjunto de carga. Isso inclui o carregamento de não Office 365 em um conjunto de revisão.  <br/> |300 GB <br/> |
|Quantidade total de dados carregados em todos os conjuntos de revisão na organização por dia.<br/> |2 TB <br/> |
|Número máximo de conjuntos de carga por caso.  <br/> |200 <br/> |
|Número máximo de conjuntos de revisão por caso.  <br/> |20 <br/> |
|Número máximo de grupos de marca por caso.  <br/> |1000 <br/> |
|Número máximo de marcas por caso.  <br/> |1000 <br/> |
|Máximo de trabalhos simultâneos em sua organização para adicionar conteúdo a um conjunto de revisão. Esses trabalhos são nomeados **Adicionando dados a um conjunto de** revisão e são exibidos na guia **Trabalhos** em um caso.| 10 <sup>4</sup> |
|Máximo de trabalhos simultâneos para adicionar conteúdo a um conjunto de revisão por usuário. Esses trabalhos são nomeados **Adicionando dados a um conjunto de** revisão e são exibidos na guia **Trabalhos** em um caso. | 3 |
|||

## <a name="hold-limits"></a>Limites de espera

A tabela a seguir lista os limites de ressarcições associados a Advanced eDiscovery caso.

| Descrição do limite | Limite |
|:-----|:-----|
|Número máximo de caixas de correio em uma única caixa de espera. Esse limite inclui o total combinado de caixas de correio de usuário e as caixas de correio associadas Microsoft 365 grupos, Microsoft Teams e Yammer Grupos. <br/> |1.000  <br/> |
|Número máximo de sites em uma única espera de caso. Esse limite inclui o total combinado de sites OneDrive for Business, sites SharePoint e os sites associados a grupos Microsoft 365, Microsoft Teams e grupos Yammer.  <br/> |100  <br/> |

## <a name="indexing-limits"></a>Limites de indexação

A tabela a seguir lista os limites de indexação em Advanced eDiscovery.

| Descrição do limite | Limite |
|:-----|:-----|
|Número máximo de caracteres extraídos de um único arquivo.  <br/> |10 milhões<sup>1</sup> <br/> |
|Tamanho máximo de um único arquivo.   <br/> |100 MB<sup>1</sup> <br/> |
|Profundidade máxima de itens incorporados em um documento.  <br/> |25<sup>1</sup> <br/> |
|Tamanho máximo de arquivos processados pelo Reconhecimento Óptico de Caracteres (OCR).  <br/> |24 MB<sup>1</sup> <br/> 
|Número máximo de trabalhos de indexação por organização por dia. <br/> |10<sup>6</sup> <br/>|  
|||

## <a name="search-limits"></a>Limites da pesquisa

Os limites descritos nesta seção estão relacionados ao  uso da ferramenta de pesquisa na guia Pesquisas para coletar dados de uma ocorrência. Para obter mais informações, [consulte Coletar dados para uma ocorrência em Advanced eDiscovery](collecting-data-for-ediscovery.md).

| Descrição do limite | Limite |
|:-----|:-----|
|Número máximo de caixas de correio ou sites que podem ser pesquisados em uma única pesquisa. |Sem limite|
|Número máximo de pesquisas que podem ser executados ao mesmo tempo. |Sem limite |
|Número máximo de pesquisas que um único usuário pode iniciar ao mesmo tempo. |10  | 
|Número máximo de caracteres para uma consulta de pesquisa (incluindo operadores e condições). |10.000 &nbsp; <sup>2</sup>|
|Número máximo de caracteres para uma consulta de pesquisa para SharePoint e OneDrive for Business sites (incluindo operadores e condições). |10.000<br>4.000 com Curinga &nbsp; <sup>2</sup>|
|Número mínimo de caracteres alfa para caracteres curinga de prefixo; por exemplo, **um \* *_ ou _* set \***.|3 |  
|As variantes máximas retornadas ao usar o caractere curinga de prefixo para pesquisar uma frase exata ou ao usar um caractere curinga de prefixo e o **operador Boolean NEAR.** |10.000 &nbsp; <sup>3</sup>|
|Número máximo de itens por caixa de correio de usuário que são exibidos na página de visualização para pesquisas. Os itens mais novos são exibidos. |100|
|Número máximo de itens de todas as caixas de correio exibidas na página de visualização para pesquisas.|1.000|
|Número máximo de caixas de correio que podem ser visualizadas para resultados de pesquisa.  Se houver mais de 1.000 caixas de correio que contenham itens que corresponderem à consulta de pesquisa, apenas as 1.000 caixas de correio principais com a maioria dos resultados estarão disponíveis para visualização.|1.000|
|Número máximo de itens de sites SharePoint e OneDrive for Business exibidos na página de visualização para pesquisas. Os itens mais novos são exibidos. |200|
|Número máximo de sites SharePoint e OneDrive for Business que podem ser visualizados para resultados de pesquisa. Se houver mais de 200 sites que contenham itens que corresponderem à consulta de pesquisa, apenas os 200 sites principais com mais resultados estarão disponíveis para visualização.|200|
|Número máximo de itens por caixa de correio de pasta pública exibida na página de visualização para pesquisas. |100|
|Número máximo de itens encontrados em todos os itens de caixa de correio de pasta pública exibidos na página de visualização para pesquisas. |200|
|Número máximo de caixas de correio de pasta pública que podem ser visualizadas para resultados de pesquisa. Se houver mais de 500 caixas de correio de pasta pública que contenham itens que corresponderem à consulta de pesquisa, apenas as 500 caixas de correio mais importantes com a maioria dos resultados estarão disponíveis para visualização.|500|
|||

## <a name="search-times"></a>Tempos de pesquisa

A Microsoft coleta informações de desempenho para pesquisas executados por todas as organizações. Embora a complexidade da consulta de pesquisa possa afetar os tempos de pesquisa, o maior fator que afeta o tempo de duração das pesquisas é o número de caixas de correio pesquisadas. Embora a Microsoft não forneça um Contrato de Nível de Serviço para tempos de pesquisa, a tabela a seguir lista os tempos médios de pesquisa para pesquisas de coleção com base no número de caixas de correio incluídas na pesquisa.
  
  | Número de caixas de correio | Tempo médio de pesquisa |
  |:-----|:-----|
  |100  <br/> |30 segundos  <br/> |
  |1.000  <br/> |45 segundos  <br/> |
  |10.000  <br/> |4 minutos  <br/> |
  |25.000  <br/> |10 minutos  <br/> |
  |50.000  <br/> |20 minutos  <br/> |
  |100.000  <br/> |25 minutos  <br/> |
  |||

## <a name="viewer-limits"></a>Limites do visualizador

| Descrição do limite | Limite |
|:-----|:-----|
|Tamanho máximo de Excel arquivo que pode ser exibido no visualizador nativo.  <br/> |4 MB  <br/> |
|||

## <a name="export-limits---final-export-out-of-review-set"></a>Limites de exportação - Exportação final fora do Conjunto de Revisão

Os limites descritos nesta seção estão relacionados à exportação de documentos de um conjunto de revisão.

| Descrição do limite | Limite |
|:-----|:-----|
|Tamanho máximo de uma única exportação.|5 milhões de documentos ou 500 GB, o que for menor|
|Máximo de exportações simultâneas por conjunto de revisão. | 1 |
|||

## <a name="review-set-download-limits"></a>Revisar os limites de download definidos

| Descrição do limite | Limite |
|:-----|:-----|
|Tamanho total do arquivo ou número máximo de documentos baixados de um conjunto de revisão.  <br/> |3 MB ou 50 documentos <sup>5</sup>|
|||

<br/>
<br/>

> [!NOTE]
> <sup>1</sup> Qualquer item que exceda um único limite de arquivo será aparecer como um erro de processamento.
>
> <sup>2</sup> Ao pesquisar SharePoint e OneDrive for Business locais, os caracteres nas URLs dos sites que estão sendo pesquisados contam com esse limite. O número total de caracteres consiste em:<br>
> - Todos os caracteres nos campos Usuários e Filtros.
> - Todos os filtros de permissões de pesquisa que se aplicam ao usuário.
> - Os caracteres de qualquer propriedade de local na pesquisa; Isso inclui ExchangeLocation,PublicFolderLocation,SharPointLocation,ExchangeLocationExclusion,PublicFolderLocationExclusion,SharePointLocationExclusion, OneDriveLocationExclusion.
>   Por exemplo, incluindo todos os SharePoint e contas OneDrive na pesquisa contarão como seis caracteres, pois a palavra "ALL" aparecerá para o campo SharePointLocation e OneDriveLocation.
>
> <sup>3 Para</sup> consultas que não são frases (um valor de palavra-chave que não usa aspas duplas), usamos um índice de prefixo especial. Isso nos diz que uma palavra ocorre em um documento, mas não onde ela ocorre no documento. Para fazer uma consulta de frase (um valor de palavra-chave com aspas duplas), precisamos comparar a posição dentro do documento para as palavras na frase. Isso significa que não podemos usar o índice de prefixo para consultas de frase. Nesse caso, expandimos internamente a consulta com todas as palavras possíveis às quais o prefixo se expande; por exemplo, **time _ pode expandir para \* *_*"time OR timer OR times OR timex OR timeboxed OR ..."**. O limite de 10.000 é o número máximo de variantes que a palavra pode expandir, e não o número de documentos correspondentes à consulta. Não há limite superior para termos que não são frases.
>
> <sup>4</sup> Esse limite é compartilhado com a exportação de conteúdo em outras ferramentas de Descoberta Online. Isso significa que as exportações simultâneas na pesquisa de conteúdo e na Descoberta Principal (e adicionar conteúdo aos conjuntos de revisão Advanced eDiscovery) são aplicadas em relação a esse limite.
>
> <sup>5</sup> Esse limite se aplica ao download de documentos selecionados de um conjunto de revisão. Ele não se aplica à exportação de documentos de um conjunto de revisão. Para obter mais informações sobre como baixar e exportar documentos, consulte [Exportar dados de caso em Advanced eDiscovery](exporting-data-ediscover20.md).
>
> <sup>6</sup> Limites de indexação por organização por dia. Como solução alternativa, você pode selecionar  vários custodiantes na guia  Fontes de dados em um caso e clicar em Atualizar índice para evitar a criação de um trabalho de índice separado para cada custodiante. 
