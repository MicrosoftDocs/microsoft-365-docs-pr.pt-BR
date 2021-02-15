---
title: Testar a análise de relevância na Descoberta Avançada
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
ms.assetid: 1b092f7c-ea55-44f5-b419-63f3458fd7e0
ROBOTS: NOINDEX, NOFOLLOW
description: Saiba como usar a guia Teste após o cálculo em lotes na Descoberta eDiscovery Avançada para testar, comparar e validar a qualidade geral do processamento.
ms.openlocfilehash: 3ac12c176f2e46ac0321976a7e0689fbd8893bba
ms.sourcegitcommit: 5ba0015c1554048f817fdfdc85359eee1368da64
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/06/2021
ms.locfileid: "49769166"
---
# <a name="test-relevance-analysis-in-advanced-ediscovery"></a>Testar a análise de relevância na Descoberta Avançada
  
A guia Teste na Descoberta Avançada permite testar, comparar e validar a qualidade geral do processamento. Esses testes são executados após o cálculo em lotes. Ao marcar os arquivos na coleção, um especialista faz o parecer final sobre se cada arquivo marcado é relevante para o caso.
  
Em cenários individuais e com vários problemas, os testes geralmente são executados por problema. Os resultados podem ser exibidos após cada teste, e os resultados do teste podem ser reformulados com arquivos de teste de amostra especificados.
  
## <a name="testing-the-rest"></a>Testando o restante

O teste "Testar o Restante" é usado para validar as decisões de recortar, por exemplo, para revisar somente os arquivos acima de uma pontuação de corte de relevância específica com base nos resultados finais da Descoberta Avançada. O especialista revisa um exemplo de arquivos em uma pontuação de corte selecionada para avaliar o número de arquivos relevantes dentro desse conjunto.
  
Este teste fornece estatísticas e uma comparação entre o conjunto de revisão e a população Test the Rest. Os resultados do conjunto de revisão são aqueles calculados pela Relevância durante o Treinamento. Os resultados incluem cálculos com base em configurações e parâmetros de entrada, como:
  
- Teste as estatísticas de amostra do número de arquivos em uma amostra e identifique os arquivos relevantes.

- Comparação tabular dos parâmetros Population do conjunto de Revisão e o Restante, por exemplo, o número de arquivos, o número estimado de arquivos relevantes, a riqueza estimada e o custo médio de localizar outro arquivo relevante. As configurações de parâmetro de custo podem ser definidas pelo administrador.

Para executar o teste "Testar o Restante":

1. Abra a **guia Teste \> de Relevância.**

2. Na guia **Teste,** clique em **Novo teste.** A **caixa de** diálogo Criar teste é exibida, conforme mostrado no exemplo a seguir.

    ![Resultados de “Test the Rest” de relevância](../media/46e6898a-f929-4fd0-88d9-6f91d04b6ce2.png)
  
3. Em **Nome do teste** e **descrição,** digite o nome e a descrição.

4. Na lista **de tipos de** teste, selecione Testar o **Restante**

5. Na lista **Problema/Categoria,** selecione o nome do problema.

6. Na lista **Carregar,** selecione o carregamento. 

7. Em **% de** leitura, aceite o valor padrão ou selecione um valor para a pontuação de relevância de corte. 

8. Em **Definir tamanho,** ou aceite o valor padrão. Os ícones de restauração restaurarão os valores padrão.

9. Clique **na marcação Iniciar.** Um exemplo de teste é gerado.

10. Revise e marque cada um dos arquivos na **guia \>** Marca de Relevância e, quando terminar, clique em **Calcular**.

11. Na guia Teste, você pode clicar em Exibir **resultados** para ver os resultados do teste. Um exemplo é mostrado na captura de tela a seguir.

    ![Resultados do “Test the rest”](../media/b95744a9-047d-4c29-992d-04fa7e58e58a.png)
  
Na captura de tela anterior, a seção Exemplos de parâmetros da tabela contém detalhes sobre o número de arquivos na amostra marcados pelo especialista e o número de arquivos **relevantes** encontrados nesse exemplo.
  
A **seção Parâmetros** População da tabela contém os resultados do teste, incluindo a população de conjunto de revisão de arquivos com uma pontuação abaixo da pontuação selecionada e a população de arquivos "O Restante" com uma pontuação acima do corte selecionado. Para cada população, os seguintes resultados são exibidos:
  
- Inclui arquivos com % de leitura - Corte declarado

- O número total de arquivos

- O número estimado de arquivos relevantes

- A riqueza estimada

- O custo médio de revisão para localizar outro arquivo relevante

## <a name="testing-the-slice"></a>Testando a fatia

O teste "Testar a Fatia" realiza testes semelhantes ao teste "Testar o Restante", mas a um segmento do conjunto de arquivos, conforme especificado pelo %de Leitura de Relevância.

Para executar o teste "Testar a fatia":
  
1. Abra a **guia Teste \> de Relevância.**

2. Na guia **Teste,** clique em **Novo teste.** A **caixa de diálogo** Criar teste é exibida.

3. Em **Nome do teste** e **descrição,** digite as informações.

4. Na lista **De tipo de** teste, selecione Testar a **fatia**.

5. Na lista **Problema,** selecione o nome do problema.

6. Na lista **Carregar,** selecione o carregamento.

7. Em **% de leitura entre**, aceite os valores padrão de intervalo baixo e alto ou selecione valores para as pontuações de relevância de corte.

8. Em **Definir tamanho,** selecione um valor ou aceite o valor padrão.

    Os ícones de restauração restaurarão o valor padrão.

9. Clique **na marcação Iniciar.** Um exemplo de teste é gerado.

10. Revise e marque cada um dos arquivos na **guia \>** Marca de Relevância e, quando terminar, clique em **Calcular**.

11. Na guia Teste, você pode clicar em Exibir **resultados** para ver os resultados do teste.
