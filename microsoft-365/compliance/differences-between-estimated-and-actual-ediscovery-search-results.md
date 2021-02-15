---
title: Diferenças entre os resultados estimados e reais da pesquisa de DescobertaScoberta
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
description: Entenda por que os resultados estimados e reais da pesquisa podem variar nas pesquisas que são executados com as ferramentas de Descoberta Online no Office 365.
ms.openlocfilehash: a5a66e070bf41cf6b3263dbae1e6ac5d136d9465
ms.sourcegitcommit: 222fb7fe2b26dde3d8591b61cc02113d6135012c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/06/2021
ms.locfileid: "49760249"
---
# <a name="differences-between-estimated-and-actual-ediscovery-search-results"></a>Diferenças entre os resultados estimados e reais da pesquisa de DescobertaScoberta

Este tópico se aplica às pesquisas que você pode executar usando uma das seguintes ferramentas de Descoberta e Do Microsoft 365: 

- Pesquisa de conteúdo
- Descoberta Eletrônica Central 
   
Quando você executar uma pesquisa de Descoberta eDiscovery, a ferramenta que você está usando retornará uma estimativa do número de itens (e seu tamanho total) que atendem aos critérios de pesquisa. Por exemplo, quando você executar uma pesquisa no centro de conformidade do Microsoft 365, os resultados estimados da pesquisa serão exibidos na página do flyout da pesquisa selecionada.
  
![Estimativa dos resultados exibidos no painel de detalhes da pesquisa selecionada](../media/74e4ce83-40be-41a9-b60f-5ad447e79fe4.png)
  
Essa é a mesma estimativa do tamanho total e do número de itens exibidos na Ferramenta de Exportação de Descobertas e Quando você exporta resultados para um computador local e no relatório de Resumo de Exportação baixado com os resultados da pesquisa.
  
**Resultados estimados na ferramenta de Exportação de Descobertas e Descobertas**

![Resultados estimados na ferramenta Exportação de Descobertas e Descobertas](../media/d34312a5-0ee6-49aa-9460-7ea0015a6e66.png)
  
**Resultados estimados no relatório de Resumo de Exportação**

![Os resultados estimados da pesquisa estão incluídos no relatório de resumo de exportação](../media/44b579da-86c2-4f33-81b5-84d604003eda.png)
  
No entanto, como você observará na captura de tela anterior do relatório Resumo de Exportação, o tamanho e o número de resultados reais da pesquisa baixados são diferentes do tamanho e do número de resultados estimados da pesquisa.
  
![Diferença entre resultados de pesquisa estimados e baixados](../media/84aef318-230f-430d-9d9e-02f21342d364.png)
  
Aqui estão alguns motivos para essas diferenças:
  
- **A maneira como os resultados são estimados.** Uma estimativa dos resultados da pesquisa é apenas essa, uma estimativa (e não uma contagem real) dos itens que atendem aos critérios de consulta de pesquisa. Para compilar a estimativa de itens do Exchange, uma lista das IDs de mensagem que atendem aos critérios de pesquisa é solicitada do banco de dados do Exchange pela ferramenta de Descoberta eDiscovery que você está usando. Mas quando você exporta os resultados da pesquisa, a pesquisa é reruncar e as mensagens reais são recuperadas do banco de dados do Exchange. Portanto, essas diferenças podem resultar em como o número estimado de itens e o número real de itens são determinados.

- **Alterações que ocorrem entre o tempo ao estimar e exportar resultados de pesquisa.** Quando você exporta os resultados da pesquisa, a pesquisa é reiniciada para coletar os itens mais recentes no índice de pesquisa que atendem aos critérios de pesquisa. É possível que haja itens adicionais criados, enviados ou recebidos que atendem aos critérios de pesquisa no tempo entre quando os resultados estimados da pesquisa foram coletados e quando os resultados da pesquisa foram exportados. Também é possível que os itens que estavam no índice de pesquisa quando os resultados da pesquisa foram estimados não estão mais lá porque foram limpos do local de conteúdo antes que os resultados da pesquisa sejam exportados. Uma maneira de atenuar esse problema é especificar um intervalo de datas para uma pesquisa de Descoberta eDiscovery. Outra maneira é colocar em espera locais de conteúdo para que os itens sejam preservados e não possam ser limpos. 

   Embora raro, mesmo no caso em que uma espera é aplicada, a manutenção de itens de calendário integrados (que não são editáveis pelo usuário, mas estão incluídos em muitos resultados de pesquisa) pode ser removida de tempos em tempos. Essa remoção periódica de itens de calendário resultará em menos itens exportados.

- **Itens não índicedos.** Itens não índicedos para pesquisa podem causar diferenças entre os resultados estimados e reais da pesquisa. Você pode incluir itens não índicedos ao exportar os resultados da pesquisa. Se você incluir itens não índicedos ao exportar resultados de pesquisa, talvez haja mais itens exportados. Isso causará uma diferença entre os resultados de pesquisa estimados e exportados.

    Ao usar a ferramenta de pesquisa de conteúdo, você tem a opção de incluir itens não índicedos na estimativa de pesquisa. O número de itens não índicedos retornados pela pesquisa é listado na página do flyout junto com os outros resultados estimados da pesquisa. Todos os itens não índicedos também seriam incluídos no tamanho total dos resultados estimados da pesquisa. Ao exportar os resultados da pesquisa, você tem a opção de incluir ou não itens não índicedos. A maneira como você configura essas opções pode resultar em diferenças entre os resultados estimados e reais da pesquisa baixados.

- **Exportar os resultados de uma Pesquisa de Conteúdo que inclui todos os locais de conteúdo.** Se a pesquisa de onde você está exportando resultados for uma pesquisa de todos os locais de conteúdo em sua organização, somente os itens não índicedos de locais de conteúdo que contêm itens que corresponderem aos critérios de pesquisa serão exportados. In other words, if no search results are found in a mailbox or site, then any unindexed items in that mailbox or site won't be exported. No entanto, itens não índicedos de todos os locais de conteúdo (mesmo aqueles que não contêm itens que corresponderem à consulta de pesquisa) serão incluídos nos resultados estimados da pesquisa.

    Como alternativa, se a pesquisa que você está exportando resultados de locais de conteúdo específicos incluídos, os itens não índicedos (que não são excluídos pelos critérios de pesquisa) de todos os locais de conteúdo especificados na pesquisa serão exportados. Nesse caso, o número estimado de itens não índicedos e o número de itens não índicedos exportados devem ser os mesmos.

    O motivo para não exportar itens não índicedos de cada local na organização é porque pode aumentar a probabilidade de erros de exportação e aumentar o tempo necessário para exportar e baixar os resultados da pesquisa.

- **Formatos de arquivo brutos versus formatos de arquivo exportados.** Para itens do Exchange, o tamanho estimado dos resultados da pesquisa é calculado usando os tamanhos brutos de mensagens do Exchange. No entanto, as mensagens de email são exportadas em um arquivo PST ou como mensagens individuais (que são formatadas como arquivos EML). Ambas as opções de exportação usam um formato de arquivo diferente das mensagens brutas do Exchange, o que resulta no tamanho total do arquivo exportado diferente do tamanho estimado do arquivo.

- **Versões do documento.** Para documentos do SharePoint, várias versões de um documento não são incluídas nos resultados estimados da pesquisa. Mas você tem a opção de incluir todas as versões do documento ao exportar os resultados da pesquisa, o que aumentará o número real (e o tamanho total) dos documentos exportados. 

- **Des duplicação.** Para itens do Exchange, a des duplicação reduz o número de itens exportados. Você tem a opção de des duplicar os resultados da pesquisa ao exportá-los. Para mensagens do Exchange, isso significa que apenas uma única instância de uma mensagem é exportada, mesmo que essa mensagem possa ser encontrada em várias caixas de correio. Os resultados estimados da pesquisa incluem todas as instâncias de uma mensagem. Portanto, se você escolher a opção de des duplicação ao exportar os resultados da pesquisa, o número real de itens exportados pode ser consideravelmente menor do que o número estimado de itens.

    Outra coisa a ter em mente se você escolher a opção de des duplicação é que todos os itens do Exchange são exportados em um único arquivo PST e a estrutura de pastas das caixas de correio de origem não é preservada. O arquivo PST exportado contém apenas os itens de email. No entanto, um relatório de resultados de pesquisa contém uma entrada para cada mensagem exportada que identifica a caixa de correio de origem onde a mensagem está localizada. Isso ajuda a identificar todas as caixas de correio que contêm uma mensagem duplicada. Se você não habilitou a deduplicação, um arquivo PST separado é exportado para cada caixa de correio incluída na pesquisa. 
 
> [!NOTE]
> Se você não selecionar  a opção Incluir itens que são criptografados ou têm uma opção de formato não reconhecedo quando você exporta resultados de pesquisa ou apenas baixa os relatórios, os relatórios de erro de índice são baixados, mas eles não têm nenhuma entrada. Isso não significa que não haja erros de indexação. Isso significa apenas que os itens não índicedos não foram incluídos na exportação. 
