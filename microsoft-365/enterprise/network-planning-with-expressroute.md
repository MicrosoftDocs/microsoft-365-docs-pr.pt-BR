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
description: Neste artigo, você aprenderá sobre o Azure ExpressRoute para o Office 365 e como usá-lo para planejamento de rede.
ms.openlocfilehash: 7159640adeae1b4a4ff364683f939a97b6e06a92
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46687234"
---
# <a name="network-planning-with-expressroute-for-office-365"></a>Planejamento de rede com o ExpressRoute para Office 365

*Esse artigo se aplica ao Microsoft 365 Enterprise e ao Office 365 Enterprise.*

O ExpressRoute para Office 365 fornece conectividade de camada 3 entre a rede e os datacenters da Microsoft. Os circuitos usam anúncios de rota do Border Gateway Protocol (BGP) dos servidores front-end do Office 365. Da perspectiva de seus dispositivos locais, quando eles precisam selecionar o caminho TCP/IP correto para o Office 365, o Azure ExpressRoute é visto como uma alternativa para a Internet.
  
O Azure ExpressRoute adiciona um caminho direto a um conjunto específico de recursos e serviços suportados oferecidos pelos servidores do Office 365 nos datacenters da Microsoft. O Azure ExpressRoute não substitui a conectividade com a Internet nos datacenters da Microsoft ou serviços básicos da Internet, como a resolução de nome de domínio. O Azure ExpressRoute e seus circuitos de Internet devem estar protegidos e redundantes.
  
A tabela a seguir realça algumas diferenças entre a Internet e as conexões ExpressRoute do Azure no contexto do Office 365.

|**Diferenças no planejamento de rede**|**Conexão de rede da Internet**|**Conexão de rede ExpressRoute**|
|:-----|:-----|:-----|
| Acesso aos serviços de Internet necessários, incluindo;  <br/>  Resolução de nomes DNS  <br/>  Verificação de revogação de certificado  <br/>  Redes de distribuição de conteúdo  <br/> |Sim  <br/> |As solicitações à infraestrutura de DNS e/ou CDN de propriedade da Microsoft podem usar a rede ExpressRoute.  <br/> |
| Acesso aos serviços do Office 365, incluindo;  <br/>  Exchange Online  <br/>  SharePoint Online  <br/>  Skype for Business Online  <br/>  Office em um navegador  <br/>  Portal e autenticação do Office 365  <br/> |Sim, todos os aplicativos e recursos  <br/> |Sim, [aplicativos e recursos específicos](https://aka.ms/o365endpoints) <br/> |
|Segurança local no perímetro.  <br/> |Sim  <br/> |Sim  <br/> |
|Planejamento de alta disponibilidade.  <br/> |Failover para uma conexão de rede da Internet alternativa  <br/> |Failover para uma conexão ExpressRoute alternativa  <br/> |
|Conexão direta com um perfil de rede previsível.  <br/> |Não  <br/> |Sim  <br/> |
|Conectividade IPv6.  <br/> |Sim  <br/> |Sim  <br/> |

Expanda os títulos abaixo para obter mais diretrizes de planejamento de rede. Também registramos uma série [de treinamento para o Azure ExpressRoute para Office 365](https://channel9.msdn.com/series/aer) que mergulha mais fundo.

## <a name="existing-azure-expressroute-customers"></a>Clientes do Azure ExpressRoute existentes

Se você estiver usando um circuito do Azure ExpressRoute existente e quiser adicionar a conectividade do Office 365 sobre esse circuito, examine o número de circuitos, locais de egresso e o tamanho dos circuitos para garantir que eles atendam às necessidades do seu uso do Office 365. A maioria dos clientes requer largura de banda adicional e muitos exigem circuitos adicionais.
  
Para habilitar o acesso ao Office 365 sobre seus circuitos do Azure ExpressRoute existentes, [Configure os filtros de rota](https://docs.microsoft.com/azure/expressroute/how-to-routefilter-portal) para garantir que os serviços do Office 365 estejam acessíveis.
  
A assinatura do Azure ExpressRoute é centrada no cliente, o que significa que as assinaturas estão vinculadas aos clientes. Como cliente, você pode ter vários circuitos do Azure ExpressRoute e pode acessar muitos recursos da Microsoft Cloud nesses circuitos. Por exemplo, você pode optar por acessar uma máquina virtual hospedada no Azure, um locatário de teste do Office 365 e um locatário de produção do Office 365 em um par de circuitos do Azure ExpressRoute.
  
Esta tabela descreve os dois tipos de relações de emparelhamento que você pode optar por implementar sobre seus circuitos.

|**Relação de emparelhamento**|**Privado do Azure**|**Microsoft**|
|:-----|:-----|:-----|
|**Serviços** <br/> |IaaS: máquinas virtuais do Azure  <br/> |PaaS: serviços públicos do Azure  <br/> SaaS: Office 365  <br/> SaaS: Dynamics 365  <br/> |
|Início de conexão * * * * <br/> |Cliente para a Microsoft  <br/> Cliente da Microsoft  <br/> |Cliente para a Microsoft  <br/> Cliente da Microsoft  <br/> |
|**Suporte a QoS** <br/> |Sem QoS  <br/> |QoS<sup>1</sup> <br/> |

<sup>1 </sup> A QoS oferece suporte somente ao Skype for Business no momento.
  
## <a name="bandwidth-planning-for-azure-expressroute"></a>Planejamento de largura de banda para o Azure ExpressRoute

Todos os clientes do Office 365 têm necessidades exclusivas de largura de banda, dependendo do número de pessoas em cada local, como elas estão ativas em cada aplicativo do Office 365 e outros fatores, como o uso de equipamento local ou híbrido e configurações de segurança de rede.
  
Ter pouca largura de banda resultará em congestionamento, retransmissões de dados e atrasos imprevisíveis. A largura de banda excessiva resultará em um custo desnecessário. Em uma rede existente, a largura de banda é freqüentemente mencionada em termos da quantidade de espaço disponível no circuito como uma porcentagem. Ter 10% de capacidade provavelmente resultará em congestionamento e ter 80% de espaço, geralmente significa custo desnecessário. As alocações de destino de capacidade típica são de 20% a 50%.
  
Para encontrar o nível certo de largura de banda, o melhor mecanismo é testar o consumo de rede existente. Essa é a única maneira de obter uma medida verdadeira de uso e necessidade, já que cada configuração de rede e aplicativos são exclusivos de algumas maneiras. Ao avaliar, convém pagar de perto para o consumo de largura de banda total, a latência e o congestionamento de TCP para entender suas necessidades de rede.
  
Depois de ter uma linha de base estimada que inclua todos os aplicativos de rede, piloto do Office 365 com um pequeno grupo que abrange os diferentes perfis de pessoas em sua organização para determinar o uso real e usar as duas medidas para estimar a quantidade de largura de banda necessária para cada local do escritório. Se houver algum problema de congestionamento ou latência de TCP encontrado em seus testes, talvez seja necessário mover a saída para mais perto das pessoas usando o Office 365 ou remover uma verificação intensiva de rede, como a descriptografia/inspeção de SSL.
  
Todas as nossas recomendações sobre qual tipo de processamento de rede é recomendado aplicam-se aos circuitos ExpressRoute e Internet. O mesmo vale para o restante das orientações em nosso site de [ajuste de desempenho](https://aka.ms/tune).
  
## <a name="applying-security-controls-to-azure-expressroute-for-office-365-scenarios"></a>Aplicando controles de segurança ao Azure ExpressRoute para cenários do Office 365

A proteção da conectividade expressa do Azure começa com os mesmos princípios de proteção da conectividade com a Internet. Muitos clientes optam por implantar os controles de rede e de perímetro ao longo do caminho ExpressRoute conectando sua rede local ao Office 365 e a outras nuvens da Microsoft. Esses controles podem incluir firewalls, proxies de aplicativos, prevenção de perda de dados, detecção de invasão, sistemas de prevenção de invasão e assim por diante. Em muitos casos, os clientes aplicam diferentes níveis de controles ao tráfego iniciado no local da Microsoft, versus o tráfego iniciado pela Microsoft indo para a rede local do cliente, versus o tráfego iniciado no local para um destino de Internet geral.
  
Aqui estão alguns exemplos de integração de segurança com o [modelo de conectividade ExpressRoute](https://docs.microsoft.com/azure/expressroute/expressroute-connectivity-models) que você escolhe implantar.

|**Opção de integração do ExpressRoute**|**Modelo de perímetro de segurança de rede**|
|:-----|:-----|
|Localizado em um Exchange na nuvem  <br/> |Instalar nova ou aproveitar a infraestrutura de segurança/perímetro existente no recurso de colocal onde a conexão ExpressRoute é estabelecida.  <br/> Aproveite o recurso de posicionamento puramente para fins de roteamento/interconexão e conexões de back-out do recurso de co-local na infraestrutura de segurança/perímetro local.  <br/> |
|Ethernet ponto a ponto  <br/> |Encerre a conexão do ExpressRoute ponto a ponto no local de infraestrutura de segurança/perímetro existente.  <br/> Instale a nova infraestrutura de segurança/perímetro específica para o caminho ExpressRoute e encerre a conexão ponto a ponto.  <br/> |
|Qualquer um IPVPN  <br/> |Aproveite uma infraestrutura de segurança/perímetro local existente em todos os locais que são inseridos no IPVPN usado para o ExpressRoute para a conectividade do Office 365.  <br/> Hairpin o IPVPN usado para o ExpressRoute para Office 365 para locais específicos no local designados para servir como segurança/perímetro.  <br/> |

Alguns provedores de serviços também oferecem funcionalidade gerenciada de segurança/perímetro como parte de suas soluções de integração com o Azure ExpressRoute.
  
Ao considerar o posicionamento da topologia das opções de perímetro de rede/segurança usadas para o ExpressRoute para conexões do Office 365, veja a seguir considerações adicionais
  
- Os controles de rede/segurança de profundidade e tipo podem ter impacto no desempenho e na escalabilidade da experiência do usuário do Office 365.

- Os fluxos de saída (local-local- \> Microsoft) e de entrada (Microsoft- \> local) [se habilitado] podem ter requisitos diferentes. Eles provavelmente são diferentes de saída para destinos de Internet gerais.

- Os requisitos do Office 365 para portas/protocolos e sub-redes IP necessárias são os mesmos se o tráfego é roteado através do ExpressRoute para o Office 365 ou pela Internet.

- O posicionamento do Topological dos controles de segurança/rede do cliente determina a extremidade final para encerrar a rede entre o usuário e o serviço do Office 365 e pode ter um impacto significativo na latência e no congestionamento da rede.

- Recomendamos que os clientes projetem sua topologia de segurança/perímetro para uso com o ExpressRoute para Office 365 de acordo com as práticas recomendadas para redundância, alta disponibilidade e recuperação de desastres.

Veja um exemplo de Woodgrove Bank que compara as diferentes opções de conectividade do Azure ExpressRoute com os modelos de segurança de perímetro descritos acima.
  
### <a name="example-1-securing-azure-expressroute"></a>Exemplo 1: protegendo o Azure ExpressRoute
  
O Woodgrove Bank está pensando em implementar o Azure ExpressRoute e depois de planejar a arquitetura ideal para o [Roteamento com o expressroute para Office 365](routing-with-expressroute.md) e depois de usar as orientações acima para entender os requisitos de largura de banda, eles determinam o melhor método para proteger seu perímetro.
  
Para o Woodgrove, uma organização multinacional com locais em vários continentes, a segurança deve abranger todos os perímetros. A opção de conectividade ideal para o Woodgrove é uma conexão de vários pontos com vários locais de emparelhamento em todo o mundo para atender às necessidades de seus funcionários em cada continente. Cada continente inclui circuitos do Azure ExpressRoute redundantes dentro do continente e a segurança deve abranger todos eles.
  
A infraestrutura existente do Woodgrove é confiável e pode lidar com o trabalho adicional, como resultado, o Woodgrove Bank é capaz de usar a infraestrutura para o seu Azure ExpressRoute e a segurança de perímetro da Internet. Se esse não for o caso, o Woodgrove poderá optar por comprar equipamento adicional para complementar o equipamento existente ou para lidar com um tipo diferente de conexão.
  
## <a name="high-availability-and-failover-with-azure-expressroute"></a>Alta disponibilidade e failover com o Azure ExpressRoute
<a name="BKMK_high-availability"> </a>

Recomendamos o provisionamento de pelo menos dois circuitos ativos de cada egresso com o ExpressRoute para seu provedor ExpressRoute. Este é o local mais comum que vemos falhas para os clientes e você pode evitar facilmente o provisionamento de um par de circuitos ativos/ativos do ExpressRoute. Recomendamos também pelo menos dois circuitos de Internet ativos/ativos porque muitos serviços do Office 365 estão disponíveis apenas na Internet.
  
Dentro do ponto de egresso da sua rede há muitos outros dispositivos e circuitos que desempenham uma função crítica em como as pessoas percebem a disponibilidade. Essas partes de seus cenários de conectividade não são cobertas pelos SLAs do ExpressRoute ou do Office 365, mas eles desempenham uma função crucial na disponibilidade de serviço de ponta a ponta, conforme observado pelas pessoas da sua organização.
  
Destaque as pessoas que usam o e o Office 365, se uma falha de qualquer componente afetar a experiência de pessoas usando o serviço, procure maneiras de limitar a porcentagem total de pessoas afetadas. Se um modo de failover for Operacionalmente complexo, considere a experiência de pessoas de longa duração para a recuperação e procure os modos de failover operacional simples e automatizado.
  
Fora da sua rede, o Office 365, o ExpressRoute e o seu provedor ExpressRoute têm níveis diferentes de disponibilidade.
  
### <a name="service-availability"></a>Disponibilidade do serviço
  
- Os serviços do Office 365 são cobertos por [contratos de nível de serviço](https://technet.microsoft.com/library/office-365-service-level-agreement.aspx)bem definidos, que incluem métricas de tempo de atividade e disponibilidade para serviços individuais. Uma razão para o Office 365 ser capaz de manter esses altos níveis de disponibilidade de serviço é a capacidade de os componentes individuais realizarem failover perfeito entre os vários datacenters da Microsoft, usando a rede global da Microsoft. Esse failover se estende do datacenter e da rede para os vários pontos de saída da Internet e habilita o failover sem interrupções da perspectiva das pessoas que usam o serviço.

- [O ExpressRoute fornece um SLA de disponibilidade de 99,9%](https://azure.microsoft.com/support/legal/sla/expressroute/v1_0/) em circuitos dedicados individuais entre a borda da rede da Microsoft e o provedor ExpressRoute ou infraestrutura de parceiro. Esses níveis de serviço são aplicados no nível de circuito ExpressRoute, que consiste em [duas interconexões independentes](https://azure.microsoft.com/documentation/articles/expressroute-introduction/) entre o equipamento redundante da Microsoft e o equipamento de provedor de rede em cada local de emparelhamento.

### <a name="provider-availability"></a>Disponibilidade do provedor
  
- As disposições de nível de serviço da Microsoft são interrompidas no seu fornecedor ou parceiro do ExpressRoute. Este também é o primeiro lugar que você pode fazer escolhas que influenciarão seu nível de disponibilidade. Você deve avaliar atentamente as características de arquitetura, disponibilidade e resiliência que seu provedor ExpressRoute oferece entre o perímetro da rede e a conexão de seus provedores em cada local de emparelhamento da Microsoft. Preste atenção aos aspectos lógicos e físicos da redundância, do equipamento de emparelhamento, dos circuitos de WAN fornecidos e de qualquer valor adicional adicione serviços, como serviços NAT ou firewalls gerenciados.

### <a name="designing-your-availability-plan"></a>Projetando seu plano de disponibilidade
  
Recomendamos enfaticamente que você planeje e projete alta disponibilidade e resiliência em seus cenários de conectividade de ponta a ponta para o Office 365. Um design deve incluir;
  
- Não há pontos únicos de falha, incluindo tanto os circuitos da Internet quanto do ExpressRoute.

- minimizar o número de pessoas afetadas e duração desse impacto para os modos de falha mais previstos.

- Otimizando o processo de recuperação simples, Reproduzível e automático de modos de falha mais previstos.

- suporte a todas as demandas do tráfego de rede e funcionalidade através de caminhos redundantes, sem degradação substancial.

Seus cenários de conectividade devem incluir uma topologia de rede otimizada para vários caminhos de rede independentes e ativos para o Office 365. Isso resultará em uma disponibilidade de ponta a ponta melhor do que uma topologia otimizada somente para redundância no nível do dispositivo ou equipamento individual.
  
> [!TIP]
> Se os seus usuários estão distribuídos entre vários continentes ou regiões geográficas e cada um desses locais se conecta através de circuitos WAN redundantes a um único local local onde um único circuito do ExpressRoute está localizado, seus usuários terão a disponibilidade de serviço menos completa do que um design de topologia de rede que inclui circuitos de ExpressRoute independentes que conectam as diferentes regiões ao local de emparelhamento
  
Recomendamos o provisionamento de pelo menos dois circuitos do ExpressRoute com cada circuito conectado com um local de emparelhamento geográfico diferente. Você deve provisionar esse par ativo-ativo de circuitos para cada região onde as pessoas usarão a conectividade do ExpressRoute para os serviços do Office 365. Isso permite que cada região permaneça conectada durante um desastre que afete um local principal, como um datacenter ou um local de emparelhamento. Configurá-los como ativo/ativo permite que o tráfego do usuário final seja distribuído entre vários caminhos de rede. Isso reduz o escopo de pessoas afetadas durante paralisações de dispositivos ou equipamentos de rede.
  
Não recomendamos o uso de um único circuito ExpressRoute com a Internet como um backup.
  
### <a name="example-2-failover-and-high-availability"></a>Exemplo 2: failover e alta disponibilidade
  
O design multigeográfico do Woodgrove Bank passou por uma revisão de roteamento, largura de banda, segurança e agora deve passar por uma alta disponibilidade. O Woodgrove pensa sobre alta disponibilidade como abranger três categorias; resiliência, confiabilidade e redundância.
  
A resiliência permite que o Woodgrove se recupere rapidamente de falhas. A confiabilidade permite que o Woodgrove ofereça um resultado consistente no sistema. A redundância permite que o Woodgrove mova entre uma ou mais instâncias espelhadas da infraestrutura.
  
Em cada configuração de borda, o Woodgrove tem firewalls, proxies e IDS redundantes. Para a América do Norte, o Woodgrove tem uma configuração de borda no datacenter de Dallas e outra configuração de borda no datacenter da Virgínia. O equipamento redundante em cada local oferece resiliência para esse local.
  
A configuração de rede no Woodgrove Bank é criada com base em alguns princípios fundamentais:
  
- Em cada região geográfica, há vários circuitos do Azure ExpressRoute.

- Cada circuito dentro de uma região pode dar suporte a todo o tráfego de rede dentro dessa região.

- O roteamento certamente prefere um ou outro caminho, dependendo da disponibilidade, local e assim por diante.

- O failover entre os circuitos do Azure ExpressRoute ocorre automaticamente sem configuração ou ação adicional necessária para o Woodgrove.

- O failover entre os circuitos da Internet ocorre automaticamente sem configuração ou ação adicional necessária para o Woodgrove.

Nessa configuração, com redundância no nível físico e virtual, o Woodgrove Bank é capaz de oferecer resiliência local, resiliência regional e resiliência global de forma confiável. O Woodgrove optou por essa configuração depois de avaliar um único circuito do Azure ExpressRoute por região, bem como a possibilidade de failover para a Internet.
  
Se o Woodgrove não puder ter vários circuitos do Azure ExpressRoute por região, o tráfego de roteamento originado na América do Norte para o circuito do Azure ExpressRoute na Ásia Pacífico adicionaria um nível de latência inaceitável e a configuração de encaminhador DNS necessária adiciona complexidade.
  
A utilização da Internet como uma configuração de backup não é recomendada. Isso quebra o princípio de confiabilidade do Woodgrove, resultando em uma experiência inconsistente usando a conexão. Além disso, a configuração manual seria necessária para failover considerando os anúncios de BGP que foram configurados, configuração NAT, configuração de DNS e a configuração de proxy. Essa complexidade adicional de failover aumenta o tempo de recuperação e diminui sua capacidade de diagnosticar e solucionar problemas de etapas envolvidas.
  
Ainda tem dúvidas sobre como planejar e implementar o gerenciamento de tráfego ou o Azure ExpressRoute? Leia o restante da nossa [orientação de rede e desempenho](https://aka.ms/tune) ou as [perguntas frequentes sobre o Azure ExpressRoute](https://azure.microsoft.com/documentation/articles/expressroute-faqs/).
  
## <a name="working-with-azure-expressroute-providers"></a>Trabalhando com provedores do Azure ExpressRoute
<a name="BKMK_high-availability"> </a>

Escolha os locais dos seus circuitos com base em sua largura de banda, latência, segurança e planejamento de alta disponibilidade. Quando você souber os locais ideais que gostaria de colocar os circuitos [, analise a lista atual de provedores por região](https://azure.microsoft.com/documentation/articles/expressroute-locations/).
  
Trabalhe com seu provedor ou provedores para selecionar as melhores opções de conectividade, ponto a ponto, vários pontos ou hospedados. Lembre-se de que você pode misturar e combinar as opções de conectividade, desde que a largura de banda e outros componentes redundantes ofereçam suporte ao seu design de roteamento e alta disponibilidade.
  
Aqui está um link curto que você pode usar para voltar: [https://aka.ms/planningexpressroute365](https://aka.ms/planningexpressroute365)
  
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
