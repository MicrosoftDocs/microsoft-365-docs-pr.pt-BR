---
title: Usar o módulo de relevância na descoberta eletrônica avançada
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
titleSuffix: Office 365
ms.date: 9/14/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 5d671821-d188-42da-a9ce-9cfe92beedfd
description: Saiba mais sobre o módulo de relevância na descoberta eletrônica avançada, incluindo um fluxo de trabalho e diretrizes e etapas para treinamento e análise de arquivo.
ms.openlocfilehash: 8d5cbfff2b205ba785cda269bb09560b2a813f3c
ms.sourcegitcommit: c43ebb915fa0eb7eb720b21b62c0d1e58e7cde3d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/30/2020
ms.locfileid: "44936604"
---
# <a name="use-the-relevance-module-in-advanced-ediscovery-classic"></a>Usar o módulo de relevância na descoberta eletrônica avançada (clássico)

> [!NOTE]
> Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279). 
  
Na descoberta eletrônica avançada, o módulo de relevância inclui o treinamento de relevância e a revisão de arquivos relacionados a uma ocorrência. O fluxo de trabalho de relevância é mostrado e descrito da seguinte maneira:
  
![Fluxo de trabalho de relevância](../media/44c67dd2-7a20-40a9-b0ed-784364845c77.gif)
  
- **Ciclos de avaliação e controle**:
    
  - **Avaliação**: a descoberta eletrônica avançada permite a avaliação prévia com base em uma amostra aleatória de arquivos e usa essa avaliação para aplicar decisões para determinar o desempenho do processo de codificação de previsão. 
    
  - **Track**: a descoberta eletrônica avançada calcula e exibe resultados provisórios da avaliação ao monitorar a validade estatística do processo. 
    
- **Ciclos de treinamento e acompanhamento**:
    
  - **Marca**: a descoberta eletrônica avançada aprende critérios de relevância específicos para cada problema com base na revisão iterativa do especialista e na marcação de arquivos individuais.
    
  - **Track**: a descoberta eletrônica avançada calcula e exibe resultados provisórios do treinamento de relevância enquanto monitora a validade estatística do processo. 
    
- **Cálculo em lote**: a descoberta eletrônica avançada Obtém os critérios de relevância acumulados e aprendidos, aplica-os a todo o conjunto de arquivos e gera pontuações de relevância para cada arquivo.
    
- **Decide**@ @ @ @ @ @ @ @ @ @ @ @ @ @ @ @ @ @ @ @ @ @ @ @ @ @ @ @ @ @ @ @ @
    
- **Test**: os resultados de descoberta eletrônica avançada podem ser testados para verificar a validade e a eficácia do processamento avançado de descoberta eletrônica.
    
## <a name="guidelines-for-relevance-training-and-review"></a>Diretrizes para treinamento e análise de relevância

Veja a seguir uma visão geral das diretrizes de treinamento e análise de relevância:
  
- **Erros e inconsistências**: se forem feitos erros de marcação durante o treinamento, retorne a amostras de arquivos anteriores para corrigi-los. Se houver muitos erros para corrigir ou se houver uma nova perspectiva do caso ou problema, os critérios de relevância deverão ser redefinidos pelo administrador e o treinamento de relevância reiniciado.
    
- **Marcação e treinamento**: 
    
  - Os arquivos devem ser marcados com base apenas no conteúdo. Não considere metadados, como os responsáveis, a data ou o caminho do arquivo. 
    
  - Não considere indicações de intervalo de datas no texto ao marcar arquivos.
    
  - Não considere imagens gráficas incorporadas ao marcar arquivos.
    
  - Se estiver exibindo um arquivo usando o ícone de **exibição de texto formatado** durante a marcação, não considere a formatação de texto. Por exemplo, uma palavra exibida com um tachado (uma linha horizontal através do seu centro indicando exclusão) ainda é considerada por relevância como parte do texto analisado. 
    
  - Ignorar o texto aplicado à relevância (conforme definido pelo gerente de caso ou administrador) será removido no conteúdo do arquivo exibido no modo de exibição de texto em relevância. Se os valores para ignorar texto tiverem sido definidos após o treinamento de relevância já ter sido iniciado, o novo texto ignorado será aplicado a arquivos de exemplo criados a partir do ponto em que foi definido. O recurso Ignorar texto deve ser usado com cautela, pois seu uso pode reduzir o desempenho da análise de arquivos
    
  - Use a opção **ignorar marcação** apenas quando necessário. A descoberta eletrônica avançada não treina com base em arquivos ignorados. Em avaliação, se for difícil dizer se um arquivo é relevante, é melhor marcar como relevante (R) ou não relevante (NR) sempre que possível, em vez de selecionar **ignorar**. Quando a descoberta eletrônica avançada avaliar o treinamento, ela poderá ser vista como esses tipos de arquivos foram processados.
    
  - Até mesmo arquivos com uma quantidade muito pequena de texto extraído deve ser marcado em treinamento como R/NR, e não como "ignorar", quando possível. 
    
  - A marcação pode impactar o classificador, desde que o arquivo seja legível e possa ser marcado como R/NR.
    
  - O número de sequência de arquivo na lista de arquivos de amostra exibidos na guia **marca** permite que o usuário retorne à ordem de exibição original dos arquivos. 
    
  - Você pode retornar a qualquer amostra e alterar a marcação dos arquivos de avaliação e de conjunto de treinamento. As alterações serão aplicadas durante a criação do próximo exemplo.
    
  - Os arquivos do Excel digitalizados no formato PDF devem ser tratados da mesma forma que os arquivos nativos do Excel ao marcar arquivos.
    
  - Quando estiver em dúvida sobre a marcação de relevância de um arquivo, consulte um especialista. Marcações incorretas durante o treinamento de relevância podem causar perda de tempo mais tarde no processo e também podem ter um impacto negativo sobre a qualidade dos resultados gerais.
    
  - As palavras-chave que foram definidas nas listas de palavras-chave serão exibidas em cores para ajudar o usuário a identificar arquivos relevantes durante a marcação.
    
- **Cálculo em lotes**: os arquivos que foram marcados como R/NR pelo especialista receberão uma pontuação de 0 ou 100. Isso se aplica à marcação feita antes do cálculo em lote. Se o especialista tiver alternado o problema para ficar inativo após o cálculo de lote e a marcação contínua desse problema, as pontuações recentemente marcadas não serão 100/0, mas sim a pontuação original.
    
- **Modo de problemas e de amostragem**: problemas geralmente estão desativados quando o trabalho deles é concluído (o treinamento de relevância é estabilizado e o cálculo do lote foi realizado), quando os problemas são cancelados ou quando outro usuário está trabalhando com os problemas.
    
## <a name="steps-in-relevance-training"></a>Etapas no treinamento de relevância

Na guia ** \> controle de relevância** , a descoberta eletrônica avançada fornece recomendações sobre como proceder no processamento, com as próximas etapas a seguir. As implicações são descritas abaixo quando cada uma das etapas a seguir é recomendada no processo de treinamento de relevância. 
  
- Marcação/continuação de marcação: marcação de arquivo e classificação de relevância executada por um especialista para cada arquivo e problema em um exemplo.
    
  - Implicação: um exemplo existente precisa ser marcado.
    
- Avaliação/continuação da avaliação: habilita a validação antecipada da relevância do problema de caso e uma exibição preliminar da relevância da população de arquivo importada para o caso atual.
    
  - Implicação: mais avaliação obrigatória ou recomendada.
    
- Treinamento de treinamento/continuação: processo durante o qual a descoberta eletrônica avançada aprende do especialista que está marcando os exemplos de arquivo e obtém a capacidade de identificar critérios de relevância pertinentes a cada problema dentro do contexto de cada caso.
    
  - Implicação: o problema precisa de mais treinamento; o próximo exemplo deve ser criado e marcado. 
    
- Cálculo em lote: processo de relevância no qual a descoberta eletrônica avançada Obtém o conhecimento adquirido durante o estágio de treinamento e a aplica à população de arquivo inteiro. Todos os arquivos no grupo de arquivos pertinente são avaliados por relevância e recebem uma pontuação de relevância.
    
  - Implicação: o problema foi estabilizado e o cálculo de lote pode ser executado.
    
- Atualização: relevância indica quando um especialista revisa e marca uma amostra de arquivos selecionados a partir de uma carga de arquivos adicional durante um cenário de cargas sem interrupção.
    
  - Implicação: uma nova carga foi adicionada e a atualização é necessária para continuar trabalhando.
    
- Inconsistências de marca: o processo identifica, por meio de um algoritmo de descoberta eletrônica avançado, inconsistências no processo de marcação de arquivos que podem afetar negativamente a análise.
    
  - Implicação: o exemplo a seguir inclui arquivos que foram marcados em exemplos anteriores e sua marcação deve ser refeita.
    
- Classificador de atualização: permite que o usuário Aplique alterações de marcação ou propagação.
    
  - Implicação: as alterações de marcação e propagação podem ser aplicadas sem a necessidade de executar outra amostra de relevância manualmente.
    
- Em retenção: o processo de treinamento de relevância foi concluído.
    
  - Implicação: nenhum treinamento de relevância é necessário neste ponto.
    
Embora a descoberta eletrônica avançada orienta você durante o processo, com as próximas etapas recomendadas em estágios diferentes, ela também permite que você navegue entre guias e páginas e faça escolhas para lidar com situações que possam ser pertinentes a seu processo de análise de caso, de problema ou de documento individual. 
  
É possível aceitar ou substituir as opções de processamento de próxima etapa de descoberta eletrônica avançada. Se você deseja executar uma etapa diferente da próxima etapa recomendada, clique na **próxima etapa** listada na exibição de problema expandida na caixa de diálogo, clique no botão **Modificar** ao lado da próxima etapa e selecione outra opção de próxima etapa. 
  
> [!NOTE]
> Algumas opções podem permanecer desabilitadas após a desbloqueio, pois elas não são suportadas para uso nesse ponto no processo. 
  
## <a name="see-also"></a>Também consulte

[Descoberta Eletrônica Avançada (clássica)](office-365-advanced-ediscovery.md)
  
[Noções básicas sobre avaliação em relevância](assessment-in-relevance-in-advanced-ediscovery.md)
  
[Marcação e avaliação](tagging-and-assessment-in-advanced-ediscovery.md)
  
[Treinamento de marcação e relevância](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[Análise de relevância de rastreamento](track-relevance-analysis-in-advanced-ediscovery.md)
  
[Decidindo com base nos resultados](decision-based-on-the-results-in-advanced-ediscovery.md)
  
[Testando análise de relevância](test-relevance-analysis-in-advanced-ediscovery.md)

