---
title: Testar análise de relevância na descoberta eletrônica avançada
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
ms.assetid: 1b092f7c-ea55-44f5-b419-63f3458fd7e0
description: Saiba como usar a guia teste após o cálculo de lote em descoberta eletrônica avançada para testar, comparar e validar a qualidade geral do processamento.
ms.openlocfilehash: c5a885b3483b9ce319fffefa55037c0c2c8f3c85
ms.sourcegitcommit: c43ebb915fa0eb7eb720b21b62c0d1e58e7cde3d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/30/2020
ms.locfileid: "44936204"
---
# <a name="test-relevance-analysis-in-advanced-ediscovery-classic"></a>Testar análise de relevância na descoberta eletrônica avançada (clássica)

> [!NOTE]
> A Descoberta Eletrônica Avançada exige um Office 365 E3, com um complemento de Conformidade Avançada ou uma assinatura do E5 para sua organização. Se você não tiver esse plano e quiser tentar a Descoberta Eletrônica Avançada, poderá [Inscrever-se para uma avaliação do Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279). 
  
A guia teste em descoberta eletrônica avançada permite testar, comparar e validar a qualidade geral do processamento. Esses testes são executados após o cálculo em lotes. Ao marcar os arquivos na coleção, um especialista faz o julgamento final sobre se cada arquivo marcado é realmente relevante para o caso. 
  
Em cenários de um e vários problemas, os testes são normalmente executados por problema. Os resultados podem ser exibidos após cada teste, e os resultados do teste podem ser retrabalhados com os arquivos de teste de amostra especificados.
  
## <a name="testing-the-rest"></a>Testando o restante

O teste "Test The Rest" é usado para validar decisões de remoção, por exemplo, para revisar apenas arquivos acima de uma pontuação específica de corte de relevância com base nos resultados finais avançados da descoberta eletrônica. O especialista revisa uma amostra de arquivos sob uma pontuação de corte selecionada para avaliar o número de arquivos relevantes dentro desse conjunto.
  
Esse teste fornece estatísticas e uma comparação entre o conjunto de revisão e o teste da população REST. Os resultados do conjunto de revisão são aqueles calculados por relevância durante o treinamento. Os resultados incluem cálculos, com base em configurações e parâmetros de entrada, como:
  
- Teste as estatísticas de exemplo do número de arquivos em uma amostra e identificado arquivos relevantes. 
    
- Comparação de tabulação dos parâmetros de população do conjunto de análise e do restante, por exemplo, o número de arquivos, o número estimado de arquivos relevantes, a riqueza estimada e o custo médio de localizar um arquivo relevante adicional. As configurações de parâmetros de custo podem ser definidas pelo administrador.
    
1. Abra a **guia \> teste de relevância** . 
    
2. Na guia **teste** , clique em **novo teste**. A caixa de diálogo **criar teste** é exibida, conforme mostrado no exemplo a seguir. 
    
    ![Resultados de “Test the Rest” de relevância](../media/46e6898a-f929-4fd0-88d9-6f91d04b6ce2.png)
  
3. Em **nome do teste**e **Descrição**, digite o nome e a descrição.
    
4. Na lista **tipo de teste** , selecione **testar o restante**
    
5. Na lista **problema/categoria** , selecione o nome do problema. 
    
6. Na lista **carregar** , selecione carregar. 
    
7. Em **leitura%**, aceite o valor padrão ou selecione um valor para a pontuação de relevância de corte. 
    
8. Em **tamanho do conjunto**, ou aceite o valor padrão. Observe que os ícones de restauração restaurarão os valores padrão.
    
9. Clique em **Iniciar marcação**. Um exemplo de teste é gerado.
    
10. Revise e marque cada um dos arquivos na **guia \> marca de relevância** e, quando terminar, clique em **calcular**.
    
11. Na guia teste, você pode clicar em **exibir resultados** para ver os resultados do teste. Um exemplo é mostrado na figura a seguir. 
    
    ![Resultados do “Test the rest”](../media/b95744a9-047d-4c29-992d-04fa7e58e58a.png)
  
Na figura acima, a seção **parâmetros de exemplo** da tabela contém detalhes sobre o número de arquivos no exemplo marcado pelo especialista e o número de arquivos relevantes encontrados nesse exemplo. 
  
A seção **parâmetros de população** da tabela contém os resultados do teste, incluindo a população de análise definida de arquivos com uma pontuação abaixo do corte selecionado e o preenchimento "o restante" dos arquivos com uma pontuação acima do corte selecionado. Para cada população, os seguintes resultados são exibidos: 
  
- Inclui arquivos com corte de leitura%-declarado
    
- O número total de arquivos 
    
- O número estimado de arquivos relevantes 
    
- A riqueza estimada 
    
- O custo de análise média de localizar outro arquivo relevante
    
## <a name="testing-the-slice"></a>Testando a fatia

O teste "testar a fatia" executa testes semelhantes ao teste "testar o REST", mas para um segmento do conjunto de arquivos conforme especificado por relevância Read%.
  
1. Abra a **guia \> teste de relevância** . 
    
2. Na guia **teste** , clique em **novo teste**. A caixa de diálogo **criar teste** é exibida. 
    
3. Em **nome do teste** e **Descrição**, digite as informações.
    
4. Na lista **tipo de teste** , selecione **testar a fatia**.
    
5. Na lista **problema** , selecione o nome do problema. 
    
6. Na lista **carregar** , selecione carregar. 
    
7. Em **% de leitura**, aceite os valores de intervalo baixo e alto padrão ou selecione valores para as pontuações de relevância de corte. 
    
8. Em **tamanho do conjunto**, selecione um valor ou aceite o valor padrão.
    
    Os ícones de restauração restaurarão o valor padrão.
    
9. Clique em **Iniciar marcação**. Um exemplo de teste é gerado.
    
10. Revise e marque cada um dos arquivos na **guia \> marca de relevância** e, quando terminar, clique em **calcular**. 
    
11. Na guia teste, você pode clicar em **exibir resultados** para ver os resultados do teste. 
    
## <a name="see-also"></a>Também consulte

[Descoberta Eletrônica Avançada (clássica)](office-365-advanced-ediscovery.md)
  
[Noções básicas sobre avaliação em relevância](assessment-in-relevance-in-advanced-ediscovery.md)
  
[Marcação e avaliação](tagging-and-assessment-in-advanced-ediscovery.md)
  
[Treinamento de marcação e relevância](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[Análise de relevância de rastreamento](track-relevance-analysis-in-advanced-ediscovery.md)
  
[Decidindo com base nos resultados](decision-based-on-the-results-in-advanced-ediscovery.md)

