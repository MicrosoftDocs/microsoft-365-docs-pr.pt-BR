---
title: Avaliação de rede do Microsoft 365 (versão prévia)
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 09/17/2020
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
description: Avaliação de rede do Microsoft 365 (versão prévia)
ms.openlocfilehash: 21fb9515ea1621225cffbe23fe87d0daeb5265de
ms.sourcegitcommit: adaedd1418a3bd6e4875b77fd9e008b47e0b2a51
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/18/2020
ms.locfileid: "48104541"
---
# <a name="microsoft-365-network-assessment-preview"></a>Avaliação de rede do Microsoft 365 (versão prévia)

Na conectividade de rede do centro de administração do Microsoft 365, as **avaliações de rede** expostam uma agregação de muitas métricas de desempenho de rede em um instantâneo da integridade do perímetro da rede corporativa, representado por um valor de pontos de 0-100. Uma avaliação de rede informa quanto o design de rede responsável pelo cliente está impactando a experiência do usuário do Office 365. As avaliações de rede têm o escopo para o locatário inteiro e para cada localização geográfica a partir da qual os usuários se conectam ao seu locatário, fornecendo aos administradores da Microsoft 365 uma maneira fácil de obter instantaneamente um Gestalt da integridade da rede da empresa e rapidamente se aprofundam em um relatório detalhado de qualquer local do escritório global.

O valor de pontos de avaliação de rede é uma média de latência TCP, velocidade de download e métricas de qualidade de conexão UDP compiladas uma vez por dia. As métricas de desempenho para redes de propriedade da Microsoft são excluídas dessas medidas para garantir que os resultados da avaliação sejam inequívocas e específicos da rede corporativa.

![Valor de avaliação de rede](../media/m365-mac-perf/m365-mac-perf-overview-score-top.png)

Um valor de avaliação de rede muito baixo sugere que os clientes do Microsoft 365 terão problemas significativos para se conectar ao locatário ou manter uma experiência de usuário responsiva, enquanto um valor alto indica uma rede configurada corretamente com poucos problemas de desempenho contínuos. Um valor de 80% representa uma linha de base saudável onde você não deve receber queixas regulares do usuário sobre a conectividade ou a capacidade de resposta do Microsoft 365 devido ao desempenho da rede. Conforme são feitas melhorias de conectividade de rede iterativa, esse valor aumentará junto com a experiência do usuário.

| Avaliação de rede | Experiência de usuário esperada |
| :----------------- | :----------------------- |
| 100                | Melhor                     |
| 80                 | Atende às recomendações    |
| 60                 | Aceitável               |
| 40                 | Os usuários podem enfrentar problemas |
| 508                 | Os usuários podem reclamar       |
| ,0                  | Problemas de rede um tópico comum de discussão |

>[!IMPORTANT]
>Os insights de rede, as recomendações de desempenho e as avaliações no centro de administração do Microsoft 365 estão atualmente no status de visualização e só estão disponíveis para os locatários do Microsoft 365 que foram registrados no programa de visualização de recurso.

## <a name="network-assessment-panel"></a>Painel de avaliação de rede

Cada avaliação de rede, com escopo para o locatário ou para um local específico do Office, mostra um painel com detalhes sobre a avaliação. Este painel mostra um gráfico de barras da avaliação como uma porcentagem e como o total de pontos para cada carga de trabalho do componente, incluindo apenas as cargas de trabalho onde os dados de medição foram recebidos. Para uma avaliação de rede de local do Office, também mostramos uma comparação com a porcentagem de clientes da Microsoft 365 em cada um dos cinco Quintiles que relatavam dados na mesma cidade do local do escritório.

![Exemplo de valor de avaliação de rede](../media/m365-mac-perf/m365-mac-perf-overview-score.png)

A **divisão de avaliação** no painel mostra a avaliação de cada uma das cargas de trabalho do componente.

O **histórico de avaliação** mostra os últimos 30 dias da avaliação e o benchmark. Você também pode relatar o histórico de métricas de qualquer local do Office por até dois anos usando a guia histórico. A guia histórico permite que você selecione seus atributos para relatar e escolhendo um período de relatório, você pode realçar o impacto de um projeto de atualização de rede e ver a melhoria na avaliação da sua rede.

## <a name="tenant-network-assessments-and-office-location-network-assessments"></a>Avaliações de rede de locatários e avaliações de rede de local do escritório

Uma avaliação de rede mede o design do perímetro de rede de um local do escritório para a rede da Microsoft. Os aprimoramentos no perímetro de rede são mais bem executados em cada local do escritório.

Mostramos um valor de avaliação de rede para todo o Microsoft 365 locatário na página de visão geral do desempenho da rede, que é uma média ponderada das avaliações de rede para todos os locais do Office. Há também um valor de avaliação de rede específico para cada local de escritório detectado na página de resumo desse local.

## <a name="exchange-online"></a>Exchange Online

Para o Exchange Online, a latência TCP da máquina cliente para a porta frontal do serviço do Exchange é medida. Isso pode ser afetado pela distância que a rede se movimenta na LAN e na WAN dos clientes. Também pode ser afetado por dispositivos ou serviços intermediários de rede que atrasam a conectividade ou fazem com que os pacotes sejam reenviados. E é afetado por quanto distância da porta frontal mais próxima do Exchange Service é. A mediana (também conhecida como a medida 50 º percentil ou P50) é tomada para todas as medições nos três dias anteriores.

A avaliação do Exchange Online é feita usando a tabela a seguir. Qualquer número de latência TCP entre os limites é atribuído pontos linearmente dentro da banda.

| Latência TCP   | Pontos |
| :------------ | :----- |
| 10 ms ou menos  | 100    |
| 25ms          | 80     |
| 100 ms         | 60     |
| 200ms         | 40     |
| 300ms         | 508     |
| 350ms ou mais | ,0      |

## <a name="sharepoint-online"></a>SharePoint Online

Para o SharePoint Online, a velocidade de download disponível para o usuário acessar um documento do SharePoint ou do OneDrive é medida. Isso pode ser afetado pela largura de banda disponível em circuitos de rede entre a máquina cliente e a rede da Microsoft. Também é possível impactar com o congestionamento de rede que existe em gargalos em dispositivos de rede complexos ou em áreas de Wi-Fi de cobertura ruim. A velocidade de download é medida em megabytes por segundo, que é aproximadamente um décimo de um dos circuitos classificados de megabits por segundo. A unidade de MegaByte por segundo é útil porque você pode ver diretamente o arquivo de tamanho que pode ser baixado em 1 segundo. O 25º percentil (também conhecido como a medida P25) é usado para todas as medições nos três dias anteriores. Este 25º percentil ajuda a reduzir o impacto de congestionamento variável ao longo do tempo.

A avaliação do SharePoint Online é feita usando a tabela a seguir. Qualquer número de velocidade de download entre os limites é atribuído pontos linearmente na banda.

| Velocidade de download | Pontos |
| :------------- | :----- |
| 20MBps ou mais | 100    |
| 14MBps         | 80     |
| 8MBps          | 60     |
| 4MBps          | 40     |
| 2MBps          | 508     |
| 0MBps          | ,0      |

## <a name="microsoft-teams"></a>Microsoft Teams

Para o Microsoft Teams, a qualidade da rede é medida como latência de UDP, tremulação de UDP e perda de pacotes UDP. O UDP é usado para a chamada e conferência de áudio e conectividade de mídia de vídeo para o Microsoft Teams. Isso pode ser afetado pelos mesmos fatores para a latência e velocidade de download, além de falhas de conectividade no suporte a UDP de uma rede, pois o UDP é configurado separadamente para o protocolo TCP mais comum. A mediana (também conhecida como a medida 50 º percentil ou P50) é tomada para todas as medições nos três dias anteriores. 

Calculamos uma pontuação de opinião média dessas medidas UDP para uma escala de um para cinco. Em seguida, mapeamos isso para a escala de pontos de 0-100 para a avaliação de rede do Microsoft Teams.  A qualidade geral é superior a 87,5 pontos e o mau inválido está abaixo de 50 pontos.

## <a name="related-topics"></a>Tópicos relacionados

[Conectividade de rede no centro de administração do Microsoft 365 (versão prévia)](office-365-network-mac-perf-overview.md)

[Microsoft 365 Network Performance insights (versão prévia)](office-365-network-mac-perf-insights.md)

[Teste de conectividade do Microsoft 365 no centro de administração do M365 (versão prévia)](office-365-network-mac-perf-onboarding-tool.md)

[Serviços de local de conectividade de rede da Microsoft 365 (versão prévia)](office-365-network-mac-location-services.md)

[Ferramenta de teste de conectividade de rede 365 da Microsoft (versão prévia)](office-365-network-mac-perf-onboarding-tool.md)
