---
title: Estatísticas e relatórios de coleta
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
ms.reviewer: nickrob
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Saiba como acessar e usar estatísticas e relatórios para coleções de rascunho e coleções que foram comprometidas com um conjunto de revisão em Advanced eDiscovery.
ms.openlocfilehash: 5edbd4a3b7212e027c777ed6ce5284f4e9cf595c
ms.sourcegitcommit: 8f1721de52dbe3a12c11a0fa5ed0ef5972ca8196
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/17/2021
ms.locfileid: "50838834"
---
# <a name="collection-statistics-and-reports-in-advanced-ediscovery"></a>Estatísticas de coleção e relatórios em Advanced eDiscovery

Depois de criar um conjunto de rascunhos, você pode exibir estatísticas nos itens recuperados, como os locais de conteúdo que contêm a maioria dos itens que corresponderam aos critérios de pesquisa e ao número de itens retornados pela consulta de pesquisa. Você também pode visualizar um subconjunto dos resultados.

Quando você identificar o conjunto de documentos que deseja examinar mais, você pode adicionar os resultados da pesquisa a um conjunto de revisão para coletar e processar.

## <a name="statistics-and-reports-for-draft-collections"></a>Estatísticas e relatórios para coleções de rascunho

Esta seção descreve as estatísticas disponíveis para coleções de rascunho. Essas estatísticas estão disponíveis na guia **Estatísticas de** pesquisa na página de sobrevoo de um conjunto de rascunhos.

### <a name="collection-estimates"></a>Estimativas de coleção

Esta seção exibe um resumo gráfico dos itens estimados retornados pela coleção. Isso indica o número de itens que corresponderem aos critérios de pesquisa da coleção. Essas informações dão uma ideia do número estimado de itens retornados pela coleção.

![Estimativas de coleção para uma coleção de rascunho](../media/AeDCollectionEstimates.png)

- **Itens estimados por locais**: O número total de itens estimados retornados pela coleção. O número específico de itens localizados em caixas de correio e localizados em sites também é exibido.

- **Locais estimados com hits**: O número total de locais de conteúdo que contêm itens retornados pela coleção. O número específico de caixas de correio e locais de site também é exibido.

- **Volume de dados por local (em MB)**: o tamanho total de todos os itens estimados retornados pela coleção. O tamanho específico de itens de caixa de correio e itens de site também é exibido.

### <a name="condition-report"></a>Relatório de condição

Esta seção exibe estatísticas sobre a consulta de pesquisa de coleção e o número de itens estimados que corresponderam a diferentes partes da consulta de pesquisa. Você pode usar essas estatísticas para analisar o número de itens que corresponderem a cada componente da consulta de pesquisa. Isso pode ajudá-lo a refinar os critérios de pesquisa para a coleção e, se necessário, restringir o escopo da coleção.

- **Tipo de** local : o tipo de local de conteúdo ao qual as estatísticas de consulta são aplicáveis. O valor de **Exchange** indica um local de caixa de correio; um valor de **SharePoint** indica um local do site.

- **Parte**: A parte da consulta de pesquisa à que as estatísticas são aplicáveis. **O** primário indica toda a consulta de pesquisa. **A** palavra-chave indica que as estatísticas na linha são para uma palavra-chave específica. Se você usar uma lista de palavras-chave quando para a consulta de pesquisa na coleção, as estatísticas de cada componente da consulta serão incluídas nesta tabela.

- **Condição**: o componente real (palavra-chave ou condição) da consulta de pesquisa que foi executado para a coleção de rascunho que retornou as estatísticas exibidas na linha correspondente.

- **Locais com hits**: o número dos locais  de conteúdo (especificados pela coluna Tipo de local) que contêm itens que corresponderem à consulta primária ou de palavra-chave listada na **coluna** Condição.

- **Itens**: o número de itens (do local de conteúdo especificado) que combinam com a consulta listada na **coluna Condição.** Conforme explicado anteriormente, se um item contiver várias instâncias de uma palavra-chave que está sendo pesquisada, ele só será contado uma vez nesta coluna.

- **Tamanho (MB)**: o tamanho total de todos os itens encontrados (no local de conteúdo especificado) que corresponderem à consulta de pesquisa na **coluna** Condição.

### <a name="top-locations"></a>Principais locais

Esta seção exibe estatísticas sobre os locais de conteúdo específicos com a maioria dos itens retornados pela coleção.

- O nome do nome do local (o endereço de email das caixas de correio e a URL para sites).

- Tipo de local (uma caixa de correio ou site).

- Número estimado de itens no local de conteúdo retornado pela coleção.

- O tamanho total dos itens estimados em cada local de conteúdo.

## <a name="statistics-and-reports-for-committed-collections"></a>Estatísticas e relatórios para coleções comprometidas

Esta seção descreve as estatísticas que estão disponíveis depois que você confirma uma coleção em um conjunto de revisão, incluindo o número real de itens adicionados ao conjunto de revisão. Essas estatísticas (além de informações de conjunto de carga) fornecem informações históricas sobre o conteúdo adicionado a um caso.

Depois que você confirma uma coleção em um conjunto de revisão, as guias a seguir são exibidas na página de sobrevoo da conexão comprometida. Cada uma dessas guias contém diferentes tipos de informações sobre a coleção.

![Guias na página de sobrevoo da coleção comprometida](../media/CommittedCollectionFlyoutPage.png)

### <a name="collection-contents"></a>Conteúdo da coleção

Esta seção da guia **Resumo** contém estatísticas e outras informações sobre os itens coletados das fontes de dados na coleção e adicionados ao conjunto de revisão.

- **Total de itens extraídos**. O número total de itens adicionados ao conjunto de revisão. Esse número indica a soma de itens pai e itens filho adicionados ao conjunto de revisão.

  > [!TIP]
  > Passe o cursor sobre as barras de item pai ou filho para exibir o número total de itens pai ou filho.

- **Itens pai**. O número de itens retornados pela coleção usada para coletar os itens que foram adicionados ao conjunto de revisão. Esse número corresponde a (e é igual a) o número estimado de itens exibidos na **seção Parâmetros de** coleção. O número de itens pai que ele coleta informações que foram usadas para coletar os itens que foram adicionados ao conjunto de revisão.
 
   Um item pai pode conter vários itens filho. Por exemplo, uma mensagem de email é um item pai se ela contiver um arquivo anexado ou tiver um anexo na nuvem. Nesse caso, o arquivo anexado ou o destino do anexo de nuvem são considerados itens filho. Quando você confirma uma coleção, os itens pai e todos os itens filho correspondentes são adicionados ao conjunto de revisão como itens ou arquivos individuais.

- **Itens filho**. O número de itens filho adicionados ao conjunto de revisão. Os itens filho são anexos ou outras partes de um item pai. Os itens filho incluem arquivos anexados, anexos de nuvem, imagens e assinaturas de email. Quando você confirma uma coleção em um conjunto de revisão, os itens filho são extraídos, indexados e adicionados ao conjunto de revisão como arquivos individuais.

- **Itens exclusivos**. O número de itens exclusivos adicionados ao conjunto de revisão. Itens exclusivos são exclusivos do conjunto de revisão. Todos os itens são exclusivos quando a primeira coleção é adicionada a um novo conjunto de revisão porque não havia itens anteriores no conjunto de revisão.

- **Itens duplicados identificados**. O número de itens da coleção que não foram adicionados ao conjunto de revisão porque o mesmo item já existe no conjunto de revisão. As estatísticas sobre itens duplicados podem ajudar a explicar as diferenças entre o número de itens estimados de uma coleção de rascunho e o número real de itens adicionados ao conjunto de revisão.

### <a name="indexing"></a>Indexação

A **seção Indexação** na guia **Resumo de** um conjunto de revisão comprometida contém informações de indexação sobre os itens adicionados ao conjunto de revisão.

**Novos itens indexados**. O número de itens que foram indexados recentemente antes de eles foram adicionados ao conjunto de revisão. Um exemplo de um item recém-indexado são itens filho que são extraídos de um item pai e indexados antes de ser adicionado ao conjunto de revisão. Além disso, os itens que não estão localizados em fontes de  dados de custodia e locais de conteúdo não custodiados listados na guia Fontes de dados no caso são indexados antes de ser adicionados à revisão. Por exemplo, itens recém-indexados incluiriam itens coletados de locais adicionais.

**Itens indexados atualizados**. O número de itens parcialmente indexados que foram indexados com êxito e adicionados ao conjunto de revisão. Isso indexa parcialmente itens de locais de  conteúdo custodiante e não custodial A guia Fontes de dados que foram indexadas com êxito quando a coleção foi comprometida com o conjunto de revisão.

**Erros de indexação**. O número de itens parcialmente indexados que não puderam ser indexados antes de serem adicionados ao conjunto de revisão. Esses itens podem exigir correção de erros.

### <a name="collection-parameters"></a>Parâmetros de coleção

Esta seção exibe as informações de coleção que foram usadas para coletar os itens que foram adicionados ao conjunto de revisão. Esta guia exibe informações semelhantes às informações na **guia Estatísticas de** Pesquisa. Esta seção fornece uma foto rápida da consulta de pesquisa usada pela coleção, dos locais de conteúdo pesquisados e dos resultados estimados da coleção. Conforme explicado anteriormente, o número de itens estimados nesta seção seria igual ao número de itens pai mostrados na seção **Conteúdo da** coleção.

### <a name="search-statistics-tab"></a>Guia Estatísticas de pesquisa

As estatísticas exibidas na guia **Estatísticas de** Pesquisa são as mesmas estatísticas da última vez em que uma coleção de rascunho foi executado. Isso inclui estimativas de coleção, relatório de condição e locais principais. Essas informações são preservadas do conjunto de rascunhos para referência histórica e podem ser comparadas à coleção real que foi comprometida com o conjunto de revisão.

## <a name="differences-between-draft-collection-estimates-and-the-actual-committed-collection"></a>Diferenças entre as estimativas da coleção de rascunho e a coleção real comprometida

Quando você executar um conjunto de rascunhos, uma estimativa do número de itens (e  seu tamanho total) que atendem aos **critérios** de coleção é exibida na guia Resumo e na seção **Estimativas** de coleção da guia Estatísticas de pesquisa. Depois que você confirma um conjunto de rascunhos em um conjunto de revisão, o número real de itens (e seu tamanho total) adicionados ao conjunto de revisão são geralmente diferentes das estimativas. Na maioria dos casos, mais itens são adicionados ao conjunto de revisão do que foram estimados na coleção de rascunho. A lista a seguir descreve os motivos mais comuns para essas diferenças e dicas para identificá-las:

- **Itens filho**. Itens filho extraídos de seus itens pai e adicionados como arquivos individuais. O número de itens filho pode aumentar significativamente o número de itens que são realmente adicionados ao conjunto de revisão. Em geral, o número de  itens pai identificados  na seção Conteúdo da coleção na guia Resumo de uma coleção comprometida deve ser igual ao número de itens estimados da coleção de rascunho.

- **Itens duplicados**. Os itens da coleção de rascunho que já foram adicionados ao conjunto de revisão em uma coleção anterior não serão adicionados. Conforme explicado anteriormente, o número de itens duplicados na coleção é exibido na seção **Conteúdo da** coleção na guia **Resumo.**

- **Opções de configuração de coleção**. Quando você confirma um conjunto de rascunhos em um conjunto de revisão, você precisa incluir threads de conversa, anexos de nuvem e versões de documento. Qualquer um desses itens adicionados ao conjunto de revisão não está incluído nas estimativas do conjunto de rascunhos. Eles são identificados e coletados somente quando você confirma a coleção. Selecionar essas opções provavelmente aumentará o número de itens adicionados ao conjunto de revisão. 

    Por exemplo, várias versões SharePoint documentos não estão incluídas na estimativa do conjunto de rascunhos. Mas se você selecionar a opção para incluir todas as versões do documento ao exportar os resultados da pesquisa, o que aumentará o número real (e o tamanho total) dos itens adicionados ao conjunto de revisão. 

    Para obter mais informações sobre essas opções, consulte [Commit a draft collection to a review set](commit-draft-collection.md#commit-a-draft-collection-to-a-review-set-in-advanced-ediscovery). 

Aqui estão outros motivos pelos quais os resultados estimados de uma coleção de rascunhos podem ser diferentes dos resultados reais comprometidos.

- **A maneira como os resultados são estimados para coleções de rascunho.** Uma estimativa dos resultados da pesquisa retornada por uma coleção de rascunhos é exatamente essa, uma estimativa (e não uma contagem real) dos itens que atendem aos critérios de consulta da coleção. Para compilar a estimativa de itens de email, uma lista das IDs de mensagem que atendem aos critérios de pesquisa é solicitada do banco de dados Exchange. Mas quando você confirma a coleção em um conjunto de revisão, a coleção é reprisada e as mensagens reais são recuperadas do banco de dados Exchange de dados. Portanto, as diferenças podem resultar devido à forma como o número estimado de itens e o número real de itens são determinados.

- **Alterações que ocorrem entre o tempo durante a estimativa e a confirmação de coleções de rascunho.** Quando você confirma um conjunto de rascunhos em um conjunto de revisão, a pesquisa é reprisada para coletar os itens mais recentes no índice de pesquisa que atendem aos critérios de pesquisa. É possível que itens adicionais foram criados, enviados ou excluídos que atendem aos critérios de pesquisa no momento em que o conjunto de rascunhos foi executado pela última vez e quando a coleção de rascunhos é comprometida com um conjunto de revisão. Também é possível que os itens que estavam no índice de pesquisa quando os resultados da coleção de rascunhos foram estimados não estão mais lá porque eles foram limpos de uma fonte de dados antes de comprometer a coleção. Uma maneira de atenuar esse problema é especificar um intervalo de datas para uma coleção. Outra maneira é colocar uma espera em locais de conteúdo para que os itens sejam preservados e não possam ser limpos.

- **Itens nãoindexados.** Se o conjunto de rascunhos incluiu a pesquisa em todas as caixas de correio Exchange ou todos os sites SharePoint, somente itens não SharePoint de locais de conteúdo que contenham itens que corresponderem aos critérios de coleção serão adicionados ao conjunto de revisão. Em outras palavras, se nenhum resultado for encontrado em uma caixa de correio ou site, nenhum item não índicedo nessa caixa de correio ou site não será adicionado ao conjunto de revisão. No entanto, itens desindexados de todos os locais de conteúdo (mesmo aqueles que não contêm itens que corresponderem à consulta de coleção) serão incluídos nos resultados estimados da coleção.

    Como alternativa, se o conjunto de rascunhos incluiu locais de conteúdo específicos (o que significa que caixas de correio ou sites específicos, onde especificados na página Locais adicionais no assistente de conjunto de rascunhos), os itens não especificados (que não são excluídos pelos critérios de coleção) dos locais de conteúdo especificados na pesquisa serão exportados.  Nesse caso, o número estimado de itens não índicedos e o número de itens não índicedos adicionados ao conjunto de revisão devem ser os mesmos.
