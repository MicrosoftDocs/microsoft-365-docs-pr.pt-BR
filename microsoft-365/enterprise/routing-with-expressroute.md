---
title: Como rotear com o ExpressRoute para Office 365
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 12/3/2019
audience: ITPro
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
- MOE150
- BCS160
ms.assetid: e1da26c6-2d39-4379-af6f-4da213218408
description: Neste artigo, saiba mais sobre os requisitos de roteamento, circuitos e domínios de roteamento do Azure ExpressRoute para uso com o Office 365.
ms.openlocfilehash: 7201c23777cbf4ca5285736db5a947955a443c51
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46686980"
---
# <a name="routing-with-expressroute-for-office-365"></a>Como rotear com o ExpressRoute para Office 365

*Esse artigo se aplica ao Microsoft 365 Enterprise e ao Office 365 Enterprise.*

Para entender corretamente o tráfego de roteamento para o Office 365 usando o Azure ExpressRoute, você precisará de um bom entendimento dos principais requisitos de roteamento do [ExpressRoute](https://azure.microsoft.com/documentation/articles/expressroute-routing/) e dos circuitos e domínios de roteamento do [ExpressRoute.](https://azure.microsoft.com/documentation/articles/expressroute-circuit-peerings/) Estes são os conceitos básicos para usar o ExpressRoute nos que os clientes do Office 365 dependerão.
  
Alguns dos principais itens nos artigos acima que você precisará entender incluem:
  
- Os circuitos do ExpressRoute não são mapeados para uma infraestrutura física específica, mas são uma conexão lógica feita em um único local de ponto pela Microsoft e por um provedor de pares em seu nome.

- Há um mapeamento 1:1 entre um circuito expressroute e uma chave s do cliente.

- Cada circuito pode dar suporte a duas relações de pares independentes (a paridade privada do Azure e o peering da Microsoft); O Office 365 requer o peering da Microsoft.

- Cada circuito tem uma largura de banda fixa que é compartilhada em todas as relações de paridade.

- Todos os endereços IPv4 públicos e números AS públicos que serão usados para o circuito expressRoute devem ser validados como pertencentes a você ou atribuídos exclusivamente a você pelo proprietário do intervalo de endereços.

- Os circuitos virtuais do ExpressRoute são redundantes globalmente e seguirão as práticas padrão de roteamento BGP. É por isso que recomendamos dois circuitos físicos por saída para o provedor em uma configuração ativa/ativa.

Consulte a [página de Perguntas Frequentes para](https://azure.microsoft.com/documentation/articles/expressroute-faqs/) obter mais informações sobre serviços suportados, custos e detalhes de configuração. Consulte o [artigo locais do ExpressRoute para](https://azure.microsoft.com/documentation/articles/expressroute-locations/) obter informações sobre a lista de provedores de conectividade que oferecem suporte ao peering da Microsoft. Também gravamos uma série de 10 partes do [Azure ExpressRoute](https://channel9.msdn.com/series/aer) para Treinamento do Office 365 no Channel 9 para ajudar a explicar os conceitos mais detalhadamente.
  
## <a name="ensuring-route-symmetry"></a>Garantindo a simetria de rota

Os servidores front-end do Office 365 podem ser acessados na Internet e no ExpressRoute. Esses servidores preferem rotear de volta para os circuitos locais em vez do ExpressRoute quando ambos estão disponíveis. Por isso, existe a possibilidade de assimetria de rota se o tráfego de sua rede preferir rotear pelos circuitos da Internet. Rotas assimétricas são um problema porque dispositivos que executam inspeção de pacotes com estado podem bloquear o tráfego de retorno que segue um caminho diferente dos pacotes de saída seguidos.
  
Independentemente de você iniciar uma conexão com o Office 365 pela Internet ou pela Rota Expressa, a origem deve ser um endereço publicamente encaminhável. Com muitos clientes fazendo o mesmo com a Microsoft, ter endereços privados onde a duplicação é possível entre os clientes não é viável.
  
A seguir estão os cenários em que as comunicações do Office 365 com sua rede local serão iniciadas. Para simplificar o design de rede, recomendamos roteá-los pelo caminho da Internet.
  
- Serviços SMTP, como emails de um locatário do Exchange Online para um host local ou Email do SharePoint Online enviado do SharePoint Online para um host local. O protocolo SMTP é usado mais amplamente na rede da Microsoft do que os prefixos de rota compartilhados por circuitos expressRoute e os servidores SMTP locais de publicidade via ExpressRoute causarão falhas com esses outros serviços.

- ADFS durante a validação de senha para entrar.

- [Implantações híbridas do Exchange Server.](https://technet.microsoft.com/library/jj200581%28v=exchg.150%29.aspx)

- [Pesquisa híbrida federada do SharePoint.](https://technet.microsoft.com/library/dn197174.aspx)

- [BCS híbrido do SharePoint.](https://technet.microsoft.com/library/dn197239.aspx )

- [Federação híbrida](https://technet.microsoft.com/library/jj205403.aspx) do Skype for Business e/ou [Skype for Business.](https://technet.microsoft.com/library/skype-for-business-online-federation-and-public-im-conectivity.aspx)

- [Skype for Business Cloud Connector](https://technet.microsoft.com/library/mt605227.aspx ).

Para a Microsoft rotear de volta para sua rede para esses fluxos de tráfego bi-direcional, as rotas BGP para seus dispositivos locais devem ser compartilhadas com a Microsoft. Ao anunciar prefixos de rota para a Microsoft via ExpressRoute, você deve seguir estas práticas recomendadas:

1) Não anuncie o mesmo prefixo de rota de Endereço IP público para a Internet pública e sobre o ExpressRoute. É altamente recomendável que os anúncios de Prefixo de Rota IP BGP para a Microsoft via ExpressRoute sejam de um intervalo que não é divulgado na Internet. Se isso não for possível devido ao espaço de endereço IP disponível, é essencial garantir que você anunva um intervalo mais específico sobre o ExpressRoute do que qualquer circuito da Internet.

2) Use pools DE IP NAT separados por circuito expressRoute e separados aos de seus circuitos de Internet.

3) Esteja ciente de que qualquer rota anunciada para a Microsoft atrairá o tráfego de rede de qualquer servidor na rede da Microsoft, não apenas aquelas para as quais as rotas são anunciadas para sua rede pela Rota Expressa. Só anuncia rotas para servidores onde os cenários de roteamento são definidos e bem compreendidos por sua equipe. Anunciar prefixos de rota de Endereço IP separados em cada um dos vários circuitos expressRoute da rede.
  
## <a name="deciding-which-applications-and-features-route-over-expressroute"></a>Decidir quais aplicativos e recursos serão roteado pelo ExpressRoute

Ao configurar uma relação de paridade usando o domínio de roteamento de mesmo nível da Microsoft e for aprovado para o acesso apropriado, você poderá ver todos os serviços de PaaS e SaaS disponíveis no ExpressRoute. Os serviços do Office 365 projetados para o ExpressRoute podem ser gerenciados com comunidades [BGP ou](https://aka.ms/bgpexpressroute365) filtros [de rota.](https://docs.microsoft.com/azure/expressroute/how-to-routefilter-portal)
  
Outros aplicativos, como o Vídeo do Office 365, são aplicativos do Office 365; No entanto, o Vídeo do Office 365 é composto por três componentes diferentes, o portal, o serviço de streaming e a rede de distribuição de conteúdo. O portal reside no SharePoint Online, o serviço de streaming reside nos Serviços de Mídia do Azure e a rede de distribuição de conteúdo reside na CDN do Azure. A tabela a seguir descreve esses componentes.

|**Componente**|**Aplicativo subjacente**|**Incluído na Comunidade BGP do SharePoint Online?**|**Usar**|
|:-----|:-----|:-----|:-----|
|Portal de vídeo do Office 365  <br/> |SharePoint Online  <br/> |Sim  <br/> |Configuração, carregamento  <br/> |
|Serviço de streaming de vídeo do Office 365  <br/> |Serviços de Mídia do Azure  <br/> |Não  <br/> |Serviço de streaming, usado no caso de o vídeo não estar disponível na CDN  <br/> |
|Rede de distribuição de conteúdo de vídeo do Office 365  <br/> |Azure CDN  <br/> |Não  <br/> |Origem principal do download/streaming de vídeo. [Saiba mais sobre a rede de vídeo do Office 365.](https://support.office.com/article/Office-365-Video-networking-Frequently-Asked-Questions-FAQ-2bed67a1-4052-49ff-a4ce-b7e6530eb98e)  <br/> |

Cada um dos recursos do Office 365 que estão disponíveis usando o peering da Microsoft está listado no artigo de pontos de extremidade do [Office 365](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2) por tipo de aplicativo e FQDN. O motivo para usar o FQDN nas tabelas é permitir que os clientes gerenciem o tráfego usando arquivos PAC ou outras configurações de proxy. Consulte nosso guia para gerenciar pontos de extremidade do [Office 365,](https://aka.ms/manageo365endpoints) por exemplo, arquivos PAC.
  
Em algumas situações, utilizamos um domínio curinga em que um ou mais sub-FQDNs são anunciados de forma diferente do domínio curinga de nível superior. Isso geralmente acontece quando o curinga representa uma longa lista de servidores que são todos anunciados para o ExpressRoute e a Internet, enquanto um pequeno subconjunto de destinos é anunciado apenas na Internet ou o inverso. Consulte as tabelas abaixo para entender onde estão as diferenças.
  
Esta tabela exibe os FQDNs curinga anunciados para a Internet e o Azure ExpressRoute junto com os sub-FQDNs anunciados somente na Internet.

|**Domínio curinga anunciado nos circuitos ExpressRoute e Internet**|**Sub-FQDN anunciado somente em circuitos da Internet**|
|:-----|:-----|
|\*.microsoftonline.com  <br/> |click.email.microsoftonline.com  <br/> portal.microsoftonline.com  <br/> provisioningapi.microsoftonline.com  <br/> adminwebservice.microsoftonline.com  <br/> |
|\*.officeapps.live.com  <br/> |nexusRules.officeapps.live.com  <br/> nexus.officeapps.live.com  <br/> odc.officeapps.live.com  <br/> odc.officeapps.live.com  <br/> cdn.odc.officeapps.live.com  <br/> ols.officeapps.live.com  <br/> ocsredir.officeapps.live.com  <br/> ocws.officeapps.live.com  <br/> ocsa.officeapps.live.com  <br/> |

Normalmente, os arquivos PAC se destinam a enviar solicitações de rede aos pontos de extremidade anunciados do ExpressRoute diretamente para o circuito e todas as outras solicitações de rede para seu proxy. Se você estiver configurando um arquivo PAC assim, redação do arquivo PAC na seguinte ordem:
  
1. Inclua os sub-FQDNs da coluna dois na tabela acima, na parte superior do arquivo PAC, enviando o tráfego em direção ao seu proxy. Nós fizemos um arquivo PAC de exemplo para você usar em nosso artigo sobre como gerenciar pontos de extremidade do [Office 365.](https://aka.ms/manageexpressroute365)

2. Inclua todos os FQDNs marcados [](https://aka.ms/o365endpoints) para o ExpressRoute neste artigo abaixo da primeira seção, enviando o tráfego diretamente para o circuito do ExpressRoute.

3. Inclua quaisquer outros pontos de extremidade de rede ou regras abaixo dessas duas entradas, enviando o tráfego em direção ao seu proxy.

Esta tabela exibe os domínios curinga que são anunciados nos circuitos da Internet apenas junto com os sub-FQDNs anunciados para o Azure ExpressRoute e os circuitos da Internet. Para o arquivo PAC acima, os FQDNs na coluna dois da tabela abaixo estão listados como anunciados para o ExpressRoute no link referenciado, o que significa que eles seriam incluídos no segundo grupo de entradas no arquivo.

|**Domínio curinga anunciado somente em circuitos da Internet**|**Sub-FQDN anunciado nos circuitos ExpressRoute e Internet**|
|:-----|:-----|
|\*.office.com  <br/> |\*.outlook.office.com  <br/> home.office.com  <br/> outlook.office.com  <br/> portal.office.com  <br/> <div style="display: inline">www.office.com</div>  <br/> |
|\*.office.net  <br/> |agent.office.net  <br/> |
|\*.office365.com  <br/> |outlook.office365.com  <br/> smtp.office365.com  <br/> |
|\*.outlook.com  <br/> |\*.protection.outlook.com  <br/> \*.mail.protection.outlook.com  <br/> autodiscover- \<tenant\> .outlook.com  <br/> |
|\*.windows.net  <br/> |login.windows.net  <br/> |

## <a name="routing-office-365-traffic-over-the-internet-and-expressroute"></a>Roteamento do tráfego do Office 365 pela Internet e Pela Rota Expressa

Para rotear para o aplicativo do Office 365 de sua escolha, você precisará determinar vários fatores principais.
  
1. A largura de banda que o aplicativo exigirá. A amostragem do uso existente é o único método confiável para determinar isso em sua organização.

2. De qual(s) saída(s) você deseja que o tráfego de rede saia da rede. Você deve planejar minimizar a latência de rede para conectividade com o Office 365, pois isso afetará o desempenho. Como o Skype for Business usa voz e vídeo em tempo real, ele é particularmente suscetível a uma latência de rede ruim.

3. Se você quiser que todos ou um subconjunto de seus locais de rede aproveitem o ExpressRoute.

4. De quais locais o provedor de rede escolhido oferece o ExpressRoute.

Depois de determinar as respostas para essas perguntas, você pode provisionar um circuito expressroute que atenda às necessidades de largura de banda e local. Para obter mais assistência de planejamento de rede, consulte o guia de ajuste de rede do [Office 365](https://aka.ms/tune) e o estudo de caso sobre como a Microsoft lida com o planejamento [de desempenho de rede.](https://aka.ms/tunemsit)
  
### <a name="example-1-single-geographic-location"></a>Exemplo 1: Localização geográfica única
  
Este exemplo é um cenário para uma empresa fictícia chamada Trey Research que tem uma única localização geográfica.
  
Os funcionários da Trey Research só têm permissão para se conectar aos serviços e sites na Internet que o departamento de segurança explicitamente permite no par de proxies de saída que ficam entre a rede corporativa e seu ISP.
  
Trey Research planeja usar o Azure ExpressRoute para Office 365 e reconhece que parte do tráfego, como o tráfego destinado a redes de distribuição de conteúdo, não poderá rotear pela conexão do ExpressRoute para Office 365. Como todo o tráfego já é circulado para os dispositivos proxy por padrão, essas solicitações continuarão a funcionar como antes. Depois que Trey Research determinar que eles podem atender aos requisitos de roteamento do Azure ExpressRoute, eles continuarão a criar um circuito, configurarão o roteamento e vinculam o novo circuito do ExpressRoute a uma rede virtual. Quando a configuração fundamental do Azure ExpressRoute for aplicada, Trey Research usará o arquivo PAC do [#2](https://aka.ms/manageo365endpoints#ID0EACAAA=2._Proxies) que publicamos para rotear o tráfego com dados específicos do cliente pela Rota Expressa direta para conexões do Office 365.
  
Conforme mostrado no diagrama a seguir, Trey Research é capaz de satisfazer o requisito de rotear o tráfego do Office 365 pela Internet e um subconjunto de tráfego pela Rota Expressa usando uma combinação de alterações de configuração de proxy de saída e roteamento.
  
1. Usando o [#2 PAC](https://aka.ms/manageo365endpoints#ID0EACAAA=2._Proxies) que publicamos para rotear o tráfego por meio de um ponto de saída de Internet separado para o Azure ExpressRoute para o Office 365.

2. Os clientes são configurados com uma rota padrão para os proxies de Trey Research.

Neste cenário de exemplo, Trey Research está usando um dispositivo de proxy de saída. Da mesma forma, os clientes que não estão usando o Azure ExpressRoute para Office 365 podem querer usar essa técnica para rotear o tráfego com base no custo de inspecionar o tráfego destinado a pontos de extremidade de alto volume conhecidos.
  
Os FQDNs de volume mais alto para o Exchange Online, o SharePoint Online e o Skype for Business Online são os seguintes:
  
![Rede de borda do cliente do ExpressRoute](../media/dab8cc42-b1d6-46d6-b2f6-d70f9e16d5ea.png)
  
- outlook.office365.com, outlook.office.com

- \<tenant-name\>.sharepoint.com, \<tenant-name\> -my.sharepoint.com, \<tenant-name\> - \<app\> .sharepoint.com

- \*. Lync.com os intervalos de IP para tráfego não TCP

- \*broadcast.officeapps.live.com, \* excel.officeapps.live.com, \* onenote.officeapps.live.com, \* powerpoint.officeapps.live.com, \* view.officeapps.live.com, \* visio.officeapps.live.com, \* word-edit.officeapps.live.com, \* word-view.officeapps.live.com, office.live.com

Saiba mais sobre como implantar e gerenciar configurações de proxy no [Windows 8](https://blogs.technet.com/b/deploymentguys/archive/2013/05/08/windows-8-supporting-proxy-services-with-static-configurations-web-hosted-pac-files-and-domain-policy-configured-proxy.aspx) e garantir que o [Office 365](https://blogs.technet.com/b/onthewire/archive/2014/03/28/ensuring-your-office-365-network-connection-isn-t-throttled-by-your-proxy.aspx)não seja acelerada por seu proxy.
  
Com um único circuito expressRoute, não há alta disponibilidade para Trey Research. Caso haja falha no par redundante de dispositivos de borda trey que estão atendendo a conectividade expressRoute, não há um circuito expressRoute adicional para o failover. Isso deixa Trey Research em dúvida, uma vez que fazer o failing over para a Internet exigirá uma nova configuração manual e, em alguns casos, novos endereços IP. Se Trey quiser adicionar alta disponibilidade, a solução mais simples é adicionar circuitos expressRoute adicionais para cada local e configurar os circuitos de maneira ativa/ativa.
  
## <a name="routing-expressroute-for-office-365-with-multiple-locations"></a>Roteamento do ExpressRoute para Office 365 com vários locais

O último cenário, roteamento do tráfego do Office 365 pela Rota Expressa é a base para uma arquitetura de roteamento ainda mais complexa. Independentemente do número de locais, do número de continentes em que esses locais existem, do número de circuitos da Rota Expressa e assim por diante, será necessário ser capaz de rotear algum tráfego para a Internet e algum tráfego pela Rota Expressa.
  
As perguntas adicionais que devem ser respondidas para clientes com vários locais em várias regiões geográficas incluem:
  
1. Você precisa de um circuito expressroute em todos os locais? Se você estiver usando o Skype for Business Online ou estiver preocupado com a sensibilidade de latência para o SharePoint Online ou o Exchange Online, um par redundante de circuitos ativos/ativos do ExpressRoute é recomendado em cada local. Consulte o guia de conectividade de rede e qualidade de mídia do Skype for Business para obter mais detalhes.

2. Se um circuito do ExpressRoute não estiver disponível em uma determinada região, como o tráfego destinado do Office 365 deve ser roteado?

3. Qual é o método preferencial para consolidar o tráfego no caso de redes com muitos locais pequenos?

Cada um deles apresenta um desafio exclusivo que exige que você avalie sua própria rede, bem como as opções disponíveis da Microsoft.

|**Considerações**|**Componentes de rede a avaliar**|
|:-----|:-----|
|Circuitos em mais de um local  <br/> |Recomendamos um mínimo de dois circuitos configurados de maneira ativa/ativa.  <br/> As necessidades de custo, latência e largura de banda devem ser comparadas.  <br/> Use o custo de rota BGP, arquivos PAC e NAT para gerenciar o roteamento com vários circuitos.  <br/> |
|Roteamento de locais sem um circuito ExpressRoute  <br/> |Recomendamos saída e resolução DNS o mais próximo da pessoa que inicia a solicitação para o Office 365.  <br/> O encaminhamento DNS pode ser usado para permitir que escritórios remotos descubram o ponto de extremidade apropriado.  <br/> Os clientes no escritório remoto devem ter uma rota disponível que fornece acesso ao circuito expressRoute.  <br/> |
|Consolidação de escritório pequeno  <br/> |A largura de banda disponível e o uso de dados devem ser cuidadosamente comparados.  <br/> |

> [!NOTE]
> A Microsoft preferirá o ExpressRoute pela Internet se a rota estiver disponível, independentemente da localização física.
  
Cada uma dessas considerações deve ser levada em consideração para cada rede exclusiva. Veja um exemplo abaixo.
  
### <a name="example-2-multi-geographic-locations"></a>Exemplo 2: localizações multi-geográficas
  
Este exemplo é um cenário para uma empresa fictícia chamada Humongous Insurance que tem várias localizações geográficas.
  
A Humongous Insurance está geograficamente dispersa com escritórios em todo o mundo. Eles querem implementar o Azure ExpressRoute para Office 365 para manter a maior parte do tráfego do Office 365 em conexões diretas de rede. A Humongous Insurance também tem escritórios em dois continentes adicionais. Os funcionários no escritório remoto onde o ExpressRoute não é viável precisarão rotear de volta para uma ou ambas as instalações principais para usar uma conexão expressRoute.
  
O princípio principal é obter o tráfego destinado do Office 365 para um datacenter da Microsoft o mais rápido possível. Neste exemplo, Humongous Insurance deve decidir se seus escritórios remotos devem ser encaminhados pela Internet para chegar a um datacenter da Microsoft o mais rápido possível ou se seus escritórios remotos devem ser encaminhados por uma rede interna para chegar a um datacenter da Microsoft por uma conexão ExpressRoute o mais rápido possível.
  
Os datacenters, as redes e a arquitetura de aplicativos da Microsoft foram projetados para levar comunicações globalmente diferentes e ser atendidos da maneira mais eficiente possível. Esta é uma das maiores redes do mundo. As solicitações destinadas ao Office 365 que permanecem em redes de clientes por mais tempo do que o necessário não poderão tirar proveito dessa arquitetura.
  
Na situação da Humongous Insurance, eles devem continuar dependendo dos aplicativos que pretendem usar no ExpressRoute. Por exemplo, se eles são clientes do Skype for Business Online ou planejam aproveitar a conectividade do ExpressRoute ao se conectar a reuniões externas do Skype for Business Online, o design recomendado no guia de conectividade de rede e qualidade de mídia do Skype for Business Online é provisionar um circuito expressroute adicional para o terceiro local. Isso pode ser mais caro de uma perspectiva de rede; No entanto, o roteamento de solicitações de um continente para outro antes da entrega a um datacenter da Microsoft pode causar uma experiência ruim ou inutilizável durante reuniões e comunicações do Skype for Business Online.
  
Se a Humongous Insurance não estiver usando ou não planeja aproveitar o Skype for Business Online de forma alguma, o roteamento do tráfego de rede destinado do Office 365 de volta a um continente com uma conexão expressRoute pode ser viável, mas pode causar latência desnecessária ou congestionamento TCP. Em ambos os casos, é recomendável rotear o tráfego destinado à Internet para a Internet no site local para aproveitar as redes de distribuição de conteúdo das quais o Office 365 depende.
  
![ExpressRoute multi-região geográfica](../media/98fdd883-2c5a-4df7-844b-bd28cd0b9f50.png)
  
Quando Humongous Insurance está planejando sua estratégia multi-geográfica, há várias coisas a considerar em torno do tamanho do circuito, número de circuitos, failover e assim por diante.
  
Com o ExpressRoute em um único local com várias regiões tentando usar o circuito, a Humongous Insurance deseja garantir que as conexões com o Office 365 do escritório remoto sejam enviadas para o datacenter do Office 365 mais próximo da sede e recebidas pelo local da sede. Para fazer isso, a Humongous Insurance implementa o encaminhamento de DNS para reduzir o número de viagens de ida e volta e as consultas de DNS necessárias para estabelecer a conexão apropriada com o ambiente do Office 365 mais próximo ao ponto de saída da Internet da sede. Isso impede que o cliente resolva um servidor front-end local e garante que o servidor front-end ao qual a pessoa se conecta está perto da sede em que a Humongous Insurance está se conectando com a Microsoft. Você também pode aprender [a atribuir um encaminhador condicional para um nome de domínio.](https://technet.microsoft.com/library/Cc794735%28v=WS.10%29.aspx)
  
Nesse cenário, o tráfego do escritório remoto resolveria a infraestrutura de front-end do Office 365 na América do Norte e aproveitaria o Office 365 para se conectar aos servidores de back-end de acordo com a arquitetura do aplicativo do Office 365. Por exemplo, o Exchange Online encerraria a conexão na América do Norte e esses servidores front-end se conectariam ao servidor de caixa de correio de back-end onde quer que o locatário residesse. Todos os serviços têm um serviço de porta frontal amplamente distribuído composto por destinos unicast e anycast.
  
Se Humongous tiver escritórios principais em vários continentes, um mínimo de dois circuitos ativos/ativos por região será recomendado para reduzir a latência para aplicativos confidenciais, como o Skype for Business Online. Se todos os escritórios estão em um único continente ou não estão usando colaboração em tempo real, ter um ponto de saída consolidado ou distribuído é uma decisão específica do cliente. Quando vários circuitos estão disponíveis, o roteamento BGP garantirá o failover caso um único circuito se torne indisponível.
  
Saiba mais sobre configurações de [roteamento de exemplo](https://azure.microsoft.com/documentation/articles/expressroute-config-samples-routing/) e [https://azure.microsoft.com/documentation/articles/expressroute-config-samples-nat/](https://azure.microsoft.com/documentation/articles/expressroute-config-samples-nat/) .
  
## <a name="selective-routing-with-expressroute"></a>Roteamento seletivo com Rota Expressa

O roteamento seletivo com o ExpressRoute pode ser necessário por vários motivos, como testes, a implantação do ExpressRoute em um subconjunto de usuários. Há várias ferramentas que os clientes podem usar para rotear seletivamente o tráfego de rede do Office 365 pelo ExpressRoute:
  
1. **Filtragem/segregação** de rota - permitindo que o BGP roteie para o Office 365 pela Rota Expressa para um subconjunto de suas sub-redes ou roteadores. Isso encaminha seletivamente por segmento de rede do cliente ou local físico do escritório. Isso é comum para o lançamento escalonado do ExpressRoute para Office 365 e é configurado em seus dispositivos BGP.

2. **Arquivos/URLs pac** - direcionando o tráfego de rede destinado do Office 365 para FQDNs específicos para roteamento em um caminho específico. Isso encaminha seletivamente por computador cliente conforme identificado pela [implantação de arquivo PAC.](https://aka.ms/manageo365endpoints#ID0EACAAA=2._Proxies)

3. **Filtragem de rota**  -  [Os filtros](https://docs.microsoft.com/azure/expressroute/how-to-routefilter-portal) de rota são uma maneira de consumir um subconjunto de serviços com suporte por meio do peering da Microsoft.

4. **Comunidades BGP** - a filtragem baseada em marcas da comunidade [BGP](https://aka.ms/bgpexpressroute365) permite que um cliente determine quais aplicativos do Office 365 atravessarão o ExpressRoute e qual atravessará a Internet.

Aqui está um link curto que você pode usar para voltar: [https://aka.ms/erorouting](https://aka.ms/erorouting)
  
## <a name="related-topics"></a>Tópicos Relacionados

[Avaliando a conectividade de rede do Office 365](assessing-network-connectivity.md)
  
[Microsoft Azure ExpressRoute para Office 365](azure-expressroute.md)
  
[Como gerenciar o ExpressRoute para a conectividade do Office 365](managing-expressroute-for-connectivity.md)
  
[Planejamento de rede com o ExpressRoute para Office 365](network-planning-with-expressroute.md)
  
[Como implementar o ExpressRoute para Office 365](implementing-expressroute.md)
  
[Qualidade da mídia e desempenho de conectividade de rede no Skype for Business Online](https://support.office.com/article/5fe3e01b-34cf-44e0-b897-b0b2a83f0917)
  
[Como otimizar a sua rede para o Skype for Business Online](https://support.office.com/article/b363bdca-b00d-4150-96c3-ec7eab5a8a43)
  
[ExpressRoute e QoS no Skype for Business Online](https://support.office.com/article/20c654da-30ee-4e4f-a764-8b7d8844431d)
  
[Fluxo de chamadas usando o ExpressRoute](https://support.office.com/article/413acb29-ad83-4393-9402-51d88e7561ab)
  
[Usando comunidades BGP no ExpressRoute para cenários do Office 365](bgp-communities-in-expressroute.md)
  
[Ajuste de desempenho do Office 365 usando linhas de base e histórico de desempenho](performance-tuning-using-baselines-and-history.md)
  
[Plano de solução de problemas de desempenho do Office 365](performance-troubleshooting-plan.md)
  
[URLs e intervalos de endereços IP do Office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)
  
[Rede do Office 365 e ajuste de desempenho](network-planning-and-performance.md)
