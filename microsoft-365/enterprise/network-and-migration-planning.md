---
title: Planejamento de migração e rede para o Office 365
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 6/29/2018
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- BCS160
ms.assetid: f5ee6c33-bcd7-4b0b-b0f8-dc1d9fb8d132
description: Este artigo contém links para informações sobre planejamento de rede, teste e migração para o Office 365.
ms.openlocfilehash: 2b08b05b8863fd9351510878f9438264bb2999f5
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/17/2020
ms.locfileid: "47948443"
---
# <a name="network-and-migration-planning-for-office-365"></a>Planejamento de migração e rede para o Office 365

*Este artigo se aplica tanto ao Microsoft 365 Enterprise quanto ao Office 365 Enterprise.*

Este artigo contém links para informações sobre planejamento e teste de rede e migração para o Office 365.
  
Antes de implantar o pela primeira vez ou migrar para o Office 365, você pode usar as informações nesses tópicos para estimar a largura de banda necessária e, em seguida, testar e verificar se você tem largura de banda suficiente para implantar ou migrar para o Office 365.

Este artigo faz parte do [planejamento de rede e do ajuste de desempenho do Office 365](https://aka.ms/tune).

Para obter as etapas para otimizar sua rede para o Microsoft 365 e outras plataformas e serviços de nuvem da Microsoft, consulte o cartaz de [rede do Microsoft Cloud para arquitetos corporativos](https://aka.ms/cloudarchnetworking) .
   
## <a name="estimate-network-bandwidth-requirements"></a>Estimar requisitos de largura de banda de rede
<a name="EstimateBandwidthRequirements"> </a>

O uso do Office 365 pode aumentar a utilização do circuito de Internet da sua organização. É importante determinar se a quantidade de largura de banda disponível atualmente é suficiente para lidar com o aumento estimado quando o Office 365 for totalmente implantado, deixando, pelo menos, 20% de capacidade para lidar com o mais ocupado de dias.
  
Para estimar a largura de banda, use as seguintes etapas:
  
1. Avalie o número de clientes que usarão cada egresso de Internet. Deixe nossa rede multiterabitr o máximo possível de conexão. 
    
2. Determine quais serviços e recursos do Office 365 estarão disponíveis para uso dos clientes. Provavelmente, você terá grupos de pessoas com diferentes serviços ou perfis de uso.
    
3. Meça o uso da rede para um grupo piloto de clientes. Verifique se os clientes pilotos são representativos dos diferentes perfis de pessoas na organização, bem como os diferentes locais geográficos. Você pode fazer uma verificação cruzada de seus resultados em relação às nossas calculadoras antigas para o [Exchange](https://techcommunity.microsoft.com/t5/exchange-team-blog/announcing-the-exchange-client-network-bandwidth-calculator-beta/ba-p/601744) e o [Microsoft Teams](https://docs.microsoft.com/microsoftteams/prepare-network) ou o [estudo de caso](https://www.microsoft.com/itshowcase/Article/Content/631/Optimizing-network-performance-for-Microsoft-Office-365) que realizamos em nossa própria rede. 
    
4. Use as medidas do grupo piloto para extrapolar as necessidades de toda a organização e testar novamente para validar as estimativas antes de fazer qualquer alteração em sua rede.
    
## <a name="test-your-existing-network"></a>Testar sua rede existente
<a name="calculators"> </a>

 **Ferramentas de rede.** Teste e valide a largura de banda da Internet para determinar as restrições de download, carregamento e latência. Essas ferramentas ajudarão você a determinar os recursos de sua rede para a migração e depois que você estiver totalmente implantado. 
    
- [Analisador de conectividade remota da Microsoft](https://go.microsoft.com/fwlink/p/?LinkId=517243): testa a conectividade no seu ambiente do Exchange Online.
    
- Use o [Assistente de recuperação e suporte da Microsoft para o office 365](https://diagnostics.office.com/#/Download?env=SOC) para corrigir problemas do Outlook e do Office 365. 
    
## <a name="best-practices-for-network-planning-and-improving-migration-performance-for-office-365"></a>Práticas recomendadas para planejamento de rede e melhoria do desempenho de migração para o Office 365
<a name="BestPractices"> </a>

Aprofundar-se nas práticas recomendadas para obter mais informações sobre a melhoria da experiência do Office 365.
  
1. Quer começar a ajudar os usuários imediatamente? Consulte [práticas recomendadas para usar o office 365 em uma rede lenta](https://support.office.com/article/fd16c8d2-4799-4c39-8fd7-045f06640166) para obter dicas sobre como usar o Office 365, incluindo o SharePoint Online, o Exchange Online e o Lync Online, quando sua rede simplesmente não está operando. Este artigo links para as cargas de conteúdo no TechNet e Support.office.com para otimizar a experiência do Office 365 e inclui informações sobre maneiras fáceis de personalizar suas páginas da Web e como definir as configurações do Internet Explorer para a melhor experiência do Office 365. 
    
2. Leia os [princípios de conectividade de rede do office 365](https://aka.ms/o365networkingprinciples) para entender os princípios de conectividade para o gerenciamento seguro do tráfego do Office 365 e obter o melhor desempenho possível. Este artigo vai ajudá-lo a entender as diretrizes mais recentes para otimizar com segurança a conectividade de rede do Office 365. 
    
3. Melhorar o desempenho da migração de email Gerenciando cuidadosamente o agendamento de atualizações do Windows. Você pode atualizar seus computadores clientes em lotes e garantir que todos os computadores clientes sejam atualizados antes de migrar para o Office 365 para regulamentar o uso da largura de banda da rede. Para saber mais, confira [atualizar e configurar manualmente as áreas de trabalho para o Office 365 para as atualizações mais recentes](https://support.microsoft.com/gp/office-2013-365-update).
    
4. O tráfego de rede do Office 365 funciona melhor quando é tratado como um serviço de Internet confiável e tem permissão para ignorar a maior parte da filtragem e verificação tradicionais que algumas organizações colocam no tráfego de rede para serviços de Internet não confiáveis. Isso geralmente inclui a remoção do processamento de saída, como a autenticação de usuário de proxy e a inspeção de pacotes, e a garantia de egresso local para a Internet com a conversão adequada de endereço de rede (NAT) e capacidade de largura de banda suficiente para lidar com as solicitações de rede aumentadas. Confira o [Gerenciamento de pontos de extremidade do office 365](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)para obter orientação adicional sobre como configurar sua rede para lidar com o Office 365 como um serviço de Internet confiável na sua rede.
    
1. Verifique se o [Gerenciamento de pontos de extremidade do Office 365](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a). O tráfego adicional indo para o Office 365 resulta em um aumento de conexões de proxy de saída, bem como um aumento no tráfego seguro sobre TLS/SSL.
    
2. Se os proxies de saída exigirem autenticação do usuário, você poderá experimentar uma conectividade lenta ou uma perda de funcionalidade. Ignorar o requisito de autenticação para os domínios do Office 365 pode reduzir essa sobrecarga.
    
3. Se você tiver um grande número de calendários e caixas de correio compartilhadas, poderá ver um aumento no número de conexões do Outlook para o Exchange. Por exemplo, o cliente Outlook pode abrir até duas conexões adicionais para cada calendário compartilhado em uso. Nessa situação, verifique se o proxy de egresso pode lidar com as conexões ou ignore o proxy para conexões com o Office 365 para Outlook.
    
4. Determine o número máximo de dispositivos com suporte para um endereço IP público e como carregar o balanceamento entre vários endereços IP. Para obter mais informações, consulte [NAT support with Office 365](nat-support-with-microsoft-365.md).
    
5. Se você estiver inspecionando conexões de saída de computadores em sua rede, ignorar essa filtragem para os domínios do Office 365 melhorará a conectividade e o desempenho. Além disso, ignorar a inspeção de saída geralmente remove a necessidade de um único egresso de Internet e habilita a saída da Internet local para solicitações de rede de destino do Office 365.
    
6. Alguns clientes acham que as configurações de rede interna podem afetar o desempenho. Configurações como tamanho da unidade de transmissão máxima (MTU), negociação automática de rede ou detecção automática e rotas de alta qualidade para a Internet são locais comuns a serem pesquisados.
    
## <a name="network-planning-reference-for-office-365"></a>Referência de planejamento de rede para o Office 365
<a name="NetReference"> </a>

Estes tópicos contêm informações detalhadas de referência de rede do Office 365.
  
- [Gerenciar pontos de extremidade do Office 365](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)
    
- [Redes de distribuição de conteúdo](content-delivery-networks.md)
    
- [Registros de Sistema de Nomes de Domínio Externos para o Office 365](external-domain-name-system-records.md)
    
- [Suporte a IPv6 nos serviços do Office 365](ipv6-support.md)
    
- [Princípios de conectividade de rede do Office 365](https://aka.ms/o365networkingprinciples)
    
- [Perguntas frequentes sobre o sistema de rede de vídeo do Office 365](office-365-video-networking-faq.md)
    
- [Planejar dispositivos de rede que se conectam aos serviços do Office 365](plan-for-network-devices.md)
    
- [Guias de configuração para os serviços do Office 365](setup-guides-for-microsoft-365.md)
 
## <a name="see-also"></a>Confira também

[Visão geral do Microsoft 365 Enterprise](microsoft-365-overview.md)
