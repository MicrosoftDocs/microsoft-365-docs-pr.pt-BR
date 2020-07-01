---
title: Rastrear a análise de relevância na descoberta eletrônica avançada
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
ms.assetid: 3ab1e2c3-28cf-4bf5-b0a8-c0222f32bdf5
description: Saiba como exibir e interpretar o status de treinamento de relevância e os resultados para problemas de caso em descoberta eletrônica avançada.
ms.openlocfilehash: bf1fe2fc6c0f3ff80fd7e53d55149a61009e2b32
ms.sourcegitcommit: c43ebb915fa0eb7eb720b21b62c0d1e58e7cde3d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/30/2020
ms.locfileid: "44936214"
---
# <a name="track-relevance-analysis-in-advanced-ediscovery-classic"></a>Rastrear a análise de relevância na descoberta eletrônica avançada (clássica)

> [!NOTE]
> Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279). 
  
Na descoberta eletrônica avançada, a guia controle de relevância exibe a validade calculada do treinamento de relevância executado na guia marca e indica a próxima etapa a ser tomada em relevância do processo de treinamento iterativo. 
  
## <a name="tracking-relevance-training-status"></a>Status de treinamento de relevância de rastreamento

1. Exibir os seguintes detalhes no controle de relevância para os problemas de caso, conforme mostrado no exemplo a seguir de uma caixa de diálogo de **nome de problema** abaixo. 
    
  - **Avaliação**: Este indicador de progresso mostra a que grau o treinamento de relevância realizado neste ponto atingiu o alvo da avaliação em termos de margem de erro. A riqueza dos resultados de treinamento de relevância também é exibida. 
    
  - **Treinamento**: Este indicador de progresso por cores e exibição de dica de ferramenta indica a estabilidade dos resultados de treinamento de relevância e uma escala numérica que mostra o número de amostras de treinamento de relevância marcadas para cada problema. O especialista monitora o andamento do processo de treinamento de relevância iterativa. 
    
  - **Cálculo em lote**: Este indicador de progresso fornece informações sobre a conclusão do cálculo em lote.
    
  - **Próxima etapa**: exibe a recomendação para que a próxima etapa seja executada. 
    
    No exemplo, uma avaliação concluída com êxito para um problema é exibida, indicada pelo indicador de progresso de cor preenchido e pela marca de execução. A marcação está em andamento, mas o caso ainda é considerado instável (o status de estabilidade também é mostrado em uma dica de ferramenta). A recomendação de próxima etapa é "treinamento". 
    
    ![Etapa 1 do treinamento do Controle de Relevância](../media/a00fe607-680a-48eb-9d61-4565319f7ab6.png)
  
    O modo de exibição expandido exibe informações e opções adicionais. A margem de erro atual exibida é a margem de erro da recuperação no estado atual de avaliação, dado os arquivos de avaliação existentes (já marcados).
    
    > [!NOTE]
    >  O estágio de avaliação pode ser ignorado, desmarcando a caixa de seleção de **avaliação** por problema e, em seguida, para "todos os problemas". No entanto, como resultado, não haverá estatísticas para esse problema. > limpar a caixa de seleção de **avaliação** só pode ser feita antes da avaliação ser realizada. Onde houver vários problemas em um caso, a avaliação será ignorada somente se a caixa de seleção estiver desmarcada para cada problema 
  
    Quando a avaliação não é concluída com o primeiro conjunto de exemplos de arquivos, a avaliação pode ser a próxima etapa para marcar mais arquivos. 
    
    No **Relevance** \> **controle**de relevância, o indicador de progresso de treinamento e a dica de ferramenta indicam o número estimado de amostras adicionais necessárias para alcançar a estabilidade. Esta estimativa fornece uma diretriz para o treinamento adicional necessário.
    
    ![Treinamento do controle de relevância](../media/98dbc3f5-5238-4d73-9f88-1aa4d77ea729.png)
  
2. Quando tiver terminado a marcação e se precisar continuar o treinamento, clique em **treinamento**. Outro conjunto de exemplos de arquivos é gerado a partir do conjunto de arquivos carregado para obter treinamento adicional. Em seguida, você retorna à guia marca para marcar e treinar mais arquivos.
    
### <a name="reaching-stable-training-levels"></a>Atingir níveis de treinamento estáveis

Após os arquivos de avaliação terem alcançado um nível estável de treinamento, a descoberta eletrônica avançada estará pronta para o cálculo em lote.
  
> [!NOTE]
> Normalmente, após três amostras de treinamento estáveis, a próxima etapa é "cálculo em lote". Podem haver exceções, por exemplo, quando houve alterações na marcação de arquivos de exemplos anteriores ou quando os arquivos semente foram adicionados. 
  
### <a name="performing-batch-calculation"></a>Executando cálculo em lote

O cálculo de lote é executado como a próxima etapa após o treinamento ter sido concluído com êxito (quando um status de treinamento estável é mostrado pela barra de progresso, uma marca de e o status de estável na ferramenta dica.) O cálculo de lote aplica o conhecimento adquirido durante o treinamento de relevância a todo o preenchimento de arquivo, para avaliar a relevância dos arquivos e para atribuir pontuações de relevância.
  
Quando há mais de um problema, o cálculo do lote é feito por questão. Durante o cálculo do lote, o andamento é monitorado durante o processamento de todos os arquivos. 
  
Aqui, a próxima etapa recomendada é "nenhum", que indica que nenhum treinamento adicional de relevância iterativa é necessário neste ponto. A fase seguinte é a de **relevância- \> decisão** . 
  
Se você deseja importar novos arquivos após o cálculo de lote, o administrador pode adicionar os arquivos importados a uma nova carga.
  
> [!NOTE]
> Se você clicar em **Cancelar** durante o cálculo do lote, o processo salvará o que já foi executado. Se você executar o cálculo em lotes novamente, o processo continuará a partir do último ponto executado. 
  
### <a name="assessing-tagging-consistency"></a>Avaliando a consistência de marcação

Se houver inconsistências na marcação de arquivos, ela poderá afetar a análise. O processo de consistência de marcação de descoberta eletrônica avançada pode ser usado quando os resultados não são ideais ou a consistência está em dúvida. Uma lista de possíveis arquivos marcados inconsistentes é retornada, e eles podem ser revisados e remarcados, conforme necessário.
  
> [!NOTE]
> Após sete ou mais rodadas de treinamento após a avaliação, a consistência de marcação **Relevance** pode ser visualizada no andamento do \> **Track** \> **Issue** \> treinamento de **resultados detalhados** do problema de controle \> **Training progress**de relevância. Essa análise é feita para um problema de cada vez. 
  
1. No ** \> controle de relevância**, expanda a linha de um problema.
    
2. À direita da **próxima etapa**, clique em **Modificar**.
    
3. Selecione **inconsistências de marca** como a opção **próxima etapa** , após sete amostras de treinamento e clique em **OK**.
    
4. Selecione **inconsistências de marca**. A guia **marca** é aberta exibindo uma lista das inconsistências a serem marcadas novamente, conforme necessário. 
    
5. Clique em **calcular** para enviar as alterações. A próxima etapa após a marcação de inconsistências é "treinamento". 
    
## <a name="viewing-and-using-relevance-results"></a>Exibindo e usando resultados de relevância

Na guia ** \> controle de relevância** , expanda a linha de um problema e ao lado de **resultados detalhados**, clique em **Exibir**. Os painéis de resultados detalhados são exibidos, conforme mostrado e descrito abaixo.
  
![Resultados detalhado do treinamento de relevância](../media/495c04a9-ed1e-4355-8cab-c14270ca2bbb.png)
  
### <a name="tagging-summary"></a>Resumo de marcação

 No exemplo mostrado abaixo, o **Resumo de marcação** exibe os totais para cada um dos processos de marcação de avaliação, treinamento e arquivo de verificação. 
  
![Resumo de marcação de controle de relevância](../media/0ec906fc-bc84-4245-a964-fb3ca37891db.png)
  
### <a name="keywords"></a>Keywords

Uma palavra-chave é uma cadeia de caracteres exclusiva, palavra, frase ou sequência de palavras em um arquivo identificado por uma descoberta eletrônica avançada como um indicador significativo do fato de um arquivo ser relevante. A palavra-chave "include" da lista de colunas e os pesos em arquivos marcados como relevantes e as colunas "exclude" lista palavras-chave e pesos em arquivos marcados como não relevantes.
  
A descoberta eletrônica avançada atribui valores de peso de palavra-chave negativas ou positivos. Quanto maior o peso, maior a probabilidade de um arquivo em que a palavra-chave seja exibida é atribuída uma pontuação de relevância maior durante o cálculo do lote. 
  
A lista de descoberta eletrônica avançada de palavras-chave pode ser usada para complementar uma lista criada por um especialista ou como uma verificação de sanidade indireta em qualquer ponto do processo de revisão de arquivo.
  
### <a name="training-progress"></a>Progresso do treinamento

O painel **andamento do treinamento** inclui um gráfico de progresso de treinamento e um indicador de qualidade, conforme mostrado no exemplo abaixo. 
  
![Progresso do treinamento do Controle de Relevância](../media/8a5089f5-a162-4246-ae09-bc1921859860.png)
  
 **Indicador de qualidade de treinamento**: exibe a classificação da consistência de marcação da seguinte maneira:
  
- **Boa**: os arquivos são marcados de forma consistente. (Luz verde exibida)
    
- **Médio**: alguns arquivos podem ser marcados de forma inconsistente. (Luz amarela exibida)
    
- **Aviso**: muitos arquivos podem ser marcados de forma inconsistente. (Luz vermelha exibida)
    
 **Gráfico de progresso do treinamento**: mostra o grau de estabilidade de treinamento de relevância após vários ciclos de treinamento de relevância em comparação ao valor de medida F. À medida que mudamos da esquerda para a direita no gráfico, o intervalo de confiança diminui e é usado, juntamente com a medida F, por uma relevância avançada de descoberta eletrônica para determinar a estabilidade quando os resultados de treinamento de relevância são otimizados.
  
> [!NOTE]
> A relevância usa F2, uma métrica de c-Measure onde a recuperação recebe duas vezes mais peso que a precisão. Para casos com grande riqueza (mais de 25%), a relevância usa F1 (taxa de 1:1). A taxa de medida de F pode ser configurada em **Relevance setup** \> **Configurações avançadas**de configuração de relevância. 
  
### <a name="batch-calculation-results"></a>Resultados do cálculo em lote

O painel **resultados do cálculo em lotes** inclui o número de arquivos que foram pontuados para fins de relevância da seguinte maneira: 
  
- **Success**
    
- **Vazio**: não contém texto, por exemplo, somente espaços/abas
    
- **Falha**: devido a tamanho excessivo ou não pôde ser lido
    
- **Ignorado**: devido ao tamanho excessivo
    
- **Nebulous**: contém texto sem sentido ou nenhum recurso relevante para o problema
    
> [!NOTE]
> Empty, Failed, ignored ou nebulous receberá uma pontuação de relevância de-1. 
  
### <a name="training-statistics"></a>Estatísticas de treinamento

O painel **Estatísticas de treinamento** exibe as estatísticas e os gráficos com base nos resultados do treinamento de relevância de descoberta eletrônica avançada. 
  
![Estatística do treinamento do controle de relevância](../media/9a07740e-20d3-49fb-b9b9-84265e0a1836.png)
  
Este modo de exibição mostra o seguinte:
  
- **Taxa de recuperação de revisão**: comparação de resultados de acordo com as pontuações de relevância em uma revisão hipotéticamente linear. A rechamada é estimada de acordo com o tamanho do conjunto de revisão definido.
    
- **Parâmetros**: estatísticas calculadas cumulativas pertencentes ao conjunto de revisão em relação à população de arquivo para o caso inteiro.
    
- **Revisão**: porcentagem de arquivos a serem revisados com base nesse corte.
    
- **Recall**: porcentagem de arquivos relevantes no conjunto de revisão. 
    
- **Distribuição por Pontuação de relevância**: os arquivos na exibição cinza escuro à esquerda estão abaixo da Pontuação de corte. Uma dica de ferramenta exibe a pontuação de relevância e a porcentagem relacionada de arquivos no conjunto de arquivos de revisão em relação ao total de arquivos.
    
## <a name="see-also"></a>Também consulte

[Descoberta Eletrônica Avançada (clássica)](office-365-advanced-ediscovery.md)
  
[Noções básicas sobre avaliação em relevância](assessment-in-relevance-in-advanced-ediscovery.md)
  
[Realizando e revisando a avaliação](tagging-and-assessment-in-advanced-ediscovery.md)
  
[Realizando treinamento de relevância](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[Tomada de decisões com base nos resultados](decision-based-on-the-results-in-advanced-ediscovery.md)
  
[Testando análise de relevância](test-relevance-analysis-in-advanced-ediscovery.md)

