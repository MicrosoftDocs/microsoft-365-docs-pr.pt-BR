---
title: Avaliação de rede do Microsoft 365 (visualização)
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 09/21/2020
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
description: Avaliação de rede do Microsoft 365 (visualização)
ms.openlocfilehash: 3d80130dbf9ca41342bc1a01fe3ce992303efb48
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/22/2020
ms.locfileid: "48200742"
---
# <a name="microsoft-365-network-assessment-preview"></a>Avaliação de rede do Microsoft 365 (visualização)

Na conectividade de rede do Centro de Administração do Microsoft 365, as avaliações de rede agregam uma agregação de muitas **métricas** de desempenho de rede em um instantâneo da sua saúde de perímetro de rede corporativa, representada por um valor de pontos de 0 a 100. Uma avaliação de rede informa o quanto o design de rede responsável pelo cliente está afetando a experiência do usuário do Office 365. As avaliações de rede têm como escopo todo o locatário e para cada localização geográfica a partir da qual os usuários se conectam ao seu locatário, fornecendo aos administradores do Microsoft 365 uma maneira fácil de compreender instantaneamente uma gestão da saúde da rede da empresa e detalhar rapidamente um relatório detalhado para qualquer local de escritório global.

O valor dos pontos de avaliação de rede é uma média de latência de TCP, velocidade de download e métricas de qualidade de conexão UDP compiladas uma vez por dia. As métricas de desempenho para redes de propriedade da Microsoft são excluídas dessas medições para garantir que os resultados da avaliação não sejam ambíguos e específicos à rede corporativa.

![Valor de avaliação de rede](../media/m365-mac-perf/m365-mac-perf-overview-score-top.png)

Um valor de avaliação de rede muito baixo sugere que os clientes do Microsoft 365 terão problemas significativos para se conectar ao locatário ou manter uma experiência do usuário responsiva, enquanto um valor alto indica uma rede corretamente configurada com poucos problemas de desempenho contínuos. Um valor de 80% representa uma linha de base saudável em que você não deve esperar receber reclamações de usuários regulares sobre a conectividade ou a capacidade de resposta do Microsoft 365 devido ao desempenho da rede. À medida que melhorias iterativas de conectividade de rede são feitas, esse valor aumentará junto com a experiência do usuário.

| Avaliação de rede | Experiência do usuário esperada |
| :----------------- | :----------------------- |
| 100                | Melhor                     |
| 80                 | Atende às recomendações    |
| 60                 | Aceitável               |
| 40                 | Os usuários podem ter problemas |
| 20                 | Os usuários podem reclamar       |
| 0                  | Problemas de rede um tópico comum de discussão |

>[!IMPORTANT]
>Informações de rede, recomendações de desempenho e avaliações no Centro de administração do Microsoft 365 estão atualmente no status de visualização e só estão disponíveis para locatários do Microsoft 365 que foram inscritos no programa de visualização de recursos.

## <a name="network-assessment-panel"></a>Painel de avaliação de rede

Cada avaliação de rede, seja com escopo para o locatário ou para um local específico do escritório, mostra um painel com detalhes sobre a avaliação. Este painel mostra um gráfico de barras da avaliação como uma porcentagem e como o total de pontos para cada carga de trabalho de componente, incluindo apenas cargas de trabalho em que os dados de medição foram recebidos. Para uma avaliação da rede local do escritório, também mostramos uma comparação com a porcentagem de clientes do Microsoft 365 em cada um dos cinco milimos que relataram dados na mesma cidade do seu local de escritório.

![Exemplo de valor de avaliação de rede](../media/m365-mac-perf/m365-mac-perf-overview-score.png)

O **detalhamento da Avaliação** no painel mostra a avaliação de cada uma das cargas de trabalho do componente.

O **histórico de avaliação** mostra os últimos 30 dias da avaliação e o parâmetro de comparação. Você também pode relatar o histórico de métricas de qualquer local do escritório por até dois anos usando a guia histórico. A guia histórico permite que você selecione seus atributos para relatar e escolhendo um período de tempo de relatório que você pode destacar o impacto de um projeto de atualização de rede e ver o aprimoramento da sua avaliação de rede.

## <a name="tenant-network-assessments-and-office-location-network-assessments"></a>Avaliações de rede de locatários e avaliações de rede local do escritório

Uma avaliação de rede mede o design do perímetro de rede de um local de escritório para a rede da Microsoft. É melhor fazer melhorias no perímetro da rede em cada local do escritório.

Mostramos um valor de avaliação de rede para todo o locatário do Microsoft 365 na página de visão geral do desempenho da rede, que é uma média ponderada das avaliações de rede para todos os locais de escritório. Há também um valor de avaliação de rede específico para cada local de escritório detectado na página de resumo desse local.

## <a name="exchange-online"></a>Exchange Online

Para o Exchange Online, a latência TCP da máquina cliente para a porta frontal do serviço do Exchange é medida. Isso pode ser afetado pela distância que a rede percorre pela LAN e WAN dos clientes. Ele também pode ser afetado por dispositivos ou serviços intermediários de rede que atrasam a conectividade ou causam a reenconsão dos pacotes. E isso é afetado pela distância da porta frontal do serviço Exchange mais próxima. A mediana (também conhecida como 50º percentil ou medida P50) é tomada para todas as medições dos três dias anteriores.

A avaliação do Exchange Online é feita usando a tabela a seguir. Qualquer número de latência TCP entre os limites é atribuído a pontos linearmente dentro da faixa.

| Latência TCP   | Pontos |
| :------------ | :----- |
| 10 ms ou menos  | 100    |
| 25 ms          | 80     |
| 100 ms         | 60     |
| 200 ms         | 40     |
| 300 ms         | 20     |
| 350 ms ou mais | 0      |

## <a name="sharepoint-online"></a>SharePoint Online

Para o SharePoint Online, a velocidade de download disponível para um usuário acessar um documento do SharePoint ou do OneDrive é medida. Isso pode ser afetado pela largura de banda disponível em circuitos de rede entre o computador cliente e a rede da Microsoft. Ela também é frequentemente afetada pelo congestionamento de rede que existe em gargalos em dispositivos de rede complexos ou em áreas de cobertura Wi-Fi ruins. A velocidade de download é medida em megabytes por segundo, que é aproximadamente um décimo de um circuito classificado de megabits por segundo. A unidade MegaByte por segundo é útil porque você pode ver diretamente qual arquivo de tamanho pode ser baixado em 1 segundo. O 25º percentil (também conhecido como medida P25) é feito para todas as medições dos três dias anteriores. Esse 25º percentil ajuda a reduzir o impacto da variação do congestionamento ao longo do tempo.

A avaliação do SharePoint Online é feita usando a tabela a seguir. Qualquer número de velocidade de download entre os limites é atribuído a pontos linearmente dentro da faixa.

| Velocidade de download | Pontos |
| :------------- | :----- |
| 20MBps ou mais | 100    |
| 14MBps         | 80     |
| 8MBps          | 60     |
| 4MBps          | 40     |
| 2MBps          | 20     |
| 0MBps          | 0      |

## <a name="microsoft-teams"></a>Microsoft Teams

Para o Microsoft Teams, a qualidade de rede é medida como latência UDP, tremência de UDP e perda de pacotes UDP. O UDP é usado para conectividade de mídia de áudio e vídeo de chamada e conferência para o Microsoft Teams. Isso pode ser afetado pelos mesmos fatores que a velocidade de latência e download, além de lacunas de conectividade no suporte a UDP de uma rede, já que o UDP é configurado separadamente para o protocolo TCP mais comum. A mediana (também conhecida como 50º percentil ou medida P50) é tomada para todas as medições dos três dias anteriores. 

Calculamos uma pontuação média de opinião dessas medidas UDP para uma escala de um a cinco. Em seguida, mapeemos isso para a escala de 0 a 100 pontos para a avaliação de rede do Microsoft Teams.  O bem geral está acima de 87,5 pontos e o ruim geral está abaixo de 50 pontos.

## <a name="related-topics"></a>Tópicos relacionados

[Conectividade de rede no Centro de administração do Microsoft 365 (visualização)](office-365-network-mac-perf-overview.md)

[Percepções de desempenho de rede do Microsoft 365 (visualização)](office-365-network-mac-perf-insights.md)

[Ferramenta de teste de conectividade de rede do Microsoft 365 (visualização)](office-365-network-mac-perf-onboarding-tool.md)

[Serviços de Localização de Conectividade de Rede do Microsoft 365 (visualização)](office-365-network-mac-location-services.md)
