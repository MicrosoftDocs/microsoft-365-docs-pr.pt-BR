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
description: Saiba como implementar o ExpressRoute para o Office 365, que fornece um caminho de roteamento alternativo para vários serviços do Office 365 voltados para a Internet.
ms.openlocfilehash: 767a99f3a27f30b7193fd0d0b8376ff4923daffb
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46687429"
---
# <a name="implementing-expressroute-for-office-365"></a>Como implementar o ExpressRoute para o Office 365

*Esse artigo se aplica ao Microsoft 365 Enterprise e ao Office 365 Enterprise.*

O ExpressRoute para Office 365 fornece um caminho de roteamento alternativo para vários serviços do Office 365 voltados para a Internet. A arquitetura do ExpressRoute para o Office 365 baseia-se no anúncio de prefixos IP públicos de serviços do Office 365 que já estão acessíveis pela Internet em seus circuitos do ExpressRoute provisionados para a redistribuição subsequente desses prefixos IP em sua rede. Com o ExpressRoute, você habilita efetivamente vários caminhos de roteamento diferentes, através da Internet e do ExpressRoute, para muitos serviços do Office 365. Esse estado de roteamento na rede pode representar uma alteração significativa na forma como sua topologia de rede interna é projetada.
  
 **Status:** Guia completo v2
  
Você deve planejar cuidadosamente sua implementação do ExpressRoute para Office 365 para acomodar as complexidades de rede de ter roteamento disponível por meio de um circuito dedicado com rotas injetadas na sua rede principal e na Internet. Se você e sua equipe não fizerem o planejamento e os testes detalhados deste guia, haverá um alto risco que você experimentará intermitente ou uma perda total de conectividade com os serviços do Office 365 quando o circuito ExpressRoute estiver habilitado.
  
Para ter uma implementação bem-sucedida, você precisará analisar seus requisitos de infraestrutura, passar pela avaliação e design detalhados de rede, planejar cuidadosamente a distribuição de forma controlada e de criar um plano detalhado de validação e teste. Para um ambiente distribuído de grande porte, não é incomum ver as implementações estendem vários meses. Este guia foi projetado para ajudá-lo a planejar o futuro.
  
Grandes implantações bem-sucedidas podem levar seis meses no planejamento e, muitas vezes, incluem membros da equipe de várias áreas na organização, incluindo rede, firewall e administradores de servidor proxy, administradores do Office 365, segurança, suporte ao usuário final, gerenciamento de projetos e patrocínio executivo. Seu investimento no processo de planejamento reduzirá a probabilidade de falhas de implantação resultando em tempo de inatividade ou em uma solução de problemas complexa e dispendiosa.
  
Esperamos que os seguintes pré-requisitos sejam concluídos antes que este guia de implementação seja iniciado.
  
1. Você concluiu uma avaliação de rede para determinar se o ExpressRoute é recomendado e aprovado.

2. Você selecionou um provedor de serviços de rede do ExpressRoute. Encontre detalhes sobre os [parceiros e locais de emparelhamento do ExpressRoute](https://azure.microsoft.com/documentation/articles/expressroute-locations/).

3. Você já leu e entendeu a [documentação do expressroute](https://azure.microsoft.com/documentation/services/expressroute/) , e sua rede interna é capaz de atender aos pré-requisitos do expressroute até o fim.

4. Sua equipe leu todas as orientações e documentações públicas em [https://aka.ms/expressrouteoffice365](https://aka.ms/expressrouteoffice365) , [https://aka.ms/ert](https://aka.ms/ert) e observados a série de [treinamentos do Azure ExpressRoute para Office 365](https://channel9.msdn.com/series/aer) no canal 9 para obter uma compreensão dos detalhes técnicos críticos, incluindo:

      - As dependências da Internet dos serviços SaaS.

      - Como evitar rotas assimétricas e lidar com roteamento complexo.

      - Como incorporar controles de segurança de perímetro, disponibilidade e nível de aplicativo.

## <a name="begin-by-gathering-requirements"></a>Comece coletando os requisitos
<a name="requirements"> </a>

Comece determinando quais recursos e serviços você planeja adotar em sua organização. Você precisa determinar quais recursos dos diferentes serviços do Office 365 serão usados e quais locais em sua rede hospedarão pessoas usando esses recursos. Com o catálogo de cenários, você precisa adicionar os atributos de rede que cada um desses cenários exige; como fluxos de tráfego de rede de entrada e saída e se os pontos de extremidade do Office 365 estão disponíveis no ExpressRoute ou não.
  
Para obter os requisitos da sua organização:
  
- Cataloga o tráfego de rede de entrada e saída para os serviços do Office 365 que sua organização está usando. Consulte a página de intervalos de endereços IP e URLs do Office 365 para obter a descrição dos fluxos que os diferentes cenários do Office 365 exigem.

- Obtenha a documentação da topologia de rede existente mostrando os detalhes do backbone e da topologia de WAN interna, conectividade de sites de satélite, conectividade de usuário da última quilometragem, roteamento para pontos de saída de perímetro de rede e serviços de proxy.

  - Identifique pontos de extremidade de serviço de entrada nos diagramas de rede que o Office 365 e outros serviços da Microsoft irão se conectar, mostrando os caminhos de conexão do ExpressRoute e da Internet.

  - Identifique todos os locais de usuários geográficos e conectividade de WAN entre os locais, juntamente com os locais que atualmente têm um egresso para a Internet e quais locais são propostos para ter um local de emparelhamento de rota de saída.

  - Identificar todos os dispositivos de borda, como proxies, firewalls e assim por diante, e catalogar sua relação com os fluxos que estão passando pela Internet e pelo ExpressRoute.

  - Documente se os usuários finais acessarão os serviços do Office 365 via roteamento direto ou proxy de aplicativo indireto para os fluxos de Internet e ExpressRoute.

- Adicione o local do seu locatário e atenda aos locais do seu diagrama de rede.

- Estimar as características de desempenho e latência de rede esperadas e observadas dos principais locais de usuários para o Office 365. Tenha em mente que o Office 365 é um conjunto global e distribuído de serviços e usuários se conectarão a locais que podem ser diferentes do local de seus locatários. Por esse motivo, é recomendável medir e otimizar a latência entre o usuário e a borda mais próxima do Microsoft Global Network em relação ao ExpressRoute e conexões com a Internet. Você pode usar suas descobertas da avaliação de rede para ajudar com essa tarefa.

- Listar os requisitos de segurança de rede da empresa e alta disponibilidade que precisam ser atendidos com a nova conexão ExpressRoute. Por exemplo, como os usuários continuam a obter acesso ao Office 365 em caso de falha no circuito de saída da Internet ou do ExpressRoute.

- Documente os fluxos de rede de entrada e saída do Office 365 usarão o caminho da Internet e que usarão o ExpressRoute. As especificações de locais geográficos de seus usuários e os detalhes de sua topologia de rede local podem exigir que o plano seja diferente de um local de usuário para outro.

### <a name="catalog-your-outbound-and-inbound-network-traffic"></a>Catalogar o tráfego de rede de entrada e de saída
<a name="trafficCatalog"> </a>

Para minimizar o roteamento e outras complexidades de rede, recomendamos que você use apenas o ExpressRoute para Office 365 para os fluxos de tráfego de rede que são necessários para passar por uma conexão dedicada devido a requisitos normativos ou como resultado da avaliação de rede. Além disso, recomendamos que você teste o escopo do roteamento ExpressRoute e a abordagem de tráfego de rede de entrada e saída, como estágios diferentes e distintos do projeto de implementação. Implantar o ExpressRoute para Office 365 para o usuário só iniciou fluxos de tráfego de rede de saída e deixar fluxos de tráfego de rede de entrada através da Internet pode ajudar a controlar o aumento na complexidade do Topological e os riscos de introdução de possibilidades de roteamento assimétrica adicionais.
  
Seu catálogo de tráfego de rede deve conter listagens de todas as conexões de rede de entrada e de saída que você terá entre a rede local e a Microsoft.
  
- Fluxos de tráfego de rede de saída são todos os cenários em que uma conexão é iniciada a partir do seu ambiente local, como de clientes ou servidores internos, com um destino dos serviços da Microsoft. Essas conexões podem ser direcionadas para o Office 365 ou indireta, como quando a conexão passa por servidores proxy, firewalls ou outros dispositivos de rede no caminho para o Office 365.

- Fluxos de tráfego de rede de entrada são todos os cenários em que uma conexão é iniciada da nuvem da Microsoft para um host local. Essas conexões normalmente precisam passar por firewall e outra infraestrutura de segurança que a política de segurança do cliente requer para fluxos de origem externa.

Leia a seção **garantindo a simetria do roteiro** do artigo de [Roteamento com o ExpressRoute para Office 365](https://support.office.com/article/Routing-with-ExpressRoute-for-Office-365-e1da26c6-2d39-4379-af6f-4da213218408) para determinar quais serviços enviarão tráfego de entrada e procure a coluna marcada **para o Office 365** no artigo de referência de [pontos de extremidade do Office 365](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2) para determinar o restante das informações de conectividade.
  
Para cada serviço que requer uma conexão de saída, convém descrever a conectividade planejada para o serviço, incluindo roteamento de rede, configuração de proxy, inspeção de pacote e necessidades de largura de banda.
  
Para cada serviço que requer uma conexão de entrada, você precisará de algumas informações adicionais. Os servidores no Microsoft Cloud estabelecerão conexões com a rede local. para garantir que as conexões sejam feitas corretamente, convém descrever todos os aspectos dessa conectividade, incluindo; as entradas de DNS públicas para os serviços que aceitarão essas conexões de entrada, os endereços IP IPv4 formatados para CIDR, o equipamento de provedor de serviços de Internet envolvido e como o NAT de entrada ou NAT de origem é tratado para essas conexões.
  
Conexões de entrada devem ser revisadas independentemente de estarem se conectando pela Internet ou pelo ExpressRoute para garantir que o roteamento assimétrico não tenha sido introduzido. Em alguns casos, os pontos de extremidade locais nos quais os serviços do Office 365 iniciam conexões de entrada também precisam ser acessados por outros serviços da Microsoft e que não são da Microsoft. É fundamental que a habilitação do roteamento do ExpressRoute para esses serviços para os objetivos do Office 365 não divida outros cenários. Em muitos casos, os clientes podem precisar implementar alterações específicas à sua rede interna, como o NAT baseado em origem, para garantir que os fluxos de entrada da Microsoft permaneçam simétricos após a habilitação do ExpressRoute.
  
Veja um exemplo do nível de detalhamento necessário. Nesse caso, o Exchange híbrido encaminharia para o sistema local no ExpressRoute.

|**Propriedade Connection**|**Valor**|
|:-----|:-----|
|**Direção do tráfego de rede** <br/> |Entrada  <br/> |
|**Serviço** <br/> |Exchange Híbrido  <br/> |
|**Ponto de extremidade público do Office 365 (origem)** <br/> |Exchange Online (endereços IP)  <br/> |
|**Ponto de extremidade público local (destino)** <br/> |5.5.5.5  <br/> |
|**Entrada de DNS pública (Internet)** <br/> |Autodiscover.contoso.com  <br/> |
|**Esse ponto de extremidade local será usado por outros serviços da Microsoft (que não são do Office 365)** <br/> |Não  <br/> |
|**Esse ponto de extremidade local será usado por usuários/sistemas na Internet** <br/> |Sim  <br/> |
|**Sistemas internos publicados por meio de pontos de extremidade públicos** <br/> |Função de acesso para cliente do Exchange Server (local) 192.168.101, 192.168.102, 192.168.103  <br/> |
|**Anúncio de IP do ponto de extremidade público** <br/> |**Para a Internet**: 5.5.0.0/16  <br/> **Para o ExpressRoute**: 5.5.5.0/24  <br/> |
|**Controles de segurança/de perímetro** <br/> |**Caminho da Internet**: DeviceID_002  <br/> **Caminho do ExpressRoute**: DeviceID_003  <br/> |
|**Alta Disponibilidade** <br/> |Ativo/ativo entre dois redundantes geograficamente  <br/> Circuitos do ExpressRoute-Chicago e Dallas  <br/> |
|**Controle de simetria de caminho** <br/> |**Método**: NAT de origem  <br/> **Caminho da Internet**: conexões de entrada NAT de origem para 192.168.5.5  <br/> |**Caminho do ExpressRoute**: conexões NAT de origem para 192.168.1.0 (Chicago) e 192.168.2.0 (Dallas)  <br/> |

Aqui está um exemplo de um serviço que só é de saída:

|**Propriedade Connection**|**Valor**|
|:-----|:-----|
|**Direção do tráfego de rede** <br/> |Saída  <br/> |
|**Serviço** <br/> |SharePoint Online  <br/> |
|**Ponto de extremidade local (origem)** <br/> |Estação de trabalho do usuário  <br/> |
|**Ponto de extremidade público do Office 365 (destino)** <br/> |SharePoint Online (endereços IP)  <br/> |
|**Entrada de DNS pública (Internet)** <br/> |\*. sharepoint.com (e FQDNs adicionais)  <br/> |
|**Referências da CDN** <br/> |cdn.sharepointonline.com (e FQDNs adicionais)-endereços IP mantidos por provedores de CDN)  <br/> |
|**Anúncio de IP e NAT em uso** <br/> |**NAT de caminho/origem da Internet**: 1.1.1.0/24  <br/> **NAT de caminho/origem do ExpressRoute**: 1.1.2.0/24 (Chicago) e 1.1.3.0/24 (Dallas)  <br/> |
|**Método de conectividade** <br/> |**Internet**: via proxy de camada 7 (arquivo. PAC)  <br/> **ExpressRoute**: roteamento direto (sem proxy)  <br/> |
|**Controles de segurança/de perímetro** <br/> |**Caminho da Internet**: DeviceID_002  <br/> **Caminho do ExpressRoute**: DeviceID_003  <br/> |
|**Alta Disponibilidade** <br/> |**Caminho da Internet**: egresso redundante da Internet  <br/> **Caminho do ExpressRoute**: roteamento ativo/ativo ' o Hot batata ' em dois circuitos do ExpressRoute com redundância geográfica-Chicago e Dallas  <br/> |
|**Controle de simetria de caminho** <br/> |**Método**: NAT de origem para todas as conexões  <br/> |

### <a name="your-network-topology-design-with-regional-connectivity"></a>Seu design de topologia de rede com conectividade regional
<a name="topology"> </a>

Depois de compreender os serviços e os fluxos de tráfego de rede associados, você poderá criar um diagrama de rede que incorpore esses novos requisitos de conectividade e ilustrar as alterações que você fará para usar o ExpressRoute para o Office 365. O diagrama deve incluir:
  
1. Todos os locais de usuário onde o Office 365 e outros serviços serão acessados.

2. Todos os pontos de saída da Internet e do ExpressRoute.

3. Todos os dispositivos de saída e de entrada que gerenciam a conectividade dentro e fora da rede, incluindo roteadores, firewalls, servidores de proxy de aplicativo e detecção/prevenção de invasão.

4. Destinos internos para todo o tráfego de entrada, como servidores ADFS internos que aceitam conexões dos servidores proxy de aplicativos Web do ADFS.

5. Catálogo de todas as sub-redes IP que serão anunciadas

6. Identifique cada local onde as pessoas irão acessar o Office 365 e liste os locais de reunião que serão usados para o ExpressRoute.

7. Locais e partes da topologia de rede interna, onde os prefixos IP da Microsoft aprendidos no ExpressRoute serão aceitos, filtrados e propagados para o.

8. A topologia de rede deve ilustrar a localização geográfica de cada segmento de rede e como ele se conecta à rede Microsoft sobre o ExpressRoute e/ou a Internet.

O diagrama abaixo mostra cada local onde as pessoas utilizarão o Office 365 junto com os anúncios de roteamento de entrada e saída para o Office 365.
  
![Reunião geográfica regional do ExpressRoute](../media/d866b36b-49bf-416b-af1b-d054e24989d2.png)
  
Para o tráfego de saída, as pessoas acessam o Office 365 de uma destas três maneiras:
  
1. Por meio de um local de reunião na América do Norte para pessoas da Califórnia.

2. Por meio de um local de reunião de Hong Kong para as pessoas de Hong Kong.

3. Pela Internet em Bangladesh, onde há menos pessoas e nenhum circuito ExpressRoute provisionado.

![Conexões de saída para o diagrama regional](../media/8319943d-08f0-4781-9ef3-d23de2ad4671.png)
  
Da mesma forma, o tráfego de rede de entrada do Office 365 retorna uma das três maneiras:
  
1. Por meio de um local de reunião na América do Norte para pessoas da Califórnia.

2. Por meio de um local de reunião de Hong Kong para as pessoas de Hong Kong.

3. Pela Internet em Bangladesh, onde há menos pessoas e nenhum circuito ExpressRoute provisionado.

![Conexões de entrada para o diagrama regional](../media/d6d6160d-bf28-4de3-a787-186c7432b306.png)
  
### <a name="determine-the-appropriate-meet-me-location"></a>Determinar o local adequado de reunião comigo

A seleção de locais de reunião-eu, que são o local físico onde o seu circuito do ExpressRoute conecta sua rede à rede da Microsoft, é influenciada pelos locais onde as pessoas acessarão o Office 365. Como uma oferta de SaaS, o Office 365 não opera sob o modelo regional de IaaS ou PaaS da mesma maneira que o Azure. Em vez disso, o Office 365 é um conjunto distribuído de serviços de colaboração, onde os usuários podem precisar se conectar a pontos de extremidade entre vários datacenters e regiões, que podem não estar necessariamente no mesmo local ou região onde o locatário do usuário está hospedado.
  
Isso significa que a consideração mais importante que você precisa fazer ao selecionar os locais de reunião para o ExpressRoute para o Office 365 é onde as pessoas da sua organização serão se conectando. A recomendação geral para a melhor conectividade do Office 365 é implementar o roteamento, de modo que as solicitações do usuário para os serviços do Office 365 sejam entregues na rede da Microsoft no caminho de rede mais curto, isso também é muitas vezes conhecido como roteamento de "Hot-batata". Por exemplo, se a maioria dos usuários do Office 365 estão em um ou dois locais, selecionar os locais de encontro que estão na proximidade mais próxima à localização desses usuários criará o design ideal. Se sua empresa tiver grandes populações de usuários em várias regiões diferentes, talvez você queira considerar o uso de vários circuitos do ExpressRoute e cumprir os locais. Para alguns dos seus locais de usuário, o caminho mais curto/mais ideal para o Microsoft Network e o Office 365, pode não estar nos pontos de WAN interna e do ExpressRoute, mas através da Internet.
  
Muitas vezes, há vários locais de reunião que podem ser selecionados em uma região com proximidade relativa aos seus usuários. Preencha a tabela a seguir para orientar suas decisões.

|**Locais de reunião de atendimento ao ExpressRoute planejados na Califórnia e Nova York**||
|:-----|:-----|
|Local  <br/> |Número de pessoas  <br/> |Latência esperada para rede da Microsoft através de egresso de Internet  <br/> |Latência esperada para o Microsoft Network over ExpressRoute  <br/> |
|Los Angeles  <br/> |10.000  <br/> |~ 15ms  <br/> |~ 10 ms (via vale do silício)  <br/> |
|DC Washington  <br/> |15.000  <br/> |~ 20 ms  <br/> |~ 10 ms (via Nova York)  <br/> |
|Dallas  <br/> |5.000  <br/> |~ 15ms  <br/> |~ 40ms (por meio de Nova York)  <br/> |

Depois que a arquitetura de rede global mostrar a região do Office 365, o provedor de serviços de rede do ExpressRoute atender a mim e a quantidade de pessoas por local tiver sido desenvolvida, ela poderá ser usada para identificar se qualquer otimização pode ser feita. Também pode mostrar as conexões de rede globais do hairpin onde as rotas de tráfego para um local distante para obter o local de reunião. Se um hairpin na rede global for descoberto, ele deverá ser corrigido antes de continuar. Encontre outro local de reunião-eu ou use pontos de saída de debates de Internet seletivos para evitar o hairpin.
  
O primeiro diagrama mostra um exemplo de um cliente com dois locais físicos na América do Norte. Você pode ver as informações sobre os locais do Office, os locais do locatário do Office 365 e várias opções para os locais do ExpressRoute. Neste exemplo, o cliente selecionou o local de reunião com base em dois princípios, em ordem:
  
1. Proximidade mais próxima às pessoas em sua organização.

2. Mais próximo da proximidade com um Microsoft datacenter onde o Office 365 está hospedado.

![Atendimento geográfico dos EUA](../media/5ec38274-b317-4ec1-91c8-90c2a7fd32ca.png)
  
Expandir esse conceito um pouco mais detalhadamente, o segundo diagrama mostra um exemplo de cliente multinacional que enfrentou informações semelhantes e tomada de decisões. Esse cliente tem um pequeno escritório em Bangladesh com apenas uma pequena equipe de dez pessoas voltadas para o crescimento da área de ti na região. Há um local de reunião com a Chennaiidade e um datacenter da Microsoft com o Office 365 hospedado na Chennai para que um local de reunião me faça sentido; no entanto, para dez pessoas, a despesa do circuito adicional é uma descansativa. À medida que você examinar sua rede, será necessário determinar se a latência envolvida no envio do tráfego de rede em sua rede é mais eficaz do que gastar a capital para adquirir outro circuito ExpressRoute.
  
Como alternativa, as dez pessoas em Bangladesh podem ter um desempenho melhor com o seu tráfego de rede enviado pela Internet para a rede da Microsoft do que rotear em sua rede interna, conforme mostramos nos diagramas introdutórios e reproduzidos abaixo.
  
![Conexões de saída para o diagrama regional](../media/8319943d-08f0-4781-9ef3-d23de2ad4671.png)
  
## <a name="create-your-expressroute-for-office-365-implementation-plan"></a>Criar seu plano de implementação do ExpressRoute para Office 365
<a name="implementation"> </a>

O plano de implementação deve abranger os detalhes técnicos da configuração do ExpressRoute, bem como os detalhes da configuração de todas as outras infra-estruturas em sua rede, como as seguintes.
  
- Planejar quais serviços são divididos entre o ExpressRoute e a Internet.

- Planejar a largura de banda, segurança, alta disponibilidade e failover.

- Criar roteamento de entrada e saída, incluindo otimizações de caminho de roteamento adequadas para locais diferentes

- Decida por quanto as rotas de ExpressRoute serão anunciadas para a sua rede e qual é o mecanismo para os clientes selecionarem o caminho da Internet ou do ExpressRoute; por exemplo, roteamento direto ou proxy de aplicativo.

- Planejar alterações de registro DNS, incluindo entradas da [estrutura de política de remetente](https://technet.microsoft.com/library/dn789058%28v=exchg.150%29.aspx) .

- Planejar a estratégia de NAT, incluindo o NAT de origem de saída e de entrada.

### <a name="plan-your-routing-with-both-internet-and-expressroute-network-paths"></a>Planejar o roteamento com caminhos de rede da Internet e do ExpressRoute
<a name="paths"> </a>

- Para sua implantação inicial, todos os serviços de entrada, como email de entrada ou conectividade híbrida, são recomendados para usar a Internet.

- Planejar o roteamento de LAN do cliente de usuário final, como [configurar um arquivo PAC/WPAD](https://aka.ms/manageo365endpoints), rota padrão, servidores proxy e anúncios de rota BGP.

- Planejar o roteamento de perímetro, incluindo servidores proxy, firewalls e proxies de nuvem.

### <a name="plan-your-bandwidth-security-high-availability-and-failover"></a>Planejar sua largura de banda, segurança, alta disponibilidade e failover
<a name="availability"> </a>

Crie um plano de largura de banda necessário para cada carga de trabalho principal do Office 365. Estimar separadamente os requisitos de largura de banda do Exchange Online, do SharePoint Online e do Skype for Business online. Você pode usar as calculadoras de estimativas fornecidas para o Exchange Online e o Skype for Business como um local inicial; no entanto, um teste piloto com uma amostra representativa dos perfis de usuário e locais é necessário para entender totalmente as necessidades de largura de banda da sua organização.
  
Adicionar como a segurança é tratada em cada local de egresso da Internet e do ExpressRoute para seu plano, lembre-se de que todas as conexões de ExpressRoute com o Office 365 usam o emparelhamento público e continuam a ser protegidas de acordo com as políticas de segurança da empresa para se conectar a redes externas.
  
Adicione detalhes ao seu plano sobre quais pessoas serão afetadas pelo tipo de paralisação e como essas pessoas poderão executar o trabalho em plena capacidade de forma mais simples.
  
#### <a name="plan-bandwidth-requirements-including-skype-for-business-requirements-on-jitter-latency-congestion-and-headroom"></a>Planejar requisitos de largura de banda, incluindo os requisitos do Skype for Business em tremulação, latência, congestionamento e capacidade
  
O Skype for Business online também tem requisitos de rede adicionais específicos que são detalhados no artigo [qualidade de mídia e desempenho de conectividade de rede no Skype for Business online](https://support.office.com/article/Media-Quality-and-Network-Connectivity-Performance-in-Skype-for-Business-Online-5fe3e01b-34cf-44e0-b897-b0b2a83f0917).
  
Leia a seção **planejamento de largura de banda para o Azure ExpressRoute** no [planejamento de rede com o expressroute para Office 365](https://support.office.com/article/Network-planning-with-ExpressRoute-for-Office-365-103208f1-e788-4601-aa45-504f896511cd).
  
Ao realizar uma avaliação de largura de banda com seus usuários pilotos, você pode usar nosso guia; [Ajuste de desempenho do Office 365 usando linhas de base e histórico de desempenho](https://support.office.com/article/Office-365-performance-tuning-using-baselines-and-performance-history-1492cb94-bd62-43e6-b8d0-2a61ed88ebae).
  
#### <a name="plan-for-high-availability-requirements"></a>Planejar requisitos de alta disponibilidade
  
Criar um plano de alta disponibilidade para atender às suas necessidades e incorporá-lo ao seu diagrama de topologia de rede atualizado. Leia a seção **alta disponibilidade e failover com o Azure ExpressRoute** no [planejamento de rede com o expressroute para Office 365](https://support.office.com/article/Network-planning-with-ExpressRoute-for-Office-365-103208f1-e788-4601-aa45-504f896511cd).
  
#### <a name="plan-for-network-security-requirements"></a>Planejar requisitos de segurança de rede
  
Criar um plano para atender aos requisitos de segurança de rede e incorporá-lo ao diagrama de topologia de rede atualizado. Leia a seção **aplicando controles de segurança ao Azure ExpressRoute para cenários do office 365** no [planejamento de rede com o expressroute para Office 365](https://support.office.com/article/Network-planning-with-ExpressRoute-for-Office-365-103208f1-e788-4601-aa45-504f896511cd).
  
### <a name="design-outbound-service-connectivity"></a>Criar conectividade de serviço de saída
<a name="outbound"> </a>

O ExpressRoute para Office 365 tem requisitos de rede de  *saída*  que podem não ser conhecidos. Especificamente, os endereços IP que representam seus usuários e redes para o Office 365 e que atuam como pontos de extremidade de origem para conexões de rede de saída para a Microsoft devem seguir os requisitos específicos descritos abaixo.
  
1. Os pontos de extremidade devem ser endereços IP públicos, registrados para sua empresa ou para portadora de fornecimento de conectividade com o ExpressRoute.

2. Os pontos de extremidade devem ser anunciados para a Microsoft e validados/aceitos pelo ExpressRoute.

3. Os pontos de extremidade não devem ser anunciados para a Internet com a mesma métrica de roteamento preferencial ou mais.

4. Os pontos de extremidade não devem ser usados para conectividade com os serviços da Microsoft que não estão configurados pelo ExpressRoute.

Se o design de sua rede não atender a esses requisitos, haverá um alto risco que seus usuários terão falhas de conectividade para o Office 365 e outros serviços da Microsoft devido à rota preta de holing ou roteamento assimétrico. Isso ocorre quando as solicitações para serviços da Microsoft são roteadas pelo ExpressRoute, mas as respostas são encaminhadas pela Internet, ou vice-versa, e as respostas são ignoradas por dispositivos de rede com estado, como firewalls.
  
O método mais comum que você pode usar para atender aos requisitos acima é usar o NAT de origem, implementado como parte da sua rede ou fornecido por sua concessionária da rota expressa. O NAT de origem permite que você abstrai os detalhes e o endereçamento de IP privado da sua rede de Internet do ExpressRoute e; juntamente com os anúncios de rotas IP adequados, forneça um mecanismo fácil para garantir a simetria do caminho. Se você estiver usando dispositivos de rede com estado específicos para locais de emparelhamento do ExpressRoute, você deve implementar pools NAT separados para cada emparelhamento de ExpressRoute para garantir a simetria do caminho.
  
Leia mais sobre os [requisitos de NAT do ExpressRoute](https://azure.microsoft.com/documentation/articles/expressroute-nat/).
  
Adicione as alterações para a conectividade de saída ao diagrama de topologia de rede.
  
### <a name="design-inbound-service-connectivity"></a>Criar conectividade de serviço de entrada
<a name="inbound"> </a>

A maioria das implantações de Enterprise Office 365 pressupõe alguma forma de conectividade de entrada do Office 365 para serviços locais, como para cenários híbridos do Exchange, SharePoint e Skype for Business, migrações de caixa de correio e autenticação usando a infraestrutura do ADFS. Quando o ExpressRoute permite que você habilite um caminho de roteamento adicional entre sua rede local e a Microsoft para conectividade de saída, essas conexões de entrada podem ser prejudicadas por roteamento assimétrico, mesmo se você pretende que esses fluxos continuem a usar a Internet. Algumas precauções descritas abaixo são recomendadas para garantir que não haja impacto nos fluxos de entrada baseados na Internet do Office 365 para sistemas locais.
  
Para minimizar os riscos de roteamento assimétrico para fluxos de tráfego de rede de entrada, todas as conexões de entrada devem usar o NAT de origem antes de serem roteadas para segmentos de sua rede com visibilidade de roteamento no ExpressRoute. Se as conexões de entrada forem permitidas em um segmento de rede com visibilidade de roteamento no ExpressRoute sem NAT de origem, as solicitações de origem do Office 365 entrarão na Internet, mas a resposta de volta para o Office 365 preferirá o caminho de rede ExpressRoute de volta para a rede da Microsoft, causando o roteamento assimétrico.
  
Você pode considerar um dos seguintes padrões de implementação para atender a esse requisito:
  
1. Executar o NAT de origem antes que as solicitações sejam roteadas para sua rede interna usando equipamento de rede, como firewalls ou balanceadores de carga no caminho da Internet para seus sistemas locais.

2. Certifique-se de que as rotas ExpressRoute não sejam propagadas para os segmentos de rede em que os serviços de entrada, como servidores front-end ou sistemas de proxy reverso, estão lidando com conexões de Internet.

Explicitamente as estatísticas desses cenários em sua rede e a manutenção de todo o tráfego de rede de entrada fluem pela Internet ajudam a minimizar a implantação e o risco operacional do roteamento assimétrico.
  
Pode haver casos em que você pode optar por direcionar alguns fluxos de entrada através de conexões ExpressRoute. Para esses cenários, considere as seguintes considerações adicionais em conta.
  
1. O Office 365 só pode direcionar pontos de extremidade locais que usam IPs públicos. Isso significa que, mesmo que o ponto de extremidade de entrada local seja exposto apenas ao Office 365 sobre o ExpressRoute, ele ainda precisa ter um IP público associado a ele.

2. A resolução de nomes DNS que os serviços do Office 365 realizam para resolver os pontos de extremidade locais ocorrem usando DNS público. Isso significa que você deve registrar o FQDN dos pontos de extremidade de serviço de entrada nos mapeamentos IP na Internet.

3. Para receber conexões de rede de entrada no ExpressRoute, as sub-redes IP públicas desses pontos de extremidade devem ser anunciadas para a Microsoft pelo ExpressRoute.

4. Avalie cuidadosamente esses fluxos de tráfego de rede de entrada para garantir que os controles de segurança e de rede adequados sejam aplicados a eles de acordo com as políticas de segurança e de rede da empresa.

5. Quando seus pontos de extremidade de entrada no local forem anunciados para a Microsoft no ExpressRoute, o ExpressRoute se tornará o caminho de roteamento preferencial para esses pontos de extremidade para todos os serviços da Microsoft, incluindo o Office 365. Isso significa que essas sub-redes de ponto de extremidade devem ser usadas apenas para comunicações com os serviços do Office 365 e nenhum outro serviço na rede da Microsoft. Caso contrário, o design causará roteamento assimétrico, onde as conexões de entrada de outros serviços da Microsoft preferem rotear a entrada pelo ExpressRoute, enquanto o caminho de retorno usará a Internet.

6. No caso de um circuito do ExpressRoute ou um local de reunião que eu esteja inativo, você precisará garantir que os pontos de extremidade de entrada no local ainda estejam disponíveis para aceitar solicitações por um caminho de rede separado. Isso pode significar o anúncio de sub-redes para esses pontos de extremidade através de vários circuitos do ExpressRoute.

7. Recomendamos a aplicação de NAT de origem para todos os fluxos de tráfego de rede de entrada que entram em sua rede através do ExpressRoute, especialmente quando eles fluem dispositivos de rede entre Estado, como firewalls.

8. Alguns serviços locais, como o proxy do ADFS ou a descoberta automática do Exchange, podem receber solicitações de entrada dos serviços do Office 365 e dos usuários da Internet. Para essas solicitações, o Office 365 direcionará o mesmo FQDN que as solicitações de usuário pela Internet. Permitir conexões de usuário de entrada da Internet para os pontos de extremidade locais, ao forçar conexões do Office 365 para usar o ExpressRoute, representa uma complexidade de roteamento significativa. Para a grande maioria dos clientes que implementarem esses cenários complexos sobre o ExpressRoute não é recomendada devido às considerações operacionais. Essa sobrecarga adicional inclui o gerenciamento de riscos de roteamento assimétrico e exigirá o gerenciamento cuidadoso de anúncios e políticas de roteamento em várias dimensões.

### <a name="update-your-network-topology-plan-to-show-how-you-would-avoid-asymmetric-routes"></a>Atualize seu plano de topologia de rede para mostrar como você evitaria rotas assimétricas
<a name="asymmetric"> </a>

Você deseja evitar o roteamento assimétrico para garantir que as pessoas em sua organização possam usar o Office 365 e outros serviços importantes na Internet sem interrupções. Há dois clientes de configurações comuns que causam roteamento assimétrico. Agora é uma boa hora para revisar a configuração de rede que você está planejando usar e verificar se um desses cenários de roteamento assimétrico pode existir.
  
Para começar, examinaremos algumas situações diferentes associadas ao diagrama de rede a seguir. Neste diagrama, todos os servidores que recebem solicitações de entrada, como ADFS ou servidores híbridos locais, estão no novo centro de dados de Jersey e são anunciados para a Internet.
  
1. Enquanto a rede de perímetro é segura, não há NAT de origem disponível para solicitações de entrada.

2. Os servidores no novo centro de dados de Jersey podem ver rotas da Internet e do ExpressRoute.

![Visão geral da conectividade do ExpressRoute](../media/8f074af6-ef38-44e8-bc5a-8b4d981fbb20.png)
  
Também temos sugestões sobre como corrigi-los.
  
#### <a name="problem-1-cloud-to-on-premises-connection-over-the-internet"></a>Problema 1: nuvem para conexão local pela Internet
  
O diagrama a seguir ilustra o caminho de rede assimétrica executado quando a configuração de rede não fornece NAT para solicitações de entrada do Microsoft Cloud pela Internet.
  
1. A solicitação de entrada do Office 365 recupera o endereço IP do ponto de extremidade local de DNS público e envia a solicitação para sua rede de perímetro.

2. Nesta configuração defeituosa, não há NAT de origem configurada ou disponível na rede de perímetro onde o tráfego é enviado resultando no endereço IP de origem real que está sendo usado como o destino de retorno.

  - O servidor em sua rede roteia o tráfego de retorno para o Office 365 por meio de qualquer conexão de rede ExpressRoute disponível.

  - O resultado é um caminho assimétrico para esse fluxo para o Office 365, resultando em uma conexão interrompida.

![Problema de roteamento 1 do ExpressRoute Asymetric](../media/9c210c2a-e0ea-4180-8ede-1bf41746ce7a.png)
  
##### <a name="solution-1a-source-nat"></a>Solução 1a: NAT de origem
  
Simplesmente adicionar um NAT de origem à solicitação de entrada resolve essa rede configurada incorretamente. Neste diagrama:
  
1. A solicitação de entrada continua a entrar na nova rede de perímetro do centro de dados de Jersey. Esse NAT de origem de tempo está disponível.

2. A resposta do servidor volta para o IP associado ao NAT de origem em vez do endereço IP original, resultando na resposta que retorna ao longo do mesmo caminho de rede.

![Solução de roteamento Asymetric do ExpressRoute 1](../media/0e87a155-f8de-48ed-92ac-27367b727a82.png)
  
##### <a name="solution-1b-route-scoping"></a>Solução 1b: escopo de rota
  
Como alternativa, você pode optar por não permitir que os prefixos BGP do ExpressRoute sejam anunciados, removendo o caminho de rede alternativo para esses computadores. Neste diagrama:
  
1. A solicitação de entrada continua a entrar na nova rede de perímetro do centro de dados de Jersey. Desta vez, os prefixos anunciados da Microsoft sobre o circuito ExpressRoute não estão disponíveis para o novo centro de dados de Jersey.

2. A resposta do servidor volta para o IP associado ao endereço IP original sobre a única rota disponível, resultando na resposta que retorna ao longo do mesmo caminho de rede.

![Solução de roteamento do ExpressRoute Asymetric 2](../media/9cb4b2bf-7aa6-487a-bc02-e02af8a979f6.png)
  
#### <a name="problem-2-cloud-to-on-premises-connection-over-expressroute"></a>Problema 2: Cloud para conexão local por meio do ExpressRoute
  
O diagrama a seguir ilustra o caminho de rede assimétrica executado quando a configuração de rede não fornece NAT para solicitações de entrada do Microsoft Cloud sobre o ExpressRoute.
  
1. A solicitação de entrada do Office 365 recupera o endereço IP do DNS e envia a solicitação para sua rede de perímetro.

2. Nesta configuração defeituosa, não há NAT de origem configurada ou disponível na rede de perímetro onde o tráfego é enviado resultando no endereço IP de origem real que está sendo usado como o destino de retorno.

  - O computador em sua rede roteia o tráfego de retorno para o Office 365 por meio de qualquer conexão de rede ExpressRoute disponível.

  - O resultado é uma conexão assimétrica com o Office 365.

![Problema de roteamento 2 do ExpressRoute Asymetric](../media/f6fd155b-bbb7-472a-846e-039a99f09913.png)
  
##### <a name="solution-2-source-nat"></a>Solução 2: NAT de origem
  
Simplesmente adicionar um NAT de origem à solicitação de entrada resolve essa rede configurada incorretamente. Neste diagrama:
  
1. A solicitação de entrada continua a entrar na rede de perímetro da Nova York Data Center. Esse NAT de origem de tempo está disponível.

2. A resposta do servidor volta para o IP associado ao NAT de origem em vez do endereço IP original, resultando na resposta que retorna ao longo do mesmo caminho de rede.

![Solução de roteamento do ExpressRoute Asymetric 3](../media/a5d2b90d-a3ec-4047-afbf-6e6e99f376a7.png)
  
### <a name="paper-verify-that-the-network-design-has-path-symmetry"></a>Papel Verifique se o design de rede tem simetria de caminho

Neste ponto, você precisa verificar em papel que seu plano de implementação oferece simetria de rota para os diferentes cenários nos quais você usará o Office 365. Você identificará a rota de rede específica que deverá ser tomada quando uma pessoa usar recursos diferentes do serviço. Da rede local e do roteamento de WAN, para os dispositivos de perímetro, para o caminho de conectividade; ExpressRoute ou Internet e para a conexão com o ponto de extremidade online.
  
Você precisará fazer isso para todos os serviços de rede do Office 365 que foram identificados anteriormente como serviços que sua organização adotará.
  
Ele ajuda a fazer este documento examinar rotas com uma segunda pessoa. Explique a eles onde cada salto de rede é esperado para obter sua rota seguinte e verifique se você está familiarizado com os caminhos de roteamento. Lembre-se de que o ExpressRoute sempre fornecerá uma rota mais com escopo para os endereços IP do servidor da Microsoft, fornecendo um custo de rota mais baixo do que uma rota padrão da Internet.
  
### <a name="design-client-connectivity-configuration"></a>Design da configuração de conectividade do cliente
<a name="asymmetric"> </a>

![Usando arquivos PAC com o ExpressRoute](../media/7cfa6482-dbae-416a-ae6f-a45e5f4de23b.png)
  
Se você estiver usando um servidor proxy para tráfego de entrada da Internet, precisará ajustar todos os arquivos de configuração de PAC ou clientes para garantir que os computadores clientes da sua rede estejam configurados corretamente para enviar o tráfego ExpressRoute que você deseja para o Office 365 sem usar seu servidor proxy, e o tráfego restante, incluindo o tráfego do Office 365, é enviado para o proxy relevante. Leia nosso guia sobre [Gerenciamento de pontos de extremidade do Office 365](https://aka.ms/manageo365endpoints) para obter exemplos de arquivos PAC.
  
> [!NOTE]
> Os pontos de extremidade mudam com frequência, sempre que semanalmente. Você só deve fazer alterações com base nos serviços e recursos que sua organização adotou para reduzir o número de alterações que você precisará fazer para se manter atualizado. Preste atenção à data de **efetivação** no RSS feed em que as alterações são anunciadas e um registro é mantido por todas as alterações passadas, os endereços IP que são anunciados não podem ser anunciados ou removidos do anúncio, até que a data efetiva seja atingida.
  
## <a name="build-your-deployment-and-testing-procedures"></a>Compilar seus procedimentos de implantação e teste
<a name="testing"> </a>

O plano de implementação deve incluir o planejamento de teste e de reversão. Se sua implementação não estiver funcionando conforme o esperado, o plano deverá ser projetado para afetar o menor número de pessoas antes que os problemas sejam descobertos. Estes são alguns princípios de alto nível que seu plano deve considerar.
  
1. Teste o segmento de rede e a integração do serviço de usuário para minimizar a interrupção.

2. Planejar o teste de rotas com traceroute e conexão TCP a partir de um host conectado à Internet separado.

3. Preferivelmente, o teste de entrada e saída de serviços deve ser feito em uma rede de teste isolada com um locatário do Office 365 de teste.

      - Como alternativa, o teste pode ser executado em uma rede de produção se o cliente ainda não estiver usando o Office 365 ou estiver no piloto.

      - Como alternativa, o teste pode ser executado durante uma interrupção de produção que é reservada somente para teste e monitoramento.

      - Como alternativa, o teste pode ser feito verificando as rotas de cada serviço em cada nó do roteador de camada 3. Esse retorno deve ser usado apenas se nenhum outro teste for possível, pois a falta de testes físicos introduz o risco.

### <a name="build-your-deployment-procedures"></a>Compilar seus procedimentos de implantação

Seus procedimentos de implantação devem ser distribuídos para pequenos grupos de pessoas em estágios para permitir testes antes da implantação em grupos maiores de pessoas. A seguir estão várias maneiras de testar a implantação do ExpressRoute.
  
1. Configure o ExpressRoute com o emparelhamento da Microsoft e faça com que os anúncios de rota sejam encaminhados para um único host somente para fins de teste em estágios.

2. Anuncie rotas à rede ExpressRoute para um único segmento de rede no primeiro e expanda notificações de rota por segmento de rede ou região.

3. Se estiver implantando o Office 365 pela primeira vez, use a implantação de rede ExpressRoute como um piloto para um pequeno número de pessoas.

4. Se estiver usando servidores proxy, você pode configurar um arquivo de PAC de teste como alternativa para direcionar um pequeno número de pessoas para o ExpressRoute com testes e comentários antes de adicionar mais.

Seu plano de implementação deve listar cada um dos procedimentos de implantação que devem ser tomadas ou comandos que precisam ser usados para implantar a configuração de rede. Quando o tempo de interrupção da rede chega a todas as alterações feitas devem ser do plano de implantação gravado, que foi gravado antecipadamente e revisado. Veja nossas orientações sobre a configuração técnica do ExpressRoute.
  
- Atualizando seus registros TXT de SPF se você alterou endereços IP para quaisquer servidores locais que continuarão a enviar emails.

- Atualização de entradas DNS para servidores locais se você tiver alterado endereços IP para acomodar uma nova configuração de NAT.

- Verifique se você assinou o RSS feed para notificações de ponto de extremidade do Office 365 para manter as configurações de roteamento ou proxy.

Depois que a implantação do ExpressRoute estiver concluída, os procedimentos do plano de teste deverão ser executados. Os resultados de cada procedimento devem ser registrados em log. Você deve incluir procedimentos para reverter para o ambiente de produção original no caso de os resultados do plano de teste indicarem que a implementação não foi bem-sucedida.
  
### <a name="build-your-test-procedures"></a>Compilar seus procedimentos de teste

Seus procedimentos de teste devem incluir testes para cada serviço de rede de entrada e saída para o Office 365, que usarão o ExpressRoute e aqueles que não o serão. Os procedimentos devem incluir o teste de cada local de rede exclusivo, incluindo usuários que não estão no local na LAN corporativa.
  
Alguns exemplos de atividades de teste incluem o seguinte.
  
1. Ping do roteador local para o roteador de operador de rede.

2. Validar os 500 + Office 365 e o CRM Online os anúncios de endereço IP são recebidos pelo roteador local.

3. Validar que o NAT de entrada e saída está operando entre o ExpressRoute e a rede interna.

4. Validar que as rotas para o NAT estão sendo anunciadas do seu roteador.

5. Valide se o ExpressRoute aceitou seus prefixos anunciados.

      - Use o cmdlet a seguir para verificar anúncios de emparelhamento:

      ```PowerShell
      Get-AzureRmExpressRouteCircuitRouteTable -DevicePath Primary -ExpressRouteCircuitName TestER -ResourceGroupName RG -PeeringType MicrosoftPeering
      ```

6. Validar seu intervalo de IP de NAT público não é anunciado para a Microsoft por meio de qualquer outro circuito de rede de Internet rota expressa ou pública, a menos que seja um subconjunto específico de um intervalo maior, como no exemplo anterior.

7. Os circuitos do ExpressRoute são emparelhados, validam que as duas sessões de BGP estão sendo executadas.

8. Configure um único host no interior do seu NAT e use Ping, tracert e tcpping para testar a conectividade no novo circuito para o host outlook.office365.com. Como alternativa, você poderia usar uma ferramenta como o Wireshark ou o monitor de rede da Microsoft 3,4 em uma porta espelhada para o MSEE para validar que é possível se conectar ao endereço IP associado ao outlook.office365.com.

9. Testar a funcionalidade de nível de aplicativo para o Exchange Online.

  - Testar o Outlook é capaz de se conectar ao Exchange Online e enviar/receber email.

  - Testar o Outlook é capaz de usar o modo online.

  - Testar a conectividade do smartphone e o recurso de envio/recebimento.

10. Testar a funcionalidade de nível de aplicativo para o SharePoint Online

  - Testar o cliente de sincronização do OneDrive for Business.

  - Testar o SharePoint Online Web Access.

11. Testar a funcionalidade de nível de aplicativo para cenários de chamada do Skype for Business:

  - Ingressar em chamada em conferência como usuário autenticado [convite iniciado pelo usuário final].

  - Convidar o usuário para chamada em conferência [convite enviado da MCU].

  - Ingressar em conferência como usuário anônimo usando o aplicativo Web do Skype for Business.

  - Ingressar na chamada de conexão de computador com fio, telefone IP e dispositivo móvel.

  - Chamada para a chamada de usuário federado para a validação PSTN: a chamada foi concluída, a qualidade da chamada é aceitável, o tempo de conexão é aceitável.

  - Verifique se o status de presença de contatos está atualizado para ambos os membros do locatário e usuários federados.

### <a name="common-problems"></a>Problemas comuns

O roteamento assimétrico é o problema de implementação mais comum. Aqui estão algumas fontes comuns a serem procuradas:
  
- Usando uma topologia de roteamento de rede aberta ou plana sem o NAT de origem em vigor.

- Não usar SNAT para rotear para serviços de entrada através da Internet e de conexões do ExpressRoute.

- Não testar serviços de entrada no ExpressRoute em uma rede de teste antes de implantar amplamente.

## <a name="deploying-expressroute-connectivity-through-your-network"></a>Implantando a conectividade ExpressRoute através da rede
<a name="testing"> </a>

Teste sua implantação para um segmento da rede por vez, distribuindo progressivamente a conectividade para diferentes partes da rede com um plano para reverter para cada novo segmento de rede. Se sua implantação estiver alinhada com uma implantação do Office 365, implante-a primeiro em seus usuários do Office 365 Pilot e estenda-a.
  
Primeiro para o teste e, em seguida, para produção:
  
- Execute as etapas de implantação para habilitar o ExpressRoute.

- Teste a exibição das rotas de rede, conforme o esperado.

- Execute testes em cada serviço de entrada e saída.

- Reversão se você descobrir algum problema.

### <a name="set-up-a-test-connection-to-expressroute-with-a-test-network-segment"></a>Configurar uma conexão de teste para o ExpressRoute com um segmento de rede de teste

Agora que você tem o plano concluído em papel, é hora de testar em uma pequena escala. Neste teste, você estabelecerá uma única conexão ExpressRoute com o emparelhamento da Microsoft para uma sub-rede de teste em sua rede local. Você pode configurar um [locatário do Office 365 de avaliação](https://go.microsoft.com/fwlink/p/?LinkID=403802) com conectividade para e a partir da sub-rede de teste e incluir todos os serviços de saída e de entrada que você usará em produção na sub-rede de teste. Configure o DNS para o segmento de rede de teste e estabeleça todos os serviços de entrada e saída. Execute seu plano de teste e verifique se você está familiarizado com o roteamento de cada serviço e a propagação de rota.
  
### <a name="execute-the-deployment-and-test-plans"></a>Executar os planos de implantação e teste

Ao concluir os itens descritos acima, Confira as áreas que você concluiu e assegure-se de que você e sua equipe as revisaram antes de executar seus planos de implantação e teste.
  
- Lista de serviços de saída e de entrada envolvidos na rede mudar.

- Diagrama de arquitetura de rede global mostrando locais de egresso de Internet e de atendimento ao ExpressRoute.

- Diagrama de roteamento de rede que demonstra os diferentes caminhos de rede usados para cada serviço implantado.

- Um plano de implantação com etapas para implementar as alterações e reverter, se necessário.

- Um plano de teste para testar cada Office 365 e serviço de rede.

- Validação de papel concluída de roteiros de produção para serviços de entrada e saída.

- Um teste concluído em um segmento de rede de teste, incluindo testes de disponibilidade.

Escolha uma janela de paralisação longa o suficiente para ser executada em todo o plano de implantação e o plano de teste, tem um tempo disponível para a solução de problemas e a hora de reverter se necessário.
  
> [!CAUTION]
> Devido à natureza complexa de roteamento através da Internet e do ExpressRoute, é recomendável que o tempo de buffer adicional seja adicionado a essa janela para lidar com a solução de problemas de roteamento complexo.
  
### <a name="configure-qos-for-skype-for-business-online"></a>Configurar a QoS para o Skype for Business Online

A QoS é necessária para obter benefícios de voz e reunião para o Skype for Business online. Você pode configurar a QoS após garantir que a conexão de rede ExpressRoute não bloqueie nenhum outro acesso de serviço do Office 365. A configuração para QoS é descrita no artigo [ExpressRoute e QoS no Skype for Business online](https://support.office.com/article/ExpressRoute-and-QoS-in-Skype-for-Business-Online-20c654da-30ee-4e4f-a764-8b7d8844431d) .
  
## <a name="troubleshooting-your-implementation"></a>Solucionando problemas de implementação
<a name="troubleshooting"> </a>

O primeiro lugar a ser examinado está nas etapas deste guia de implementação, foram perdidas em seu plano de implementação? Volte e execute testes de rede mais pequenos, se possível, para replicar o erro e depurá-lo.
  
Identifique quais serviços de entrada ou de saída falharam durante o teste. Obter especificamente os endereços IP e sub-redes para cada um dos serviços que falharam. Vá em frente e passe o diagrama de topologia de rede no papel e valide o roteamento. Valide especificamente onde o roteamento do ExpressRoute é anunciado, teste o roteamento durante a interrupção, se possível com os rastreamentos.
  
Execute o PSPing com um rastreamento de rede para cada ponto de extremidade do cliente e avalie os endereços IP de origem e destino para validá-los conforme o esperado. Execute o Telnet para qualquer host de email que você expor na porta 25 e verifique se o SNAT está ocultando o endereço IP de origem original se isso for esperado.
  
Tenha em mente que durante a implantação do Office 365 com uma conexão ExpressRoute, você precisará garantir que a configuração de rede para o ExpressRoute seja projetada de forma ideal e também tenha otimizado os outros componentes em sua rede, como computadores cliente. Além de usar este guia de planejamento para solucionar as etapas que você pode ter perdido, também escrevemos um [plano de solução de problemas de desempenho do Office 365](https://support.office.com/article/Performance-troubleshooting-plan-for-Office-365-e241e5d9-b1d8-4f1d-a5c8-4106b7325f8c) .
  
Aqui está um link curto que você pode usar para voltar: [https://aka.ms/implementexpressroute365](https://aka.ms/implementexpressroute365)
  
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
