---
title: Treinamento de marcação e relevância na descoberta eletrônica avançada do Office 365
ms.author: chrfox
author: chrfox
manager: laurawi
titleSuffix: Office 365
ms.date: 09/14/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 8576cc86-d51b-4285-b54b-67184714cc62
description: 'Conheça as etapas para marcar e, em seguida, trabalhar com um exemplo de treinamento de 40 arquivos durante o estágio de treinamento de relevância do Office 365 Advanced eDiscovery.  '
ms.openlocfilehash: e214e8a8edba7472f93274f3a4f7a06a09e2a801
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/19/2019
ms.locfileid: "40802694"
---
# <a name="tagging-and-relevance-training-in-office-365-advanced-ediscovery"></a>Treinamento de marcação e relevância na descoberta eletrônica avançada do Office 365

> [!NOTE]
> A Descoberta Eletrônica Avançada exige um Office 365 E3, com um complemento de Conformidade Avançada ou uma assinatura do E5 para sua organização. Se você não tiver esse plano e quiser tentar a Descoberta Eletrônica Avançada, poderá [Inscrever-se para uma avaliação do Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279). 
  
Este tópico descreve o procedimento para trabalhar com o módulo de treinamento de relevância de descoberta eletrônica avançada. 
  
Após a conclusão da avaliação na descoberta eletrônica avançada, e você insere o estágio de treinamento relevância, um exemplo de treinamento de 40 arquivos é trazido para a guia marca para marcação. 
  
## <a name="performing-relevance-training"></a>Realizando treinamento de relevância

1. Na guia **marca \> de relevância** , o painel de marcação é exibido por padrão no painel esquerdo e os arquivos de exemplo são exibidos, um de cada vez para marcação. 
    
    ![Painel Marca de Relevância](media/0cf19ab4-b427-4a7f-8749-0f4ed9afaf58.png)
  
    Na guia **marca** , o nome de exibição do arquivo é mostrado. Pode ser o caminho, o assunto do email, o título ou o nome definido pelo usuário. A ID, o caminho do arquivo ou o caminho do texto podem ser copiados clicando com o botão direito do mouse no caminho do arquivo. 
    
    As estatísticas de marcação de tabulação de **marca** mostram o número de exemplo de arquivo (na parte superior do painel esquerdo), o número do arquivo exibido no momento do total de arquivos no exemplo (parte inferior do painel direito) e o número total atual de arquivos marcados no exemplo (parte inferior do painel esquerdo), que é alterado à medida que você marca os arquivos. Isso se aplica a qualquer marcação de relevância feita, seja em avaliação, treinamento, atualização ou teste. 
    
    Os ícones que indicam a existência de comentários, marcas e arquivos da família são exibidos no modo de exibição de arquivo em uma barra acima do arquivo.
    
2. Determine a relevância do arquivo para o problema do caso e marque o arquivo usando os botões ou atalhos de teclado da opção de marcação, conforme mostrado na tabela a seguir:

|**Opção de marcação**|**Descrição**|**Atalho de teclado**|**Para vários problemas – atalho de teclado de marca em massa**|
|-----|-----|-----|-----|
|R  <br/> |Necessários  <br/> |Z  <br/> |Shift + Z  <br/> |
|NR  <br/> |Não relevante  <br/> |X  <br/> |Shift + X  <br/> |
|Ignorar  <br/> |Ignorar  <br/> |C  <br/> |Shift + A  <br/> |
   
  - Quando houver vários problemas para um arquivo, depois de marcar um problema, a seleção será movida para o próximo problema (se houver algum). 
    
  - Palavras-chave que foram definidas pelo administrador ou gerente de caso ao realçar palavras-chave (palavras \> -chave de configuração de relevância realçadas), serão exibidas (em cores especificadas) para ajudar a identificar arquivos relevantes durante a marcação. Se uma palavra-chave tiver um sublinhado duplo, poderá ser clicado para exibir uma dica de ferramenta com a descrição da palavra-chave. 
    
    Opcionalmente, na guia **marca** , clique em **configurações de marca** para definir as seguintes opções: 
    
    ![Configurações de marca de relevância](media/533e89fa-7eb4-409e-ab07-f5aab9296dd8.png)
  
  - **Marca em massa**: Use esta opção para atribuir vários problemas para um arquivo selecionando **todos** para definir a marca do arquivo selecionado para todos os problemas (substituições já marcadas) ou selecionando **o restante** para aplicar a marca aos outros problemas não marcados. A opção selecionada permanecerá em vigor para todos os casos deste usuário até ser alterada por esse usuário (a definição é por usuário para todos os casos do usuário). 
    
  - **Marca automática**: Marque essa caixa de seleção para definir outros problemas para um arquivo como não relevante após uma única marcação relevante.
    
  - **Avanço automático**: Marque essa caixa de seleção para mover a seleção de arquivo exibida para o próximo arquivo ao marcar o último ou apenas o problema não marcado. 
    
    Arquivos ignorados não serão considerados para fins de classificação de relevância e treinamento de relevância.
    
3. Comentários de texto livre, associados a um arquivo, podem ser exibidos e editados por meio da opção **Comentário** na lista suspensa do painel esquerdo. (opcional) 
    
4. As diretrizes para marcação podem ser exibidas selecionando a opção **diretrizes de marcação** na lista suspensa do painel esquerdo. 
    
5. Após concluir a marcação de todos os arquivos na lista e estiver pronto para calcular os resultados, clique em **calcular**. A guia **rastrear** é exibida. 
    
## <a name="working-with-the-sample-files-list"></a>Trabalhar com a lista de arquivos de exemplo

A lista arquivos de amostra permite exibir uma lista dos arquivos em um exemplo de treinamento e realizar várias ações em um ou mais arquivos. Na guia **** \> **marca** de relevância, o painel esquerdo **arquivos de exemplo** exibe uma lista de arquivos de amostra para processamento com processos de avaliação, treinamento, acompanhamento e inconsistências. 
  
1. Na guia **marca \> de relevância** , selecione os arquivos de exemplo na lista suspensa painel esquerdo. Os arquivos de exemplo estão listados no painel esquerdo. 
    
    ![Lista de arquivos de exemplo de Marca de Relevância](media/fd058bdd-645a-4af1-a1eb-bff08581cb18.png)
  
2. Selecione um exemplo ou número de arquivo específico inserindo ou selecionando seu número nas caixas de **exemplo** ou de **arquivo** . 
    
  -   - Um número de sequência de arquivos está listado na coluna esquerda da lista de arquivos exibidos na guia **marca** . Clicando no cabeçalho, a ordem de exibição original dos arquivos retorna a sua ordem original. 
    
  - Clicar em uma linha de arquivo exibe o conteúdo no painel direito.
    
  - Navegue entre arquivos no exemplo atual usando as opções de barra de menu inferior. Além disso, os atalhos de teclado de navegação estão disponíveis:
    
    Para navegar até o primeiro arquivo do exemplo: Shift + Ctrl +\<
    
    Para navegar para o arquivo anterior no exemplo: Shift +\<
    
    Para navegar até o próximo arquivo no exemplo: Shift +\>
    
    Para navegar até o último arquivo no exemplo: Shift + Ctrl +\>
    
## <a name="see-also"></a>Confira também

[Descoberta Eletrônica Avançada do Office 365](office-365-advanced-ediscovery.md)
  
[Noções básicas sobre avaliação em relevância](assessment-in-relevance-in-advanced-ediscovery.md)
  
[Marcação e avaliação](tagging-and-assessment-in-advanced-ediscovery.md)
  
[Análise de relevância de rastreamento](track-relevance-analysis-in-advanced-ediscovery.md)
  
[Decidindo com base nos resultados](decision-based-on-the-results-in-advanced-ediscovery.md)
  
[Testando análise de relevância](test-relevance-analysis-in-advanced-ediscovery.md)

