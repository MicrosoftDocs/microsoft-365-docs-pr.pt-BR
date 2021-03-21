---
title: Visão Geral da Conectividade de Rede do Microsoft 365
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 6/23/2020
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- m365initiative-coredeploy
f1.keywords:
- NOCSH
description: Discute por que a otimização de rede é importante para os serviços SaaS, o objetivo da rede do Microsoft 365 e como o SaaS exige redes diferentes de outras cargas de trabalho.
ms.openlocfilehash: d1a2b79f6e4042b97ec5a31d0ff92175baa1218e
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50923177"
---
# <a name="microsoft-365-network-connectivity-overview"></a>Visão geral da conectividade de rede do Microsoft 365

*Este artigo se aplica tanto ao Microsoft 365 Enterprise quanto ao Office 365 Enterprise.*

O Microsoft 365 é uma nuvem SaaS (Software-as-Service) distribuída que fornece cenários de produtividade e colaboração por meio de um conjunto diversificado de micros serviços e aplicativos. Componentes do cliente do Microsoft 365, como Outlook, Word e PowerPoint, são executados em computadores de usuário e se conectam a outros componentes do Microsoft 365 que são executados em datacenters da Microsoft. O fator mais significativo que determina a qualidade da experiência do usuário final do Microsoft 365 é a confiabilidade de rede e a baixa latência entre clientes do Microsoft 365 e portas de serviço do Microsoft 365.

Neste artigo, você aprenderá sobre as metas da rede do Microsoft 365 e por que a rede do Microsoft 365 exige uma abordagem diferente de otimização do que o tráfego genérico da Internet.

## <a name="microsoft-365-networking-goals"></a>Metas de rede do Microsoft 365

O objetivo final da rede do Microsoft 365 é otimizar a experiência do usuário final habilitando o acesso menos restritivo entre clientes e os pontos de extremidade mais próximos do Microsoft 365. A qualidade da experiência do usuário final está diretamente relacionada ao desempenho e à capacidade de resposta do aplicativo que o usuário está usando. Por exemplo, o Microsoft Teams depende de baixa latência para que as chamadas de telefone do usuário, conferências e colaborações de tela compartilhada sejam livres de falhas, e o Outlook se baseia em uma ótima conectividade de rede para recursos de pesquisa instantânea que aproveitam a indexação do lado do servidor e os recursos de IA.

O principal objetivo no design de rede deve ser minimizar a latência reduzindo o tempo de ida e volta (RTT) de máquinas cliente para a Rede Global da Microsoft, o backbone de rede pública da Microsoft que interconecta todos os datacenters da Microsoft com baixa latência e pontos de entrada de aplicativos de nuvem de alta disponibilidade espalhados pelo mundo. Você pode saber mais sobre a Rede Global da Microsoft no [Como a Microsoft cria uma rede global rápida e confiável](https://azure.microsoft.com/blog/how-microsoft-builds-its-fast-and-reliable-global-network/).

Otimizar o desempenho da rede do Microsoft 365 não precisa ser complicado. Você pode obter o melhor desempenho possível seguindo alguns princípios-chave:

- Identificar o tráfego de rede do Microsoft 365
- Permitir saída de filial local do tráfego de rede do Microsoft 365 para a Internet de cada local onde os usuários se conectam ao Microsoft 365
- Permitir que o tráfego do Microsoft 365 ignore proxies e dispositivos de inspeção de pacotes

Para obter mais informações sobre os princípios de conectividade de rede do Microsoft 365, consulte Princípios de Conectividade de [Rede do Microsoft 365.](microsoft-365-network-connectivity-principles.md)

## <a name="traditional-network-architectures-and-saas"></a>Arquiteturas de rede tradicionais e SaaS

Os princípios de arquitetura de rede tradicionais para cargas de trabalho de cliente/servidor são projetados em torno da suposição de que o tráfego entre clientes e pontos de extremidade não se estende fora do perímetro de rede corporativa. Além disso, em muitas redes corporativas, todas as conexões de saída da Internet percorrem a rede corporativa e se egressam de um local central.

Em arquiteturas de rede tradicionais, a latência mais alta para tráfego genérico da Internet é uma troca necessária para manter a segurança de perímetro de rede e a otimização de desempenho para o tráfego da Internet geralmente envolve a atualização ou o dimensionamento do equipamento em pontos de saída de rede. No entanto, essa abordagem não aborda os requisitos para um desempenho de rede ideal de serviços SaaS, como o Microsoft 365.

## <a name="identifying-microsoft-365-network-traffic"></a>Identificando o tráfego de rede do Microsoft 365

Estamos facilitando a identificação do tráfego de rede do Microsoft 365 e tornando mais simples gerenciar a identificação de rede.

- Novas categorias de pontos de extremidade de rede para diferenciar o tráfego de rede altamente crítico do tráfego de rede que não é afetado por latências da Internet. Há apenas algumas URLs e endereços IP de suporte na categoria "Otimizar" mais crítica.
- Serviços Web para uso de script ou configuração direta de dispositivo e gerenciamento de alterações da identificação de rede do Microsoft 365. As alterações estão disponíveis no serviço Web, no formato RSS ou no email usando um modelo do Microsoft Flow.
- Programa de parceiro de rede do [Office 365](./microsoft-365-networking-partner-program.md) com parceiros da Microsoft que fornecem dispositivos ou serviços que seguem os princípios de conectividade de rede do Microsoft 365 e têm configuração simples.

## <a name="securing-microsoft-365-connections"></a>Proteger conexões do Microsoft 365

O objetivo da segurança de rede tradicional é otimizar o perímetro da rede corporativa contra invasões e explorações maliciosas. A maioria das redes corporativas impõe a segurança de rede para o tráfego da Internet usando tecnologias como servidores proxy, firewalls, quebra e inspeção de SSL, inspeção profunda de pacotes e sistemas de prevenção contra perda de dados. Essas tecnologias oferecem redução de risco importantes para solicitações de Internet genéricas, mas podem reduzir significativamente o desempenho, a capacidade de expansão e a qualidade da experiência do usuário final quando aplicada aos pontos de extremidade do Microsoft 365.

O Microsoft 365 ajuda a atender às necessidades da sua organização para segurança de conteúdo e conformidade de uso de dados com recursos de segurança e governança integrados projetados especificamente para recursos e cargas de trabalho do Microsoft 365. Para obter mais informações sobre segurança e conformidade do Microsoft 365, consulte o roteiro de segurança [do Office 365](/office365/securitycompliance/security-roadmap). Para obter mais informações sobre as recomendações e a posição de suporte da Microsoft em soluções de rede avançadas que executam o processamento de nível avançado no tráfego do Microsoft 365, consulte [Using third-party network devices or solutions on Office 365 traffic](https://support.microsoft.com/help/2690045).

## <a name="why-is-microsoft-365-networking-different"></a>Por que a rede do Microsoft 365 é diferente?

O Microsoft 365 foi projetado para um desempenho ideal usando a segurança do ponto de extremidade e as conexões de rede criptografadas, reduzindo a necessidade de imposição de segurança de perímetro. Os datacenters do Microsoft 365 estão localizados em todo o mundo e o serviço foi projetado para usar vários métodos para conectar clientes aos melhores pontos de extremidade de serviço disponíveis. Como os dados e o processamento do usuário são distribuídos entre muitos datacenters da Microsoft, não há um único ponto de extremidade de rede ao qual as máquinas cliente podem se conectar. Na verdade, os dados e serviços no locatário do Microsoft 365 são otimizados dinamicamente pela Rede Global da Microsoft para se adaptarem aos locais geográficos dos quais são acessados pelos usuários finais.

Determinados problemas comuns de desempenho são criados quando o tráfego do Microsoft 365 está sujeito à inspeção de pacotes e à saída centralizada:

- A alta latência pode causar um desempenho extremamente ruim de fluxos de vídeo e áudio e uma resposta lenta de recuperação de dados, pesquisas, colaboração em tempo real, informações de agenda livre/ocupado, conteúdo no produto e outros serviços
- A egressão de conexões de um local central vence os recursos dinâmicos de roteamento da rede global do Microsoft 365, adicionando latência e tempo de ida e volta
- A descriptografia de SSL segurou o tráfego de rede do Microsoft 365 e recriptá-lo pode causar erros de protocolo e tem risco de segurança

Reduzir o caminho de rede para os pontos de entrada do Microsoft 365 permitindo que o tráfego do cliente se esvaia o mais próximo possível de sua localização geográfica pode melhorar o desempenho da conectividade e a experiência do usuário final no Microsoft 365. Ele também pode ajudar a reduzir o impacto de alterações futuras na arquitetura de rede no desempenho e na confiabilidade do Microsoft 365. O modelo de conectividade ideal é sempre fornecer saída de rede na localização do usuário, independentemente de estar na rede corporativa ou em locais remotos, como residência, hoteis, cafeterias e aeroportos. O tráfego genérico da Internet e o tráfego de rede corporativa baseado em WAN seriam roteados separadamente e não usariam o modelo de saída direta local. Esse modelo de saída direta local é representado no diagrama a seguir.

![Arquitetura de rede de saída local](../media/6bc636b0-1234-4ceb-a45a-aadd1044b39c.png)

A arquitetura de saída local tem os seguintes benefícios para o tráfego de rede do Microsoft 365 em relação ao modelo tradicional:
  
- Oferece o melhor desempenho do Microsoft 365, melhorando o comprimento da rota. As conexões do usuário final são roteadas dinamicamente para o ponto  de entrada mais próximo do Microsoft 365 pela infraestrutura de Porta de Entrada de Serviço Distribuído da Rede Global da Microsoft e, em seguida, o tráfego é roteado internamente para os pontos de extremidade de dados e serviços pela fibra de alta disponibilidade de alta latência da Microsoft.
- Reduz a carga na infraestrutura de rede corporativa permitindo saída local para o tráfego do Microsoft 365, ignorando proxies e dispositivos de inspeção de tráfego.
- Garante conexões em ambas as extremidades aproveitando a segurança do ponto de extremidade do cliente e os recursos de segurança na nuvem, evitando a aplicação de tecnologias redundantes de segurança de rede.

> [!NOTE]
> A _infraestrutura de Porta_ da Frente de Serviço Distribuído é a borda de rede altamente disponível e escalonável da Rede Global da Microsoft com locais geograficamente distribuídos. Ele encerra as conexões de usuário final e as encaminha de forma eficiente dentro da Rede Global da Microsoft. Você pode saber mais sobre a Rede Global da Microsoft no [Como a Microsoft cria uma rede global rápida e confiável](https://azure.microsoft.com/blog/how-microsoft-builds-its-fast-and-reliable-global-network/).

Para obter mais informações sobre como entender e aplicar princípios de conectividade de rede do Microsoft 365, consulte Princípios de Conectividade de Rede do [Microsoft 365.](microsoft-365-network-connectivity-principles.md)

## <a name="conclusion"></a>Conclusão

A otimização do desempenho de rede do Microsoft 365 realmente se resume à remoção de impedimentos desnecessários. Ao tratar as conexões do Microsoft 365 como tráfego confiável, você pode impedir que a latência seja introduzida pela inspeção de pacotes e pela concorrência pela largura de banda do proxy. Permitir conexões locais entre máquinas cliente e pontos de extremidade do Office 365 permite que o tráfego seja roteado dinamicamente pela Rede Global da Microsoft.

## <a name="related-topics"></a>Tópicos Relacionados

[Princípios de conectividade de rede do Microsoft 365](microsoft-365-network-connectivity-principles.md)

[Gerenciar pontos de extremidade do Office 365](managing-office-365-endpoints.md)

[URLs e intervalos de endereços IP do Office 365](urls-and-ip-address-ranges.md)

[URL do serviço Web e endereço IP do Office 365](microsoft-365-ip-web-service.md)

[Avaliando a conectividade de rede do Microsoft 365](assessing-network-connectivity.md)

[Planejamento de rede e ajuste de desempenho para o Microsoft 365](network-planning-and-performance.md)

[Ajuste de desempenho do Office 365 usando linhas de base e histórico de desempenho](performance-tuning-using-baselines-and-history.md)

[Plano de solução de problemas de desempenho do Office 365](performance-troubleshooting-plan.md)

[Redes de Distribuição de Conteúdo](content-delivery-networks.md)

[Teste de conectividade do Microsoft 365](https://aka.ms/netonboard)

[Como a Microsoft cria sua rede global confiável e rápida](https://azure.microsoft.com/blog/how-microsoft-builds-its-fast-and-reliable-global-network/)

[Blog de rede do Office 365](https://techcommunity.microsoft.com/t5/Office-365-Networking/bd-p/Office365Networking)