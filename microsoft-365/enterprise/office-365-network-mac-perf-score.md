---
title: Avaliação de rede do Microsoft 365 (versão prévia)
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 04/21/2020
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
ms.openlocfilehash: aacbdf73da9552a12bde250e51544f1de533637c
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46695372"
---
# <a name="microsoft-365-network-assessment-preview"></a>Avaliação de rede do Microsoft 365 (versão prévia)

Na página de conectividade do centro de administração do 365 da Microsoft para a Microsoft 365, as **avaliações de rede** expostam uma agregação de muitas métricas de desempenho de rede em um instantâneo da integridade da rede corporativa, representado por um valor de pontos de 1-100. As avaliações de rede têm o escopo para o locatário inteiro e para cada localização geográfica a partir da qual os usuários se conectam ao seu locatário, fornecendo aos administradores da Microsoft 365 uma maneira fácil de obter instantaneamente um Gestalt da integridade da rede da empresa e rapidamente se aprofundam em um relatório detalhado de qualquer local do escritório global.

O valor de pontos de avaliação de rede é uma medição média da latência, largura de banda, velocidade de download e métricas de qualidade de conexão compiladas ao vivo no momento em que são exibidas. As métricas de desempenho para redes de propriedade da Microsoft são excluídas dessas medidas para garantir que os resultados da avaliação sejam inequívocas e específicos da rede corporativa.

![Valor de avaliação de rede](../media/m365-mac-perf/m365-mac-perf-overview-score-top.png)

Um valor de avaliação de rede muito baixo sugere que os clientes do Microsoft 365 terão problemas significativos para se conectar ao locatário ou manter uma experiência de usuário responsiva, enquanto um valor alto indica uma rede configurada corretamente com poucos problemas de desempenho contínuos. Um valor de 80% representa uma linha de base saudável onde você não deve receber queixas regulares do usuário sobre a conectividade ou a capacidade de resposta do Microsoft 365 devido ao desempenho da rede. Conforme são feitas melhorias de conectividade de rede iterativa, esse valor aumentará junto com a experiência do usuário.

>[!IMPORTANT]
>Os insights de rede, as recomendações de desempenho e as avaliações no centro de administração do Microsoft 365 estão atualmente no status de visualização e só estão disponíveis para os locatários do Microsoft 365 que foram registrados no programa de visualização de recurso.

## <a name="network-assessment-panel"></a>Painel de avaliação de rede

Cada avaliação de rede, com escopo para o locatário ou para um local específico do Office, mostra um painel com detalhes sobre a avaliação. Este painel mostra um gráfico de barras da avaliação como uma porcentagem e como o total de pontos para cada carga de trabalho do componente, incluindo apenas as cargas de trabalho onde os dados de medição foram recebidos. Para uma avaliação de rede de local do Office, também mostramos um benchmark que é a mediana de todos os clientes da Microsoft 365 que informaram dados na mesma cidade que o local do escritório.

![Exemplo de valor de avaliação de rede](../media/m365-mac-perf/m365-mac-perf-overview-score.png)

A **divisão de avaliação** no painel mostra a avaliação de cada uma das cargas de trabalho do componente.

O **histórico de avaliação** mostra os últimos 30 dias da avaliação e o benchmark.

## <a name="tenant-network-assessments-and-office-location-network-assessments"></a>Avaliações de rede de locatários e avaliações de rede de local do escritório

Uma avaliação de rede mede o design do perímetro de rede de um local do escritório para a rede da Microsoft. Aprimoramentos no perímetro da rede são mais bem executados em cada local do escritório ou onde a conectividade de rede é agregada pode haver melhorias que afetam vários locais.

Mostramos um valor de avaliação de rede para todo o Microsoft 365 locatário na página de visão geral do desempenho da rede e um valor específico para cada local do escritório detectado na página de resumo desse local.

## <a name="exchange-online"></a>Exchange Online

Para o Exchange Online, a latência TCP da máquina cliente para o servidor front-end do Exchange é medida. Isso pode ser afetado pela distância que a rede se movimenta na LAN e na WAN dos clientes. Também pode ser afetado por dispositivos ou serviços intermediários de rede que atrasam a conectividade ou fazem com que os pacotes sejam reenviados.

## <a name="sharepoint-online"></a>SharePoint Online

Para o SharePoint Online, a velocidade de download disponível para o usuário acessar um documento é medida. Isso pode ser afetado pela largura de banda disponível em circuitos de rede entre a máquina cliente e a rede da Microsoft. Também é possível impactar com o congestionamento de rede que existe em gargalos em dispositivos de rede complexos ou em áreas de Wi-Fi de cobertura ruim.

## <a name="microsoft-teams"></a>Microsoft Teams

Para o Microsoft Teams, a qualidade da rede é medida como latência de UDP, tremulação de UDP e perda de pacotes UDP. O UDP é usado para a chamada e conferência de áudio e conectividade de mídia de vídeo para o Microsoft Teams. Isso pode ser afetado pelos mesmos fatores para a latência e velocidade de download, além de falhas de conectividade no suporte a UDP de uma rede, pois o UDP é configurado separadamente para o protocolo TCP mais comum.

## <a name="related-topics"></a>Tópicos relacionados

[Recomendações de desempenho de rede no centro de administração do Microsoft 365 (versão prévia)](office-365-network-mac-perf-overview.md)

[Microsoft 365 Network Performance insights (versão prévia)](office-365-network-mac-perf-insights.md)

[Teste de conectividade do Microsoft 365 no centro de administração do M365 (versão prévia)](office-365-network-mac-perf-onboarding-tool.md)

[Serviços de local de conectividade de rede da Microsoft 365 (versão prévia)](office-365-network-mac-location-services.md)
