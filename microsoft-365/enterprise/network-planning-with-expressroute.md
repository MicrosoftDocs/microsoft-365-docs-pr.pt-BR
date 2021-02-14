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
ms.openlocfilehash: 7159640adeae1b4a4ff364683f939a97b6e06a92
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46687234"
---
# <a name="network-planning-with-expressroute-for-office-365"></a>Planejamento de rede com o ExpressRoute para Office 365

*Esse artigo se aplica ao Microsoft 365 Enterprise e ao Office 365 Enterprise.*

O ExpressRoute para Office 365 fornece conectividade de camada 3 entre sua rede e os datacenters da Microsoft. Os circuitos usam anúncios de rota BGP (Border Gateway Protocol) dos servidores front-end do Office 365. Da perspectiva de seus dispositivos locais, quando eles precisam selecionar o caminho TCP/IP correto para o Office 365, o Azure ExpressRoute é visto como uma alternativa à Internet.
  
O Azure ExpressRoute adiciona um caminho direto a um conjunto específico de recursos e serviços com suporte oferecidos pelos servidores do Office 365 nos datacenters da Microsoft. O Azure ExpressRoute não substitui a conectividade com a Internet para datacenters da Microsoft ou serviços básicos da Internet, como a resolução de nome de domínio. O Azure ExpressRoute e seus circuitos de Internet devem ser protegidos e redundantes.
  
A tabela a seguir destaca algumas diferenças entre a Internet e as conexões do Azure ExpressRoute no contexto do Office 365.

|**Diferenças no planejamento de rede**|**Conexão de rede com a Internet**|**Conexão de rede do ExpressRoute**|
|:-----|:-----|:-----|
| Acesso aos serviços de Internet necessários, incluindo;  <br/>  Resolução de nomes DNS  <br/>  Verificação de revogação de certificado  <br/>  Redes de distribuição de conteúdo  <br/> |Sim  <br/> |As solicitações à infraestrutura DNS e/ou CDN de propriedade da Microsoft podem usar a rede ExpressRoute.  <br/> |
| Acesso aos serviços do Office 365, incluindo;  <br/>  Exchange Online  <br/>  SharePoint Online  <br/>  Skype for Business Online  <br/>  Office em um navegador  <br/>  Portal e autenticação do Office 365  <br/> |Sim, todos os aplicativos e recursos  <br/> |Sim, [aplicativos e recursos específicos](https://aka.ms/o365endpoints) <br/> |
|Segurança local no perímetro.  <br/> |Sim  <br/> |Sim  <br/> |
|Planejamento de alta disponibilidade.  <br/> |Failover para uma conexão de rede de Internet alternativa  <br/> |Failover para uma conexão alternativa do ExpressRoute  <br/> |
|Conexão direta com um perfil de rede previsível.  <br/> |Não  <br/> |Sim  <br/> |
|Conectividade IPv6.  <br/> |Sim  <br/> |Sim  <br/> |

Expanda os títulos abaixo para obter mais diretrizes de planejamento de rede. Também gravamos uma série de 10 partes do [Azure ExpressRoute](https://channel9.msdn.com/series/aer) para Treinamento do Office 365 que se aprofunda mais.

## <a name="existing-azure-expressroute-customers"></a>Clientes existentes do Azure ExpressRoute

Se você estiver usando um circuito existente do Azure ExpressRoute e quiser adicionar conectividade do Office 365 nesse circuito, deverá ver o número de circuitos, os locais de saída e o tamanho dos circuitos para garantir que eles atenderão às necessidades de uso do Office 365. A maioria dos clientes exige largura de banda adicional e muitos exigem circuitos adicionais.
  
Para habilitar o acesso ao Office 365 pelos circuitos existentes do Azure ExpressRoute, [configure](https://docs.microsoft.com/azure/expressroute/how-to-routefilter-portal) os filtros de rota para garantir que os serviços do Office 365 sejam acessíveis.
  
A assinatura do Azure ExpressRoute é centrada no cliente, ou seja, as assinaturas estão vinculadas aos clientes. Como cliente, você pode ter vários circuitos do Azure ExpressRoute e pode acessar muitos recursos de nuvem da Microsoft nesses circuitos. Por exemplo, você pode optar por acessar uma máquina virtual hospedada pelo Azure, um locatário de teste do Office 365 e um locatário de produção do Office 365 em um par de circuitos redundantes do Azure ExpressRoute.
  
Esta tabela descreve os dois tipos de relações de pares que você pode optar por implementar em seus circuitos.

|**Relação de paridade**|**Azure Private**|**Microsoft**|
|:-----|:-----|:-----|
|**Serviços** <br/> |IaaS: Máquinas Virtuais do Azure  <br/> |PaaS: Serviços públicos do Azure  <br/> SaaS: Office 365  <br/> SaaS: Dynamics 365  <br/> |
|Início da conexão**** <br/> |Cliente para Microsoft  <br/> Microsoft-para-Cliente  <br/> |Cliente para Microsoft  <br/> Microsoft-para-Cliente  <br/> |
|**Suporte a QoS** <br/> |Sem QoS  <br/> |QoS<sup>1</sup> <br/> |

<sup>1 </sup> A QoS é compatível com o Skype for Business apenas no momento.
  
## <a name="bandwidth-planning-for-azure-expressroute"></a>Planejamento de largura de banda para o Azure ExpressRoute

Cada cliente do Office 365 tem necessidades de largura de banda exclusivas, dependendo do número de pessoas em cada local, da sua ativos com cada aplicativo do Office 365 e de outros fatores, como o uso de equipamentos locais ou híbridos e configurações de segurança de rede.
  
Ter pouca largura de banda resultará em congestionamento, retransmissões de dados e atrasos imprevisíveis. Ter muita largura de banda resultará em custos desnecessários. Em uma rede existente, a largura de banda geralmente é referida em termos da quantidade de espaço disponível no circuito como uma porcentagem. Ter 10% de espaço reservado provavelmente resultará em congestionamento e ter 80% de espaço reservado geralmente significa custo desnecessário. As alocações de destino típicas do espaço reservado são de 20% a 50%.
  
Para encontrar o nível correto de largura de banda, o melhor mecanismo é testar o consumo de rede existente. Essa é a única maneira de obter uma verdadeira medida de uso e necessidade, pois cada configuração de rede e aplicativos são, de alguma forma, exclusivos. Ao medir, você precisará prestar muita atenção ao consumo total de largura de banda, latência e congestionamento TCP para entender as necessidades de rede.
  
Depois de ter uma linha de base estimada que inclui todos os aplicativos de rede, piloto do Office 365 com um pequeno grupo que compreende os diferentes perfis de pessoas em sua organização para determinar o uso real e use as duas medidas para estimar a quantidade de largura de banda necessária para cada local do escritório. Se houver algum problema de latência ou congestionamento TCP encontrado em seus testes, talvez seja necessário mover a saída para mais perto das pessoas que usam o Office 365 ou remover uma verificação de rede intensa, como descriptografia/inspeção de SSL.
  
Todas as nossas recomendações sobre que tipo de processamento de rede é recomendado se aplica aos circuitos ExpressRoute e Internet. O mesmo é verdadeiro para o restante das diretrizes em nosso site de ajuste [de desempenho.](https://aka.ms/tune)
  
## <a name="applying-security-controls-to-azure-expressroute-for-office-365-scenarios"></a>Aplicando controles de segurança ao Azure ExpressRoute para cenários do Office 365

A segurança da conectividade do Azure ExpressRoute começa com os mesmos princípios que a segurança da conectividade com a Internet. Muitos clientes optam por implantar controles de rede e perímetro ao longo do caminho do ExpressRoute conectando sua rede local ao Office 365 e outras nuvens da Microsoft. Esses controles podem incluir firewalls, proxies de aplicativos, prevenção contra vazamento de dados, detecção de intrusões, sistemas de prevenção de intrusões e assim por diante. Em muitos casos, os clientes aplicam níveis diferentes de controles ao tráfego iniciado a partir de uma ida local para a Microsoft, versus o tráfego iniciado da Microsoft indo para a rede local do cliente, versus o tráfego iniciado a partir de um destino de Internet geral.
  
Aqui estão alguns exemplos de integração de segurança com o modelo de conectividade do [ExpressRoute](https://docs.microsoft.com/azure/expressroute/expressroute-connectivity-models) que você escolher implantar.

|**Opção de integração com o ExpressRoute**|**Modelo de perímetro de segurança de rede**|
|:-----|:-----|
|Co-localizado em uma troca de nuvem  <br/> |Instale uma nova ou aproveite a infraestrutura de segurança/perímetro existente nas instalações de co-localização onde a conexão expressRoute está estabelecida.  <br/> Aproveite o recurso de co-localização exclusivamente para fins de roteamento/interconexão e conexões de conexão de retorno das instalações de co-localização para a infraestrutura de segurança/perímetro local.  <br/> |
|Ethernet ponto a ponto  <br/> |Encente a conexão ponto a ponto do ExpressRoute no local de infraestrutura de segurança/perímetro local existente.  <br/> Instale uma nova infraestrutura de segurança/perímetro específica para o caminho do ExpressRoute e termine a conexão Ponto a Ponto lá.  <br/> |
|IPVPN de qualquer um  <br/> |Aproveite uma infraestrutura de segurança/perímetro local existente em todos os locais que egressam para o IPVPN usado para o ExpressRoute para conectividade do Office 365.  <br/> Hairpin the IPVPN used for ExpressRoute for Office 365 to specific on-premises locations designated to serve as the security/perimeter.  <br/> |

Alguns provedores de serviços também oferecem a funcionalidade de segurança/perímetro gerenciada como parte de suas soluções de integração com o Azure ExpressRoute.
  
Ao considerar o posicionamento da topologia das opções de perímetro de rede/segurança usadas para o ExpressRoute para conexões do Office 365, a seguir estão considerações adicionais
  
- Os controles de profundidade e tipo de rede/segurança podem ter impacto no desempenho e na escalabilidade da experiência do usuário do Office 365.

- Os fluxos de saída (local- Microsoft) e de entrada \> (Microsoft- no \> local) [se habilitado] podem ter requisitos diferentes. Eles provavelmente são diferentes de Saída para destinos gerais da Internet.

- Os requisitos do Office 365 para portas/protocolos e sub-redes IP necessárias são os mesmos, independentemente de o tráfego ser roteado pelo ExpressRoute para o Office 365 ou pela Internet.

- O posicionamento máximo dos controles de rede/segurança do cliente determina a rede de ponta a ponta entre o usuário e o serviço do Office 365 e pode ter um impacto substancial na latência e congestionamento da rede.

- Os clientes são incentivados a projetar sua topologia de segurança/perímetro para uso com o ExpressRoute para Office 365, de acordo com as práticas recomendadas para redundância, alta disponibilidade e recuperação de desastres.

Aqui está um exemplo do Woodgrove Bank que compara as diferentes opções de conectividade do Azure ExpressRoute com os modelos de segurança de perímetro discutidos acima.
  
### <a name="example-1-securing-azure-expressroute"></a>Exemplo 1: Proteger o Azure ExpressRoute
  
O Woodgrove Bank está pensando em implementar o Azure ExpressRoute e, depois de planejar a arquitetura ideal para Roteamento com [o ExpressRoute para Office 365](routing-with-expressroute.md) e depois de usar as diretrizes acima para entender os requisitos de largura de banda, eles estão determinando o melhor método para proteger seu perímetro.
  
Para Woodgrove, uma organização multinacional com locais em vários continentes, a segurança deve abranger todos os perímetros. A opção de conectividade ideal para Woodgrove é uma conexão multi-ponto com vários locais de paring em todo o mundo para ajudar a manter as necessidades de seus funcionários em cada continente. Cada continente inclui circuitos redundantes do Azure ExpressRoute dentro do continente e a segurança deve abranger todos eles.
  
A infraestrutura existente do Woodgrove é confiável e pode lidar com o trabalho adicional, como resultado, o Woodgrove Bank é capaz de usar a infraestrutura para o Azure ExpressRoute e a segurança de perímetro da Internet. Se esse não fosse o caso, Woodgrove poderia optar por comprar equipamentos adicionais para complementar seus equipamentos existentes ou para lidar com um tipo diferente de conexão.
  
## <a name="high-availability-and-failover-with-azure-expressroute"></a>Alta disponibilidade e failover com o Azure ExpressRoute
<a name="BKMK_high-availability"> </a>

Recomendamos o provisionamento de pelo menos dois circuitos ativos de cada saída com o ExpressRoute para seu provedor do ExpressRoute. Esse é o local mais comum que vemos falhas para os clientes e você pode evitar facilmente provisionando um par de circuitos ativos/ativos do ExpressRoute. Também recomendamos pelo menos dois circuitos de Internet ativos/ativos porque muitos serviços do Office 365 só estão disponíveis pela Internet.
  
Dentro do ponto de saída da sua rede estão muitos outros dispositivos e circuitos que desempenham um papel fundamental na forma como as pessoas percebem a disponibilidade. Essas partes de seus cenários de conectividade não são cobertas pelo ExpressRoute ou SLAs do Office 365, mas desempenham um papel fundamental na disponibilidade do serviço de ponta a ponta, conforme percebido pelas pessoas em sua organização.
  
Concentre-se nas pessoas que usam e operam o Office 365, se uma falha de um componente afetar a experiência das pessoas usando o serviço, procure formas de limitar a porcentagem total de pessoas afetadas. Se um modo de failover for operacionalmente complexo, considere a experiência das pessoas há muito tempo para se recuperar e procurar modos de failover operacionalmente simples e automatizados.
  
Fora da sua rede, o Office 365, o ExpressRoute e seu provedor expressRoute têm níveis diferentes de disponibilidade.
  
### <a name="service-availability"></a>Disponibilidade do serviço
  
- Os serviços do Office 365 são cobertos por contratos de nível de serviço bem [definidos,](https://technet.microsoft.com/library/office-365-service-level-agreement.aspx)que incluem métricas de tempo de atividade e disponibilidade para serviços individuais. Um motivo pelo qual o Office 365 pode manter níveis de disponibilidade de serviço tão altos é a capacidade dos componentes individuais de fazer failover contínuo entre vários datacenters da Microsoft, usando a rede global da Microsoft. Esse failover se estende do datacenter e da rede até os vários pontos de saída da Internet e permite o failover perfeitamente da perspectiva das pessoas que usam o serviço.

- O ExpressRoute fornece um SLA de [disponibilidade de 99,9%](https://azure.microsoft.com/support/legal/sla/expressroute/v1_0/) em circuitos dedicados individuais entre o Microsoft Network Edge e a infraestrutura de provedor ou parceiro do ExpressRoute. Esses níveis de serviço são aplicados no nível do circuito do ExpressRoute, que consiste em duas [interconexões](https://azure.microsoft.com/documentation/articles/expressroute-introduction/) independentes entre o equipamento redundante da Microsoft e o equipamento do provedor de rede em cada local de paring.

### <a name="provider-availability"></a>Disponibilidade do provedor
  
- As acordos de nível de serviço da Microsoft param em seu provedor ou parceiro do ExpressRoute. Esse também é o primeiro lugar em que você pode fazer escolhas que influenciarão seu nível de disponibilidade. Você deve avaliar de perto a arquitetura, a disponibilidade e as características de resiliência que seu provedor expressRoute oferece entre seu perímetro de rede e sua conexão de provedores em cada local de paring da Microsoft. Preste muita atenção aos aspectos lógicos e físicos da redundância, do equipamento de peering, dos circuitos WAN fornecidos pela operadora e de qualquer valor adicional adicionais adicionais, como serviços NAT ou firewalls gerenciados.

### <a name="designing-your-availability-plan"></a>Projetando seu plano de disponibilidade
  
Recomendamos que você planeje e projete alta disponibilidade e resiliência em seus cenários de conectividade de ponta a ponta para o Office 365. Um design deve incluir;
  
- nenhum ponto de falha, incluindo os circuitos Internet e ExpressRoute.

- minimizar o número de pessoas afetadas e a duração desse impacto para os modos de falha mais previstos.

- otimização para o processo de recuperação simples, repetido e automático dos modos de falha mais previstos.

- suportando as demandas completas de seu tráfego de rede e funcionalidade por meio de caminhos redundantes, sem degradação substancial.

Seus cenários de conectividade devem incluir uma topologia de rede otimizada para vários caminhos de rede independentes e ativos para o Office 365. Isso produzirá uma melhor disponibilidade de ponta a ponta do que uma topologia otimizada apenas para redundância no nível de dispositivo ou equipamento individual.
  
> [!TIP]
> Se os usuários estão distribuídos em vários continentes ou regiões geográficas e cada um desses locais se conecta por circuitos WAN redundantes a um único local onde um único circuito expressRoute está localizado, seus usuários terão menos disponibilidade de serviço de ponta a ponta do que um design de topologia de rede que inclui circuitos ExpressRoute independentes que conectam as diferentes regiões ao local de paring mais próximo.
  
Recomendamos o provisionamento de pelo menos dois circuitos do ExpressRoute com cada circuito que se conecta a um local de peering geográfico diferente. Você deve provisionar esse par de circuitos ativos para cada região onde as pessoas usarão a conectividade ExpressRoute para serviços do Office 365. Isso permite que cada região permaneça conectada durante um desastre que afeta um local importante, como um datacenter ou um local de ponto. Configurá-los como ativos/ativos permite que o tráfego do usuário final seja distribuído em vários caminhos de rede. Isso reduz o escopo das pessoas afetadas durante as paralisações do dispositivo ou do equipamento de rede.
  
Não recomendamos usar um único circuito do ExpressRoute com a Internet como backup.
  
### <a name="example-2-failover-and-high-availability"></a>Exemplo 2: Failover e Alta Disponibilidade
  
O design multi-geográfico do Woodgrove Bank passou por uma revisão de roteamento, largura de banda, segurança e agora deve passar por uma revisão de alta disponibilidade. Woodgrove acha que a alta disponibilidade abrange três categorias; resiliência, confiabilidade e redundância.
  
A resiliência permite que Woodgrove se recupere rapidamente de falhas. A confiabilidade permite que Woodgrove ofereça um resultado consistente no sistema. A redundância permite que Woodgrove se mova entre uma ou mais instâncias espelhadas da infraestrutura.
  
Em cada configuração de borda, Woodgrove tem firewalls, proxies e IDS redundantes. Para a América do Norte, o Woodgrove tem uma configuração de borda em seu datacenter de Dallas e outra configuração de borda em seu datacenter Dem. O equipamento redundante em cada local oferece resiliência para esse local.
  
A configuração de rede no Woodgrove Bank foi criada com base em alguns princípios principais:
  
- Em cada região geográfica, há vários circuitos do Azure ExpressRoute.

- Cada circuito em uma região pode dar suporte a todo o tráfego de rede nessa região.

- O roteamento preferirá claramente um ou outro caminho, dependendo da disponibilidade, do local e assim por diante.

- O failover entre os circuitos do Azure ExpressRoute acontece automaticamente sem a configuração adicional ou a ação exigida pelo Woodgrove.

- O failover entre os circuitos da Internet acontece automaticamente sem configuração adicional ou ação exigida por Woodgrove.

Nessa configuração, com redundância no nível físico e virtual, o Woodgrove Bank é capaz de oferecer resiliência local, resiliência regional e resiliência global de maneira confiável. Woodgrove elegeu essa configuração após avaliar um único circuito do Azure ExpressRoute por região, bem como a possibilidade de fazer o logon na Internet.
  
Se Woodgrove não puder ter vários circuitos do Azure ExpressRoute por região, o tráfego de roteamento originado na América do Norte para o circuito do Azure ExpressRoute no Pacífico Asiático adicionaria um nível inaceitável de latência e a configuração necessária do encaminhador DNS adicionaria complexidade.
  
Não é recomendável utilizar a Internet como uma configuração de backup. Isso quebra o princípio de confiabilidade do Woodgrove, resultando em uma experiência inconsistente usando a conexão. Além disso, a configuração manual seria necessária para o failover considerando os anúncios BGP que foram configurados, a configuração NAT, a configuração de DNS e a configuração de proxy. Essa complexidade de failover adicionada aumenta o tempo de recuperação e diminui a capacidade de diagnosticar e solucionar problemas das etapas envolvidas.
  
Ainda tem dúvidas sobre como planejar e implementar o gerenciamento de tráfego ou o Azure ExpressRoute? Leia o restante das nossas [diretrizes de desempenho e rede](https://aka.ms/tune) ou as perguntas frequentes sobre o [Azure ExpressRoute.](https://azure.microsoft.com/documentation/articles/expressroute-faqs/)
  
## <a name="working-with-azure-expressroute-providers"></a>Trabalhando com provedores do Azure ExpressRoute
<a name="BKMK_high-availability"> </a>

Escolha os locais dos circuitos com base no planejamento de largura de banda, latência, segurança e alta disponibilidade. Depois de saber os locais ideais, você gostaria de colocar circuitos para revisar a lista [atual de provedores por região.](https://azure.microsoft.com/documentation/articles/expressroute-locations/)
  
Trabalhe com seu provedor ou provedores para selecionar as melhores opções de conectividade, ponto a ponto, vários pontos ou hospedados. Lembre-se de que você pode misturar e combinar as opções de conectividade, desde que a largura de banda e outros componentes redundantes suportem seu design de roteamento e alta disponibilidade.
  
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
