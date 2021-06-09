---
title: Marcação e avaliação no Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
titleSuffix: Office 365
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: b5c82de7-ed2f-4cc6-becd-db403faf4d18
ROBOTS: NOINDEX, NOFOLLOW
description: Revise as etapas para executar o treinamento de Avaliação, incluindo arquivos de marcação e revisão dos resultados da avaliação Advanced eDiscovery.
ms.openlocfilehash: 15bc8254ea1589d9afa17a74eaf3bfbcdfd4bba0
ms.sourcegitcommit: 5ba0015c1554048f817fdfdc85359eee1368da64
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/06/2021
ms.locfileid: "49769186"
---
# <a name="tagging-and-assessment-in-the-relevance-module-in-advanced-ediscovery"></a>Marcação e Avaliação no módulo De relevância no Advanced eDiscovery
  
Esta seção descreve o procedimento para Avaliação no módulo De relevância no Advanced eDiscovery.
  
## <a name="performing-assessment-training-and-analysis"></a>Realizar treinamento e análise de Avaliação

1. Na guia **Faixa de \> Relevância,** clique em **Avaliação** para iniciar a avaliação de caso.

    Para fins de exemplo neste procedimento, um conjunto de avaliação de exemplo de 500 arquivos é criado e a guia **Marca** é exibida, que contém o painel De marcação, conteúdo de arquivo exibido e outras opções de marcação. 

    ![Guia Marca de Relevância para Avaliação](../media/c8acf891-b1cd-4344-816c-eabb8cbbe742.png)
  
2. Revise cada arquivo no exemplo, determine a relevância do arquivo para cada problema de caso e marque o arquivo usando os  botões Relevância (R), Não Relevante (NR) e Ignorar no painel Painel de Marcação. 

    > [!NOTE]
    >  A avaliação requer 500 arquivos marcados. Se os arquivos são "ignorados", você receberá mais arquivos para marcar. 
  
3. Depois de marcar todos os arquivos no exemplo, clique em **Calcular**.

    A margem de erro e a riqueza atuais  de Avaliação são calculadas e exibidas na guia Faixa de Relevância, com detalhes expandidos por problema, conforme mostrado abaixo. Mais detalhes sobre essa caixa de diálogo são descritos na seção [Revisão dos resultados da avaliação.](#reviewing-assessment-results)

    ![Controle de relevância - avaliação](../media/da911ba5-8678-40d6-9ad5-fd0b058355c1.png)
  
    > [!TIP]
    > Por padrão, recomendamos que você prossiga para a próxima etapa padrão quando o indicador de progresso da Avaliação para o problema tiver sido concluído, indicando que o exemplo de avaliação foi revisado e arquivos relevantes suficientes foram marcados. > Caso contrário, se você quiser  exibir os resultados da guia Controlar e  controlar a margem de erro e a próxima etapa, clique em Modificar adjacente à Próxima **Etapa,** selecione **Continuar** avaliação e clique em **OK**.
  
4. Clique **em Modificar** à direita da caixa de seleção **Avaliação** para exibir e especificar parâmetros de avaliação por problema. Uma **caixa de diálogo Nível** de Avaliação para cada problema é exibida, conforme mostrado no exemplo a seguir: 

    ![Problema de caso de nível de avaliação](../media/b7113fef-d125-4617-ae1b-c9eb0bf79aec.png)
  
    Os seguintes parâmetros para o problema são calculados e exibidos na caixa de diálogo **Nível de Avaliação:** 

    **Margem de erro de** destino para estimativas de recall : Com base nesse valor, o número estimado de arquivos adicionais necessários para revisão é calculado. A margem usada para recall é maior do que 75% e com um nível de confiança de 95%.

    **Arquivos de avaliação adicionais** necessários: indica quantos arquivos mais são necessários se os requisitos atuais da margem de erro não foram atendidos. 

5. Para ajustar a margem de erro atual e ver o efeito de diferentes margens de erro (por problema):

6. Na lista **Selecionar problema,** selecione um problema. 

7. Em **Margem de erro de destino para estimativas de** recall, insira um novo valor.

8. Clique **em Atualizar valores** para ver o impacto dos ajustes. 

9. Clique **em Avançado** na caixa de diálogo Nível de **Avaliação** para ver os seguintes parâmetros e detalhes adicionais: 

    ![Exibição avançada de problema de caso de nível de avaliação](../media/577d7e0e-95df-48c2-9dec-bdeab5e801d8.png)
  
    - **Riqueza estimada**: Riqueza estimada de acordo com os resultados atuais da avaliação

    - **Para recall presumido**: Por padrão, a margem de erro de destino se aplica ao recall acima de 75%. Clique **em Editar** se quiser alterar esse parâmetro e controlar a margem de erro em um intervalo diferente de valores de recall. 

    - **Nível de** confiança : Por padrão, a margem de erro recomendada para confiança é de 95%. Clique **em Editar** se quiser alterar esse parâmetro.

    - **Margem de erro** de riqueza esperada : Considerando os valores atualizados, essa é a margem de erro esperada da riqueza, depois que todos os arquivos de avaliação adicionais são revisados.

    - **Arquivos de avaliação adicionais necessários:** dados os valores atualizados, o número de arquivos de avaliação adicionais que precisam ser revisados para alcançar o destino.

    - **Total de arquivos de avaliação necessários**: Dados os valores atualizados, total de arquivos de avaliação necessários para revisão.

    - **Número esperado de arquivos relevantes** na avaliação : Dado os valores atualizados, o número esperado de arquivos relevantes em toda a avaliação depois que todos os arquivos de avaliação adicionais são revisados.

10. Clique **em Recalcular valores**, se os parâmetros são alterados. Quando terminar, se houver um problema, clique em **OK** para salvar as alterações (ou **Next** quando houver vários problemas para revisar ou modificar e, em seguida, **Concluir**). 

    Quando há vários problemas, depois que todos os problemas foram revisados ou ajustados, um nível de **Avaliação:** a caixa de diálogo resumo é exibida, conforme mostrado no exemplo a seguir. 

    ![Resumo do nível de análise](../media/4997b46d-10a5-4abc-b3b2-7b75a370eb9e.png)
  
    Após a conclusão bem-sucedida da avaliação, prossiga para o próximo estágio no treinamento de relevância.

## <a name="reviewing-assessment-results"></a>Revisão dos resultados da avaliação

Depois que um exemplo de Avaliação é marcado, os resultados da avaliação são calculados e exibidos na guia Faixa de Relevância.
  
Os seguintes resultados são exibidos na exibição Faixa expandida:
  
- Margem de erro atual de avaliação para estimativas de recall

- Riqueza estimada

- Arquivos de avaliação adicionais necessários (para revisão)

A margem de erro de Avaliação atual é a margem de erro recomendada por Advanced eDiscovery. O número exibido para os "Arquivos de avaliação adicionais necessários" corresponde a essa recomendação.
  
O indicador de progresso da Avaliação mostra o nível de conclusão da avaliação, considerando a margem de erro atual. Quando a avaliação estiver em andamento, o usuário marcará outro exemplo de avaliação.
  
Quando o indicador de progresso da avaliação mostra a avaliação como concluída, isso significa que a revisão de exemplo de avaliação foi concluída e arquivos relevantes suficientes foram marcados. 
  
A exibição faixa expandida mostra a próxima etapa recomendada, as estatísticas de avaliação e o acesso a resultados detalhados.
  
Quando a riqueza é muito baixa, o número de arquivos de avaliação adicionais necessários para alcançar um número mínimo de arquivos relevantes para produzir estatísticas úteis é muito alto. Advanced eDiscovery, em seguida, recomendamos passar para o treinamento. O indicador de progresso da avaliação será sombreado e nenhuma estatística estará disponível.
  
Na ausência de estabilização baseada em estatísticas, haverá resultados com um nível mais baixo de precisão e nível de confiança. No entanto, esses resultados podem ser usados para encontrar arquivos relevantes quando você não precisa saber a porcentagem de arquivos relevantes encontrados. Da mesma forma, esse status pode ser usado para treinar problemas com baixa riqueza, onde as pontuações de Relevância podem acelerar o acesso a arquivos relevantes a um problema específico.
  
> [!TIP]
> Na guia **Faixa de \> Relevância,** exibição de problemas expandidos, as seguintes opções de exibição estão disponíveis: 
> 
> A próxima etapa recomendada, como Próxima **etapa:** a marcação pode ser  ignorada (por problema) clicando no botão Modificar à direita e selecionando uma etapa diferente na **próxima etapa**. Quando o indicador de progresso da avaliação não for concluído, a avaliação será a próxima opção recomendada, para marcar mais arquivos de avaliação e aumentar a precisão de estatísticas. 
> 
> Você pode alterar a margem de erro e avaliar seu impacto, clicando em **Modificar** e na caixa de diálogo Nível de Avaliação, alterando a margem de erro de destino para **estimativas** de recall e clicando em Atualizar **valores**. Além disso, nesta caixa de diálogo, você pode exibir opções avançadas clicando em **Avançado**. 
> 
> Você pode exibir estatísticas adicionais de nível de avaliação e seu impacto clicando em **Exibir**. Na caixa de diálogo Resultados de detalhes exibidos, as estatísticas estão disponíveis por problema, quando há pelo menos 500 arquivos de avaliação marcados e pelo menos 18 arquivos são marcados como Relevantes para o problema. 
