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
description: Este artigo contém links para informações sobre planejamento, teste e migração de rede para o Office 365.
ms.openlocfilehash: 2b08b05b8863fd9351510878f9438264bb2999f5
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/17/2020
ms.locfileid: "47948443"
---
# <a name="network-and-migration-planning-for-office-365"></a>Planejamento de migração e rede para o Office 365

*Esse artigo se aplica ao Microsoft 365 Enterprise e ao Office 365 Enterprise.*

Este artigo contém links para informações sobre planejamento e teste de rede e migração para o Office 365.
  
Antes de implantar pela primeira vez ou migrar para o Office 365, você pode usar as informações nestes tópicos para estimar a largura de banda necessária e, em seguida, testar e verificar se você tem largura de banda suficiente para implantar ou migrar para o Office 365.

Este artigo faz parte do [planejamento de rede e do ajuste de desempenho do Office 365.](https://aka.ms/tune)

Para ver as etapas para otimizar sua rede para o Microsoft 365 e outras plataformas e serviços em nuvem da Microsoft, consulte o cartaz Rede do [Microsoft Cloud para Arquitetos Corporativos.](https://aka.ms/cloudarchnetworking)
   
## <a name="estimate-network-bandwidth-requirements"></a>Estimar requisitos de largura de banda de rede
<a name="EstimateBandwidthRequirements"> </a>

Usar o Office 365 pode aumentar a utilização do circuito de Internet da sua organização. É importante determinar se a quantidade de largura de banda disponível no momento é suficiente para lidar com o aumento estimado depois que o Office 365 é totalmente implantado, deixando pelo menos 20% de capacidade para lidar com os dias mais movimentados.
  
Para estimar a largura de banda, use as seguintes etapas:
  
1. Avalie o número de clientes que usarão cada saída da Internet. Deixe nossa rede multi-terabit lidar com o máximo possível da conexão. 
    
2. Determine quais serviços e recursos do Office 365 estarão disponíveis para uso dos clientes. Você provavelmente terá grupos de pessoas com diferentes serviços ou perfis de uso.
    
3. Mede o uso da rede para um grupo piloto de clientes. Certifique-se de que os clientes piloto sejam representativos dos diferentes perfis de pessoas na organização, bem como das diferentes localizações geográficas. Você pode verificar seus resultados em relação às nossas calculadoras antigas para [o Exchange](https://techcommunity.microsoft.com/t5/exchange-team-blog/announcing-the-exchange-client-network-bandwidth-calculator-beta/ba-p/601744) e o [Microsoft Teams](https://docs.microsoft.com/microsoftteams/prepare-network) ou o estudo de caso [que](https://www.microsoft.com/itshowcase/Article/Content/631/Optimizing-network-performance-for-Microsoft-Office-365) realizamos em nossa própria rede. 
    
4. Use as medidas do grupo piloto para extrapolar as necessidades da organização inteira e testar outra vez para validar as estimativas antes de fazer alterações na rede.
    
## <a name="test-your-existing-network"></a>Testar sua rede existente
<a name="calculators"> </a>

 **Ferramentas de rede.** Teste e valide a largura de banda da Internet para determinar as restrições de download, upload e latência. Essas ferramentas ajudarão você a determinar os recursos da sua rede para migração, bem como após a implantação completa. 
    
- [Analisador de Conectividade Remota da Microsoft:](https://go.microsoft.com/fwlink/p/?LinkId=517243)testa a conectividade em seu ambiente do Exchange Online.
    
- Use o Assistente de Recuperação e Suporte [da Microsoft para Office 365](https://diagnostics.office.com/#/Download?env=SOC) para corrigir problemas do Outlook e do Office 365. 
    
## <a name="best-practices-for-network-planning-and-improving-migration-performance-for-office-365"></a>Práticas recomendadas para planejar a rede e melhorar o desempenho da migração para o Office 365
<a name="BestPractices"> </a>

Aprofunde-se um pouco nessas práticas recomendadas para obter mais informações sobre como melhorar sua experiência do Office 365.
  
1. Deseja começar a ajudar seus usuários imediatamente? Veja as práticas recomendadas para usar o [Office 365](https://support.office.com/article/fd16c8d2-4799-4c39-8fd7-045f06640166) em uma rede lenta para dicas sobre como usar o Office 365, incluindo o SharePoint Online, o Exchange Online e o Lync Online, quando sua rede simplesmente não está sendo um problema. Este artigo contém links para cargas de conteúdo no TechNet e no Support.office.com para otimizar sua experiência do Office 365 e inclui informações sobre maneiras fáceis de personalizar suas páginas da Web e como definir suas configurações do Internet Explorer para a melhor experiência do Office 365. 
    
2. Leia os Princípios de Conectividade de Rede do [Office 365](https://aka.ms/o365networkingprinciples) para entender os princípios de conectividade para gerenciar com segurança o tráfego do Office 365 e obter o melhor desempenho possível. Este artigo vai ajudá-lo a entender as diretrizes mais recentes para otimizar com segurança a conectividade de rede do Office 365. 
    
3. Melhore o desempenho da migração de email gerenciando cuidadosamente a agenda de atualizações do Windows. Você pode atualizar seus computadores clientes em lotes e garantir que todos os computadores clientes sejam atualizados antes de migrar para o Office 365 para regular o uso da largura de banda de rede. Para saber mais, confira Atualização manual e configuração de áreas de trabalho [do Office 365 para as atualizações mais recentes.](https://support.microsoft.com/gp/office-2013-365-update)
    
4. O tráfego de rede do Office 365 tem melhor desempenho quando é tratado como um serviço de Internet confiável e tem permissão para ignorar grande parte da filtragem e verificação tradicionais que algumas organizações agem no tráfego de rede para serviços de Internet não confiáveis. Isso geralmente inclui a remoção do processamento de saída, como a autenticação do usuário proxy e a inspeção de pacotes, além de garantir a saída local para a Internet com a NAT (Conversão de Endereços de Rede) adequada e capacidade de largura de banda suficiente para lidar com o aumento das solicitações de rede. Consulte Gerenciar pontos de extremidade do [Office 365](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)para obter mais orientações sobre como configurar sua rede para lidar com o Office 365 como um serviço de Internet confiável em sua rede.
    
1. [Certifique-se de gerenciar pontos de extremidade do Office 365.](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a) O tráfego adicional indo para o Office 365 resulta em um aumento das conexões de proxy de saída, bem como um aumento no tráfego seguro sobre TLS/SSL.
    
2. Se os proxies de saída exigirem autenticação do usuário, você poderá experimentar conectividade lenta ou perda de funcionalidade. Ignorar o requisito de autenticação para os domínios do Office 365 pode reduzir essa sobrecarga.
    
3. Se você tiver um grande número de calendários e caixas de correio compartilhadas, poderá ver um aumento no número de conexões do Outlook para o Exchange. Por exemplo, o cliente do Outlook pode abrir até duas conexões adicionais para cada calendário compartilhado em uso. Nessa situação, verifique se o proxy de saída pode manipular as conexões ou ignorar o proxy para conexões com o Office 365 para Outlook.
    
4. Determine o número máximo de dispositivos com suporte para um endereço IP público e como balancear a carga em vários endereços IP. Para saber mais, confira o [suporte nat com o Office 365.](nat-support-with-microsoft-365.md)
    
5. Se você estiver inspecionando conexões de saída de computadores em sua rede, ignorar essa filtragem para os domínios do Office 365 melhorará a conectividade e o desempenho. Além disso, ignorar a inspeção de saída geralmente elimina a necessidade de uma única saída da Internet e habilita a saída da Internet local para solicitações de rede destinadas ao Office 365.
    
6. Alguns clientes acham que as configurações de rede internas podem afetar o desempenho. Configurações como tamanho máximo de unidade de transmissão (MTU), negociação automática de rede ou detecção automática e rotas sub-ideais para a Internet são locais comuns a procurar.
    
## <a name="network-planning-reference-for-office-365"></a>Referência de planejamento de rede para o Office 365
<a name="NetReference"> </a>

Esses tópicos contêm informações detalhadas de referência de rede do Office 365.
  
- [Gerenciar pontos de extremidade do Office 365](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)
    
- [Redes de distribuição de conteúdo](content-delivery-networks.md)
    
- [Registros de Sistema de Nomes de Domínio Externos para o Office 365](external-domain-name-system-records.md)
    
- [Suporte a IPv6 nos serviços do Office 365](ipv6-support.md)
    
- [Princípios de conectividade de rede do Office 365](https://aka.ms/o365networkingprinciples)
    
- [Perguntas frequentes sobre redes de vídeo do Office 365](office-365-video-networking-faq.md)
    
- [Planejar dispositivos de rede que se conectam aos serviços do Office 365](plan-for-network-devices.md)
    
- [Guias de configuração para serviços do Office 365](setup-guides-for-microsoft-365.md)
 
## <a name="see-also"></a>Confira também

[Visão geral do Microsoft 365 Enterprise](microsoft-365-overview.md)
