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
description: Neste artigo, saiba mais sobre os requisitos de roteamento do Azure ExpressRoute, circuitos e domínios de roteamento para uso com o Office 365.
ms.openlocfilehash: 7201c23777cbf4ca5285736db5a947955a443c51
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46686980"
---
# <a name="routing-with-expressroute-for-office-365"></a>Como rotear com o ExpressRoute para Office 365

*Esse artigo se aplica ao Microsoft 365 Enterprise e ao Office 365 Enterprise.*

Para entender corretamente o tráfego de roteamento para o Office 365 usando o Azure ExpressRoute, você precisará de uma compreensão dos [requisitos de roteamento](https://azure.microsoft.com/documentation/articles/expressroute-routing/) principal do expressroute e dos [domínios de roteamento e circuitos do expressroute](https://azure.microsoft.com/documentation/articles/expressroute-circuit-peerings/). Eles formam os conceitos básicos para usar o ExpressRoute em que os clientes do Office 365 confiarão.
  
Alguns dos principais itens nos artigos acima que você precisa entender incluem:
  
- Os circuitos do ExpressRoute não são mapeados para infraestrutura física específica, mas são uma conexão lógica feita em um único local de emparelhamento pela Microsoft e um provedor de emparelhamento em seu nome.

- Há um mapeamento 1:1 entre um circuito ExpressRoute e uma chave s do cliente.

- Cada circuito pode suportar duas relações de emparelhamento independentes (emparelhamento privado do Azure e emparelhamento da Microsoft); O Office 365 requer o emparelhamento da Microsoft.

- Cada circuito tem uma largura de banda fixa que é compartilhada em todas as relações de emparelhamento.

- Todos os endereços IPv4 públicos e públicos como números que serão usados para o circuito ExpressRoute devem ser validados como pertencentes a você ou atribuídos exclusivamente a você pelo proprietário do intervalo de endereços.

- Os circuitos virtuais do ExpressRoute são redundantes globalmente e seguirão as práticas padrão de roteamento BGP. Por isso, recomendamos dois circuitos físicos por egresso para seu provedor em uma configuração ativa/ativa.

Consulte a [página perguntas frequentes](https://azure.microsoft.com/documentation/articles/expressroute-faqs/) para obter mais informações sobre os serviços com suporte, custos e detalhes de configuração. Consulte o [artigo locais de ExpressRoute](https://azure.microsoft.com/documentation/articles/expressroute-locations/) para obter informações sobre a lista de provedores de conectividade que oferecem suporte a emparelhamento da Microsoft. Também registramos uma série [de treinamentos do Azure ExpressRoute para Office 365](https://channel9.msdn.com/series/aer) no canal 9 para ajudar a explicar os conceitos com mais detalhes.
  
## <a name="ensuring-route-symmetry"></a>Garantindo a simetria da rota

Os servidores front-end do Office 365 estão acessíveis na Internet e no ExpressRoute. Esses servidores preferem rotear de volta para o local sobre os circuitos do ExpressRoute quando ambos estiverem disponíveis. Por causa disso, há uma possibilidade de a rota assimetria se o tráfego de sua rede preferir rotear seus circuitos de Internet. As rotas assimétricas são um problema porque os dispositivos que executam a inspeção de pacote com estado podem bloquear o tráfego de retorno que segue um caminho diferente dos pacotes de saída seguidos.
  
Independentemente de você iniciar uma conexão com o Office 365 pela Internet ou o ExpressRoute, a origem deve ser um endereço roteável publicamente. Com muitos clientes emparelhamento direto com a Microsoft, ter endereços privados em que a duplicação é possível entre os clientes não é viável.
  
Estes são os cenários em que as comunicações do Office 365 para a sua rede local serão iniciadas. Para simplificar o design de sua rede, recomendamos o roteamento desses caminhos através da Internet.
  
- Serviços SMTP, como email de um locatário do Exchange Online para um host local ou email do SharePoint Online enviados do SharePoint Online para um host local. O protocolo SMTP é usado mais amplamente dentro da rede da Microsoft do que os prefixos de rota compartilhados por circuitos do ExpressRoute e o anúncio de servidores SMTP no local sobre o ExpressRoute causará falhas com esses outros serviços.

- ADFS durante a validação de senha para entrada.

- [Implantações híbridas do Exchange Server](https://technet.microsoft.com/library/jj200581%28v=exchg.150%29.aspx).

- [Pesquisa híbrida federada do SharePoint](https://technet.microsoft.com/library/dn197174.aspx).

- [BCS do SharePoint híbrido](https://technet.microsoft.com/library/dn197239.aspx ).

- Federação [híbrida do Skype for Business](https://technet.microsoft.com/library/jj205403.aspx) e/ou [Skype for Business](https://technet.microsoft.com/library/skype-for-business-online-federation-and-public-im-conectivity.aspx).

- [Skype for Business Cloud Connector](https://technet.microsoft.com/library/mt605227.aspx ).

Para que a Microsoft encaminhe de volta à sua rede para esses fluxos de tráfego bidirecional, as rotas BGP para seus dispositivos locais devem ser compartilhadas com a Microsoft. Ao anunciar os prefixos de rota para a Microsoft no ExpressRoute, você deve seguir estas práticas recomendadas:

1) Não Anuncie o mesmo prefixo de rota de endereço IP público para a Internet pública e pelo ExpressRoute. É altamente recomendável que o prefixo de rota IP BGP para o Microsoft over ExpressRoute seja de um intervalo que não é anunciado para a Internet. Se isso não for possível, devido ao espaço de endereço IP disponível, será essencial garantir que você anuncie um intervalo mais específico acima do ExpressRoute do que os circuitos da Internet.

2) Use pools de IP NAT separados por circuito ExpressRoute e separado para os seus circuitos de Internet.

3) Lembre-se de que qualquer rota anunciada para a Microsoft atrai o tráfego de rede de qualquer servidor na rede da Microsoft, não apenas aqueles para os quais as rotas são anunciadas para a sua rede pelo ExpressRoute. Apenas anunciar rotas para servidores em que os cenários de roteamento são definidos e bem compreendidos pela equipe. Anunciar prefixos de rota de endereço IP separado em cada um dos vários circuitos do ExpressRoute da sua rede.
  
## <a name="deciding-which-applications-and-features-route-over-expressroute"></a>Decidindo quais aplicativos e recursos direcionam o ExpressRoute

Ao configurar um relacionamento de emparelhamento usando o domínio de roteamento de emparelhamento da Microsoft e são aprovados para o acesso apropriado, você poderá ver todos os serviços de PaaS e SaaS disponíveis no ExpressRoute. Os serviços do Office 365 projetados para o ExpressRoute podem ser gerenciados com [comunidades de BGP](https://aka.ms/bgpexpressroute365) ou [filtros de rota](https://docs.microsoft.com/azure/expressroute/how-to-routefilter-portal).
  
Outros aplicativos, como o vídeo do Office 365, são um aplicativo do Office 365; no entanto, o vídeo do Office 365 é composto por três componentes diferentes, o portal, o serviço de streaming e a rede de distribuição de conteúdo. O portal reside no SharePoint Online, o serviço de streaming reside nos serviços de mídia do Azure e a rede de distribuição de conteúdo reside dentro da CDN do Azure. A tabela a seguir descreve esses componentes.

|**Componente**|**Aplicativo subjacente**|**Incluído na Comunidade BGP do SharePoint Online?**|**Usar**|
|:-----|:-----|:-----|:-----|
|Portal de vídeo do Office 365  <br/> |SharePoint Online  <br/> |Sim  <br/> |Configuração, carregar  <br/> |
|Serviço de streaming de vídeo do Office 365  <br/> |Serviços de Mídia do Azure  <br/> |Não  <br/> |Serviço de streaming, usado no evento o vídeo não está disponível na CDN  <br/> |
|Rede de distribuição de conteúdo de vídeo do Office 365  <br/> |CDN do Azure  <br/> |Não  <br/> |Fonte principal de download/streaming de vídeo. [Saiba mais sobre a rede de vídeo do Office 365](https://support.office.com/article/Office-365-Video-networking-Frequently-Asked-Questions-FAQ-2bed67a1-4052-49ff-a4ce-b7e6530eb98e).  <br/> |

Cada um dos recursos do Office 365 que estão disponíveis usando o emparelhamento da Microsoft estão listados no [artigo de pontos de extremidade do office 365](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2) por tipo de aplicativo e FQDN. O motivo para usar o FQDN nas tabelas é permitir que os clientes gerenciem o tráfego usando arquivos PAC ou outras configurações de proxy, consulte nosso guia para [gerenciar pontos de extremidade do Office 365](https://aka.ms/manageo365endpoints) para arquivos PAC de exemplo.
  
Em algumas situações, utilizamos um domínio curinga onde um ou mais subfqdnss são anunciados de forma diferente do domínio curinga de nível superior. Isso geralmente ocorre quando o caractere curinga representa uma longa lista de servidores que são todos anunciadas para o ExpressRoute e a Internet, enquanto um pequeno subconjunto de destinos é anunciado apenas para a Internet ou vice-versa. Confira as tabelas abaixo para entender onde estão as diferenças.
  
Esta tabela exibe os FQDNs curinga que são anunciados para a Internet e para o Azure ExpressRoute junto com os subfqdns que são anunciados apenas para a Internet.

|**Domínio curinga anunciado para o ExpressRoute e circuitos da Internet**|**Subfqdn anunciado somente para circuitos da Internet**|
|:-----|:-----|
|\*. microsoftonline.com  <br/> |click.email.microsoftonline.com  <br/> portal.microsoftonline.com  <br/> provisioningapi.microsoftonline.com  <br/> adminwebservice.microsoftonline.com  <br/> |
|\*. officeapps.live.com  <br/> |nexusRules.officeapps.live.com  <br/> nexus.officeapps.live.com  <br/> odc.officeapps.live.com  <br/> odc.officeapps.live.com  <br/> cdn.odc.officeapps.live.com  <br/> ols.officeapps.live.com  <br/> ocsredir.officeapps.live.com  <br/> ocws.officeapps.live.com  <br/> ocsa.officeapps.live.com  <br/> |

Normalmente, os arquivos de PAC se destinam a enviar solicitações de rede para pontos de extremidade anunciadas do ExpressRoute diretamente para o circuito e todas as outras solicitações de rede para o seu proxy. Se você estiver configurando um arquivo de PAC como este, redija o arquivo de PAC na seguinte ordem:
  
1. Inclua os subfqdns da coluna dois na tabela acima, na parte superior do seu arquivo de PAC, enviando o tráfego para o proxy. Criamos um arquivo de exemplo de PAC para você usar em nosso artigo sobre [Gerenciamento de pontos de extremidade do Office 365](https://aka.ms/manageexpressroute365).

2. Inclua todos os FQDNs marcados para o ExpressRoute neste [artigo](https://aka.ms/o365endpoints) abaixo da primeira seção, enviando o tráfego diretamente para o seu circuito ExpressRoute.

3. Inclua outros pontos de extremidade de rede ou regras abaixo dessas duas entradas, enviando o tráfego para o proxy.

Esta tabela exibe os domínios curinga que são anunciados para circuitos da Internet somente junto com os subfqdnss anunciados para o Azure ExpressRoute e circuitos de Internet. Para o seu arquivo de PAC acima, os FQDNs na coluna dois da tabela abaixo são listados como anunciados para o ExpressRoute no link referenciado, o que significa que eles seriam incluídos no segundo grupo de entradas no arquivo.

|**Domínio curinga anunciado somente para circuitos da Internet**|**Subfqdn anunciado para o ExpressRoute e circuitos da Internet**|
|:-----|:-----|
|\*. office.com  <br/> |\*. outlook.office.com  <br/> home.office.com  <br/> outlook.office.com  <br/> portal.office.com  <br/> <div style="display: inline">www.office.com</div>  <br/> |
|\*. office.net  <br/> |agent.office.net  <br/> |
|\*. office365.com  <br/> |outlook.office365.com  <br/> smtp.office365.com  <br/> |
|\*. outlook.com  <br/> |\*. protection.outlook.com  <br/> \*. mail.protection.outlook.com  <br/> descoberta automática- \<tenant\> . Outlook.com  <br/> |
|\*. windows.net  <br/> |login.windows.net  <br/> |

## <a name="routing-office-365-traffic-over-the-internet-and-expressroute"></a>Roteamento do tráfego do Office 365 pela Internet e ExpressRoute

Para rotear para o aplicativo do Office 365 de sua escolha, você precisará determinar vários fatores chave.
  
1. Quanta largura de banda o aplicativo precisará. A amostragem do uso existente é o único método confiável para determinar isso em sua organização.

2. Que local (es) de egresso você deseja que o tráfego de rede deixe sua rede. Você deve planejar minimizar a latência de rede para conectividade com o Office 365, pois isso afetará o desempenho. Como o Skype for Business usa voz e vídeo em tempo real, é particularmente suscetível à latência de rede ruim.

3. Se quiser que todos ou um subconjunto de seus locais de rede Aproveite o ExpressRoute.

4. De quais locais o provedor de rede escolhido oferece o ExpressRoute.

Depois de determinar as respostas a essas perguntas, você poderá provisionar um circuito ExpressRoute que atenda às necessidades de largura de banda e local. Para obter mais assistência de planejamento de rede, consulte o [Guia de ajuste de rede do Office 365](https://aka.ms/tune) e o [estudo de caso sobre como a Microsoft trata o planejamento de desempenho de rede](https://aka.ms/tunemsit).
  
### <a name="example-1-single-geographic-location"></a>Exemplo 1: localização geográfica única
  
Este exemplo é um cenário para uma empresa fictícia chamada Trey Research que tem uma única localização geográfica.
  
Os funcionários da Trey Research só têm permissão para se conectar aos serviços e sites na Internet que o departamento de segurança permite explicitamente no par de proxies de saída que estão entre a rede corporativa e seu ISP.
  
O Trey Research planeja usar o Azure ExpressRoute para o Office 365 e reconhece que alguns tráfegos, como o tráfego destinado a redes de distribuição de conteúdo, não serão capazes de rotear o ExpressRoute para a conexão do Office 365. Como todo o tráfego já é direcionado para os dispositivos de proxy por padrão, essas solicitações continuarão a funcionar como antes. Depois que a Trey Research determina que podem atender aos requisitos de roteamento do serviço do Azure ExpressRoute, eles continuarão a criar um circuito, configurar o roteamento e vinculando o novo circuito ExpressRoute a uma rede virtual. Depois que a configuração básica do Azure ExpressRoute estiver em vigor, a Trey Research usará o [arquivo de PAC #2 que publicamos](https://aka.ms/manageo365endpoints#ID0EACAAA=2._Proxies) para rotear o tráfego com dados específicos do cliente através do ExpressRoute direto para conexões do Office 365.
  
Conforme mostrado no diagrama a seguir, a Trey Research é capaz de satisfazer o requisito para rotear o tráfego do Office 365 pela Internet e um subconjunto de tráfego sobre o ExpressRoute usando uma combinação de alterações de configuração de roteamento e de saída.
  
1. Usando o [arquivo de PAC de #2 publicamos](https://aka.ms/manageo365endpoints#ID0EACAAA=2._Proxies) para rotear o tráfego por meio de um ponto de saída da Internet separado para o Azure ExpressRoute para Office 365.

2. Os clientes são configurados com uma rota padrão em relação aos proxies da Trey Research.

Neste cenário de exemplo, a Trey Research está usando um dispositivo de proxy de saída. Da mesma forma, os clientes que não estão usando o Azure ExpressRoute para Office 365 podem querer usar essa técnica para rotear o tráfego com base no custo de inspecionar o tráfego destinado para pontos de extremidade de alto volume muito conhecidos.
  
Os FQDNs de volume mais altos para o Exchange Online, o SharePoint Online e o Skype for Business online são os seguintes:
  
![Rede de borda do cliente ExpressRoute](../media/dab8cc42-b1d6-46d6-b2f6-d70f9e16d5ea.png)
  
- outlook.office365.com, outlook.office.com

- \<tenant-name\>. SharePoint.com, \<tenant-name\> -My.SharePoint.com, \<tenant-name\> - \<app\> . SharePoint.com

- \*. Lync.com juntamente com intervalos IP para tráfego não-TCP

- \*broadcast.officeapps.live.com, \* Excel.officeapps.Live.com, \* onenote.officeapps.live.com, \* PowerPoint.officeapps.Live.com, \* view.officeapps.live.com, \* Visio.officeapps.Live.com, \* Word-Edit.officeapps.Live.com, \* Word-View.officeapps.Live.com, Office.Live.com

Saiba mais sobre a [implantação e o gerenciamento de configurações de proxy no Windows 8](https://blogs.technet.com/b/deploymentguys/archive/2013/05/08/windows-8-supporting-proxy-services-with-static-configurations-web-hosted-pac-files-and-domain-policy-configured-proxy.aspx) e [a garantia de que o Office 365 não está limitado pelo proxy](https://blogs.technet.com/b/onthewire/archive/2014/03/28/ensuring-your-office-365-network-connection-isn-t-throttled-by-your-proxy.aspx).
  
Com um único circuito ExpressRoute, não há alta disponibilidade para a Trey Research. No par de dispositivos redundantes de dispositivos de borda da Trey que estão atendendo à conectividade ExpressRoute falha, não há um circuito ExpressRoute adicional para failover. Isso deixa a Trey Research em um Predicament como o failover para a Internet exigirá a reconfiguração manual e, em alguns casos, novos endereços IP. Se a Trey quiser adicionar alta disponibilidade, a solução mais simples é adicionar circuitos de ExpressRoute adicionais para cada local e configurar os circuitos de uma maneira ativa/ativa.
  
## <a name="routing-expressroute-for-office-365-with-multiple-locations"></a>Roteamento ExpressRoute para o Office 365 com vários locais

O último cenário, roteamento do tráfego do Office 365 no ExpressRoute é a base para uma arquitetura de roteamento ainda mais complexa. Independentemente do número de locais, o número de continentes onde esses locais existem, o número de circuitos de ExpressRoute e assim por diante, ser capaz de rotear alguns tráfegos para a Internet e algum tráfego sobre o ExpressRoute será necessário.
  
As perguntas adicionais que devem ser respondidas para clientes com vários locais em várias geografias incluem:
  
1. Você precisa de um circuito ExpressRoute em todos os locais? Se você estiver usando o Skype for Business online ou estiver preocupado com a confidencialidade da latência para o SharePoint Online ou o Exchange Online, um par redundante de circuitos ativos/ativos do ExpressRoute é recomendado em cada local. Confira o guia de conectividade de rede e qualidade de mídia do Skype for Business para obter mais detalhes.

2. Se um circuito ExpressRoute não estiver disponível em uma determinada região, como o tráfego destinado ao Office 365 deve ser roteado?

3. Qual é o método preferido para consolidar o tráfego no caso de redes com muitos locais pequenos?

Cada um deles apresenta um desafio exclusivo que requer a avaliação de sua própria rede, bem como as opções disponíveis na Microsoft.

|**Relação**|**Componentes de rede a serem avaliados**|
|:-----|:-----|
|Circuitos em mais de um local  <br/> |Recomendamos um mínimo de dois circuitos configurados de maneira ativa/ativa.  <br/> As necessidades de custo, latência e largura de banda devem ser comparadas.  <br/> Use o custo da rota BGP, arquivos PAC e NAT para gerenciar o roteamento com vários circuitos.  <br/> |
|Roteamento de locais sem um circuito ExpressRoute  <br/> |Recomendamos a resolução de egresso e DNS, conforme próximo da pessoa que inicia a solicitação para o Office 365.  <br/> O encaminhamento de DNS pode ser usado para permitir que escritórios remotos descubram o ponto de extremidade apropriado.  <br/> Os clientes do escritório remoto devem ter uma rota disponível que forneça acesso ao circuito ExpressRoute.  <br/> |
|Consolidação de pequeno escritório  <br/> |A largura de banda e o uso de dados disponíveis devem ser cuidadosamente comparados.  <br/> |

> [!NOTE]
> A Microsoft preferirá o ExpressRoute pela Internet se a rota estiver disponível independentemente do local físico.
  
Cada uma dessas considerações deve ser levada em consideração para cada rede exclusiva. Veja a seguir um exemplo.
  
### <a name="example-2-multi-geographic-locations"></a>Exemplo 2: locais de várias geografias
  
Este exemplo é um cenário para uma empresa fictícia chamada Humongous Insurance que tem vários locais geográficos.
  
A Humongous Insurance está geograficamente dispersa com escritórios em todo o mundo. Eles querem implementar o Azure ExpressRoute para Office 365 para manter a maior parte do tráfego do Office 365 em conexões de rede direta. A Humongous Insurance também tem escritórios em dois continentes adicionais. Os funcionários no escritório remoto onde o ExpressRoute não é viável precisarão encaminhar para uma ou ambas as instalações primárias para usar uma conexão ExpressRoute.
  
O princípio de orientação é obter o tráfego destinado do Office 365 para um datacenter da Microsoft o mais rápido possível. Neste exemplo, a Humongous Insurance deve decidir se seus escritórios remotos devem se encaminhar pela Internet para obter um datacenter da Microsoft sobre qualquer conexão o mais rápido possível ou se seus escritórios remotos devem se encaminhar por uma rede interna para acessar um data center da Microsoft sobre uma conexão ExpressRoute o mais rápido possível.
  
As arquiteturas de datacenters, redes e aplicativos da Microsoft são projetadas para realizar comunicações globalmente diferentes e fazer o serviço deles da maneira mais eficiente possível. Esta é uma das maiores redes do mundo. As solicitações destinadas ao Office 365 que permanecem em redes do cliente mais do que o necessário não poderão aproveitar essa arquitetura.
  
Na situação da Humongous Insurance, elas devem prosseguir, dependendo dos aplicativos que pretendem usar no ExpressRoute. Por exemplo, se eles forem um cliente do Skype for Business online ou se você planejar a utilização da conectividade do ExpressRoute durante a conexão com reuniões externas do Skype for Business Online, o design recomendado no guia de conectividade de rede e qualidade de mídia do Skype for Business Online é provisionar um circuito ExpressRoute adicional para o terceiro local. Isso pode ser mais caro de uma perspectiva de rede; no entanto, o roteamento de solicitações de um continente para outro antes de entregar a um Microsoft datacenter pode causar uma experiência ruim ou inútil durante reuniões e comunicações do Skype for Business online.
  
Se a Humongous Insurance não estiver usando ou não planeja aproveitar o Skype for Business online de qualquer forma, o roteamento do tráfego de rede destinado ao Office 365 de volta para um continente com uma conexão ExpressRoute pode ser viável, embora possa causar latência desnecessária ou congestionamento de TCP. Em ambos os casos, o roteamento de tráfego de Internet destinado à Internet no site local é recomendado para aproveitar as redes de distribuição de conteúdo nas quais o Office 365 se baseia.
  
![Vários geografias do ExpressRoute](../media/98fdd883-2c5a-4df7-844b-bd28cd0b9f50.png)
  
Quando a Humongous Insurance estiver planejando sua estratégia de vários geografias, há várias coisas a considerar o tamanho do circuito, o número de circuitos, o failover e assim por diante.
  
Com o ExpressRoute em um único local com várias regiões tentando usar o circuito, a Humongous Insurance deseja garantir que as conexões para o Office 365 do escritório remoto sejam enviadas para a matriz mais próxima do Office 365 datacenter e recebidas pelo local da sede. Para fazer isso, a Humongous Insurance implementa o encaminhamento de DNS para reduzir o número de viagens e pesquisas de DNS necessárias para estabelecer a conexão apropriada com o ambiente do Office 365 mais próximo do ponto de saída do Headquarters Internet. Isso impede que o cliente resolva um servidor front-end local e garante que o servidor front-end ao qual a pessoa se conecta esteja próximo da sede, onde a Humongous Insurance está interligando com a Microsoft. Você também pode aprender a [atribuir um encaminhador condicional para um nome de domínio](https://technet.microsoft.com/library/Cc794735%28v=WS.10%29.aspx).
  
Neste cenário, o tráfego do escritório remoto resolveria a infraestrutura de front-ends do Office 365 na América do Norte e aproveita o Office 365 para se conectar aos servidores de back-end de acordo com a arquitetura do aplicativo do Office 365. Por exemplo, o Exchange Online encerraria a conexão na América do Norte, e esses servidores front-end se conectarão ao servidor de caixa de correio de backend onde quer que o locatário tivesse sido relado. Todos os serviços têm um serviço de porta frontal amplamente distribuído composto por destinos unicast e anycast.
  
Se a Humongous tiver grandes escritórios em vários continentes, será recomendável um mínimo de dois circuitos ativos/ativos por região para reduzir a latência de aplicativos confidenciais como o Skype for Business online. Se todos os escritórios estiverem em um único continente ou não estiver usando a colaboração em tempo real, ter um ponto de saída consolidado ou distribuído é uma decisão específica do cliente. Quando vários circuitos estiverem disponíveis, o roteamento BGP garantirá o failover caso um único circuito fique indisponível.
  
Saiba mais sobre [configurações de roteamento](https://azure.microsoft.com/documentation/articles/expressroute-config-samples-routing/) de exemplo e [https://azure.microsoft.com/documentation/articles/expressroute-config-samples-nat/](https://azure.microsoft.com/documentation/articles/expressroute-config-samples-nat/) .
  
## <a name="selective-routing-with-expressroute"></a>Roteamento seletivo com o ExpressRoute

O roteamento seletivo com o ExpressRoute pode ser necessário por vários motivos, como testes, a distribuição do ExpressRoute para um subconjunto de usuários. Há várias ferramentas que os clientes podem usar para rotear seletivamente o tráfego de rede do Office 365 no ExpressRoute:
  
1. **Filtragem de rota/diferenciação** , permitindo rotas BGP para o Office 365 over ExpressRoute para um subconjunto de suas sub-redes ou roteadores. Isso roteia seletivamente por segmento de rede do cliente ou local físico do escritório. Isso é comum para a distribuição de escalonagem do ExpressRoute para o Office 365 e é configurado em seus dispositivos BGP.

2. **Arquivos PAC/URLs** : o tráfego de rede destinado ao Office 365 para FQDNs específicos para rotear em um caminho específico. Isso roteia seletivamente por computador cliente, conforme identificado pela [implantação de Arquivo PAC](https://aka.ms/manageo365endpoints#ID0EACAAA=2._Proxies).

3. **Filtragem**  -  de rota Os [filtros de roteamento](https://docs.microsoft.com/azure/expressroute/how-to-routefilter-portal) são uma maneira de consumir um subconjunto de serviços compatíveis através de emparelhamento da Microsoft.

4. **Comunidades BGP** -a filtragem baseada nas [marcas de comunidade do BGP](https://aka.ms/bgpexpressroute365) permite que o cliente determine quais aplicativos do Office 365 atravessarão o ExpressRoute e o que atravessará a Internet.

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
