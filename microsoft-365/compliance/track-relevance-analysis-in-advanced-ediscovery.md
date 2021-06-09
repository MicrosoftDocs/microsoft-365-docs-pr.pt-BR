---
title: Rastrear análise de relevância no Advanced eDiscovery
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
ms.assetid: 3ab1e2c3-28cf-4bf5-b0a8-c0222f32bdf5
ROBOTS: NOINDEX, NOFOLLOW
description: Saiba como exibir e interpretar o status e os resultados do treinamento de relevância para problemas de caso Advanced eDiscovery.
ms.openlocfilehash: 224337969b5e662d45c5b804fa5a0ee045f4fb84
ms.sourcegitcommit: 5ba0015c1554048f817fdfdc85359eee1368da64
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/06/2021
ms.locfileid: "49769176"
---
# <a name="track-relevance-analysis-in-advanced-ediscovery"></a>Rastrear análise de relevância no Advanced eDiscovery
  
No Advanced eDiscovery, a guia Faixa de Relevância exibe a validade calculada do treinamento de relevância executado na guia Marca e indica a próxima etapa a ser seguida no processo de treinamento iterativo em Relevância. 
  
## <a name="tracking-relevance-training-status"></a>Status do treinamento de relevância de rastreamento

1. Veja os detalhes a seguir em Faixa de Relevância para os problemas de caso, conforme mostrado no exemplo a seguir de uma caixa de diálogo **Nome de** problema abaixo.

   - **Avaliação**: esse indicador de progresso mostra até que ponto o treinamento de relevância executado até esse ponto atingiu a meta de avaliação em termos de margem de erro. A riqueza dos resultados do treinamento de relevância também é exibida.

   - **Treinamento**: este indicador de progresso codificado por cores e dica de ferramenta indica a estabilidade dos resultados do treinamento de relevância e uma escala numérica mostrando o número de amostras de treinamento de relevância marcadas para cada problema. O especialista monitora o andamento do processo de treinamento de relevância iterativa. 
  
   - **Cálculo em lotes**: Este indicador de progresso fornece informações sobre a conclusão do cálculo em lotes.
  
   - **Próxima etapa**: Exibe a recomendação para a próxima etapa a ser executada. 
  
    No exemplo, uma Avaliação concluída com êxito para um problema é mostrada, indicada pelo indicador de progresso de cores concluído e pela marca de seleção. A marcação está em andamento, mas o caso ainda é considerado instável (status de estabilidade também mostrado em uma dica de ferramenta). A recomendação da próxima etapa é "Treinamento". 
  
    ![Etapa 1 do treinamento do Controle de Relevância](../media/a00fe607-680a-48eb-9d61-4565319f7ab6.png)
  
    O visor expandido exibe informações e opções adicionais. A margem de erro atual exibida é a margem de erro do recall no estado atual da avaliação, considerando os arquivos de avaliação existentes (já marcados).
  
    > [!NOTE]
    >  O estágio de Avaliação pode ser ignorado limpando a caixa de seleção **Avaliação** por problema e, em seguida, para "todos os problemas". No entanto, como resultado, não haverá estatísticas para esse problema. > a caixa de seleção **Limpar** a Avaliação só pode ser feita antes que a avaliação seja realizada. Onde existem vários problemas em um caso, a avaliação é ignorada somente se a caixa de seleção for desapurada para cada problema 
  
    Quando a avaliação não é concluída com o primeiro conjunto de exemplos de arquivos, a avaliação pode ser a próxima etapa para marcar mais arquivos.
  
    Em **Faixa de Relevância** , o indicador de progresso de treinamento e a dica de ferramenta indicam o número estimado de amostras adicionais \> necessárias para alcançar a estabilidade. Essa estimativa fornece uma diretriz para o treinamento adicional necessário.
  
    ![Treinamento do controle de relevância](../media/98dbc3f5-5238-4d73-9f88-1aa4d77ea729.png)
  
2. Quando terminar a marcação e se precisar continuar o treinamento, clique em **Treinamento**. Outro conjunto de exemplos de arquivos é gerado a partir do conjunto de arquivos carregados para treinamento adicional. Em seguida, você é retornado para a guia Marca para marcar e treinar mais arquivos.

### <a name="reaching-stable-training-levels"></a>Atingir níveis de treinamento estáveis

Depois que os arquivos de avaliação atingirem um nível estável de treinamento, Advanced eDiscovery estará pronto para cálculo em lotes.
  
> [!NOTE]
> Normalmente, após três exemplos de treinamento estáveis, a próxima etapa é "Cálculo em lotes". Pode haver exceções, por exemplo, quando houve alterações na marcação de arquivos de exemplos anteriores ou quando arquivos de semente foram adicionados. 
  
### <a name="performing-batch-calculation"></a>Executando cálculo em lotes

O cálculo em lotes é executado como a próxima etapa após a conclusão do treinamento com êxito (quando um status de treinamento estável é mostrado pela barra de progresso, uma marca de seleção e um status estável na dica de ferramenta.) O cálculo em lotes aplica o conhecimento adquirido durante o treinamento de relevância para toda a população de arquivos, para avaliar a relevância dos arquivos e atribuir pontuações de relevância.
  
Quando há mais de um problema, o cálculo em lotes é feito por problema. Durante o cálculo em lote, o andamento é monitorado durante o processamento de todos os arquivos. 
  
Aqui, a próxima etapa recomendada é "None", que indica que nenhum treinamento adicional de Relevância Iterativa é necessário neste ponto. A próxima fase é **a guia Decidir \> relevância.** 
  
Se você quiser importar novos arquivos após o cálculo em lotes, o administrador poderá adicionar os arquivos importados a uma nova carga.
  
> [!NOTE]
> Se você clicar em **Cancelar** durante o cálculo em lote, o processo salvará o que já foi executado. Se você executar o cálculo em lote novamente, o processo continuará a partir do último ponto executado. 
  
### <a name="assessing-tagging-consistency"></a>Avaliando a consistência de marcação

Se houver inconsistências na marcação de arquivo, isso pode afetar a análise. O Advanced eDiscovery de consistência de marcação pode ser usado quando os resultados não são ideais ou a consistência está em dúvida. Uma lista de possíveis arquivos marcados de forma inconsistente é retornada e eles podem ser revisados e retomados, conforme necessário.
  
> [!NOTE]
> Após sete ou mais rodadas de treinamento após a avaliação, a consistência de marcação pode ser exibida em **Problemas** de Faixa de Relevância \>  \>  \> **Resultados detalhados** \> **Andamento do treinamento.** Esta revisão é feita para um problema de cada vez.
  
1. Em **Faixa de \> Relevância,** expanda a linha de um problema.
  
2. À direita da **próxima etapa,** clique em **Modificar**.
  
3. Selecione **Marca inconsistências** como **a opção Próxima etapa,** após sete exemplos de treinamento e clique em **OK**.
  
4. Selecione **Inconsistências de marca**. A **guia Marca** é aberta exibindo uma lista das inconsistências a ser retag, conforme necessário.
  
5. Clique **em Calcular** para enviar as alterações. A próxima etapa após a marcação de inconsistências é "Treinamento". 
  
## <a name="viewing-and-using-relevance-results"></a>Exibindo e usando resultados de relevância

Na guia **Faixa de \> Relevância,** expanda a linha de um problema e, ao lado de **Resultados** detalhados, clique em **Exibir**. Os painéis de resultados detalhados são exibidos, conforme mostrado e descrito abaixo.
  
![Resultados detalhado do treinamento de relevância](../media/495c04a9-ed1e-4355-8cab-c14270ca2bbb.png)
  
### <a name="tagging-summary"></a>Resumo de marcação

 No exemplo mostrado abaixo, o resumo **de Marcação** exibe totais para cada um dos processos de marcação de arquivo de Avaliação, Treinamento e Captura.
  
![Resumo de marcação de controle de relevância](../media/0ec906fc-bc84-4245-a964-fb3ca37891db.png)
  
### <a name="keywords"></a>Palavras-chave

Uma palavra-chave é uma cadeia de caracteres, palavra, frase ou sequência exclusiva de palavras em um arquivo identificado Advanced eDiscovery como um indicador significativo de se um arquivo é relevante. As colunas "Incluir" listam palavras-chave e pesos em arquivos marcados como Relevantes, e as colunas "Excluir" listam palavras-chave e pesos em arquivos marcados como Não relevantes.
  
Advanced eDiscovery atribui valores de peso de palavra-chave negativos ou positivos. Quanto maior o peso, maior será a probabilidade de que um arquivo no qual a palavra-chave apareça tenha uma pontuação de Relevância mais alta durante o cálculo em lotes.
  
A Advanced eDiscovery de palavras-chave pode ser usada para complementar uma lista criada por um especialista ou como uma verificação de sanidade indireta em qualquer ponto do processo de revisão de arquivo.
  
### <a name="training-progress"></a>Progresso do treinamento

O **painel Progresso do** Treinamento inclui um gráfico de progresso de treinamento e uma exibição de indicador de qualidade, conforme mostrado no exemplo abaixo.
  
![Progresso do treinamento do Controle de Relevância](../media/8a5089f5-a162-4246-ae09-bc1921859860.png)
  
**Indicador de qualidade de** treinamento : exibe a classificação da consistência de marcação da seguinte forma:
  
- **Bom:** os arquivos são marcados de forma consistente. (Luz verde exibida)
  
- **Médio**: Alguns arquivos podem ser marcados inconsistentemente. (Luz amarela exibida)

- **Aviso:** muitos arquivos podem ser marcados de forma inconsistente. (Luz vermelha exibida)

**Gráfico de progresso do** treinamento : mostra o grau de estabilidade do treinamento de relevância após muitos ciclos de treinamento de relevância em comparação com o valor da medida F. À medida que movemos da esquerda para a direita no gráfico, o intervalo de confiança estreita e é usado, juntamente com a medida F, pela relevância Advanced eDiscovery para determinar a estabilidade quando os resultados do treinamento de relevância são otimizados.
  
> [!NOTE]
> A relevância usa F2, uma métrica de medida F em que Recall recebe duas vezes mais peso que Precision. Para casos com alta riqueza (mais de 25%), a Relevância usa F1 (taxa de 1:1). A taxa de medida F pode ser configurada em **Configurações avançadas** de configuração \> **de relevância.**
  
### <a name="batch-calculation-results"></a>Resultados do cálculo em lotes

O **painel de resultados de** cálculo em lotes inclui o número de arquivos que foram marcados para Relevância, da seguinte forma: 
  
- **Success**
  
- **Vazio**: não contém texto, por exemplo, somente espaços/guias
  
- **Falha**: devido ao tamanho excessivo ou não pôde ser lido
  
- **Ignorado :** devido ao tamanho excessivo
  
- **Nebulous**: contém texto sem sentido ou nenhum recursos relevantes para o problema
  
> [!NOTE]
> Empty, Failed, Ignored, or Nebulous will receive a Relevance score of -1.
  
### <a name="training-statistics"></a>Estatísticas de treinamento

O **painel Estatísticas de** treinamento exibe estatísticas e gráficos com base nos resultados Advanced eDiscovery treinamento de relevância. 
  
![Estatística do treinamento do controle de relevância](../media/9a07740e-20d3-49fb-b9b9-84265e0a1836.png)
  
Esta exibição mostra o seguinte:
  
- **Taxa de reavaliação-recall**: comparação de resultados de acordo com as pontuações de relevância em uma revisão hipoteticamente linear. O recall é estimado devido ao conjunto de tamanhos do conjunto de revisão.
  
- **Parâmetros**: Estatísticas calculadas cumulativas referentes ao conjunto de revisão em relação à população de arquivos para todo o caso.
  
- **Revisão**: Porcentagem de arquivos a analisar com base nesse recorte.
  
- **Recall**: Porcentagem de arquivos relevantes no conjunto de revisão. 
  
- **Distribuição por pontuação de relevância:** Os arquivos na exibição cinza escuro à esquerda estão abaixo da pontuação de recorte. Uma dica de ferramenta exibe a pontuação de relevância e a porcentagem relacionada de arquivos no conjunto de arquivos de revisão em relação ao total de arquivos.
