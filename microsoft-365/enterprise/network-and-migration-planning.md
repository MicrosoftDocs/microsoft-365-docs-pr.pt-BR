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
description: Este artigo contém links para informações sobre planejamento, teste e migração de rede para Office 365.
ms.openlocfilehash: 99bcc1bd0447b192860fc0bcc67fc18d87c2d5fc
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50923583"
---
# <a name="network-and-migration-planning-for-office-365"></a>Planejamento de migração e rede para o Office 365

*Esse artigo se aplica ao Microsoft 365 Enterprise e ao Office 365 Enterprise.*

Este artigo contém links para informações sobre planejamento e teste de rede e migração para Office 365.
  
Antes de implantar pela primeira vez ou migrar para o Office 365, você pode usar as informações nesses tópicos para estimar a largura de banda necessária e, em seguida, testar e verificar se você tem largura de banda suficiente para implantar ou migrar para Office 365.

Este artigo faz parte do [planejamento de rede e ajuste de desempenho para Office 365](./network-planning-and-performance.md).

Para ver as etapas para otimizar sua rede para Microsoft 365 e outras plataformas e serviços de nuvem da Microsoft, consulte o cartaz [do Microsoft Cloud Networking para Enterprise Arquitetos.](../solutions/cloud-architecture-models.md)
   
## <a name="estimate-network-bandwidth-requirements"></a>Estimar requisitos de largura de banda de rede
<a name="EstimateBandwidthRequirements"> </a>

Usar Office 365 pode aumentar a utilização do circuito da Internet da sua organização. É importante determinar se a quantidade de largura de banda disponível no momento é suficiente para lidar com o aumento estimado quando o Office 365 estiver totalmente implantado, deixando pelo menos 20% de capacidade para lidar com os dias mais movimentados.
  
Para estimar a largura de banda, use as seguintes etapas:
  
1. Avalie o número de clientes que usarão cada saída da Internet. Deixe nossa rede de vários terabits manipular a maior parte da conexão possível. 
    
2. Determine quais Office 365 serviços e recursos estarão disponíveis para os clientes usarem. Você provavelmente terá grupos de pessoas com diferentes serviços ou perfis de uso.
    
3. Mede o uso da rede para um grupo piloto de clientes. Verifique se os clientes piloto são representativos dos diferentes perfis de pessoas na organização, bem como das diferentes localizações geográficas. Você pode verificar os resultados entre nossas [](https://techcommunity.microsoft.com/t5/exchange-team-blog/announcing-the-exchange-client-network-bandwidth-calculator-beta/ba-p/601744) calculadoras antigas Exchange e Microsoft Teams [](https://www.microsoft.com/itshowcase/Article/Content/631/Optimizing-network-performance-for-Microsoft-Office-365) [ou](/microsoftteams/prepare-network) o estudo de caso que realizamos em nossa própria rede. 
    
4. Use as medidas do grupo piloto para extrapolar as necessidades de toda a organização e testar de forma a validar as estimativas antes de fazer qualquer alteração na rede.
    
## <a name="test-your-existing-network"></a>Testar sua rede existente
<a name="calculators"> </a>

 **Ferramentas de rede.** Teste e valide sua largura de banda da Internet para determinar restrições de download, upload e latência. Essas ferramentas ajudarão você a determinar os recursos da sua rede para migração, bem como depois de ser totalmente implantado. 
    
- [Analisador de Conectividade Remota da Microsoft](https://go.microsoft.com/fwlink/p/?LinkId=517243): testa a conectividade em seu Exchange Online ambiente.
    
- Use o [microsoft Assistente de Recuperação e Suporte para Office 365](https://diagnostics.office.com/#/Download?env=SOC) para corrigir Outlook e Office 365 problemas. 
    
## <a name="best-practices-for-network-planning-and-improving-migration-performance-for-office-365"></a>Práticas recomendadas para planejamento de rede e melhoria do desempenho de migração para Office 365
<a name="BestPractices"> </a>

Aprofunde um pouco mais nessas práticas recomendadas para obter mais informações sobre como melhorar sua Office 365 experiência.
  
1. Quer começar a ajudar seus usuários imediatamente? Consulte [Práticas recomendadas](https://support.office.com/article/fd16c8d2-4799-4c39-8fd7-045f06640166) para usar Office 365 em uma rede lenta para dicas sobre como usar o Office 365, incluindo o SharePoint Online, Exchange Online e Lync Online, quando sua rede não está cooperando. Este artigo vincula-se a cargas de conteúdo no TechNet e no Support.office.com para otimizar sua experiência Office 365 e inclui informações sobre maneiras fáceis de personalizar suas páginas da Web e como definir suas configurações do Internet Explorer para a melhor experiência de Office 365. 
    
2. Leia [Office 365 Princípios](./microsoft-365-network-connectivity-principles.md) de Conectividade de Rede para entender os princípios de conectividade para gerenciar com segurança Office 365 tráfego e obter o melhor desempenho possível. Este artigo vai ajudá-lo a entender as diretrizes mais recentes para otimizar com segurança a conectividade de rede do Office 365. 
    
3. Aprimora o desempenho da migração de email gerenciando cuidadosamente o cronograma para Windows Atualizações. Você pode atualizar seus computadores clientes em lotes e garantir que todos os computadores clientes sejam atualizados antes de migrar para Office 365 para regular o uso da largura de banda de rede. Para obter mais informações, consulte Atualização manual e configurar áreas de trabalho para Office 365 [para as atualizações mais recentes.](https://support.microsoft.com/gp/office-2013-365-update)
    
4. Office 365 o tráfego de rede tem melhor desempenho quando é tratado como um serviço de Internet confiável e tem permissão para ignorar grande parte da filtragem tradicional e da verificação que algumas organizações agem no tráfego de rede para serviços não confiáveis da Internet. Isso geralmente inclui remover o processamento de saída, como autenticação de usuário proxy e inspeção de pacotes, bem como garantir a saída local para a Internet com a NAT (Conversão de Endereço de Rede) adequada e capacidade de largura de banda suficiente para lidar com as solicitações de rede aumentadas. Consulte [Managing Office 365 endpoints](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)for additional guidance on configuring your network to handle Office 365 as a trusted Internet service on your network.
    
1. [Certifique-se de gerenciar Office 365 pontos de extremidade](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a). O tráfego adicional que Office 365 resulta em um aumento de conexões de proxy de saída, bem como um aumento no tráfego seguro sobre TLS/SSL.
    
2. Se seus proxies de saída exigirem autenticação do usuário, você poderá ter uma conectividade lenta ou uma perda de funcionalidade. Ignorar o requisito de autenticação para os domínios Office 365 pode reduzir essa sobrecarga.
    
3. Se você tiver um grande número de calendários e caixas de correio compartilhadas, poderá ver um aumento no número de conexões de Outlook para Exchange. Por exemplo, o Outlook cliente pode abrir até duas conexões adicionais para cada calendário compartilhado em uso. Nessa situação, certifique-se de que o proxy de saída possa manipular as conexões ou ignorar o proxy para conexões Office 365 para Outlook.
    
4. Determine o número máximo de dispositivos com suporte para um endereço IP público e como carregar o equilíbrio entre vários endereços IP. Para obter mais informações, [consulte suporte nat com Office 365](nat-support-with-microsoft-365.md).
    
5. Se você estiver inspecionando conexões de saída de computadores em sua rede, ignorar essa filtragem para os domínios de Office 365 melhorará a conectividade e o desempenho. Além disso, ignorar a inspeção de saída geralmente remove a necessidade de uma única saída da Internet e habilita a saída local da Internet para Office 365 de rede destinadas.
    
6. Alguns clientes encontram configurações de rede internas que podem afetar o desempenho. Configurações tamanho máximo da unidade de transmissão (MTU), negociação automática de rede ou detecção automática e rotas sub-ideais para a Internet são locais comuns de se procurar.
    
## <a name="network-planning-reference-for-office-365"></a>Referência de planejamento de rede para Office 365
<a name="NetReference"> </a>

Esses tópicos contêm informações detalhadas Office 365 de referência de rede.
  
- [Gerenciar pontos de extremidade do Office 365](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)
    
- [Redes de distribuição de conteúdo](content-delivery-networks.md)
    
- [Registros de Sistema de Nomes de Domínio Externos para o Office 365](external-domain-name-system-records.md)
    
- [Suporte a IPv6 nos serviços do Office 365](ipv6-support.md)
    
- [Princípios de conectividade de rede do Office 365](./microsoft-365-network-connectivity-principles.md)
    
- [Office 365 de vídeo perguntas frequentes (perguntas frequentes)](office-365-video-networking-faq.md)
    
- [Planejar dispositivos de rede que se conectam aos serviços do Office 365](plan-for-network-devices.md)
    
- [Guias de instalação para Office 365 serviços](setup-guides-for-microsoft-365.md)
 
## <a name="see-also"></a>Confira também

[Visão geral do Microsoft 365 Enterprise](microsoft-365-overview.md)