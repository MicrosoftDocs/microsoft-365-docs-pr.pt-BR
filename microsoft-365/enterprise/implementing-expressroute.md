---
title: Como implementar o ExpressRoute para o Office 365
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 12/5/2017
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
ms.assetid: 77735c9d-8b80-4d2f-890e-a8598547dea6
description: Saiba como implementar o ExpressRoute para o Office 365, que fornece um caminho de roteamento alternativo para muitos serviços do Office 365 voltados para a Internet.
ms.openlocfilehash: d0f0b5156aae5a3e2c38f51ba0b74738918593e9
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909827"
---
# <a name="implementing-expressroute-for-office-365"></a>Como implementar o ExpressRoute para o Office 365

*Este artigo se aplica tanto ao Microsoft 365 Enterprise quanto ao Office 365 Enterprise.*

O ExpressRoute para Office 365 fornece um caminho de roteamento alternativo para muitos serviços do Office 365 voltados para a Internet. A arquitetura do ExpressRoute para Office 365 baseia-se na publicidade de prefixos ip públicos dos serviços do Office 365 que já estão acessíveis pela Internet em seus circuitos ExpressRoute provisionados para redistribuição subsequente desses prefixos IP para sua rede. Com o ExpressRoute, você efetivamente habilita vários caminhos de roteamento diferentes, por meio da Internet e por meio do ExpressRoute, para muitos serviços do Office 365. Esse estado de roteamento em sua rede pode representar uma alteração significativa na forma como a topologia de rede interna foi projetada.
  
 **Status:** Guia Completo v2
  
Você deve planejar cuidadosamente a implementação do ExpressRoute para o Office 365 para acomodar as complexidades de rede de ter o roteamento disponível por meio de um circuito dedicado com rotas injetadas em sua rede principal e na Internet. Se você e sua equipe não executarem o planejamento e os testes detalhados neste guia, há um alto risco de você ter uma experiência intermitente ou uma perda total de conectividade com os serviços do Office 365 quando o circuito ExpressRoute estiver habilitado.
  
Para ter uma implementação bem-sucedida, você precisará analisar seus requisitos de infraestrutura, passar por uma avaliação e um design detalhados de rede, planejar cuidadosamente a distribuição em estágios e controlados e criar um plano detalhado de validação e teste. Para um ambiente grande e distribuído, não é incomum ver implementações por vários meses. Este guia foi projetado para ajudá-lo a planejar o futuro.
  
Grandes implantações bem-sucedidas podem levar seis meses no planejamento e geralmente incluem membros de equipe de várias áreas da organização, incluindo administradores de rede, firewall e servidor proxy, administradores do Office 365, segurança, suporte ao usuário final, gerenciamento de projeto e patrocínio executivo. Seu investimento no processo de planejamento reduzirá a probabilidade de que você experimente falhas de implantação resultando em tempo de inatividade ou solução de problemas complexos e caros.
  
Esperamos que os seguintes pré-requisitos sejam concluídos antes que este guia de implementação seja iniciado.
  
1. Você concluiu uma avaliação de rede para determinar se o ExpressRoute é recomendado e aprovado.

2. Você selecionou um provedor de serviço de rede ExpressRoute. Encontre detalhes sobre os parceiros [expressRoute e locais de paração.](/azure/expressroute/expressroute-locations)

3. Você já leu e compreendeu a documentação [do ExpressRoute](https://azure.microsoft.com/documentation/services/expressroute/) e sua rede interna é capaz de atender aos pré-requisitos do ExpressRoute de ponta a ponta.

4. Sua equipe leu todas as diretrizes e documentações públicas em , e viu a série de treinamento do [https://aka.ms/expressrouteoffice365](./azure-expressroute.md) [https://aka.ms/ert](https://aka.ms/ert) [Azure ExpressRoute para Office 365](https://channel9.msdn.com/series/aer) no Canal 9 para obter uma compreensão dos detalhes técnicos críticos, incluindo:

      - As dependências da Internet dos serviços SaaS.

      - Como evitar rotas assimétricas e manipular roteamento complexo.

      - Como incorporar controles de segurança de perímetro, disponibilidade e nível de aplicativo.

## <a name="begin-by-gathering-requirements"></a>Comece coletando requisitos
<a name="requirements"> </a>

Comece determinando quais recursos e serviços você planeja adotar em sua organização. Você precisa determinar quais recursos dos diferentes serviços do Office 365 serão usados e quais locais em sua rede hospedarão pessoas usando esses recursos. Com o catálogo de cenários, você precisa adicionar os atributos de rede que cada um desses cenários exige; como fluxos de tráfego de rede de entrada e saída e se os pontos de extremidade do Office 365 estão disponíveis no ExpressRoute ou não.
  
Para reunir os requisitos da sua organização:
  
- Cataloge o tráfego de rede de entrada e saída para os serviços do Office 365 que sua organização está usando. Consulte a página URLs e intervalos de endereços IP do Office 365 para a descrição de fluxos que diferentes cenários do Office 365 exigem.

- Reúna a documentação da topologia de rede existente mostrando detalhes do backbone e topologia wan interno, conectividade de sites de satélite, conectividade de usuário de última milha, roteamento para pontos de saída de perímetro de rede e serviços proxy.

  - Identifique os pontos de extremidade do serviço de entrada nos diagramas de rede aos quais o Office 365 e outros serviços da Microsoft se conectarão, mostrando os caminhos de conexão expressRoute e internet propostos.

  - Identifique todos os locais geográficos do usuário e a conectividade WAN entre locais, juntamente com quais locais atualmente têm uma saída para a Internet e quais locais são propostos para ter uma saída para um local de paração expressRoute.

  - Identifique todos os dispositivos de borda, como proxies, firewalls e assim por diante e cataloge sua relação para fluxos que vão pela Internet e ExpressRoute.

  - Documente se os usuários finais acessarão os serviços do Office 365 por meio de roteamento direto ou proxy de aplicativo indireto para fluxos de Internet e ExpressRoute.

- Adicione a localização de seus locatários e locais de meet-me ao diagrama de rede.

- Estimar o desempenho de rede esperado e observado e as características de latência dos principais locais de usuários para o Office 365. Lembre-se de que o Office 365 é um conjunto global e distribuído de serviços e os usuários estarão se conectando a locais que podem ser diferentes do local de seu locatário. Por esse motivo, é recomendável medir e otimizar a latência entre o usuário e a borda mais próxima da rede global da Microsoft sobre conexões ExpressRoute e Internet. Você pode usar suas descobertas da avaliação de rede para ajudar nessa tarefa.

- Listar a segurança da rede da empresa e os requisitos de alta disponibilidade que precisam ser atendidos com a nova conexão ExpressRoute. Por exemplo, como os usuários continuam a obter acesso ao Office 365 em caso de falha de saída da Internet ou do circuito ExpressRoute.

- Documento que fluxos de rede de entrada e saída do Office 365 usarão o caminho da Internet e usarão o ExpressRoute. As especificidades das localizações geográficas de seus usuários e os detalhes da topologia de rede local podem exigir que o plano seja diferente de um local de usuário para outro.

### <a name="catalog-your-outbound-and-inbound-network-traffic"></a>Catalogar seu tráfego de rede de saída e de entrada
<a name="trafficCatalog"> </a>

Para minimizar o roteamento e outras complexidades de rede, recomendamos que você use apenas o ExpressRoute para o Office 365 para os fluxos de tráfego de rede necessários para passar por uma conexão dedicada devido aos requisitos regulamentar ou como resultado da avaliação da rede. Além disso, recomendamos que você estande o escopo de roteamento e abordagem de fluxos de tráfego de saída e de entrada da rede como estágios diferentes e distintos do projeto de implementação. Implantar o ExpressRoute para o Office 365 apenas para fluxos de tráfego de rede de saída iniciados pelo usuário e deixar fluxos de tráfego de rede de entrada pela Internet pode ajudar a controlar o aumento da complexidade topológica e os riscos de introdução de possibilidades adicionais de roteamento assimétrico.
  
Seu catálogo de tráfego de rede deve conter listagem de todas as conexões de rede de entrada e saída que você terá entre sua rede local e a Microsoft.
  
- Fluxos de tráfego de rede de saída são todos os cenários em que uma conexão é iniciada a partir do seu ambiente local, como de clientes internos ou servidores, com um destino dos serviços Microsoft. Essas conexões podem ser diretas para o Office 365 ou indiretas, como quando a conexão passa por servidores proxy, firewalls ou outros dispositivos de rede no caminho para o Office 365.

- Fluxos de tráfego de rede de entrada são todos os cenários em que uma conexão é iniciada da nuvem da Microsoft para um host local. Essas conexões geralmente precisam passar pelo firewall e outra infraestrutura de segurança que a política de segurança do cliente exige para fluxos originados externamente.

Leia  a seção Garantindo a simetria de rota do artigo Roteamento com [ExpressRoute para Office 365](https://support.office.com/article/Routing-with-ExpressRoute-for-Office-365-e1da26c6-2d39-4379-af6f-4da213218408) para determinar quais serviços enviarão tráfego de entrada e procure a coluna marcada **ExpressRoute para Office 365** no artigo de referência de pontos de extremidade do [Office 365](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2) para determinar o restante das informações de conectividade.
  
Para cada serviço que exija uma conexão de saída, você precisará descrever a conectividade planejada para o serviço, incluindo roteamento de rede, configuração de proxy, inspeção de pacotes e necessidades de largura de banda.
  
Para cada serviço que exija uma conexão de entrada, você precisará de algumas informações adicionais. Os servidores na nuvem da Microsoft estabelecerão conexões com sua rede local. para garantir que as conexões sejam feitas corretamente, você vai querer descrever todos os aspectos dessa conectividade, incluindo; as entradas DNS públicas para os serviços que aceitarão essas conexões de entrada, os endereços IP IPv4 formatados cidr, quais equipamentos ISP estão envolvidos e como NAT de entrada ou NAT de origem é tratado para essas conexões.
  
As conexões de entrada devem ser revisadas independentemente de elas se conectarem pela Internet ou expressRoute para garantir que o roteamento assimétrico não tenha sido introduzido. Em alguns casos, pontos de extremidade locais aos quais os serviços do Office 365 iniciam conexões de entrada também podem precisar ser acessados por outros serviços da Microsoft e não da Microsoft. É fundamental que a habilitação do roteamento expressRoute para esses serviços para fins do Office 365 não quebre outros cenários. Em muitos casos, os clientes podem precisar implementar alterações específicas em sua rede interna, como NAT baseada em origem, para garantir que os fluxos de entrada da Microsoft permaneçam simétricos depois que o ExpressRoute for habilitado.
  
Aqui está um exemplo do nível de detalhes necessário. Nesse caso, o Exchange Hybrid seria roteado para o sistema local por meio do ExpressRoute.

|**Propriedade Connection**|**Valor**|
|:-----|:-----|
|**Direção do tráfego de rede** <br/> |Entrada  <br/> |
|**Serviço** <br/> |Exchange Híbrido  <br/> |
|**Ponto de extremidade do Office 365 público (fonte)** <br/> |Exchange Online (endereços IP)  <br/> |
|**Ponto de extremidade local público (destino)** <br/> |5.5.5.5  <br/> |
|**Entrada DNS pública (Internet)** <br/> |Autodiscover.contoso.com  <br/> |
|**Esse ponto de extremidade local será usado por outros serviços da Microsoft (que não são do Office 365)** <br/> |Não  <br/> |
|**Esse ponto de extremidade local será usado por usuários/sistemas na Internet** <br/> |Sim  <br/> |
|**Sistemas internos publicados por meio de pontos de extremidade públicos** <br/> |Exchange Server função de acesso para cliente (local) 192.168.101, 192.168.102, 192.168.103  <br/> |
|**Anúncio IP do ponto de extremidade público** <br/> |**To Internet**: 5.5.0.0/16  <br/> **Para ExpressRoute**: 5.5.5.0/24  <br/> |
|**Controles de segurança/perímetro** <br/> |**Caminho da Internet**: DeviceID_002  <br/> **Caminho ExpressRoute**: DeviceID_003  <br/> |
|**Alta Disponibilidade** <br/> |Active/Active em 2 geo-redundantes  <br/> Circuitos ExpressRoute - Chicago e Dallas  <br/> |
|**Controle de simetria de caminho** <br/> |**Método**: NAT de origem  <br/> **Caminho da Internet**: conexões de entrada NAT de origem para 192.168.5.5  <br/> |**Caminho ExpressRoute**: conexões NAT de origem para 192.168.1.0 (Chicago) e 192.168.2.0 (Dallas)  <br/> |

Aqui está um exemplo de um serviço que é somente de saída:

|**Propriedade Connection**|**Valor**|
|:-----|:-----|
|**Direção do tráfego de rede** <br/> |Saída  <br/> |
|**Serviço** <br/> |SharePoint Online  <br/> |
|**Ponto de extremidade local (origem)** <br/> |Estação de trabalho do usuário  <br/> |
|**Ponto de extremidade do Office 365 público (destino)** <br/> |SharePoint Online (endereços IP)  <br/> |
|**Entrada DNS pública (Internet)** <br/> |\*.sharepoint.com (e FQDNs adicionais)  <br/> |
|**Referências de CDN** <br/> |cdn.sharepointonline.com (e FQDNs adicionais) - endereços IP mantidos por provedores de CDN)  <br/> |
|**Anúncio IP e NAT em uso** <br/> |**Caminho da Internet/NAT de** origem : 1.1.1.0/24  <br/> **Caminho do ExpressRoute/NAT** de origem : 1.1.2.0/24 (Chicago) e 1.1.3.0/24 (Dallas)  <br/> |
|**Método Connectivity** <br/> |**Internet**: via proxy da camada 7 (arquivo.pac)  <br/> **ExpressRoute**: roteamento direto (sem proxy)  <br/> |
|**Controles de segurança/perímetro** <br/> |**Caminho da Internet**: DeviceID_002  <br/> **Caminho ExpressRoute**: DeviceID_003  <br/> |
|**Alta Disponibilidade** <br/> |**Caminho da Internet**: Saída redundante da Internet  <br/> **Caminho expressRoute**: roteamento ativo/ativo de "hot-hot", em 2 circuitos expressRoute geo-redundantes - Chicago e Dallas  <br/> |
|**Controle de simetria de caminho** <br/> |**Método**: NAT de origem para todas as conexões  <br/> |

### <a name="your-network-topology-design-with-regional-connectivity"></a>Seu design de topologia de rede com conectividade regional
<a name="topology"> </a>

Depois de entender os serviços e os fluxos de tráfego de rede associados, você pode criar um diagrama de rede que incorpore esses novos requisitos de conectividade e ilustra as alterações que você fará para usar o ExpressRoute para o Office 365. Seu diagrama deve incluir:
  
1. Todos os locais de usuários dos quais o Office 365 e outros serviços serão acessados.

2. Todos os pontos de saída de Internet e ExpressRoute.

3. Todos os dispositivos de saída e de entrada que gerenciam a conectividade dentro e fora da rede, incluindo roteadores, firewalls, servidores proxy de aplicativos e detecção/prevenção de intrusões.

4. Destinos internos para todo o tráfego de entrada, como servidores ADFS internos que aceitam conexões dos servidores proxy do aplicativo Web ADFS.

5. Catálogo de todas as sub-redes IP que serão anunciadas

6. Identifique cada local de onde as pessoas acessarão o Office 365 e listar os locais de meet-me que serão usados para ExpressRoute.

7. Locais e partes de sua topologia de rede interna, onde os prefixos IP da Microsoft aprendidos com ExpressRoute serão aceitos, filtrados e propagados para.

8. A topologia de rede deve ilustrar a localização geográfica de cada segmento de rede e como ela se conecta à rede da Microsoft por meio do ExpressRoute e/ou da Internet.

O diagrama a seguir mostra cada local onde as pessoas usarão o Office 365 junto com os anúncios de roteamento de entrada e saída para o Office 365.
  
![ExpressRoute regional geographic meet-me](../media/d866b36b-49bf-416b-af1b-d054e24989d2.png)
  
Para tráfego de saída, as pessoas acessam o Office 365 de uma das três maneiras:
  
1. Por meio de um local de reunião na América do Norte para as pessoas na Califórnia.

2. Por meio de um local de reunião em Hong Kong para as pessoas em Hong Kong.

3. Por meio da Internet em Bangladesh, onde há menos pessoas e nenhum circuito ExpressRoute provisionado.

![Conexões de saída para diagrama regional](../media/8319943d-08f0-4781-9ef3-d23de2ad4671.png)
  
Da mesma forma, o tráfego de rede de entrada do Office 365 retorna de uma das três maneiras:
  
1. Por meio de um local de reunião na América do Norte para as pessoas na Califórnia.

2. Por meio de um local de reunião em Hong Kong para as pessoas em Hong Kong.

3. Por meio da Internet em Bangladesh, onde há menos pessoas e nenhum circuito ExpressRoute provisionado.

![Conexões de entrada para diagrama regional](../media/d6d6160d-bf28-4de3-a787-186c7432b306.png)
  
### <a name="determine-the-appropriate-meet-me-location"></a>Determinar o local apropriado do meet-me

A seleção de locais de meet-me, que são o local físico onde seu circuito ExpressRoute conecta sua rede à rede da Microsoft, é influenciada pelos locais de onde as pessoas acessarão o Office 365. Como uma oferta saaS, o Office 365 não opera no modelo regional IaaS ou PaaS da mesma maneira que o Azure. Em vez disso, o Office 365 é um conjunto distribuído de serviços de colaboração, onde os usuários podem precisar se conectar a pontos de extremidade em vários datacenters e regiões, o que pode não estar necessariamente no mesmo local ou região onde o locatário do usuário está hospedado.
  
Isso significa que a consideração mais importante que você precisa fazer ao selecionar locais de meet-me para ExpressRoute para o Office 365 é de onde as pessoas em sua organização estarão se conectando. A recomendação geral para a conectividade ideal do Office 365 é implementar o roteamento, para que as solicitações do usuário aos serviços do Office 365 sejam entregues à rede da Microsoft pelo caminho de rede mais curto, isso também costuma ser chamado de roteamento de "hot-hot". Por exemplo, se a maioria dos usuários do Office 365 estiver em um ou dois locais, selecionar locais de meet-me que estão mais próximos do local desses usuários criará o design ideal. Se sua empresa tiver grandes populações de usuários em várias regiões diferentes, talvez você queira considerar ter vários circuitos ExpressRoute e locais de meet-me. Para alguns de seus locais de usuário, o caminho mais curto/ideal para a rede da Microsoft e o Office 365, pode não ser por meio de seus pontos de reunião wan e ExpressRoute internos, mas por meio da Internet.
  
Muitas vezes, há vários locais de meet-me que podem ser selecionados em uma região com proximidade relativa com seus usuários. Preencha a tabela a seguir para orientar suas decisões.

|**Locais planejados de meet-me do ExpressRoute na Califórnia e em Nova York**||
|:-----|:-----|
|Local  <br/> |Número de pessoas  <br/> |Latência esperada para a rede da Microsoft por saída da Internet  <br/> |Latência esperada para a rede microsoft via ExpressRoute  <br/> |
|Los Angeles  <br/> |10.000  <br/> |~15ms  <br/> |~10ms (via Vale do Silício)  <br/> |
|Washington DC  <br/> |15,000  <br/> |~20ms  <br/> |~10ms (via Nova York)  <br/> |
|Dallas  <br/> |5.000  <br/> |~15ms  <br/> |~40ms (via Nova York)  <br/> |

Depois que a arquitetura de rede global mostrando a região do Office 365, os locais do provedor de serviços de rede ExpressRoute se encontram e a quantidade de pessoas por local foi desenvolvida, ela pode ser usada para identificar se alguma otimização pode ser feita. Ele também pode mostrar conexões globais de rede de hairpin onde o tráfego encaminha para um local distante para obter o local do meet-me. Se um hairpin na rede global for descoberto, ele deverá ser remediado antes de continuar. Encontre outro local de reunião ou use pontos de saída seletivos de saída da Internet para evitar o hairpin.
  
O primeiro diagrama mostra um exemplo de um cliente com dois locais físicos na América do Norte. Você pode ver as informações sobre locais de escritório, locais de locatários do Office 365 e várias opções para locais de reunião do ExpressRoute. Neste exemplo, o cliente selecionou o local do meet-me com base em dois princípios, em ordem:
  
1. Proximidade mais próxima das pessoas em sua organização.

2. Mais próximo de um datacenter da Microsoft onde o Office 365 está hospedado.

![ExpressRoute US geographic meet-me](../media/5ec38274-b317-4ec1-91c8-90c2a7fd32ca.png)
  
Expandindo esse conceito um pouco mais, o segundo diagrama mostra um exemplo de cliente multinaval diante de informações e tomadas de decisões semelhantes. Esse cliente tem um pequeno escritório em Bangladesh com apenas uma pequena equipe de dez pessoas focadas em aumentar sua área de trabalho na região. Há um local de reunião em Chennai e um datacenter da Microsoft com o Office 365 hospedado em Chennai para que um local de reunião faça sentido; no entanto, para dez pessoas, a despesa do circuito adicional é onerosa. Ao olhar para sua rede, você precisará determinar se a latência envolvida no envio do tráfego de rede pela rede é mais eficaz do que gastar a capital para adquirir outro circuito expressRoute.
  
Como alternativa, as dez pessoas em Bangladesh podem ter melhor desempenho com o tráfego de rede enviado pela Internet para a rede da Microsoft do que roteando em sua rede interna, conforme mostramos nos diagramas introdutórios e reproduzidos abaixo.
  
![Conexões de saída para diagrama regional](../media/8319943d-08f0-4781-9ef3-d23de2ad4671.png)
  
## <a name="create-your-expressroute-for-office-365-implementation-plan"></a>Criar seu plano de implementação do ExpressRoute para o Office 365
<a name="implementation"> </a>

Seu plano de implementação deve abranger os detalhes técnicos da configuração do ExpressRoute, bem como os detalhes da configuração de toda a outra infraestrutura em sua rede, como o seguinte.
  
- Planeje quais serviços são divididos entre ExpressRoute e Internet.

- Planeje largura de banda, segurança, alta disponibilidade e failover.

- Projetar roteamento de entrada e saída, incluindo otimizações adequadas de caminho de roteamento para locais diferentes

- Decida até que ponto as rotas do ExpressRoute serão anunciadas em sua rede e qual é o mecanismo para os clientes selecionarem Internet ou o caminho do ExpressRoute; por exemplo, roteamento direto ou proxy de aplicativo.

- Planeje alterações no registro DNS, incluindo [entradas da Estrutura](../security/office-365-security/set-up-spf-in-office-365-to-help-prevent-spoofing.md) de Política do Remetente.

- Planeje a estratégia NAT, incluindo NAT de origem de saída e de entrada.

### <a name="plan-your-routing-with-both-internet-and-expressroute-network-paths"></a>Planejar seu roteamento com caminhos de rede de Internet e ExpressRoute
<a name="paths"> </a>

- Para sua implantação inicial, todos os serviços de entrada, como email de entrada ou conectividade híbrida, são recomendados para usar a Internet.

- Planeje o roteamento de LAN do cliente final, como a configuração de um arquivo [PAC/WPAD,](./managing-office-365-endpoints.md)rota padrão, servidores proxy e anúncios de rota BGP.

- Planeje o roteamento de perímetro, incluindo servidores proxy, firewalls e proxies de nuvem.

### <a name="plan-your-bandwidth-security-high-availability-and-failover"></a>Planejar sua largura de banda, segurança, alta disponibilidade e failover
<a name="availability"> </a>

Crie um plano para largura de banda necessária para cada carga de trabalho principal do Office 365. Estimar separadamente os requisitos de largura de banda do Exchange Online, SharePoint Online e Skype for Business Online. Você pode usar as calculadoras de estimativa que fornecemos para o Exchange Online e o Skype for Business como um ponto de partida; no entanto, um teste piloto com um exemplo representativo dos perfis de usuário e locais é necessário para entender totalmente as necessidades de largura de banda da sua organização.
  
Adicione como a segurança é manipulada em cada local de saída da Internet e expressRoute ao seu plano, lembre-se de que todas as conexões expressRoute com o Office 365 usam o peering público e ainda devem ser protegidas de acordo com as políticas de segurança da sua empresa de conexão com redes externas.
  
Adicione detalhes ao seu plano sobre quais pessoas serão afetadas por qual tipo de paralisação e como essas pessoas poderão executar seu trabalho com capacidade total da maneira mais simples.
  
#### <a name="plan-bandwidth-requirements-including-skype-for-business-requirements-on-jitter-latency-congestion-and-headroom"></a>Planejar requisitos de largura de banda, incluindo requisitos do Skype for Business em Tremida, Latência, Congestionamento e Headroom
  
O Skype for Business Online também tem requisitos de rede adicionais específicos que são detalhados no artigo Qualidade de Mídia e Desempenho de Conectividade de Rede [no Skype for Business Online](https://support.office.com/article/Media-Quality-and-Network-Connectivity-Performance-in-Skype-for-Business-Online-5fe3e01b-34cf-44e0-b897-b0b2a83f0917).
  
Leia a seção **Planejamento de largura de banda do Azure ExpressRoute** no Planejamento de rede com o [ExpressRoute para Office 365](https://support.office.com/article/Network-planning-with-ExpressRoute-for-Office-365-103208f1-e788-4601-aa45-504f896511cd).
  
Ao executar uma avaliação de largura de banda com seus usuários piloto, você pode usar nosso guia; [Ajuste de desempenho do Office 365 usando linhas de base e histórico de desempenho.](https://support.office.com/article/Office-365-performance-tuning-using-baselines-and-performance-history-1492cb94-bd62-43e6-b8d0-2a61ed88ebae)
  
#### <a name="plan-for-high-availability-requirements"></a>Planejar requisitos de alta disponibilidade
  
Crie um plano de alta disponibilidade para atender às suas necessidades e incorpore-o ao diagrama de topologia de rede atualizado. Leia a seção **Alta disponibilidade e failover com o Azure ExpressRoute** no planejamento de rede com [ExpressRoute para Office 365](https://support.office.com/article/Network-planning-with-ExpressRoute-for-Office-365-103208f1-e788-4601-aa45-504f896511cd).
  
#### <a name="plan-for-network-security-requirements"></a>Planejar requisitos de segurança de rede
  
Crie um plano para atender aos requisitos de segurança de rede e incorpore-o ao diagrama de topologia de rede atualizado. Leia a seção Aplicando controles de segurança **ao Azure ExpressRoute para cenários do Office 365** em Planejamento de rede com [ExpressRoute para Office 365](https://support.office.com/article/Network-planning-with-ExpressRoute-for-Office-365-103208f1-e788-4601-aa45-504f896511cd).
  
### <a name="design-outbound-service-connectivity"></a>Projetar conectividade de serviço de saída
<a name="outbound"> </a>

ExpressRoute para Office 365  *tem*  requisitos de rede de saída que podem ser desconhecidos. Especificamente, os endereços IP que representam seus usuários e redes para o Office 365 e atuam como pontos de extremidade de origem para conexões de rede de saída para a Microsoft devem seguir requisitos específicos descritos abaixo.
  
1. Os pontos de extremidade devem ser endereços IP públicos, que estão registrados em sua empresa ou para a operadora que fornece conectividade ExpressRoute para você.

2. Os pontos de extremidade devem ser anunciados para a Microsoft e validados/aceitos pelo ExpressRoute.

3. Os pontos de extremidade não devem ser anunciados na Internet com a mesma ou mais métrica de roteamento preferencial.

4. Os pontos de extremidade não devem ser usados para conectividade com serviços da Microsoft que não estão configurados no ExpressRoute.

Se o seu design de rede não atender a esses requisitos, há um alto risco de que os usuários experimentem falhas de conectividade no Office 365 e em outros serviços da Microsoft devido à roteamento em preto ou roteamento assimétrico. Isso ocorre quando as solicitações aos serviços da Microsoft são roteadas pelo ExpressRoute, mas as respostas são roteadas de volta pela Internet ou vice-versa, e as respostas são retiradas por dispositivos de rede de estado, como firewalls.
  
O método mais comum que você pode usar para atender aos requisitos acima é usar NAT de origem, implementado como parte de sua rede ou fornecido pela operadora ExpressRoute. NAT de origem permite que você abstraa os detalhes e o endereçamento IP privado de sua rede de Internet do ExpressRoute e; juntamente com anúncios de rota IP apropriados, forneça um mecanismo fácil para garantir a simetria do caminho. Se você estiver usando dispositivos de rede de estado específicos para locais de paração expressRoute, você deve implementar pools NAT separados para cada paração expressRoute para garantir a simetria do caminho.
  
Leia mais sobre os [requisitos do NAT expressRoute.](/azure/expressroute/expressroute-nat)
  
Adicione as alterações da conectividade de saída ao diagrama de topologia de rede.
  
### <a name="design-inbound-service-connectivity"></a>Projetar conectividade de serviço de entrada
<a name="inbound"> </a>

A maioria das implantações corporativas do Office 365 assume alguma forma de conectividade de entrada do Office 365 para serviços locais, como cenários híbridos do Exchange, SharePoint e Skype for Business, migrações de caixa de correio e autenticação usando a infraestrutura ADFS. Quando ExpressRoute você habilita um caminho de roteamento adicional entre sua rede local e a Microsoft para conectividade de saída, essas conexões de entrada podem ser inadvertidamente impactadas pelo roteamento assimétrico, mesmo se você pretende que esses fluxos continuem a usar a Internet. Algumas precauções descritas abaixo são recomendadas para garantir que não haja impacto nos fluxos de entrada baseados na Internet do Office 365 para sistemas locais.
  
Para minimizar os riscos de roteamento assimétrico para fluxos de tráfego de rede de entrada, todas as conexões de entrada devem usar NAT de origem antes que elas são roteadas para segmentos de sua rede que têm visibilidade de roteamento para ExpressRoute. Se as conexões de entrada são permitidas em um segmento de rede com visibilidade de roteamento para o ExpressRoute sem NAT de origem, as solicitações provenientes do Office 365 entrarão da Internet, mas a resposta voltando para o Office 365 preferirá o caminho de rede ExpressRoute de volta para a rede da Microsoft, causando roteamento assimétrico.
  
Você pode considerar um dos seguintes padrões de implementação para atender a esse requisito:
  
1. Execute NAT de origem antes que as solicitações sejam roteados para sua rede interna usando equipamentos de rede, como firewalls ou balanceadores de carga no caminho da Internet para seus sistemas locais.

2. Certifique-se de que as rotas expressRoute não sejam propagadas para os segmentos de rede nos quais residem serviços de entrada, como servidores front-end ou sistemas de proxy reverso, manipulando conexões com a Internet.

Contabilizar explicitamente esses cenários em sua rede e manter todos os fluxos de tráfego de rede de entrada pela Internet ajuda a minimizar a implantação e o risco operacional de roteamento assimétrico.
  
Pode haver casos em que você pode optar por direcionar alguns fluxos de entrada em conexões ExpressRoute. Para esses cenários, leve em consideração as seguintes considerações adicionais.
  
1. O Office 365 só pode direcionar pontos de extremidade locais que usam IPs públicos. Isso significa que, mesmo que o ponto de extremidade de entrada local seja exposto apenas ao Office 365 sobre o ExpressRoute, ele ainda precisa ter o IP público associado a ele.

2. Toda a resolução de nome DNS que os serviços do Office 365 executam para resolver pontos de extremidade locais ocorrem usando o DNS público. Isso significa que você deve registrar o FQDN dos pontos de extremidade de serviço de entrada para mapeamentos IP na Internet.

3. Para receber conexões de rede de entrada por meio do ExpressRoute, as sub-redes IP públicas para esses pontos de extremidade devem ser anunciadas à Microsoft por meio do ExpressRoute.

4. Avalie cuidadosamente esses fluxos de tráfego de rede de entrada para garantir que os controles de rede e segurança adequados sejam aplicados a eles de acordo com as políticas de rede e segurança da sua empresa.

5. Depois que seus pontos de extremidade de entrada locais são anunciados para a Microsoft por meio do ExpressRoute, o ExpressRoute se tornará efetivamente o caminho de roteamento preferencial para esses pontos de extremidade para todos os serviços da Microsoft, incluindo o Office 365. Isso significa que essas sub-redes de ponto de extremidade só devem ser usadas para comunicações com serviços do Office 365 e nenhum outro serviço na rede da Microsoft. Caso contrário, seu design causará roteamento assimétrico em que as conexões de entrada de outros serviços da Microsoft preferem rotear a entrada sobre ExpressRoute, enquanto o caminho de retorno usará a Internet.

6. Caso um circuito ExpressRoute ou local de meet-me esteja inocatado, você precisará garantir que os pontos de extremidade de entrada locais ainda estão disponíveis para aceitar solicitações em um caminho de rede separado. Isso pode significar sub-redes de publicidade para esses pontos de extremidade por meio de vários circuitos ExpressRoute.

7. Recomendamos aplicar NAT de origem para todos os fluxos de tráfego de rede de entrada que entram em sua rede por meio do ExpressRoute, especialmente quando esses fluxos de dispositivos de rede entre estados, como firewalls.

8. Alguns serviços locais, como proxy ADFS ou Descoberta Automática do Exchange, podem receber solicitações de entrada de serviços do Office 365 e usuários da Internet. Para essas solicitações, o Office 365 direcionará o mesmo FQDN que as solicitações de usuário pela Internet. Permitir conexões de usuário de entrada da Internet para esses pontos de extremidade locais, ao mesmo tempo que força as conexões do Office 365 a usar o ExpressRoute, representa uma complexidade de roteamento significativa. Para a grande maioria dos clientes que implementam cenários complexos sobre o ExpressRoute não é recomendado devido a considerações operacionais. Essa sobrecarga adicional inclui o gerenciamento de riscos de roteamento assimétrico e exigirá que você gerencie cuidadosamente anúncios e políticas de roteamento em várias dimensões.

### <a name="update-your-network-topology-plan-to-show-how-you-would-avoid-asymmetric-routes"></a>Atualize seu plano de topologia de rede para mostrar como evitar rotas assimétricas
<a name="asymmetric"> </a>

Você deseja evitar o roteamento assimétrico para garantir que as pessoas em sua organização possam usar o Office 365 perfeitamente, bem como outros serviços importantes na Internet. Há duas configurações comuns que os clientes têm que causam roteamento assimétrico. Agora é um bom momento para revisar a configuração de rede que você está planejando usar e verificar se um desses cenários de roteamento assimétrico poderia existir.
  
Para começar, examinaremos algumas situações diferentes associadas ao diagrama de rede a seguir. Neste diagrama, todos os servidores que recebem solicitações de entrada, como ADFS ou servidores híbridos locais, estão no data center de Nova Jérsei e são anunciados na Internet.
  
1. Embora a rede de perímetro seja segura, não há NAT de origem disponível para solicitações de entrada.

2. Os servidores no data center de Nova Jérsei podem ver as rotas da Internet e do ExpressRoute.

![Visão geral da conectividade do ExpressRoute](../media/8f074af6-ef38-44e8-bc5a-8b4d981fbb20.png)
  
Também temos sugestões sobre como corrigi-los.
  
#### <a name="problem-1-cloud-to-on-premises-connection-over-the-internet"></a>Problema 1: nuvem para conexão local pela Internet
  
O diagrama a seguir ilustra o caminho de rede assimétrico tomado quando sua configuração de rede não fornece NAT para solicitações de entrada da nuvem da Microsoft pela Internet.
  
1. A solicitação de entrada do Office 365 recupera o endereço IP do ponto de extremidade local do DNS público e envia a solicitação para sua rede de perímetro.

2. Nesta configuração defeituosa, não há NAT de origem configurada ou disponível na rede de perímetro para a qual o tráfego é enviado, resultando no endereço IP de origem real sendo usado como destino de retorno.

  - O servidor em sua rede encaminha o tráfego de retorno para o Office 365 por meio de qualquer conexão de rede expressRoute disponível.

  - O resultado é um caminho assimétrico para esse fluxo para o Office 365, resultando em uma conexão interrompida.

![Problema de roteamento 1 expressRoute assimétrico](../media/9c210c2a-e0ea-4180-8ede-1bf41746ce7a.png)
  
##### <a name="solution-1a-source-nat"></a>Solução 1a: NAT de origem
  
Simplesmente adicionar um NAT de origem à solicitação de entrada resolve essa rede mal configurada. Neste diagrama:
  
1. A solicitação de entrada continua a entrar pela rede de perímetro do data center de Nova Jérsei. Desta vez, o NAT de origem está disponível.

2. A resposta do servidor retorna para o IP associado ao NAT de origem em vez do endereço IP original, resultando na resposta retornando ao longo do mesmo caminho de rede.

![Solução de roteamento 1 expressRoute assimétrica](../media/0e87a155-f8de-48ed-92ac-27367b727a82.png)
  
##### <a name="solution-1b-route-scoping"></a>Solução 1b: Roteamento de Rota
  
Como alternativa, você pode optar por não permitir que os prefixos BGP expressRoute sejam anunciados, removendo o caminho de rede alternativo para esses computadores. Neste diagrama:
  
1. A solicitação de entrada continua a entrar pela rede de perímetro do data center de Nova Jérsei. Desta vez, os prefixos anunciados pela Microsoft por meio do circuito ExpressRoute não estão disponíveis para o data center de Nova Jérsei.

2. A resposta do servidor retorna para o IP associado ao endereço IP original pela única rota disponível, resultando na resposta retornando ao longo do mesmo caminho de rede.

![Solução de roteamento 2 expressRoute 2](../media/9cb4b2bf-7aa6-487a-bc02-e02af8a979f6.png)
  
#### <a name="problem-2-cloud-to-on-premises-connection-over-expressroute"></a>Problema 2: nuvem para conexão local por meio do ExpressRoute
  
O diagrama a seguir ilustra o caminho de rede assimétrico tomado quando sua configuração de rede não fornece NAT para solicitações de entrada da nuvem da Microsoft sobre ExpressRoute.
  
1. A solicitação de entrada do Office 365 recupera o endereço IP do DNS e envia a solicitação para sua rede de perímetro.

2. Nesta configuração defeituosa, não há NAT de origem configurada ou disponível na rede de perímetro para a qual o tráfego é enviado, resultando no endereço IP de origem real sendo usado como destino de retorno.

  - O computador em sua rede encaminha o tráfego de retorno para o Office 365 por meio de qualquer conexão de rede expressRoute disponível.

  - O resultado é uma conexão assimétrica com o Office 365.

![Problema de roteamento 2 expressRoute 2](../media/f6fd155b-bbb7-472a-846e-039a99f09913.png)
  
##### <a name="solution-2-source-nat"></a>Solução 2: NAT de origem
  
Simplesmente adicionar um NAT de origem à solicitação de entrada resolve essa rede mal configurada. Neste diagrama:
  
1. A solicitação de entrada continua a entrar pela rede de perímetro do data center de Nova York. Desta vez, o NAT de origem está disponível.

2. A resposta do servidor retorna para o IP associado ao NAT de origem em vez do endereço IP original, resultando na resposta retornando ao longo do mesmo caminho de rede.

![Solução 3 de roteamento assimétrico expressRoute](../media/a5d2b90d-a3ec-4047-afbf-6e6e99f376a7.png)
  
### <a name="paper-verify-that-the-network-design-has-path-symmetry"></a>Paper verify that the network design has path symmetry

Neste ponto, você precisa verificar no papel que seu plano de implementação oferece simetria de rota para os diferentes cenários em que você estará usando o Office 365. Você identificará a rota de rede específica que deve ser tomada quando uma pessoa usa diferentes recursos do serviço. Desde a rede local e o roteamento wan, para os dispositivos de perímetro, para o caminho de conectividade; ExpressRoute ou a Internet e a conexão com o ponto de extremidade online.
  
Você precisará fazer isso para todos os serviços de rede do Office 365 que foram identificados anteriormente como serviços que sua organização adotará.
  
Isso ajuda a fazer este artigo passar pelas rotas com uma segunda pessoa. Explique a eles de onde cada salto de rede deve obter sua próxima rota e certifique-se de que você esteja familiarizado com os caminhos de roteamento. Lembre-se de que o ExpressRoute sempre fornecerá uma rota mais com escopo para endereços IP do servidor Microsoft, dando a ele um custo de rota menor do que uma rota padrão da Internet.
  
### <a name="design-client-connectivity-configuration"></a>Projetar Configuração de Conectividade do Cliente
<a name="asymmetric"> </a>

![Usando arquivos PAC com ExpressRoute](../media/7cfa6482-dbae-416a-ae6f-a45e5f4de23b.png)
  
Se você estiver usando um servidor proxy para tráfego vinculado à Internet, será necessário ajustar qualquer arquivo de configuração do PAC ou cliente para garantir que os computadores cliente em sua rede sejam configurados corretamente para enviar o tráfego ExpressRoute desejado para o Office 365 sem transitar o servidor proxy e o tráfego restante, incluindo algum tráfego do Office 365, é enviado para o proxy relevante. Leia nosso guia sobre como gerenciar pontos de extremidade do [Office 365](./managing-office-365-endpoints.md) por exemplo, arquivos PAC.
  
> [!NOTE]
> Os pontos de extremidade mudam com frequência, tanto quanto semanalmente. Você só deve fazer alterações com base nos serviços e recursos adotados pela sua organização para reduzir o número de alterações que você precisará fazer para permanecer atual. Preste muita atenção  à Data Efetiva no feed RSS onde as alterações são anunciadas e um registro é mantido de todas as alterações passadas, os endereços IP anunciados podem não ser anunciados ou removidos do anúncio, até que a data efetiva seja atingida.
  
## <a name="build-your-deployment-and-testing-procedures"></a>Criar seus procedimentos de implantação e teste
<a name="testing"> </a>

Seu plano de implementação deve incluir o planejamento de teste e replicação. Se sua implementação não estiver funcionando conforme o esperado, o plano deve ser projetado para afetar o menor número de pessoas antes que os problemas sejam descobertos. A seguir estão alguns princípios de alto nível que seu plano deve considerar.
  
1. Estágio do segmento de rede e integração do serviço do usuário para minimizar a interrupção.

2. Planeje rotas de teste com traceroute e conexão TCP de um host conectado à Internet separado.

3. Preferencialmente, os testes de serviços de entrada e saída devem ser feitos em uma rede de teste isolada com um locatário do Office 365 de teste.

      - Como alternativa, os testes podem ser executados em uma rede de produção se o cliente ainda não estiver usando o Office 365 ou estiver em piloto.

      - Como alternativa, os testes podem ser executados durante uma paralisação de produção que é reservado apenas para teste e monitoramento.

      - Como alternativa, os testes podem ser feitos verificando rotas para cada serviço em cada nó do roteador de camada 3. Esse fall back só deve ser usado se nenhum outro teste for possível, pois a falta de testes físicos apresenta risco.

### <a name="build-your-deployment-procedures"></a>Criar seus procedimentos de implantação

Seus procedimentos de implantação devem ser implantados em pequenos grupos de pessoas em estágios para permitir testes antes de implantar em grupos maiores de pessoas. A seguir estão várias maneiras de estágio da implantação do ExpressRoute.
  
1. Configurar o ExpressRoute com o peering da Microsoft e ter os anúncios de rota encaminhados para um único host apenas para fins de teste em estágios.

2. Anunciar rotas para a rede ExpressRoute para um único segmento de rede em primeiro lugar e expanda anúncios de rota por segmento de rede ou região.

3. Se implantar o Office 365 pela primeira vez, use a implantação de rede ExpressRoute como piloto para um pequeno número de pessoas.

4. Se estiver usando servidores proxy, você pode configurar um arquivo PAC de teste para direcionar um pequeno número de pessoas para o ExpressRoute com testes e comentários antes de adicionar mais.

Seu plano de implementação deve listar cada um dos procedimentos de implantação que devem ser tomados ou comandos que precisam ser usados para implantar a configuração de rede. Quando o tempo de paralisação da rede chegar, todas as alterações que estão sendo feitas devem ser do plano de implantação escrito que foi escrito com antecedência e revisado por pares. Consulte nossas diretrizes sobre a configuração técnica do ExpressRoute.
  
- Atualizando seus registros TXT SPF se você tiver alterado os endereços IP de todos os servidores locais que continuarão a enviar emails.

- Atualizando quaisquer entradas DNS para servidores locais se você tiver alterado endereços IP para acomodar uma nova configuração NAT.

- Certifique-se de que você se inscreve no feed RSS para notificações de ponto de extremidade do Office 365 para manter qualquer roteamento ou configurações de proxy.

Após a conclusão da implantação do ExpressRoute, os procedimentos no plano de teste devem ser executados. Os resultados de cada procedimento devem ser registrados. Você deve incluir procedimentos para reverter para o ambiente de produção original caso os resultados do plano de teste indiquem que a implementação não foi bem-sucedida.
  
### <a name="build-your-test-procedures"></a>Criar seus procedimentos de teste

Seus procedimentos de teste devem incluir testes para cada serviço de rede de saída e de entrada para o Office 365 que estarão usando ExpressRoute e aqueles que não o usarão. Os procedimentos devem incluir testes de cada local de rede exclusivo, incluindo usuários que não estão no local na LAN corporativa.
  
Alguns exemplos de atividades de teste incluem o seguinte.
  
1. Ping do roteador local para o roteador da operadora de rede.

2. Valide os anúncios de endereço IP do Office 365 e CRM Online 500+ que são recebidos pelo roteador local.

3. Valide se o NAT de entrada e de saída está operando entre o ExpressRoute e a rede interna.

4. Valide se as rotas para o NAT estão sendo anunciadas do roteador.

5. Valide se ExpressRoute aceitou seus prefixos anunciados.

      - Use o seguinte cmdlet para verificar anúncios de paridade:

      ```PowerShell
      Get-AzureRmExpressRouteCircuitRouteTable -DevicePath Primary -ExpressRouteCircuitName TestER -ResourceGroupName RG -PeeringType MicrosoftPeering
      ```

6. Valide seu intervalo de IP NAT público não é anunciado para a Microsoft por meio de qualquer outro expressRoute ou circuito de rede pública da Internet, a menos que seja um subconjunto específico de um intervalo maior, como no exemplo anterior.

7. Os circuitos ExpressRoute estão emparelhados, valide que ambas as sessões BGP estão em execução.

8. Configurar um único host no interior do NAT e usar ping, rastreamento e tcpping para testar a conectividade no novo circuito para o host outlook.office365.com. Como alternativa, você pode usar uma ferramenta como o Wireshark ou o Microsoft Network Monitor 3.4 em uma porta espelhada para o MSEE para validar que você pode se conectar ao endereço IP associado ao outlook.office365.com.

9. Testar a funcionalidade de nível do aplicativo para o Exchange Online.

  - Teste o Outlook é capaz de se conectar ao Exchange Online e enviar/receber emails.

  - Testar o Outlook é capaz de usar o modo online.

  - Teste a conectividade do smartphone e o recurso de envio/recebimento.

10. Testar a funcionalidade de nível do aplicativo para o SharePoint Online

  - Teste o cliente de sincronização do OneDrive for Business.

  - Teste o acesso à Web do SharePoint Online.

11. Testar a funcionalidade de nível do aplicativo para cenários de chamadas do Skype for Business:

  - Participe da chamada de conferência como usuário autenticado [convite iniciado pelo usuário final].

  - Convidar o usuário para a chamada de conferência [convite enviado da MCU].

  - Participe da conferência como usuário anônimo usando o aplicativo Web do Skype for Business.

  - Participe da chamada de sua conexão de computador com fio, telefone IP e dispositivo móvel.

  - Call to federated user o Call to PSTN Validation: call is completed, call quality is acceptable, connection time is acceptable.

  - Verifique se o status de presença para contatos é atualizado para membros do locatário e usuários federados.

### <a name="common-problems"></a>Problemas comuns

O roteamento assimétrico é o problema de implementação mais comum. Aqui estão algumas fontes comuns para procurar:
  
- Usando uma topologia de roteamento de rede aberta ou plana sem NAT de origem no local.

- Não usar o SNAT para rotear para serviços de entrada por meio de conexões de Internet e ExpressRoute.

- Não testar serviços de entrada no ExpressRoute em uma rede de teste antes de implantar amplamente.

## <a name="deploying-expressroute-connectivity-through-your-network"></a>Implantando a conectividade ExpressRoute por meio de sua rede
<a name="testing"> </a>

Estágio sua implantação para um segmento da rede por vez, progressivamente implantando a conectividade para diferentes partes da rede com um plano para reverter para cada novo segmento de rede. Se sua implantação estiver alinhada a uma implantação do Office 365, implante-a primeiro nos usuários piloto do Office 365 e se estenda a partir daí.
  
Primeiro para seu teste e, em seguida, para produção:
  
- Execute as etapas de implantação para habilitar o ExpressRoute.

- Teste sua visão das rotas de rede conforme esperado.

- Execute testes em cada serviço de entrada e saída.

- Reação se você descobrir algum problema.

### <a name="set-up-a-test-connection-to-expressroute-with-a-test-network-segment"></a>Configurar uma conexão de teste para ExpressRoute com um segmento de rede de teste

Agora que você tem o plano concluído no papel, é hora de testar em pequena escala. Neste teste, você estabelecerá uma única conexão ExpressRoute com o Microsoft Peering para uma sub-rede de teste em sua rede local. Você pode configurar um locatário do [Office 365](https://go.microsoft.com/fwlink/p/?LinkID=403802) de avaliação com conectividade de e para a sub-rede de teste e incluir todos os serviços de saída e de entrada que você estará usando em produção na sub-rede de teste. Configurar o DNS para o segmento de rede de teste e estabelecer todos os serviços de entrada e saída. Execute seu plano de teste e certifique-se de que você está familiarizado com o roteamento para cada serviço e a propagação de rota.
  
### <a name="execute-the-deployment-and-test-plans"></a>Executar os planos de implantação e teste

Ao concluir os itens descritos acima, verifique as áreas concluídas e verifique se você e sua equipe os revisaram antes de executar seus planos de implantação e teste.
  
- Lista de serviços de saída e de entrada envolvidos na alteração de rede.

- Diagrama de arquitetura de rede global mostrando a saída da Internet e locais de meet-me expressRoute.

- Diagrama de roteamento de rede que demonstra os diferentes caminhos de rede usados para cada serviço implantado.

- Um plano de implantação com etapas para implementar as alterações e a replicação, se necessário.

- Um plano de teste para testar cada serviço de rede e office 365.

- Validação de papel concluída de rotas de produção para serviços de entrada e saída.

- Um teste concluído em um segmento de rede de teste, incluindo teste de disponibilidade.

Escolha uma janela de paralisação que seja longa o suficiente para executar todo o plano de implantação e o plano de teste, tem algum tempo disponível para solução de problemas e tempo para reverter, se necessário.
  
> [!CAUTION]
> Devido à natureza complexa do roteamento na Internet e no ExpressRoute, é recomendável que o tempo de buffer adicional seja adicionado a essa janela para lidar com a solução de problemas de roteamento complexo.
  
### <a name="configure-qos-for-skype-for-business-online"></a>Configurar QoS para Skype for Business Online

A QoS é necessária para obter benefícios de voz e reunião para o Skype for Business Online. Você pode configurar a QoS depois de garantir que a conexão de rede ExpressRoute não bloqueie qualquer outro acesso de serviço do Office 365. A configuração para QoS está descrita no artigo [ExpressRoute e QoS no Skype for Business Online](https://support.office.com/article/ExpressRoute-and-QoS-in-Skype-for-Business-Online-20c654da-30ee-4e4f-a764-8b7d8844431d) .
  
## <a name="troubleshooting-your-implementation"></a>Solução de problemas de sua implementação
<a name="troubleshooting"> </a>

O primeiro lugar a ser olhado é nas etapas deste guia de implementação, houve alguma falta no seu plano de implementação? Volte e execute outros pequenos testes de rede, se possível, para replicar o erro e depurá-lo lá.
  
Identifique quais serviços de entrada ou de saída falharam durante o teste. Obter especificamente os endereços IP e sub-redes para cada um dos serviços que falharam. Vá em frente e ande pelo diagrama de topologia de rede no papel e valide o roteamento. Valide especificamente para onde o roteamento expressRoute é anunciado, Teste esse roteamento durante a paralisação, se possível, com rastreamentos.
  
Execute o PSPing com um rastreamento de rede para cada ponto de extremidade do cliente e avalie endereços IP de origem e destino para validar se eles estão conforme esperado. Execute a telnet para qualquer host de email que você exponha na porta 25 e verifique se o SNAT está ocultando o endereço IP de origem original, se isso for esperado.
  
Lembre-se de que, ao implantar o Office 365 com uma conexão ExpressRoute, você precisará garantir que a configuração de rede do ExpressRoute seja idealmente projetada e você também tenha otimizado os outros componentes em sua rede, como computadores cliente. Além de usar este guia de planejamento para solucionar problemas das etapas que você pode ter perdido, também escrevemos um plano de solução de problemas de desempenho [para o Office 365](https://support.office.com/article/Performance-troubleshooting-plan-for-Office-365-e241e5d9-b1d8-4f1d-a5c8-4106b7325f8c) .
  
Aqui está um link curto que você pode usar para voltar: [https://aka.ms/implementexpressroute365]()
  
## <a name="related-topics"></a>Tópicos Relacionados

[Avaliando a conectividade de rede do Office 365](assessing-network-connectivity.md)
  
[Microsoft Azure ExpressRoute para Office 365](azure-expressroute.md)
  
[Como gerenciar o ExpressRoute para a conectividade do Office 365](managing-expressroute-for-connectivity.md)
  
[Como rotear com o ExpressRoute para Office 365](routing-with-expressroute.md)
  
[Planejamento de rede com o ExpressRoute para Office 365](network-planning-with-expressroute.md)
  
[Usando comunidades BGP no ExpressRoute para cenários do Office 365](bgp-communities-in-expressroute.md)
  
[Qualidade da mídia e desempenho de conectividade de rede no Skype for Business Online](https://support.office.com/article/5fe3e01b-34cf-44e0-b897-b0b2a83f0917)
  
[Como otimizar a sua rede para o Skype for Business Online](https://support.office.com/article/b363bdca-b00d-4150-96c3-ec7eab5a8a43)
  
[ExpressRoute e QoS no Skype for Business Online](https://support.office.com/article/20c654da-30ee-4e4f-a764-8b7d8844431d)
  
[Fluxo de chamadas usando o ExpressRoute](https://support.office.com/article/413acb29-ad83-4393-9402-51d88e7561ab)
  
[Ajuste de desempenho do Office 365 usando linhas de base e histórico de desempenho](performance-tuning-using-baselines-and-history.md)
  
[Plano de solução de problemas de desempenho do Office 365](performance-troubleshooting-plan.md)
  
[URLs e intervalos de endereços IP do Office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)
  
[Rede do Office 365 e ajuste de desempenho](network-planning-and-performance.md)