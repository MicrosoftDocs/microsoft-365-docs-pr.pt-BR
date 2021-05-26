---
title: Diferenças entre os resultados estimados e reais da pesquisa de Descoberta EDiscovery
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
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- SPO160
- MOE150
- MET150
ms.assetid: 8f20ca4f-a908-46ec-99e6-9890d269ecf2
description: Entenda por que os resultados de pesquisa estimados e reais podem variar em pesquisas executados com ferramentas de Descoberta Office 365.
ms.openlocfilehash: 17a4c2eea9833afa2112fa8ab918dcda074eeb36
ms.sourcegitcommit: 727a75b604d5ff5946a0854662ad5a8b049f2874
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/25/2021
ms.locfileid: "52653506"
---
# <a name="differences-between-estimated-and-actual-ediscovery-search-results"></a>Diferenças entre os resultados estimados e reais da pesquisa de Descoberta EDiscovery

Este tópico aplica-se às pesquisas que você pode executar usando uma das seguintes ferramentas Microsoft 365 descoberta de eDiscovery: 

- Pesquisa de conteúdo
- Descoberta Eletrônica Central

Quando você executar uma pesquisa de Descoberta Digital, a ferramenta que você está usando retornará uma estimativa do número de itens (e seu tamanho total) que corresponderão aos critérios de pesquisa. Por exemplo, quando você executar uma pesquisa no centro de conformidade Microsoft 365, os resultados estimados da pesquisa serão exibidos na página de sobrevoo da pesquisa selecionada.
  
![Estimativa de resultados exibidos na página de sobrevoo de pesquisa](../media/EstimatedSearchResults1.png)
  
Esta é a mesma estimativa do tamanho total e do número de itens exibidos na Ferramenta de Exportação de Descoberta e quando você exporta resultados para um computador local e no relatório Resumo de Exportação baixado com os resultados da pesquisa.
  
**Resultados estimados na ferramenta Exportação de Descobertas Online**

![Resultados estimados na ferramenta Exportação de Descobertas Online](../media/d34312a5-0ee6-49aa-9460-7ea0015a6e66.png)
  
**Resultados estimados no relatório Resumo da Exportação**

![Os resultados estimados da pesquisa estão incluídos no relatório de resumo de exportação](../media/44b579da-86c2-4f33-81b5-84d604003eda.png)
  
No entanto, como você observará na captura de tela anterior do relatório Resumo de Exportação, o tamanho e o número de resultados reais da pesquisa baixados são diferentes do tamanho e do número de resultados de pesquisa estimados.
  
![Diferença entre resultados de pesquisa estimados e baixados](../media/84aef318-230f-430d-9d9e-02f21342d364.png)
  
Aqui estão alguns motivos para essas diferenças:
  
- **A maneira como os resultados são estimados**. Uma estimativa dos resultados da pesquisa é exatamente essa, uma estimativa (e não uma contagem real) dos itens que atendem aos critérios de consulta de pesquisa. Para compilar a estimativa de itens Exchange, uma lista das IDs de mensagem que atendem aos critérios de pesquisa é solicitada do banco de dados Exchange pela ferramenta de Descoberta Digital que você está usando. Mas quando você exporta os resultados da pesquisa, a pesquisa é reprisada e as mensagens reais são recuperadas do banco de dados de Exchange. Portanto, essas diferenças podem resultar devido à forma como o número estimado de itens e o número real de itens são determinados.

- **Alterações que ocorrem entre o tempo ao estimar e exportar resultados da pesquisa.** Quando você exporta os resultados da pesquisa, a pesquisa é reiniciada para coletar os itens mais recentes no índice de pesquisa que atendem aos critérios de pesquisa. É possível que haja itens adicionais criados, enviados ou recebidos que atendem aos critérios de pesquisa no tempo entre quando os resultados estimados da pesquisa foram coletados e quando os resultados da pesquisa foram exportados. Também é possível que os itens que estavam no índice de pesquisa quando os resultados da pesquisa foram estimados não estão mais lá porque eles foram limpos do local do conteúdo antes que os resultados da pesquisa sejam exportados. Uma maneira de atenuar esse problema é especificar um intervalo de datas para uma pesquisa de Descoberta e. Outra maneira é colocar uma espera em locais de conteúdo para que os itens sejam preservados e não possam ser limpos. 

   Embora rara, mesmo quando uma responsabilidade é aplicada, a manutenção de itens de calendário integrados (que não são editáveis pelo usuário, mas estão incluídos em muitos resultados de pesquisa) pode ser removida de tempos em tempos. Essa remoção periódica de itens de calendário resultará em menos itens exportados.

- **Itens nãoindexados.** Itens não índicedos para pesquisa podem causar diferenças entre resultados de pesquisa estimados e reais. Você pode incluir itens nãoindexados ao exportar os resultados da pesquisa. Se você incluir itens nãoindexados ao exportar resultados da pesquisa, pode haver mais itens exportados. Isso causará uma diferença entre os resultados de pesquisa estimados e exportados.

    Ao usar a ferramenta de pesquisa conteúdo, você tem a opção de incluir itens não índicedos ao exportar resultados da pesquisa. O número de itens não índicedos retornados pela pesquisa está listado na página de sobrevoo juntamente com os outros resultados estimados da pesquisa. Todos os itens nãoindexados também seriam incluídos no tamanho total dos resultados estimados da pesquisa. Ao exportar resultados da pesquisa, você tem a opção de incluir ou não itens não índicedos. A forma como você configura essas opções pode resultar em diferenças entre os resultados de pesquisa estimados e reais baixados.

- **Exportando os resultados de uma pesquisa de conteúdo que inclui todos os locais de conteúdo.** Se a pesquisa de que você está exportando resultados foi uma pesquisa de todos os locais de conteúdo em sua organização, somente os itens não índicedos de locais de conteúdo que contêm itens que corresponderem aos critérios de pesquisa serão exportados. In other words, if no search results are found in a mailbox or site, then any unindexed items in that mailbox or site won't be exported. No entanto, itens desindexados de todos os locais de conteúdo (mesmo aqueles que não contêm itens que corresponderem à consulta de pesquisa) serão incluídos nos resultados estimados da pesquisa.

    Como alternativa, se a pesquisa que você está exportando resultados de locais de conteúdo específicos incluídos, os itens não especificados (que não são excluídos pelos critérios de pesquisa) de todos os locais de conteúdo especificados na pesquisa serão exportados. Nesse caso, o número estimado de itens não índicedos e o número de itens não índicedos que são exportados devem ser os mesmos.

    O motivo para não exportar itens não índicedos de todos os locais da organização é porque pode aumentar a probabilidade de erros de exportação e aumentar o tempo necessário para exportar e baixar os resultados da pesquisa.

- **Itens não SharePoint e OneDrive incluídos nas estimativas de pesquisa.** Os itens não SharePoint sites e OneDrive for Business contas não estão incluídos nos resultados estimados da pesquisa. Isso porque o índice SharePoint não contém dados para itens não indexados. Somente itens nãoindexados de caixas de correio são incluídos nas estimativas de pesquisa. No entanto, se você incluir itens nãoindexados ao exportar resultados da pesquisa, itens não SharePoint e OneDrive serão incluídos, o que aumentará o número de itens que são realmente exportados. Isso resultará em diferenças entre os resultados estimados (que não incluem itens não SharePoint e OneDrive sites) e os itens reais baixados. A regra sobre a exportação de itens não índicedos somente de locais de conteúdo que contenham itens que corresponderem aos critérios de pesquisa ainda se aplica nessa situação.

- **Versões de documento em SharePoint e OneDrive**. Ao pesquisar SharePoint sites e OneDrive contas, várias versões de um documento não são incluídas na contagem de resultados de pesquisa estimados. Mas você tem a opção de incluir todas as versões do documento ao exportar os resultados da pesquisa. Se você incluir versões de documento ao exportar resultados da pesquisa, o número real (e o tamanho total) dos itens exportados serão aumentados.

- **SharePoint pastas**. Se o nome das pastas no SharePoint corresponde a uma consulta de pesquisa, a estimativa de pesquisa incluirá uma contagem dessas pastas (mas não os itens nessas pastas). Quando você exporta os resultados da pesquisa, os itens na pasta são exportados, mas a pasta real não é exportada. O resultado é que o número de itens exportados exportados será maior do que o número de resultados de pesquisa estimados. Se uma pasta estiver vazia, o número de resultados reais de pesquisa exportados será reduzido por um item, pois a pasta real não será exportada.

- **SharePoint listas**. Se o nome de uma lista SharePoint corresponde a uma consulta de pesquisa, a estimativa de pesquisa incluirá uma contagem de todos os itens na lista. Quando você exporta os resultados da pesquisa, a lista (e os itens de lista) é exportada como um único arquivo CSV. Isso reduzirá o número real de itens realmente exportados. Se a lista contiver anexos, os anexos serão exportados como documentos separados, o que também aumentará o número de itens exportados.

- **Formatos de arquivo brutos versus formatos de arquivo exportados.** Para Exchange itens, o tamanho estimado dos resultados da pesquisa é calculado usando os tamanhos brutos Exchange mensagens. No entanto, as mensagens de email são exportadas em um arquivo PST ou como mensagens individuais (que são formatadas como arquivos EML). Ambas as opções de exportação usam um formato de arquivo diferente do Exchange mensagens brutas, o que resulta no tamanho total do arquivo exportado ser diferente do tamanho do arquivo estimado.

- **Des duplicação de Exchange itens durante a exportação**. Para Exchange itens, a de duplicação reduz o número de itens exportados. Você tem a opção de des duplicar os resultados da pesquisa ao exportá-los. Para Exchange mensagens, isso significa que apenas uma única instância de uma mensagem é exportada, mesmo que essa mensagem possa ser encontrada em várias caixas de correio. Os resultados estimados da pesquisa incluem todas as instâncias de uma mensagem. Portanto, se você escolher a opção de des duplicação ao exportar resultados da pesquisa, o número real de itens exportados pode ser consideravelmente menor do que o número estimado de itens.

O relatório de resultados da pesquisa (arquivo Results.csv) contém uma entrada para cada mensagem duplicada e identifica a caixa de correio de origem onde uma mensagem duplicada está localizada. Isso ajuda a identificar todas as caixas de correio que contêm uma mensagem duplicada.

> [!NOTE]
> Se você não selecionar  a opção Incluir itens que são criptografados ou têm uma opção de formato não reconhecedo quando você exporta os resultados da pesquisa ou baixa os relatórios, os relatórios de erro de índice são baixados, mas eles não têm nenhuma entrada. Isso não significa que não haja erros de indexação. Isso significa apenas que itens não indexados não foram incluídos na exportação.
