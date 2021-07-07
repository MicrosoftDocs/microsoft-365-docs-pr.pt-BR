---
title: Análise de regressão de memória
description: Como inferir regressão de memória
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
ms.openlocfilehash: cd95c4e0eb04b05860ded256066913cf87d67e86
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2021
ms.locfileid: "53322462"
---
# <a name="memory-regression-analysis"></a>Análise de Regressão de Memória

A Base de Teste ajuda você a perceber com mais clareza aumentos significativos de uso de memória nas VMs de teste que executam seus aplicativos. As métricas de desempenho, como o uso da memória, podem indicar a saúde geral do aplicativo e acreditamos que essa adição ajudará muito a manter o desempenho ideal de seus aplicativos.

Leia mais para obter mais detalhes ou assista a este vídeo para obter uma rápida explicação sobre as melhorias mais recentes. 

Para obter mais informações sobre a base de teste para a capacidade do M365 de ajudar na análise de regressão, consulte Resultados de regressão com base na confiabilidade do processo.

<b>Olhando mais de perto as regressões de memória</b>

O painel base de teste do M365 mostra a memória consumida pelo aplicativo em uma nova atualização de Windows pré-lançada e a compara com a memória usada pela última atualização Windows lançada. 

Com os aprimoramentos deste mês, a análise de regressão de memória agora é destaque em seus processos favoritos. Os aplicativos podem conter vários processos e você pode selecionar manualmente seus processos favoritos por meio da guia Confiabilidade. Nosso serviço identificará regressões de memória nesses processos favoritos ao comparar os testes executados em diferentes Windows de atualização. Se uma regressão for detectada, detalhes sobre a regressão estarão facilmente disponíveis.

Agora vamos analisar esse recurso em detalhes e discutir como você pode solucionar problemas de regressão de memória usando o Analisador de Desempenho Windows desempenho.

O sinal de falha causado por uma regressão de memória é mostrado no painel Base de Teste do M365 na página Resultados do teste em Utilização de Memória:

![Resultados de utilização de memória](Media/01_memory-utilization-results.png)


A falha no aplicativo devido ao maior consumo de memória também será exibida como ```Fail``` na página Resumo do Teste:

![Resultados de resumo de teste](Media/02_test-summary.png)

Ao fornecer esses sinais de falha antecipadamente, nosso objetivo é sinalizar claramente possíveis problemas que podem interromper e afetar a experiência do usuário final para seu aplicativo. 

Em seguida, você pode baixar os arquivos de log e usar o Analisador de Desempenho Windows, ou seu kit de ferramentas preferencial, para investigar mais. Você também pode trabalhar em conjunto com a equipe da Base de Teste do M365 para resolver o problema e ajudar a evitar problemas que impactam os usuários finais.

Os sinais de memória são capturados na guia Utilização de Memória no serviço Base de Teste para M365 para todas as executações de teste. O exemplo a seguir mostra um teste recente executado com o aplicativo onboarded "Stress de memória de teste de fumaça" na atualização de segurança de agosto de 2020. (Este aplicativo foi escrito por nossa equipe para ilustrar regressões de memória.)

![Resultados de regressão de memória](Media/03_memory-regression%20comparison.png)

Neste exemplo, o processo favorito "USLTestMemoryStress.exe" consumiu uma média de aproximadamente 100 MB na atualização de agosto de pré-lançamento em comparação com a atualização lançada em julho, portanto, a Base de Teste para M365 identificou uma regressão. 

Os outros processos , mostrados aqui como "USLTestMemoryStress_Aux1.exe" e "USLTestMemoryStress_Aux2.exe", também pertencem ao mesmo aplicativo, mas consumiram aproximadamente a mesma quantidade de memória para as duas versões para que "passaram" e foram considerados corretamente.

A regressão no processo principal foi determinada como "significativamente significativa" para que o serviço se comunicava e realçava essa diferença para o usuário. Se a comparação não tiver sido significativa, ela não será realçada. A utilização de memória pode ser barulhento, portanto, usamos modelos estatísticos para distinguir, entre versões e versões, diferenças significativas de diferenças inconsequentes. 

Uma comparação raramente pode ser sinalizada quando não há diferença verdadeira (um falso positivo), mas essa é uma troca necessária para melhorar a probabilidade de identificar corretamente as regressões (ou verdadeiros positivos).)

A próxima etapa é entender o que causou a regressão de memória. Você pode baixar os arquivos zip para ambas as execuções na opção Baixar arquivos de log, conforme mostrado abaixo. 

Esses arquivos zip contêm os resultados de sua execução de teste, incluindo resultados de script e dados de desempenho de memória e CPU incluídos no arquivo ETL.

![Arquivos de teste de regressão de memória](Media/04_memory-regression-test-files.png)

Você pode baixar e descompoar os logs das duas versões de teste e localizar o arquivo ETL em cada pasta e renomeá-los como target.etl (para o teste executado na atualização de pré-lançamento) e baseline.etl (para o teste executado na última atualização lançada) para simplificar a exploração e a navegação.
 
## <a name="next-steps"></a>Próximas etapas

Avance para o próximo artigo para começar a entender a análise inteligente de regressão da CPU.
> [!div class="nextstepaction"]
> [Próxima etapa](cpu.md)

<!---
Add button for next page
-->
