---
title: Planejamento de rede com o ExpressRoute para Office 365
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 2/14/2018
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: 103208f1-e788-4601-aa45-504f896511cd
description: Neste artigo, você aprenderá sobre o Azure ExpressRoute para Office 365 e como utilizá-lo para planejamento de rede.
ms.openlocfilehash: 440d4fafadd7e9b504dc4ffdac1123a2956ed798
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50923571"
---
# <a name="network-planning-with-expressroute-for-office-365"></a>Planejamento de rede com o ExpressRoute para Office 365

*Este artigo se aplica tanto ao Microsoft 365 Enterprise quanto ao Office 365 Enterprise.*

O ExpressRoute para Office 365 fornece conectividade da camada 3 entre sua rede e os datacenters da Microsoft. Os circuitos usam anúncios de rota BGP (Protocolo de Gateway de Borda) dos servidores front-end do Office 365. Na perspectiva de seus dispositivos locais, quando eles precisam selecionar o caminho TCP/IP correto para o Office 365, o Azure ExpressRoute é visto como uma alternativa à Internet.
  
O Azure ExpressRoute adiciona um caminho direto a um conjunto específico de recursos e serviços com suporte oferecidos pelos servidores do Office 365 nos datacenters da Microsoft. O Azure ExpressRoute não substitui a conectividade com a Internet para datacenters da Microsoft ou serviços básicos da Internet, como resolução de nome de domínio. O Azure ExpressRoute e seus circuitos de Internet devem ser protegidos e redundantes.
  
A tabela a seguir destaca algumas diferenças entre a Internet e as conexões do Azure ExpressRoute no contexto do Office 365.

|**Diferenças no planejamento de rede**|**Conexão de rede com a Internet**|**Conexão de rede ExpressRoute**|
|:-----|:-----|:-----|
| Acesso aos serviços de Internet necessários, incluindo;  <br/>  Resolução de nome DNS  <br/>  Verificação de revogação de certificado  <br/>  Redes de distribuição de conteúdo  <br/> |Sim  <br/> |As solicitações para a infraestrutura DNS e/ou CDN de propriedade da Microsoft podem usar a rede ExpressRoute.  <br/> |
| Acesso aos serviços do Office 365, incluindo;  <br/>  Exchange Online  <br/>  SharePoint Online  <br/>  Skype for Business Online  <br/>  Office em um navegador  <br/>  Portal e Autenticação do Office 365  <br/> |Sim, todos os aplicativos e recursos  <br/> |Sim, [aplicativos e recursos específicos](./urls-and-ip-address-ranges.md) <br/> |
|Segurança local no perímetro.  <br/> |Sim  <br/> |Sim  <br/> |
|Planejamento de alta disponibilidade.  <br/> |Failover para uma conexão de rede de Internet alternativa  <br/> |Failover para uma conexão ExpressRoute alternativa  <br/> |
|Conexão direta com um perfil de rede previsível.  <br/> |Não  <br/> |Sim  <br/> |
|Conectividade IPv6.  <br/> |Sim  <br/> |Sim  <br/> |

Expanda os títulos abaixo para obter mais diretrizes de planejamento de rede. Também gravamos uma série de treinamento do [Azure ExpressRoute](https://channel9.msdn.com/series/aer) de 10 partes para o Office 365 que se aprofunda mais.

## <a name="existing-azure-expressroute-customers"></a>Clientes existentes do Azure ExpressRoute

Se você estiver usando um circuito existente do Azure ExpressRoute e quiser adicionar conectividade do Office 365 a esse circuito, você deverá ver o número de circuitos, locais de saída e tamanho dos circuitos para garantir que eles atenderão às necessidades de seu uso do Office 365. A maioria dos clientes exige largura de banda adicional e muitos exigem circuitos adicionais.
  
Para habilitar o acesso ao Office 365 nos circuitos [](/azure/expressroute/how-to-routefilter-portal) existentes do Azure ExpressRoute, configure os filtros de rota para garantir que os serviços do Office 365 sejam acessíveis.
  
A assinatura do Azure ExpressRoute é centrada no cliente, o que significa que as assinaturas estão vinculadas aos clientes. Como cliente, você pode ter vários circuitos do Azure ExpressRoute e pode acessar muitos recursos de nuvem da Microsoft nesses circuitos. Por exemplo, você pode optar por acessar uma máquina virtual hospedada do Azure, um locatário de teste do Office 365 e um locatário de produção do Office 365 em vez de um par de circuitos redundantes do Azure ExpressRoute.
  
Esta tabela descreve os dois tipos de relações de paridade que você pode optar por implementar ao longo de seus circuitos.

|**Relação de paridade**|**Azure Private**|**Microsoft**|
|:-----|:-----|:-----|
|**Serviços** <br/> |IaaS: Máquinas virtuais do Azure  <br/> |PaaS: serviços públicos do Azure  <br/> SaaS: Office 365  <br/> SaaS: Dynamics 365  <br/> |
|Iniciação de conexão**** <br/> |Cliente para Microsoft  <br/> Microsoft para Cliente  <br/> |Cliente para Microsoft  <br/> Microsoft para Cliente  <br/> |
|**Suporte a QoS** <br/> |Sem QoS  <br/> |QoS<sup>1</sup> <br/> |

<sup>1 </sup> A QoS dá suporte ao Skype for Business somente no momento.
  
## <a name="bandwidth-planning-for-azure-expressroute"></a>Planejamento de largura de banda do Azure ExpressRoute

Cada cliente do Office 365 tem necessidades de largura de banda exclusivas, dependendo do número de pessoas em cada local, do quão ativos eles estão com cada aplicativo do Office 365 e outros fatores, como o uso de equipamentos locais ou híbridos e configurações de segurança de rede.
  
Ter pouca largura de banda resultará em congestionamento, retransmissões de dados e atrasos imprevisíveis. Ter muita largura de banda resultará em custos desnecessários. Em uma rede existente, a largura de banda geralmente é referida em termos da quantidade de espaço de cabeamento disponível no circuito como uma porcentagem. Ter 10% de espaço na cabeça provavelmente resultará em congestionamento e ter 80% de espaço de cabeamento geralmente significa custo desnecessário. As alocações típicas de destino do headroom são de 20% a 50%.
  
Para encontrar o nível correto de largura de banda, o melhor mecanismo é testar o consumo de rede existente. Essa é a única maneira de obter uma medida verdadeira de uso e necessidade, pois cada configuração de rede e aplicativos são de algumas maneiras exclusivas. Ao medir, você precisará prestar muita atenção ao consumo total de largura de banda, latência e congestionamento TCP para entender suas necessidades de rede.
  
Depois de ter uma linha de base estimada que inclui todos os aplicativos de rede, o Office 365 piloto com um pequeno grupo que compreende os diferentes perfis de pessoas em sua organização para determinar o uso real e usar as duas medidas para estimar a quantidade de largura de banda necessária para cada local do escritório. Se houver algum problema de latência ou congestionamento TCP encontrado em seu teste, talvez seja necessário mover a saída para mais perto das pessoas que usam o Office 365 ou remover a verificação intensiva de rede, como descriptografia/inspeção SSL.
  
Todas as nossas recomendações sobre qual tipo de processamento de rede é recomendado se aplica a circuitos ExpressRoute e Internet. O mesmo é verdadeiro para o restante das diretrizes em nosso site de ajuste [de desempenho.](./network-planning-and-performance.md)
  
## <a name="applying-security-controls-to-azure-expressroute-for-office-365-scenarios"></a>Aplicação de controles de segurança ao Azure ExpressRoute para cenários do Office 365

A segurança da conectividade do Azure ExpressRoute começa com os mesmos princípios que proteger a conectividade com a Internet. Muitos clientes optam por implantar controles de rede e perímetro ao longo do caminho do ExpressRoute conectando sua rede local ao Office 365 e outras nuvens da Microsoft. Esses controles podem incluir firewalls, proxies de aplicativos, prevenção contra vazamento de dados, detecção de intrusão, sistemas de prevenção contra intrusões e assim por diante. Em muitos casos, os clientes aplicam diferentes níveis de controles ao tráfego iniciados no local indo para a Microsoft, versus o tráfego iniciado a partir da Microsoft indo para a rede local do cliente, versus o tráfego iniciado a partir de um local indo para um destino geral da Internet.
  
Aqui estão alguns exemplos de integração de segurança com o modelo de conectividade [ExpressRoute](/azure/expressroute/expressroute-connectivity-models) que você escolhe implantar.

|**Opção de integração expressRoute**|**Modelo de perímetro de segurança de rede**|
|:-----|:-----|
|Co-localizado em um exchange de nuvem  <br/> |Instale nova ou aproveite a infraestrutura de segurança/perímetro existente na instalação de co-localização onde a conexão ExpressRoute está estabelecida.  <br/> Aproveite a instalação de co-local puramente para fins de roteamento/interconexão e conexões de back-haul do recurso de co-localização para a infraestrutura local de segurança/perímetro.  <br/> |
|Ethernet ponto a ponto  <br/> |Termine a conexão ExpressRoute Ponto a Ponto no local de infraestrutura de segurança/perímetro local existente.  <br/> Instale a nova infraestrutura de segurança/perímetro específica do caminho ExpressRoute e termine a conexão Ponto a Ponto.  <br/> |
|Any-to-Any IPVPN  <br/> |Aproveite uma infraestrutura de segurança/perímetro local existente em todos os locais que se aproximam do IPVPN usado para o ExpressRoute para conectividade do Office 365.  <br/> Hairpin o IPVPN usado para ExpressRoute para Office 365 para locais locais específicos designados para servir como segurança/perímetro.  <br/> |

Alguns provedores de serviços também oferecem funcionalidade gerenciada de segurança/perímetro como parte de suas soluções de integração com o Azure ExpressRoute.
  
Ao considerar a colocação de topologia das opções de perímetro de rede/segurança usadas para expressroute para conexões do Office 365, a seguir estão considerações adicionais
  
- Os controles de profundidade e de tipo de rede/segurança podem ter impacto no desempenho e na escalabilidade da experiência do usuário do Office 365.

- Fluxos de saída (local– Microsoft) e de entrada \> (Microsoft- local) [se habilitado] podem ter \> requisitos diferentes. Eles provavelmente são diferentes de Saída para destinos gerais da Internet.

- Os requisitos do Office 365 para portas/protocolos e sub-redes IP necessárias são os mesmos se o tráfego é roteado por meio do ExpressRoute para Office 365 ou pela Internet.

- A colocação topológica dos controles de rede/segurança do cliente determina a rede de ponta a ponta entre o usuário e o serviço do Office 365 e pode ter um impacto substancial na latência e no congestionamento da rede.

- Os clientes são incentivados a projetar sua topologia de segurança/perímetro para uso com o ExpressRoute para o Office 365, de acordo com as práticas recomendadas para redundância, alta disponibilidade e recuperação de desastres.

Veja um exemplo do Woodgrove Bank que compara as diferentes opções de conectividade do Azure ExpressRoute com os modelos de segurança de perímetro discutidos acima.
  
### <a name="example-1-securing-azure-expressroute"></a>Exemplo 1: Proteger o Azure ExpressRoute
  
O Woodgrove Bank está pensando em implementar o Azure ExpressRoute e, depois de planejar a arquitetura ideal para Roteamento com [o ExpressRoute para Office 365](routing-with-expressroute.md) e depois de usar as diretrizes acima para entender os requisitos de largura de banda, eles estão determinando o melhor método para proteger seu perímetro.
  
Para Woodgrove, uma organização multi-nacional com locais em vários continentes, a segurança deve abranger todos os perímetros. A opção de conectividade ideal para Woodgrove é uma conexão de vários pontos com vários locais de pariação ao redor do mundo para a fim de atendimento às necessidades de seus funcionários em cada continente. Cada continente inclui circuitos redundantes do Azure ExpressRoute dentro do continente e a segurança deve abranger todos eles.
  
A infraestrutura existente de Woodgrove é confiável e pode lidar com o trabalho adicional, como resultado, o Woodgrove Bank é capaz de usar a infraestrutura para sua segurança de perímetro do Azure ExpressRoute e da Internet. Se não fosse esse o caso, Woodgrove poderia optar por comprar equipamentos adicionais para complementar seus equipamentos existentes ou manipular um tipo diferente de conexão.
  
## <a name="high-availability-and-failover-with-azure-expressroute"></a>Alta disponibilidade e failover com o Azure ExpressRoute
<a name="BKMK_high-availability"> </a>

Recomendamos o provisionamento de pelo menos dois circuitos ativos de cada saída com ExpressRoute para o provedor ExpressRoute. Esse é o lugar mais comum que vemos falhas para clientes e você pode evitá-lo facilmente provisionando um par de circuitos ExpressRoute ativos/ativos. Também recomendamos pelo menos dois circuitos ativos/ativos da Internet, pois muitos serviços do Office 365 estão disponíveis apenas pela Internet.
  
Dentro do ponto de saída da sua rede estão muitos outros dispositivos e circuitos que desempenham um papel crítico na maneira como as pessoas percebem a disponibilidade. Essas partes de seus cenários de conectividade não são abordadas por SLAs do ExpressRoute ou do Office 365, mas desempenham um papel fundamental na disponibilidade de serviço de ponta a ponta, conforme percebido pelas pessoas em sua organização.
  
Concentre-se nas pessoas que usam e operam o Office 365, se uma falha de qualquer componente afetar a experiência das pessoas usando o serviço, procure maneiras de limitar a porcentagem total de pessoas afetadas. Se um modo de failover for operacionalmente complexo, considere a experiência das pessoas de muito tempo para recuperação e procure modos de failover operacionalmente simples e automatizados.
  
Fora da sua rede, o Office 365, o ExpressRoute e seu provedor ExpressRoute têm níveis de disponibilidade diferentes.
  
### <a name="service-availability"></a>Disponibilidade do serviço
  
- Os serviços do Office 365 são cobertos por contratos de nível de serviço bem [definidos](/office365/servicedescriptions/office-365-platform-service-description/service-level-agreement), que incluem métricas de tempo de atividade e disponibilidade para serviços individuais. Um motivo pelo qual o Office 365 pode manter níveis de disponibilidade de serviço tão altos é a capacidade dos componentes individuais de fazer failover perfeitamente entre os vários datacenters da Microsoft, usando a rede global da Microsoft. Esse failover se estende do datacenter e da rede para os vários pontos de saída da Internet e permite o failover perfeitamente da perspectiva das pessoas que usam o serviço.

- O ExpressRoute fornece um SLA de disponibilidade de [99,9%](https://azure.microsoft.com/support/legal/sla/expressroute/v1_0/) em circuitos individuais dedicados entre o Microsoft Network Edge e o provedor expressRoute ou a infraestrutura de parceiros. Esses níveis de serviço são aplicados no nível do circuito ExpressRoute, que consiste em duas [interconexões](/azure/expressroute/expressroute-introduction) independentes entre o equipamento redundante da Microsoft e o equipamento do provedor de rede em cada local de peering.

### <a name="provider-availability"></a>Disponibilidade do provedor
  
- As modalidades de nível de serviço da Microsoft param em seu provedor ou parceiro expressRoute. Este também é o primeiro lugar em que você pode fazer escolhas que influenciarão seu nível de disponibilidade. Você deve avaliar de perto as características de arquitetura, disponibilidade e resiliência que seu provedor ExpressRoute oferece entre seu perímetro de rede e sua conexão de provedores em cada local de paração da Microsoft. Preste muita atenção aos aspectos lógicos e físicos da redundância, do equipamento de paração, dos circuitos WAN fornecidos pela operadora e de qualquer valor adicional adicione serviços como serviços NAT ou firewalls gerenciados.

### <a name="designing-your-availability-plan"></a>Projetando seu plano de disponibilidade
  
Recomendamos que você planeje e projete alta disponibilidade e resiliência em seus cenários de conectividade de ponta a ponta para o Office 365. Um design deve incluir;
  
- nenhum ponto único de falha, incluindo os circuitos Internet e ExpressRoute.

- minimizando o número de pessoas afetadas e a duração desse impacto para os modos de falha mais esperados.

- otimizando para o processo de recuperação simples, repetido e automático dos modos de falha mais esperados.

- suportando as demandas completas do tráfego de rede e funcionalidade por meio de caminhos redundantes, sem degradação substancial.

Seus cenários de conectividade devem incluir uma topologia de rede otimizada para vários caminhos de rede independentes e ativos para o Office 365. Isso gerará uma melhor disponibilidade de ponta a ponta do que uma topologia otimizada apenas para redundância no nível de equipamento ou dispositivo individual.
  
> [!TIP]
> Se seus usuários são distribuídos em vários continentes ou regiões geográficas e cada um desses locais se conecta por circuitos WAN redundantes a um único local onde um único circuito ExpressRoute está localizado, seus usuários terão menos disponibilidade de serviço de ponta a ponta do que um design de topologia de rede que inclui circuitos ExpressRoute independentes que conectam as diferentes regiões ao local de par mais próximo.
  
Recomendamos o provisionamento de pelo menos dois circuitos ExpressRoute com cada circuito que se conecta a um local de paração geográfica diferente. Você deve provisionar esse par ativo de circuitos para cada região onde as pessoas usarão a conectividade ExpressRoute para serviços do Office 365. Isso permite que cada região permaneça conectada durante um desastre que afeta um local importante, como um datacenter ou um local de peering. Configurá-los como ativos/ativos permite que o tráfego do usuário final seja distribuído em vários caminhos de rede. Isso reduz o escopo das pessoas afetadas durante a insa de equipamento de rede ou dispositivo.
  
Não recomendamos usar um único circuito ExpressRoute com a Internet como backup.
  
### <a name="example-2-failover-and-high-availability"></a>Exemplo 2: Failover e Alta Disponibilidade
  
O design multi-geográfico do Woodgrove Bank passou por uma revisão de roteamento, largura de banda, segurança e agora deve passar por uma revisão de alta disponibilidade. Woodgrove considera que a alta disponibilidade abrange três categorias; resiliência, confiabilidade e redundância.
  
A resiliência permite que Woodgrove se recupere de falhas rapidamente. A confiabilidade permite que Woodgrove ofereça um resultado consistente dentro do sistema. A redundância permite que Woodgrove se mova entre uma ou mais instâncias espelhadas da infraestrutura.
  
Em cada configuração de borda, Woodgrove tem Firewalls, Proxies e IDS redundantes. Para a América do Norte, Woodgrove tem uma configuração de borda em seu datacenter de Dallas e outra configuração de borda em seu datacenter da Virgínia. O equipamento redundante em cada local oferece resiliência para esse local.
  
A configuração de rede no Woodgrove Bank é criada com base em alguns princípios principais:
  
- Em cada região geográfica, há vários circuitos do Azure ExpressRoute.

- Cada circuito em uma região pode dar suporte a todo o tráfego de rede nessa região.

- O roteamento prefere claramente um ou outro caminho, dependendo da disponibilidade, local e assim por diante.

- O failover entre os circuitos do Azure ExpressRoute acontece automaticamente sem configuração adicional ou ação necessária por Woodgrove.

- O failover entre circuitos da Internet acontece automaticamente sem configuração adicional ou ação necessária por Woodgrove.

Nessa configuração, com redundância no nível físico e virtual, o Woodgrove Bank é capaz de oferecer resiliência local, resiliência regional e resiliência global de forma confiável. Woodgrove elegeu essa configuração após avaliar um único circuito do Azure ExpressRoute por região, bem como a possibilidade de falha na internet.
  
Se Woodgrove não puder ter vários circuitos do Azure ExpressRoute por região, o tráfego de roteamento originado na América do Norte para o circuito do Azure ExpressRoute no Pacífico Asiático adicionaria um nível inaceitável de latência e a configuração necessária do encaminhador DNS adicionaria complexidade.
  
Não é recomendável aproveitar a Internet como configuração de backup. Isso quebra o princípio de confiabilidade de Woodgrove, resultando em uma experiência inconsistente usando a conexão. Além disso, a configuração manual seria necessária para o failover considerando os anúncios BGP que foram configurados, a configuração NAT, a configuração DNS e a configuração de proxy. Essa complexidade de failover adicionada aumenta o tempo de recuperação e diminui a capacidade de diagnosticar e solucionar problemas das etapas envolvidas.
  
Ainda tem dúvidas sobre como planejar e implementar o gerenciamento de tráfego ou o Azure ExpressRoute? Leia o restante de nossas diretrizes [de desempenho e](./network-planning-and-performance.md) rede ou perguntas frequentes do [Azure ExpressRoute.](/azure/expressroute/expressroute-faqs)
  
## <a name="working-with-azure-expressroute-providers"></a>Trabalhar com provedores do Azure ExpressRoute
<a name="BKMK_high-availability"> </a>

Escolha os locais de seus circuitos com base em sua largura de banda, latência, segurança e planejamento de alta disponibilidade. Depois de saber os locais ideais, você gostaria de colocar circuitos para revisar a lista [atual de provedores por região.](/azure/expressroute/expressroute-locations)
  
Trabalhe com seu provedor ou provedores para selecionar as melhores opções de conectividade, ponto a ponto, vários pontos ou hospedados. Lembre-se de que você pode misturar e corresponder às opções de conectividade, desde que a largura de banda e outros componentes redundantes suportem seu roteamento e design de alta disponibilidade.
  
Aqui está um link curto que você pode usar para voltar: [https://aka.ms/planningexpressroute365]()
  
## <a name="related-topics"></a>Tópicos Relacionados
<a name="BKMK_high-availability"> </a>

[Avaliando a conectividade de rede do Office 365](assessing-network-connectivity.md)
  
[Microsoft Azure ExpressRoute para Office 365](azure-expressroute.md)
  
[Como gerenciar o ExpressRoute para a conectividade do Office 365](managing-expressroute-for-connectivity.md)
  
[Como rotear com o ExpressRoute para Office 365](routing-with-expressroute.md)
  
[Como implementar o ExpressRoute para Office 365](implementing-expressroute.md)
  
[Usando comunidades BGP no ExpressRoute para cenários do Office 365](bgp-communities-in-expressroute.md)
  
[Qualidade da mídia e desempenho de conectividade de rede no Skype for Business Online](https://support.office.com/article/5fe3e01b-34cf-44e0-b897-b0b2a83f0917)
  
[Como otimizar a sua rede para o Skype for Business Online](https://support.office.com/article/b363bdca-b00d-4150-96c3-ec7eab5a8a43)
  
[ExpressRoute e QoS no Skype for Business Online](https://support.office.com/article/20c654da-30ee-4e4f-a764-8b7d8844431d)
  
[Fluxo de chamadas usando o ExpressRoute](https://support.office.com/article/413acb29-ad83-4393-9402-51d88e7561ab)
  
[Ajuste de desempenho do Office 365 usando linhas de base e histórico de desempenho](performance-tuning-using-baselines-and-history.md)
  
[Plano de solução de problemas de desempenho do Office 365](performance-troubleshooting-plan.md)
  
[URLs e intervalos de endereços IP do Office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)
  
[Rede do Office 365 e ajuste de desempenho](network-planning-and-performance.md)
  
[Perguntas frequentes sobre pontos de extremidade do Office 365](https://support.office.com/article/d4088321-1c89-4b96-9c99-54c75cae2e6d)