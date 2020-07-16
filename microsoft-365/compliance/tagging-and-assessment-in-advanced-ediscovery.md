---
title: Marcação e avaliação na descoberta eletrônica avançada
f1.keywords:
- NOCSH
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
ms.assetid: b5c82de7-ed2f-4cc6-becd-db403faf4d18
description: Revise as etapas para executar o treinamento de avaliação, incluindo arquivos de marcação e revisar os resultados da avaliação na descoberta eletrônica avançada.
ms.openlocfilehash: 57e4e8da0dbeec5e1dba384ae0e62ffb6b3bb03a
ms.sourcegitcommit: c43ebb915fa0eb7eb720b21b62c0d1e58e7cde3d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/30/2020
ms.locfileid: "44936688"
---
# <a name="tagging-and-assessment-in-advanced-ediscovery-classic"></a>Marcação e avaliação na descoberta eletrônica avançada (clássica)

> [!NOTE]
> A Descoberta Eletrônica Avançada exige um Office 365 E3, com um complemento de Conformidade Avançada ou uma assinatura do E5 para sua organização. Se você não tiver esse plano e quiser tentar a Descoberta Eletrônica Avançada, poderá [Inscrever-se para uma avaliação do Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279). 
  
Esta seção descreve o procedimento para o módulo de avaliação de relevância de descoberta eletrônica avançada. 
  
## <a name="performing-assessment-training-and-analysis"></a>Realizando treinamento e análise de avaliação

1. Na guia ** \> controle de relevância** , clique em **avaliação** para iniciar a avaliação de caso. 
    
    Por exemplo, neste procedimento, um conjunto de avaliação de amostra de 500 arquivos é criado e a guia **marca** é exibida, que contém o painel de marcação, o conteúdo do arquivo exibido e outras opções de marcação. 
    
    ![Guia Marca de Relevância para Avaliação](../media/c8acf891-b1cd-4344-816c-eabb8cbbe742.png)
  
2. Revise cada arquivo no exemplo, determine a relevância do arquivo para cada problema de caso e marque o arquivo usando os botões relevância (R), não relevante (NR) e pular no painel **painel de marcação** . 
    
    > [!NOTE]
    >  A avaliação requer arquivos marcados 500. Se os arquivos forem "ignorados", você receberá mais arquivos para marcá-los. 
  
3. Depois de marcar todos os arquivos no exemplo, clique em **calcular**. 
    
    A margem de erro atual de avaliação e a riqueza são calculadas e exibidas na guia **controle de relevância** , com detalhes expandidos por problema, conforme mostrado abaixo. Mais detalhes sobre esta caixa de diálogo são descritos na seção posterior "resultados da análise de avaliações". 
    
    ![Controle de relevância - avaliação](../media/da911ba5-8678-40d6-9ad5-fd0b058355c1.png)
  
    > [!TIP]
    > Por padrão, recomendamos que você prossiga para a próxima etapa padrão quando o indicador de progresso da avaliação do problema tiver sido concluído, indicando que o exemplo de avaliação foi revisado e que os arquivos relevantes suficientes foram marcados. > caso contrário, se você quiser exibir os resultados da guia **rastrear** e controlar a margem de erro e a próxima etapa, clique em **Modificar** adjacente à **próxima etapa**, selecione **continuar avaliação**e clique em **OK**. 
  
1. Clique em **Modificar** à direita da caixa de seleção de **avaliação** para exibir e especificar os parâmetros de avaliação por problema. Uma caixa de diálogo de **nível de avaliação** para cada problema é exibida, conforme mostrado no exemplo a seguir: 
    
    ![Problema de caso de nível de avaliação](../media/b7113fef-d125-4617-ae1b-c9eb0bf79aec.png)
  
    Os seguintes parâmetros para o problema são calculados e exibidos na caixa de diálogo **nível de avaliação** : 
    
    **Margem de erro de destino para estimativas de cancelamento**: com base nesse valor, o número estimado de arquivos adicionais necessários para a revisão é calculado. A margem usada para a recuperação é maior que 75% e com um nível de confiança 95%. 
    
    **Arquivos de avaliação adicionais necessários**: indica o número de arquivos necessários se os requisitos da margem de erro atual não tiverem sido atendidos. 
    
2. Para ajustar a margem de erro atual e ver o efeito de diferentes margens de erro (por problema):
    
1. Na lista **selecionar problema** , selecione um problema. 
    
2. Em **margem de erro de destino para estimativas de cancelamento**, insira um novo valor.
    
3. Clique em **atualizar valores** para ver o impacto dos ajustes. 
    
3. Clique em **avançado** na caixa de diálogo **nível de avaliação** para ver os seguintes parâmetros e detalhes adicionais: 
    
    ![Exibição avançada de problema de caso de nível de avaliação](../media/577d7e0e-95df-48c2-9dec-bdeab5e801d8.png)
  
    **Riqueza estimada**: riqueza estimada de acordo com os resultados da avaliação atual
    
    **Para recalls presumidos**: por padrão, a margem de erro de destino se aplica à recuperação acima de 75%. Clique em **Editar** se quiser alterar esse parâmetro e controlar a margem de erro em um intervalo diferente de valores de recuperação. 
    
    **Nível de confiança**: por padrão, a margem de erro recomendada para confiança é de 95%. Clique em **Editar** se quiser alterar esse parâmetro. 
    
    **Margem de erro de riqueza esperada**: dado os valores atualizados, esta é a margem esperada de erro da riqueza, após todos os arquivos de avaliação adicionais serem revisados.
    
    **Arquivos de avaliação adicionais necessários**: dado os valores atualizados, o número de arquivos de avaliação adicionais que precisam ser revisados para chegar ao destino.
    
    **Total de arquivos de avaliação necessários**: dado os valores atualizados, os arquivos de avaliação total necessários para análise.
    
    **Número esperado de arquivos relevantes na avaliação**: dado os valores atualizados, o número esperado de arquivos relevantes em toda a avaliação após todos os arquivos de avaliação adicionais serem analisados.
    
4. Clique em **Recalcular valores**, se os parâmetros forem alterados. Quando você terminar, se houver um problema, clique em **OK** para salvar as alterações (ou **ao avançar** quando houver vários problemas para revisar ou modificar e depois **concluir**). 
    
    Quando há vários problemas, após todos os problemas terem sido revisados ou ajustados, um **nível de avaliação: Resumo** é exibido, conforme mostrado no exemplo a seguir. 
    
    ![Resumo do nível de análise](../media/4997b46d-10a5-4abc-b3b2-7b75a370eb9e.png)
  
    Após a conclusão bem-sucedida da avaliação, prossiga para o próximo estágio no treinamento de relevância.
    
## <a name="reviewing-assessment-results"></a>Analisar resultados da avaliação

Depois que um exemplo de avaliação é marcado, os resultados da avaliação são calculados e exibidos na guia controle de relevância.
  
Os resultados a seguir são exibidos na exibição de faixa expandida: 
  
- Margem de erro atual de avaliação para estimativas de cancelamento
    
- Riqueza estimada
    
- Arquivos de avaliação adicionais necessários (para revisão)
    
A margem de erro atual da avaliação é a margem de erro recomendada pela descoberta eletrônica avançada. O número exibido para os "arquivos de avaliação adicionais necessários" corresponde a essa recomendação.
  
O indicador de progresso da avaliação mostra o nível de conclusão da avaliação, considerando a margem de erro atual. Quando a avaliação estiver em andamento, o usuário marcará outro exemplo de avaliação.
  
Quando o indicador de progresso da avaliação mostrar a avaliação como concluída, isso significa que a análise da amostra de avaliação foi concluída e os arquivos relevantes suficientes foram marcados. 
  
A exibição de faixa expandida mostra a próxima etapa recomendada, as estatísticas de avaliação e o acesso aos resultados detalhados.
  
Quando a riqueza é muito baixa, o número de arquivos de avaliação adicionais necessários para atingir um número mínimo de arquivos relevantes para produzir estatísticas úteis é muito alto. A descoberta eletrônica avançada recomendará a migração para o treinamento. O indicador de progresso da avaliação será sombreado e nenhuma estatística estará disponível. 
  
Na ausência de estabilização com base Estatistica, haverá resultados com um nível inferior de precisão e nível de confiança. No entanto, esses resultados podem ser usados para localizar arquivos relevantes quando você não precisa saber a porcentagem de arquivos relevantes encontrados. Da mesma forma, esse status pode ser usado para treinar problemas com uma riqueza inferior, em que as pontuações de relevância podem acelerar o acesso a arquivos relevantes para um problema específico.
  
> [!TIP]
> Na guia ** \> controle de relevância** , exibição de problema expandido, as seguintes opções de exibição estão disponíveis: > a próxima etapa recomendada, como **próxima etapa: a marcação** pode ser ignorada (por problema) clicando no botão **Modificar** à direita e selecionando uma etapa diferente na **próxima etapa**. Quando o indicador de progresso da avaliação não for concluído, a avaliação será a próxima opção recomendada para marcar mais arquivos de avaliação e aumentar a precisão das estatísticas. > você pode alterar a margem de erro e avaliar seu impacto, clicando em **Modificar**e, na **caixa de diálogo nível de avaliação**, alterando a **margem de erro de destino para obter estimativas de cancelamento**e clicando em **atualizar valores**. Além disso, nessa caixa de diálogo, você pode exibir opções avançadas clicando em **avançado**. > você pode exibir estatísticas de nível de avaliação adicionais e seu impacto clicando em **Exibir**. Na caixa de diálogo resultados detalhados exibidos, as estatísticas estão disponíveis por questão, quando há pelo menos 500 arquivos de avaliação marcados e pelo menos 18 arquivos são marcados conforme relevante para o problema. 
  
## <a name="see-also"></a>Também consulte

[Descoberta Eletrônica Avançada (clássica)](office-365-advanced-ediscovery.md)
  
[Noções básicas sobre avaliação em relevância](assessment-in-relevance-in-advanced-ediscovery.md)
  
[Treinamento de marcação e relevância](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[Análise de relevância de rastreamento](track-relevance-analysis-in-advanced-ediscovery.md)
  
[Decidindo com base nos resultados](decision-based-on-the-results-in-advanced-ediscovery.md)
  
[Testando análise de relevância](test-relevance-analysis-in-advanced-ediscovery.md)

