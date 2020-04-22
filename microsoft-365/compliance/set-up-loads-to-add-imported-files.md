---
title: Configurar carregamentos para adicionar arquivos importados na descoberta eletrônica avançada
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
ms.assetid: 0e0a9d04-294f-4f54-8bf1-b32d81345126
description: 'Revise as etapas para adicionar arquivos importados à última carga definida ou ao lote de arquivos antes de realizar o treinamento de relevância na descoberta eletrônica avançada.  '
ms.openlocfilehash: 7914013d21cfd7bba0e474a0e8d831bcfad0239d
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2020
ms.locfileid: "43636289"
---
# <a name="set-up-loads-to-add-imported-files-in-advanced-ediscovery-classic"></a>Configurar carregamentos para adicionar arquivos importados na descoberta eletrônica avançada (clássico)

> [!NOTE]
> A Descoberta Eletrônica Avançada exige um Office 365 E3, com um complemento de Conformidade Avançada ou uma assinatura do E5 para sua organização. Se você não tiver esse plano e quiser tentar a Descoberta Eletrônica Avançada, poderá [Inscrever-se para uma avaliação do Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279). 
  
Na descoberta eletrônica avançada, uma carga é um novo lote de arquivos adicionados a um caso. Por padrão, uma carga é definida e todos os arquivos importados são adicionados a ela. Antes de realizar o treinamento de relevância, os arquivos importados devem ser adicionados à carga. 
  
Considere as seguintes situações:
  
- Os novos arquivos são conhecidos como semelhantes aos arquivos anteriores carregados para o banco de dados de caso ou a carga de arquivos anterior era um conjunto aleatório da coleção de arquivos. Nesta instância, adicione os arquivos importados à carga de arquivo atual.
    
- Os novos arquivos são diferentes dos anteriores (por exemplo, de uma fonte diferente) ou você não tem conhecimento prévio de que eles sejam semelhantes ou diferentes às cargas anteriores. Neste cenário, adicione os arquivos importados a uma nova carga de arquivo. A descoberta eletrônica avançada reconhece isso como um cenário de cargas sem interrupção, invoca um processo de atualização, bloqueia o treinamento de relevância e os cálculos de lote até que a atualização seja concluída, e a nova carga é integrada e treinada. 
    
## <a name="adding-imported-files-to-the-current-load"></a>Adicionando arquivos importados à carga atual

Todos os arquivos importados devem ser adicionados a uma carga a ser processada na descoberta eletrônica avançada. Arquivos importados são adicionados à última carga definida. Se você importar arquivos adicionais mais tarde, eles também devem ser adicionados à carga.
  
1. Na guia **configuração \> de relevância de relevância** , selecione **cargas**.
    
    ![Guia Cargas de Configuração de Relevância](../media/278aac7f-655f-462f-852a-6baa5d818768.png)
  
2. **Incluir arquivos**: selecione uma opção para os arquivos a serem incluídos. Por padrão, a adição de arquivos à carga atual baseia-se na população "todos os arquivos".
    
    > [!TIP]
    > Carregar todos os arquivos de seleção disponíveis em relevância. Se você planeja carregar apenas um subconjunto dos arquivos disponíveis, primeiro consulte o suporte, pois o carregamento de subconjuntos pode afetar adversamente o treinamento de relevância. 
  
3. No **Gerenciamento de cargas**, selecione uma carga.
    
4. Clique em **Adicionar arquivos**. Os arquivos são adicionados à carga e uma mensagem de confirmação é exibida. 
    
5. Clique em **OK**.
    
Agora, os arquivos podem ser processados na relevância avançada da descoberta eletrônica para treinar os arquivos.
  
## <a name="editing-a-load-name-within-a-case"></a>Editando um nome de carregamento dentro de um caso

Se alterar o nome da carga, é recomendável usar um nome que seja significativo para o caso.
  
1. Na guia **configuração \> de relevância de relevância** , selecione **cargas**.
    
2. Na lista de **Gerenciamento de cargas** , selecione uma carga e clique no ícone **Editar** . A janela Editar carregar é exibida. 
    
3. Insira as alterações e clique em **OK**.
    
## <a name="adding-imported-files-to-a-new-load"></a>Adicionando arquivos importados a uma nova carga

Depois de iniciar o treinamento de relevância ou executar o cálculo em lote, talvez você queira importar e processar um conjunto adicional de arquivos. 
  
Durante a atualização, você pode criar, marcar e analisar o conjunto de atualização. A descoberta eletrônica avançada compara sua avaliação de arquivos relevantes e não relevantes na nova carga para aqueles nas cargas anteriores. Com base nos resultados, você será solicitado a tomar decisões de ajuste, se necessário, e a descoberta eletrônica avançada fornecerá recomendações com base nas informações de relevância acumuladas. 
  
As cargas sem interrupção e a funcionalidade de atualização variam da seguinte maneira: 
  
- Quando você importa uma nova carga de arquivo após o cálculo de lote, a descoberta eletrônica avançada determina para qual extensão os arquivos estão em uma das seguintes categorias:
    
  - Semelhante (homogêneo): um novo e personalizado treinamento de relevância não é necessário e o conhecimento obtido da carga anterior pode ser aplicado "como está" à nova carga. 
    
  - Distinct (heterogêneo): um novo treinamento personalizado de relevância é necessário, e o conhecimento obtido da carga anterior não pode ser aplicado. 
    
    Esses termos se referem ao nível de similaridade de arquivos entre cargas e não dentro das cargas. 
    
- Ao importar um novo carregamento de arquivo durante o treinamento de relevância (antes do cálculo em lote), a atualização permite que você continue o treinamento de relevância no conjunto de arquivos do Reino. A descoberta eletrônica avançada não estima se a nova carga é semelhante ou distinta da carga anterior. Ele simplesmente coleta informações sobre a nova carga e permite que o treinamento de relevância continue nos conjuntos novos e anteriores de arquivos. 
    
- Quando há vários problemas no treinamento de relevância, bem como problemas após o cálculo de lote, o processo de atualização é executado uma vez para todos os problemas, e os resultados são calculados e exibidos para cada problema.
    
> [!NOTE]
> O tamanho do exemplo de atualização pode variar. Ele depende do tamanho da nova carga em relação às cargas anteriores e no número de amostras concluídas antes da adição da nova carga. O exemplo de atualização normalmente é um conjunto de 200 a 2.000 arquivos da nova carga. 
  
> [!TIP]
> A atualização para todas as outras tarefas e requer a marcação e a revisão de arquivos individuais. Portanto, você pode reduzir a sobrecarga ao adicionar novos arquivos em lotes grandes. 
  
## <a name="adding-a-new-file-load-using-catch-up-and-rolling-loads"></a>Adicionando uma nova carga de arquivos usando cargas de captura e de rolagem

1. Na guia **configuração \> de relevância de relevância** , selecione **cargas**.
    
2. Em **Gerenciamento de cargas**, clique **+** no ícone para adicionar uma carga. Uma mensagem de confirmação é exibida. 
    
3. Clique em **Sim** para continuar. A caixa de diálogo **Adicionar novo carregamento** é exibida. 
    
    > [!NOTE]
    > Você só pode adicionar uma nova carga se as ações foram executadas à carga anterior. 
  
4. Na caixa de diálogo **Adicionar novo carregamento** , digite as informações em **nome da carga** e **Descrição** e clique em **OK**. A descoberta eletrônica avançada adiciona uma nova carga.
    
5. Para importar o novo arquivo de carga, clique em **Adicionar arquivos**. Todos os novos arquivos são adicionados a esse carregamento. Depois que a descoberta eletrônica avançada importa os arquivos, ele reconhece o cenário de cargas sem interrupção e indica o ajuste como a próxima etapa.
    
6. Clique em **acompanhar** na parte inferior da caixa de diálogo para executar o cenário. 
    
    Um conjunto de atualização único, geralmente contendo 200 a 2.000 arquivos da nova carga, é criado para todos os problemas para permitir a marcação de arquivos simultâneas.
    
    Os detalhes são fornecidos sobre se as cargas são parecidas ou distintas, se a descoberta eletrônica avançada mesclou ou divide as cargas automaticamente e informações sobre o processamento na próxima etapa.
    
    Em seguida, você pode marcar arquivos e executar uma operação de cálculo. A marcação permite que a relevância determine se as cargas são similares ou distintas e permite que você continue trabalhando no novo conjunto de arquivos.
    
7. Após o conjunto de atualização ser revisado, exiba o **controle de relevância \> ** para os resultados de pesquisa. 
    
1. Se a nova carga de arquivos foi adicionada durante o treinamento de relevância (o que significa que o problema ainda não passou no cálculo em lote), o **treinamento de continuação** é a próxima etapa, independentemente dos resultados de atualização. 
    
    As cargas novas e anteriores são processadas à medida que um treinamento de carga e relevância continua no conjunto da United. Você já terminou este procedimento e pode continuar o treinamento de relevância. 
    
2. Se a nova carga foi adicionada após o cálculo em lote, prossiga com as etapas a seguir.
    
8. Para novas cargas adicionadas após o cálculo em lotes, a descoberta eletrônica avançada determina se a nova carga é semelhante ou distinta das cargas anteriores, como a seguir:
    
1. Se as cargas foram semelhantes: nenhum treinamento adicional de relevância é necessário. O painel mostra a próxima etapa recomendada é executar o cálculo de lote * * novamente para calcular as pontuações de relevância para a nova carga. As cargas foram parecidas, portanto, a análise do classificador anterior pode ser executada nos novos arquivos. 
    
2. Se as cargas foram distintas: é necessário mais treinamento de relevância e a próxima etapa é a decisão de acompanhamento. Selecione uma decisão de ajuste da seguinte maneira:
    
    Se você selecionar **mesclar cargas**, as mesclagens de descoberta eletrônica avançada e as novas cargas anteriores e novas para o conjunto de treinamento. Embora o primeiro carregamento tenha sido calculado em lote, mais treinamento é necessário. Continue treinando as cargas novas e anteriores juntas. Em seguida, o cálculo em lotes será executado novamente e as pontuações de cálculo em lotes anteriores deverão ser ignoradas. Escolha esta seleção quando as pontuações de relevância para cargas existentes puderem ser recalculadas, por exemplo, quando a revisão das cargas de arquivo existentes não tiver sido iniciada.
    
    Se você selecionar **cargas divididas**, continue o treinamento de relevância apenas na nova carga. Nesta instância, as pontuações de cálculo em lotes anteriores permanecerão como estão. Escolha essa opção quando as pontuações de relevância existentes para as cargas existentes não puderem ser recalculadas, por exemplo, se a análise de cargas existentes já tiver sido iniciada. As pontuações de relevância são gerenciadas separadamente desse ponto em diante e não podem ser mescladas.
    
3. Clique em **continuar treinamento**.
    
## <a name="see-also"></a>Também consulte

[Descoberta Eletrônica Avançada (clássica)](office-365-advanced-ediscovery.md)
  
[Como definir problemas e atribuir usuários](define-issues-and-assign-users.md)
  
[Como definir as palavras-chave realçadas e opções avançadas](define-highlighted-keywords-and-advanced-options.md)

