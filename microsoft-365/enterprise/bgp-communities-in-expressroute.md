---
title: Usando comunidades BGP no ExpressRoute para cenários do Office 365
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 6/26/2018
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: 9ac4d7d4-d9f8-40a8-8c78-2a6d7fe96099
description: Saiba como usar comunidades BGP no Azure ExpressRoute para gerenciar o número de prefixos IP e largura de banda necessária para cenários do Office 365.
ms.openlocfilehash: 3a1de8725ae967352723649e602d944ca6948310
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46687367"
---
# <a name="using-bgp-communities-in-expressroute-for-office-365-scenarios"></a>Usando comunidades BGP no ExpressRoute para cenários do Office 365

Conectar-se ao Office 365 usando o Azure ExpressRoute é baseado em anúncios de BGP de sub-redes IP específicas que representam redes nas quais os pontos de extremidade do Office 365 estão implantados. Devido à natureza global do Office 365 e ao número de serviços que constituem o Office 365, os clientes geralmente precisam gerenciar os anúncios que eles aceitam em sua rede. Reduzir o número de sub-redes IP; chamado de prefixos IP no restante deste artigo, para alinhar-se com a terminologia de gerenciamento de rede do BGP, atende às seguintes metas finais para os clientes:
  
- **Gerenciar o número de prefixos IP anunciados aceitos** -clientes que possuem uma infraestrutura de rede interna ou uma operadora de rede que suporta apenas um número limitado de prefixos IP e clientes que têm uma operadora de rede que encargos por aceitar prefixos acima de um número limitado devem avaliar o número total de prefixos já anunciados para a sua rede e selecionar 365 quais

- **Gerenciar a quantidade de largura de banda necessária no circuito do Azure ExpressRoute** -os clientes podem querer controlar o envelope de largura de banda dos serviços do Office 365 sobre o caminho ExpressRoute vs. Internet Path. Isso permite que os clientes Reserve largura de banda do ExpressRoute para aplicativos específicos como o Skype for Business e roteiam os aplicativos do Office 365 restantes no caminho da Internet.

Para ajudar os clientes com essas metas, os prefixos IP do Office 365 anunciados no ExpressRoute são marcados com valores de comunidade BGP específicos do serviço, conforme mostrado no exemplo abaixo.
  
> [!NOTE]
> Você deve esperar que alguns tráfegos de rede associados a outros aplicativos sejam incluídos no valor da Comunidade. Esse é o comportamento esperado para um software global como uma oferta de serviço com serviços compartilhados e datacenters. Isso foi minimizado, sempre que possível, com as duas metas acima, gerenciando a contagem de prefixo e/ou a largura de banda em mente.

|**Serviço**|**Valor da Comunidade BGP**|**Observações**|
|:-----|:-----|:-----|
|Exchange Online\*  <br/> |12076:5010  <br/> |Inclui serviços do Exchange e do EOP\*  <br/> |
|SharePoint Online\*  <br/> |12076:5020  <br/> |SharePoint Online  <br/> |
|Skype for Business\*  <br/> |12076:5030  <br/> |Skype for Business online & serviços do Microsoft Teams  <br/> |
|Outros serviços do Office 365\*  <br/> |12076:5100  <br/> |Inclui o Azure Active Directory (cenários de sincronização de diretório e autenticação), bem como os serviços de portal do Office 365  <br/> |
|\* O escopo dos cenários de serviço incluídos no ExpressRoute está documentado no artigo de [pontos de extremidade do Office 365](https://aka.ms/o365endpoints) .  <br/> \*\*Os serviços adicionais e os valores da Comunidade BGP podem ser adicionados no futuro. [Consulte a lista atual de comunidades de BGP](https://azure.microsoft.com/documentation/articles/expressroute-routing/).  <br/> |

## <a name="what-are-the-most-common-scenarios-for-using-bgp-communities"></a>Quais são os cenários mais comuns para usar comunidades BGP?

Os clientes podem usar comunidades BGP para regular grupos de prefixos IP que são aceitos pela rede por meio do Azure ExpressRoute, influenciando a contagem total de prefixo IP e o envelope de largura de banda esperado de determinados serviços do Office 365. É importante entender que todo o Office 365 exigirá o tráfego de entrada da Internet, independentemente do uso das comunidades do Azure ExpressRoute ou BGP. Os três cenários a seguir são os usos mais comuns dessa funcionalidade.
  
### <a name="scenario-1-minimizing-the-number-of-office-365-ip-prefixes"></a>Cenário 1: minimizar o número de prefixos IP do Office 365

A Contoso Corporation é uma empresa de pessoa de 50.000 que atualmente usa o Office 365 para o Exchange Online e o SharePoint Online. Ao examinar os requisitos do ExpressRoute a contoso determina seus dispositivos de rede em muitos locais regionais não é possível lidar com tamanhos de tabela de roteamento acima 100 entradas de rota adicionais. A contoso analisou o número total de prefixos IP que o ExpressRoute anunciaria para o conjunto completo de serviços do Office 365 e concluiu que excede 100. Para permanecer sob as entradas de rota adicionais 100, a contoso escopo o uso do ExpressRoute para o Office 365 apenas para o valor da Comunidade BGP online do SharePoint, 12076:5020, recebido por meio de emparelhamento da Microsoft.

|**Marca de comunidade BGP usada**|**Funcionalidade roteável sobre o Azure ExpressRoute**|**Rotas da Internet necessárias**|
|:-----|:-----|:-----|
|SharePoint  <br/> (12076:5020)  <br/> |SharePoint Online &amp; onedrive for Business  <br/> | Solicitações de DNS, CRL, &amp; CDN  <br/>  Todos os outros serviços do Office 365 não suportados especificamente no Azure ExpressRoute  <br/>  Todos os outros serviços do Microsoft Cloud  <br/>  Portal do Office 365, autenticação do Office 365, &amp; Office em um navegador  <br/>  Exchange Online, proteção do Exchange Online e Skype for Business Online  <br/> |

> [!NOTE]
> Para obter contagens de prefixo mais baixas para cada serviço, uma quantidade mínima de sobreposição entre os serviços persistirá. Esse é um comportamento esperado.
  
### <a name="scenario-2-scoping-expressroute-and-internal-bandwidth-use-to-some-office-365-services"></a>Cenário 2: escopo ExpressRoute e largura de banda interna usada para alguns serviços do Office 365

A Fabrikam Inc, uma grande empresa multinacional com uma rede heterogênea distribuída, é um assinante de muitos serviços do Office 365, incluindo; Exchange Online, SharePoint Online e Skype for Business online. A infraestrutura de roteamento interna da Fabrikam pode lidar com milhares de prefixos IP em suas tabelas de roteamento; no entanto, a Fabrikam só quer provisionar o ExpressRoute e largura de banda interna para aplicativos do Office 365 que são mais confidenciais para o desempenho da rede e usar a largura de banda da Internet existente para todos os outros aplicativos do Office 365.
  
Por esse motivo, a Fabrikam escopoá sua largura de banda do Azure ExpressRoute para apenas o valor da Comunidade BGP do Skype for Business Online, 12076:5030, recebidas por meio de emparelhamento da Microsoft. O tráfego de rede restante associado ao Office 365 continua a usar os pontos de saída da Internet.

|**Marca de comunidade BGP usada**|**Funcionalidade roteável sobre o Azure ExpressRoute**|**Rotas da Internet necessárias**|
|:-----|:-----|:-----|
|Skype for Business  <br/> (12076:5030)  <br/> |Sinalização SIP do Skype, downloads, voz, vídeo e compartilhamento de área de trabalho  <br/> | Solicitações de DNS, CRL, &amp; CDN  <br/>  Todos os outros serviços do Office 365 não suportados especificamente no Azure ExpressRoute  <br/>  Todos os outros serviços do Microsoft Cloud  <br/>  Portal do Office 365, autenticação do Office 365, &amp; Office em um navegador  <br/>  Telemetria do Skype for Business, dicas rápidas de cliente do Skype, conectividade de IM pública  <br/>  Exchange Online, proteção do Exchange Online e SharePoint Online  <br/> |

### <a name="scenario-3-scoping-azure-expressroute-for-office-365-services-only"></a>Cenário 3: escopo do Azure ExpressRoute somente para serviços do Office 365

O Woodgrove Bank é um cliente de vários serviços de nuvem da Microsoft, incluindo o Office 365. Após avaliar sua capacidade de rede e consumo o Woodgrove Bank decide implantar o Azure ExpressRoute como o caminho preferencial para os serviços do Office 365 com suporte. As tabelas de roteamento podem suportar o conjunto completo de prefixos IP 365 do Office e os circuitos do Azure ExpressRoute que foram provisionados dão suporte a todas as necessidades de largura de banda e latência projetadas.
  
Para garantir o tráfego de rede associado aos serviços de nuvem da Microsoft diferentes do Office 365, os escopos do Woodgrove Bank o uso do ExpressRoute para o Office 365 a todos os prefixos IP marcados com os valores de comunidade BGP específicos do Office 365, 12076:5010, 12076:5020, 12076:5030, 12076:5100.

|**Marca de comunidade BGP usada**|**Funcionalidade roteável sobre o Azure ExpressRoute**|**Rotas da Internet necessárias**|
|:-----|:-----|:-----|
|Exchange, Skype for Business & Microsoft Teams, SharePoint, &amp; outros serviços  <br/> (12076:5010, 12076:5020, 12076:5030, 12076:5100)  <br/> |Proteção do Exchange Online do Exchange Online &amp;  <br/> SharePoint Online &amp; onedrive for Business  <br/> Sinalização SIP do Skype, downloads, voz, vídeo e compartilhamento de área de trabalho  <br/> Portal do Office 365, autenticação do Office 365, &amp; Office em um navegador  <br/> | Solicitações de DNS, CRL, &amp; CDN  <br/>  Todos os outros serviços do Office 365 não suportados especificamente no Azure ExpressRoute  <br/>  Todos os outros serviços do Microsoft Cloud  <br/> |

## <a name="key-planning-considerations-to-using-bgp-communities"></a>Principais considerações de planejamento para usar comunidades BGP

Os clientes que optam por aproveitar as comunidades de BGP para influenciar como o ExpressRoute é anunciado e propagado por meio da rede do cliente deve levar em conta as seguintes considerações:
  
- Ao usar comunidades BGP em seu design de rede, é importante garantir que a simetria da rota ainda seja mantida. Em alguns casos, a adição ou remoção de comunidades BGP pode criar uma situação em que o roteamento simétrico é interrompido e sua configuração de roteamento deve ser atualizada para restabelecer o roteamento simétrico.

- Escopo o Azure ExpressRoute com valores de comunidade BGP é uma ação de cliente. A Microsoft anunciará todos os prefixos IP associados à relação de emparelhamento independente de qualquer escopo configurado pelo cliente.

- O Azure ExpressRoute não dá suporte a ações na rede da Microsoft com base nas comunidades de BGP atribuídas pelo cliente.

- Os prefixos IP usados pelo Office 365 são marcados apenas com valores de comunidade de BGP específicos de serviço, comunidades BGP específicas de local não são suportadas. Os serviços do Office 365 são globais por natureza, não há suporte para a filtragem de prefixos com base no local do locatário ou dados dentro da nuvem do Office 365. A abordagem recomendada é configurar sua rede para coordenar o caminho de rede mais curto ou preferencial do local da rede do usuário para a rede global da Microsoft, independentemente do local físico do endereço IP do serviço do Office 365 que está solicitando.

- Os prefixos IP incluídos em cada valor de comunidade BGP representam uma sub-rede que contém endereços IP para o aplicativo do Office 365 associado ao valor. Em alguns casos, mais de um aplicativo do Office 365 tem endereços IP dentro de uma sub-rede que resultam em um prefixo IP existente em mais de um valor de comunidade. Isso é esperado, embora raramente, o comportamento devido à fragmentação de alocação e não afeta a contagem de prefixo ou as metas de gerenciamento de largura de banda. Os clientes são incentivados a usar a abordagem "permitir o que é necessário" em vez de "negar o que não é necessário" ao aproveitar as vantagens de comunidades BGP para o Office 365 para minimizar o efeito.

- O uso de comunidades BGP não altera os requisitos de conectividade de rede subjacentes ou a configuração necessária para usar o Office 365. Os clientes que desejam acessar o Office 365 ainda precisam ter acesso à Internet.

- O escopo do Azure ExpressRoute com comunidades BGP só afeta as rotas que sua rede interna pode ver sobre a relação de emparelhamento da Microsoft. Você pode precisar fazer configurações de nível de aplicativo adicionais, como o uso de uma PAC ou configuração de WPAD em conjunto com o roteamento com escopo.

- Além de usar as comunidades de BGP atribuídas pela Microsoft, os clientes podem optar por atribuir suas próprias comunidades de BGP aos prefixos IP do Office 365 aprendidas por meio do Azure ExpressRoute para influenciar o roteamento interno. Um caso de uso popular é atribuir uma comunidade de BGP baseada em local a todas as rotas aprendidas por cada um dos locais de emparelhamento do ExpressRoute e, em seguida, usar essas informações downstream na rede do cliente para coordenar o caminho de rede mais curto ou preferencial para a rede da Microsoft. O uso de comunidades de BGP atribuídas ao cliente com o ExpressRoute para cenários do Office 365 está fora do escopo da visibilidade ou controle da Microsoft.

Aqui está um link curto que você pode usar para voltar: [https://aka.ms/bgpexpressroute365](https://aka.ms/bgpexpressroute365) .
  
## <a name="related-topics"></a>Tópicos Relacionados

[Avaliando a conectividade de rede do Office 365](assessing-network-connectivity.md)
  
[Microsoft Azure ExpressRoute para Office 365](azure-expressroute.md)
  
[Como gerenciar o ExpressRoute para a conectividade do Office 365](managing-expressroute-for-connectivity.md)
  
[Como rotear com o ExpressRoute para Office 365](routing-with-expressroute.md)
  
[Planejamento de rede com o ExpressRoute para Office 365](network-planning-with-expressroute.md)
  
[Qualidade da mídia e desempenho de conectividade de rede no Skype for Business Online](https://support.office.com/article/5fe3e01b-34cf-44e0-b897-b0b2a83f0917)
  
[ExpressRoute e QoS no Skype for Business Online](https://support.office.com/article/20c654da-30ee-4e4f-a764-8b7d8844431d)
  
[Fluxo de chamadas usando o ExpressRoute](https://support.office.com/article/413acb29-ad83-4393-9402-51d88e7561ab)
  
[Como implementar o ExpressRoute para Office 365](implementing-expressroute.md)
  
[Suporte para comunidades BGP](https://azure.microsoft.com/documentation/articles/expressroute-routing/)
  
[Ajuste de desempenho do Office 365 usando linhas de base e histórico de desempenho](performance-tuning-using-baselines-and-history.md)
  
[Plano de solução de problemas de desempenho do Office 365](performance-troubleshooting-plan.md)
  
[Treinamento do Azure ExpressRoute para Office 365](https://channel9.msdn.com/series/aer)
