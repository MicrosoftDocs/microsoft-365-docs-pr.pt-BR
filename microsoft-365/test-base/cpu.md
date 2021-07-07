---
title: Análise de regressão de CPU
description: Noções básicas sobre resultados e métricas de regressão para consumo de CPU
search.appverid: MET150
author: mansipatel-usl
ms.author: mapatel
manager: rshastri
audience: Software-Vendor
ms.topic: how-to
ms.date: 07/06/2021
ms.service: virtual-desktop
localization_priority: Normal
ms.collection: TestBase-M365
ms.custom: ''
ms.reviewer: mapatel
f1.keywords: NOCSH
ms.openlocfilehash: bc28c128902ae353fb35c3b6010856ade934a436
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2021
ms.locfileid: "53322442"
---
# <a name="intelligent-cpu-regression-analysis"></a>Análise de regressão de CPU inteligente

A utilização da CPU pode indicar se um aplicativo é afetado por uma atualização do sistema operacional. 

A Base de Teste para Microsoft 365 fornece aos desenvolvedores de software uma visão das regressões de desempenho da CPU que ocorrem quando seu aplicativo está sendo executado em diferentes versões de uma atualização futura do sistema operacional (sistema operacional) Windows futuro. 

Essas regressões de CPU permitem que os desenvolvedores detectem e resolvam problemas de aplicativo (e possíveis falhas) antes que a atualização do sistema operacional seja implantada amplamente, impedindo assim uma experiência ruim para o usuário final.


### <a name="how-cpu-regression-analysis-works"></a>Como funciona a análise de regressão da CPU ###

Como um usuário da Base de Teste, você pode carregar os binários do aplicativo (em um único arquivo .zip), juntamente com scripts de teste associados e selecionar a versão do sistema operacional Windows na qual você gostaria de testar seu aplicativo no portal base de teste no Azure. 

Em seguida, o serviço Base de Teste executa os scripts de teste e executa a Análise **de Regressão da CPU.** 

O serviço verifica se a utilização da CPU para o aplicativo na versão de pré-lançamento da atualização do sistema operacional de destino está em linha com a utilização da CPU para a versão lançada do sistema operacional. 

A utilização da CPU não é uma comparação 100% like-for-like porque os processos em execução nas duas versões do sistema operacional podem ou não ser uma combinação exata devido a versões diferentes do sistema operacional; no entanto, a análise realizada pela Base de Teste pode mostrar se a utilização da CPU para seu aplicativo é impactada por uma atualização futura do sistema operacional e especificamente quais processos foram regredidos de testes anteriores.

No instantâneo abaixo, há duas versões do sistema operacional em relação às quais as utilizações da CPU são comparadas para o mesmo aplicativo. 
-   A guia utilização da CPU mostra os limites superiores e inferiores de utilização para ambas as versões em percentis 90 e 10, respectivamente. 
-   Os gráficos mostram a série de tempo de utilização da CPU juntamente com a utilização média. 

Os clientes agora podem usar a funcionalidade para determinar se a utilização da CPU do aplicativo é impactada pelas atualizações do sistema operacional e especificamente quais processos foram regredidos da execução anterior.


![Análise de regressão de CPU](Media/cpu-regression-analysis.jpg)

### <a name="relevant-process-identification"></a>Identificação de processo relevante ###

Aqui, abordamos como identificar processos regredidos no aplicativo. 

Analisar a regressão de desempenho requer o acompanhamento de diferentes tipos de contadores de desempenho para cada processo em execução em uma máquina virtual durante a execução do teste. 

Essa análise captura muitas variáveis para muitos processos para um determinado aplicativo. Nem todos os processos estão associados a uma executar ou aplicativo. Para resolver esse desafio, um algoritmo de classificação de informações mútuo usando probabilidade e a teoria da informação é aplicado para descobrir quais processos são mais relevantes para um determinado aplicativo. 

Um aplicativo pode ser considerado um tipo de variável aleatória discreta enquanto um processo é considerado outro tipo de variável aleatória discreta. A associação das duas variáveis aleatórias é medida usando probabilidades condicionais para relevância. 

Em seguida, os processos são exibidos na ordem de sua relevância para cada aplicativo. Você também pode favorito de um subconjunto de processos que podem ser monitorados, por padrão, juntamente com processos relevantes para análise de regressão de CPU. Depois que uma regressão é detectada, você pode baixar o kit de ferramentas do Analisador de Desempenho Windows e analisar os motivos das regressões de desempenho da CPU. 

O Windows de desempenho assume o log de rastreamento de eventos (ETL) como entradas e esses arquivos .etl estão disponíveis nos arquivos de log baixáveis para execução de teste no portal. Se você quiser saber mais sobre a depuração do desempenho da CPU, consulte a documentação Windows Analisador de Desempenho.

