---
title: Limites avançados de descoberta eletrônica
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
description: Saiba mais sobre os limites em vigor para a solução de descoberta eletrônica avançada no Microsoft 365. Isso inclui limites de caso, limites de indexação e limites de pesquisa ao usar a ferramenta de pesquisa para coletar dados de caso.
ms.openlocfilehash: 622d2669457a2a1e84909aadae9b653ca37684ce
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/20/2019
ms.locfileid: "37072714"
---
# <a name="limits-in-advanced-ediscovery"></a>Limites na descoberta eletrônica avançada

Este artigo descreve os limites da solução de descoberta eletrônica avançada no Microsoft 365.

## <a name="case-limits"></a>Limites de caso

A tabela a seguir lista os limites para casos na descoberta eletrônica avançada.

|**Descrição do limite**|**Limite**|
|:-----|:-----|
|Número total de documentos que podem ser adicionados a um caso (para todos os conjuntos de revisão em um caso).  <br/> |1 milhão  <br/> |
|Tamanho total do arquivo por conjunto de carga.  <br/> |100 GB  <br/> |
|Quantidade total de dados carregados em um caso por dia.<br/> |2 TB <br/> |
|Número máximo de conjuntos de cargas por caso.  <br/> |15 <br/> |
|Número máximo de conjuntos de revisão por caso.  <br/> |508 <br/> |
|||

## <a name="indexing-limits"></a>Limites de indexação

A tabela a seguir lista os limites de indexação na descoberta eletrônica avançada.

|**Descrição do limite**|**Limite**|
  |:-----|:-----|
  |Número máximo de caracteres extraídos de um único arquivo.  <br/> |10 milhões<sup>1</sup> <br/> |
  |Tamanho máximo de um único arquivo.   <br/> |100 MB<sup>1</sup> <br/> |
  |Profundidade máxima de itens incorporados em um documento.  <br/> |25<sup>1</sup> <br/> |
  |Tamanho máximo do arquivo processado pelo reconhecimento óptico de caracteres (OCR).  <br/> |24 MB<sup>1</sup> <br/> |  
|||

## <a name="search-limits"></a>Limites da pesquisa

Os limites descritos nesta seção estão relacionados ao uso da ferramenta de pesquisa na guia **pesquisas** para coletar dados de uma ocorrência. Para obter mais informações, consulte [coletar dados por um caso na descoberta eletrônica avançada](collecting-data-for-ediscovery.md).

|**Descrição do limite**|**Limite**|
|:-----|:-----|
|Número máximo de caixas de correio ou sites que podem ser pesquisados em uma única pesquisa.  <br/> |Sem limite  <br/> |
|Número máximo de pesquisas que podem ser executadas ao mesmo tempo.  <br/> |Sem limite  <br/> | 
|Número máximo de pesquisas que um único usuário pode iniciar ao mesmo tempo.  <br/> |10   <br/> | 
|Número máximo de caracteres para uma consulta de pesquisa (incluindo operadores e condições).  <br/> |**Caixas de correio**: 10.000<br/>**Sites**: 4.000 ao pesquisar todos os Sites ou 2.000 ao Pesquisar até 20 sites <sup>2</sup> <br/> |
|Número mínimo de caracteres alfabéticos para curingas de prefixo; por exemplo **,\* um** ou **conjunto\***. <br/> |3D  <br/> |  
|Máximo de variantes retornadas ao usar curinga de prefixo para pesquisar uma frase exata ou ao usar um caractere curinga de prefixo e o operador booleano **Near** ou **ONEAR** .  <br/> |10.000 <sup>3</sup> <br/> |
|Número máximo de itens por caixa de correio do usuário que são exibidos na página de visualização para pesquisas. Os itens mais recentes são exibidos.   <br/> |100  <br/> |
|Número máximo de itens de todas as caixas de correio exibidas na página de visualização para pesquisas.  <br/> |1,000  <br/> |
|Número máximo de caixas de correio que podem ser visualizadas para resultados de pesquisa.  Se houver mais de 1000 caixas de correio que contenham itens que correspondam à consulta de pesquisa, somente as primeiras caixas de correio de 1.000 com a maioria dos resultados estarão disponíveis para visualização.<br/> |1,000  <br/> |
|Número máximo de itens de sites do SharePoint e do OneDrive for Business exibidos na página de visualização para pesquisas. Os itens mais recentes são exibidos.  <br/> |200  <br/> |
|Número máximo de sites do SharePoint e do OneDrive for Business que podem ser visualizados nos resultados da pesquisa. Se houver mais de 200 sites que contenham itens que correspondam à consulta de pesquisa, somente os primeiros 200 sites com mais resultados estarão disponíveis para visualização.  <br/> |200  <br/> |
|Número máximo de itens por caixa de correio de pasta pública exibida na página de visualização para pesquisas.  <br/> |100  <br/> |
|Número máximo de itens encontrados em todos os itens de caixa de correio de pasta pública exibidos na página de visualização para pesquisas.  <br/> |200  <br/> |
|Número máximo de caixas de correio de pasta pública que podem ser visualizadas para resultados de pesquisa. Se houver mais de 500 caixas de correio de pasta pública que contenham itens que correspondam à consulta de pesquisa, somente as primeiras caixas de correio de 500 com a maioria dos resultados estarão disponíveis para visualização.  <br/> |500  <br/> |
|||

## <a name="viewer-limits"></a>Limites do Visualizador

|**Descrição do limite**|**Limite**|
  |:-----|:-----|
  |Tamanho máximo do arquivo do Excel que pode ser exibido no visualizador nativo.  <br/> |4 MB  <br/> |
|||

## <a name="review-set-download-limits"></a>Analisar limites de download de conjunto

|**Descrição do limite**|**Limite**|
|:-----|:-----|
|Tamanho total do arquivo ou número máximo de documentos baixados de um conjunto de revisão.  <br/> |3 MB ou 50 documentos <sup>4</sup>|
|||

<br/>
<br/>

> [!NOTE]
> <sup>1</sup> qualquer item que exceda um limite de arquivo único aparecerá como um erro de processamento.<br/>
> <sup>2</sup> ao pesquisar os locais do SharePoint e do onedrive for Business, os caracteres nas URLs dos sites que estão sendo pesquisados de acordo com esse limite.<br/>
> <sup>3</sup> para consultas que não são de frase (um valor de palavra-chave que não usa aspas duplas) usamos um índice de prefixo especial. Isso nos diz que uma palavra ocorre em um documento, mas não onde ele ocorre no documento. Para fazer uma consulta de frase (um valor de palavra-chave com aspas duplas), precisamos comparar a posição dentro do documento para as palavras da frase. Isso significa que não é possível usar o índice de prefixo para consultas de frase. Nesse caso, expandimos internamente a consulta com todas as palavras possíveis às quais o prefixo se expande; por exemplo, **o\* tempo** pode ser expandido para **"tempo ou temporizador ou horários, ou para a caixa de entrada ou para o relógio ou..."**. O limite de 10.000 é o número máximo de variantes que a palavra pode expandir, e não o número de documentos que correspondem à consulta. Não há um limite superior para termos de não frase.<br/>
> <sup>4</sup> este limite se aplica ao download de documentos selecionados a partir de um conjunto de revisão. Ela não se aplica à exportação de documentos a partir de um conjunto de revisão. Para obter mais informações sobre como baixar e exportar documentos, consulte [exportar dados de caso na descoberta eletrônica avançada](exporting-data-ediscover20.md). <br/>

