---
title: Networking up (para a nuvem)— Um ponto de vista do arquiteto
description: Saiba como otimizar sua rede para conectividade na nuvem evitando as armadilhas mais comuns.
ms.author: bcarter
author: brendacarter
manager: bcarter
ms.audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-identity-device-management
- M365-security-compliance
ms.custom: ''
f1.keywords: NOCSH
ms.openlocfilehash: 7de9aec29b0a57e85e3539fc2e99384de545c52a
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50904631"
---
# <a name="networking-up-to-the-cloudone-architects-viewpoint"></a>Networking up (para a nuvem)— Um ponto de vista do arquiteto

Neste artigo, [Ed Fisher](https://www.linkedin.com/in/edfisher/), Arquiteto de Conformidade & Segurança da Microsoft, descreve como otimizar sua rede para conectividade na nuvem, evitando as armadilhas mais comuns. 

## <a name="about-the-author"></a>Sobre o autor

![Foto de Ed Fisher](../media/solutions-architecture-center/ed-fisher-networking.jpg) 

Atualmente, sou um Especialista Técnico Principal na região Sudeste com foco em Segurança & Conformidade. Eu tenho trabalhado com clientes mudando para Office 365 nos últimos 10 anos. Tenho trabalhado com lojas menores com vários locais para agências e empresas governamentais com milhões de usuários distribuídos em todo o mundo e muitos outros clientes entre eles, com a maioria com dezenas de milhares de usuários, vários locais em várias partes do mundo, a necessidade de um grau mais alto de segurança e uma infinidade de requisitos de conformidade. Eu já ajuda centenas de empresas e milhões de usuários a se mover para a nuvem com segurança e segurança.

Com um plano de fundo nos últimos 25 anos que inclui segurança, infraestrutura e engenharia de rede e ter movido dois dos meus empregadores anteriores para o Office 365 antes de ingressar na Microsoft, eu tenho estado do seu lado da tabela várias vezes e lembre-se de como isso é. Embora nenhum dois clientes sejam sempre os mesmos, a maioria tem necessidades semelhantes e, ao consumir um serviço padronizado, como qualquer plataforma SaaS ou PaaS, as melhores abordagens tendem a ser as mesmas.

## <a name="its-not-the-networkits-how-youre-misusing-it"></a>Não é a rede, é como você está (mis)using it!

Não importa quantas vezes isso aconteça, nunca  falha ao me surpreender como equipes de segurança e equipes de rede criativas tentam se conectar com os serviços de nuvem da Microsoft. Sempre há alguma política de segurança, um padrão de conformidade ou uma maneira melhor de insistir em usar, sem  estar disposto a se envolver em uma conversa sobre o que está tentando realizar, ou como elas são melhores, mais fáceis, mais econômicas e maneiras mais eficazes de fazer isso.

Quando esse tipo de coisa é escalonado para mim, geralmente estou disposto a aceitar o desafio e explicar como estão e por que e levá-los para onde precisam estar. Mas se estou sendo completamente franco, preciso compartilhar que, às vezes, quero deixá-los fazer o que quiserem e voltar para dizer que eu disse isso quando eles finalmente admitirem que não funciona. Às vezes, posso querer fazer isso, mas *não* quero. O que faço é tentar explicar tudo o que incluirei nesta postagem. Independentemente da sua função, se sua organização quiser usar os serviços de nuvem da Microsoft, provavelmente há alguma sabedoria no que segue que pode ajudá-lo.

## <a name="guiding-principles"></a>Princípios orientadores

Vamos começar com algumas regras básicas sobre o que estamos fazendo aqui. Estamos discutindo como se conectar com segurança aos serviços de nuvem para garantir a complexidade mínima e o desempenho máximo, mantendo a segurança real. Nada disso é contrário a nada disso, mesmo que você, ou seu cliente, não use seu servidor proxy favorito para tudo.

- **Só porque você pode, não significa** que você deve : ou parafrasear o Dr. Ian Malcom do filme do Estacionamento Jurássico "... Sim, sim, mas sua equipe de segurança estava tão preocupado com se eles poderiam ou não parar para pensar se deveriam."
- **Segurança não significa complexidade**: você não está mais seguro apenas porque você gasta mais dinheiro, roteia por mais dispositivos ou clica em mais botões.
- **Office 365 é acessado pela Internet**: Mas isso não é a mesma coisa que Office 365 é a Internet. É um serviço SaaS gerenciado pela Microsoft e administrado por você. Ao contrário dos sites que você visita na Internet, você pode espiar atrás da janela e aplicar os controles necessários para atender às suas políticas e aos padrões de conformidade, desde que entenda que, embora possa atender aos seus objetivos, talvez seja necessário fazê-los de uma maneira diferente.
- Os pontos de bloqueio são ruins, as interrupções **localizadas** são boas : todos sempre querem fazer o backhaul de todo o tráfego da Internet para todos os usuários em algum ponto central, geralmente para que eles possam monitorá-lo e impor a política, mas geralmente porque é mais barato do que provisionar o acesso à Internet em todos os seus locais ou é exatamente como eles fazem isso. Mas esses pontos de bloqueio são exatamente isso... pontos em que o tráfego se engasgue. Não há nada de errado em impedir que seus usuários navegam no Instagram ou streaming de vídeos de gato, mas não tratem seu tráfego de aplicativos de negócios críticos da mesma maneira.
- Se o DNS não estiver **satisfeito,** não será nada feliz: a rede melhor projetada pode ser prejudicada por DNS ruim, seja recursando solicitações para servidores em outras áreas do mundo ou usando os servidores DNS do ISP ou outros servidores DNS públicos que armazenam em cache informações de resolução DNS.
- **Só porque era** assim que você fazia isso, não significa que você deve fazer isso agora: a tecnologia muda constantemente e Office 365 não é exceção. A aplicação de medidas de segurança desenvolvidas e implantadas para serviços locais ou para controlar o surf na Web não fornecerá o mesmo nível de garantia de segurança e poderá ter um impacto negativo significativo no desempenho.
- **Office 365 foi criado para ser acessado pela Internet**: é isso em resumo. Não importa o que você deseja fazer entre seus usuários e sua borda, o tráfego ainda passa pela Internet depois que ele sai da sua rede e antes de chegar à nossa. Mesmo se você estiver usando o Azure ExpressRoute para rotear algum tráfego sensível à latência de sua rede diretamente para a nossa, a conectividade com a Internet é absolutamente necessária. Aceite-o. Não pense demais.

## <a name="where-bad-choices-are-often-made"></a>Onde escolhas ruins geralmente são feitas

Embora haja muitos lugares em que decisões ruins são tomadas em nome da segurança, esses são os que eu encontro com mais frequência com os clientes. Muitas conversas de clientes envolvem todas elas ao mesmo tempo.

### <a name="insufficient-resources-at-the-edge"></a>Recursos insuficientes na borda

Muito poucos clientes estão implantando ambientes greenfield, e eles têm anos de experiência com como seus usuários funcionam e como é sua saída da Internet. Se os clientes têm servidores proxy ou permitem acesso direto e simplesmente tráfego de saída NAT, eles fazem isso há anos e não consideram o quanto mais eles começarão a se movimentar à medida que movem aplicativos tradicionalmente internos para a nuvem.

A largura de banda sempre é uma preocupação, mas os dispositivos NAT podem não ter potência suficiente para lidar com a carga aumentada e podem começar a fechar conexões prematuramente para liberar recursos. A maioria dos softwares cliente que se conecta Office 365 espera conexões persistentes e um usuário utilizando totalmente Office 365 pode ter 32 ou mais conexões simultâneas. Se o dispositivo NAT estiver soltando-os prematuramente, esses aplicativos podem se tornar não responsivos à medida que tentam usar as conexões que não estão mais lá. Quando eles deagem e tentam estabelecer novas conexões, eles colocam ainda mais carga na engrenagem de rede.

### <a name="localized-breakout"></a>Breakout localizado

Todo o resto nesta lista se resume a uma coisa: sair da rede e entrar na nossa o mais rápido possível. O backhauling do tráfego de seus usuários para um ponto de saída central, especialmente quando esse ponto de saída está em outra região que seus usuários estão, introduz latência desnecessária e afeta a experiência do cliente e velocidades de download. A Microsoft tem pontos de presença em todo o mundo com front-ends para todos os nossos serviços e o paramento estabelecido com praticamente todos os PRINCIPAIS ISP, portanto, rotear o tráfego de seus usuários *localmente* garante que ele entre em nossa rede rapidamente com latência mínima.

### <a name="dns-resolution-traffic-should-follow-the-internet-egress-path"></a>O tráfego de resolução DNS deve seguir o caminho de saída da Internet

Obviamente, para um cliente encontrar qualquer ponto de extremidade, ele precisa usar DNS. Os servidores DNS da Microsoft avaliam a origem das solicitações DNS para garantir que retornemos a resposta que está, em termos de Internet, mais próxima da origem da solicitação. Certifique-se de que seu DNS está configurado para que as solicitações de resolução de nomes saiam do mesmo caminho que o tráfego dos usuários, para que você não dê a eles saída local, mas para um ponto de extremidade em outra região. Isso significa permitir que servidores DNS locais "acessem a raiz" em vez de encaminhar para servidores DNS em data centers remotos. E tenha cuidado com os serviços DNS públicos e privados, que podem armazenar em cache os resultados de uma parte do mundo e servi-los a solicitações de outras partes do mundo.

### <a name="to-proxy-or-not-to-proxy-that-is-the-question"></a>Para proxy ou não para proxy, essa é a questão

Uma das primeiras coisas a considerar é se as conexões dos usuários proxy para Office 365. Essa é fácil; não proxy. Office 365 é acessado pela Internet, mas não é a Internet. É uma extensão dos seus serviços principais e deve ser tratado como tal. Tudo o que você pode querer que um proxy faça, como DLP ou antimalware ou inspeção de conteúdo, já está disponível no serviço e pode ser usado em escala e sem a necessidade de quebrar conexões criptografadas por TLS. Mas se você realmente quiser fazer proxy de tráfego que não pode controlar, preste atenção às nossas diretrizes e às categorias [https://aka.ms/pnc](../enterprise/microsoft-365-network-connectivity-principles.md) de tráfego em [https://aka.ms/ipaddrs](../enterprise/urls-and-ip-address-ranges.md) . Temos três categorias de tráfego para Office 365. Otimizar e Permitir realmente deve ir direto e ignorar seu proxy. O padrão pode ser protegido. Os detalhes estão nesses documentos... lê-los.

A maioria dos clientes que insistem em usar um proxy, quando eles realmente olham para o que estão fazendo, percebem que quando o cliente faz uma solicitação HTTP CONNECT para o proxy, o proxy agora é apenas um roteador extra caro. Os protocolos em uso, como MAPI e RTC, não são nem mesmo protocolos que os proxies da Web entendem, portanto, mesmo com a quebra de TLS, você não está realmente recebendo nenhuma segurança extra. Você *está* recebendo latência extra. Confira mais sobre isso, incluindo as categorias Otimizar, Permitir e Padrão para Microsoft 365 [https://aka.ms/pnc](../enterprise/microsoft-365-network-connectivity-principles.md) tráfego.

Por fim, considere o impacto geral para o proxy e sua resposta correspondente para lidar com esse impacto. À medida que mais e mais conexões estão sendo feitas por meio do proxy, ele pode diminuir o Fator de Escala TCP para que ele não tenha que fazer o buffer de tanto tráfego. Vi clientes em que seus proxies estavam tão sobrecarregados que estavam usando um Fator de Escala 0. Como o Fator de Escala é um valor exponencial e queremos usar 8, cada redução no valor do Fator de Escala é um enorme impacto negativo para a taxa de transferência.

Inspeção TLS significa SEGURANÇA! Mas não realmente! Muitos clientes com proxies querem usá-los para inspecionar todo o tráfego, e isso significa que o TLS "quebra e inspeciona". Quando você faz isso para um site acessado por HTTPS (questões de privacidade, não obstante), seu proxy pode ter que fazer isso por 10 ou até mesmo 20 fluxos simultâneos por algumas centenas de milissegundos. Se houver um download grande ou talvez um vídeo envolvido, uma ou mais dessas conexões poderão durar muito mais, mas, no geral, a maioria dessas conexões estabelece, transfere e feche muito rapidamente. Fazer a pausa e inspecionar significa que o proxy deve fazer o dobro do trabalho. Para cada conexão do cliente com o proxy, o proxy também deve fazer uma conexão separada de volta ao ponto de extremidade. Então, 1 se torna 2, 2 se torna 4, 32 se torna 64...veja para onde estou indo? Você provavelmente dimensionou sua solução de proxy muito bem para o surf típico da Web, mas quando você tenta fazer o mesmo para as conexões do cliente com o Office 365, o número de conexões simultâneas e de longa duração pode ser ordens de magnitude maior do que o tamanho para o qual você dimensionou.

### <a name="streaming-isnt-important-except-that-it-is"></a>Streaming não é importante, exceto por *ser*

Os únicos serviços em Office 365 que usam UDP são Skype (em breve serão retirados) e Microsoft Teams. Teams usa o UDP para o tráfego de streaming, incluindo áudio, vídeo e compartilhamento de apresentação. O tráfego de streaming é ao vivo, como quando você está tendo uma reunião online com voz, vídeo e apresentando decks ou realizando demonstrações. Eles usam UDP porque se os pacotes são descartados ou ficam fora de ordem, ele é praticamente imperceptível pelo usuário e o fluxo pode continuar.

Quando você não permite o tráfego UDP de saída de clientes para o serviço, eles podem voltar a usar o TCP. Mas se um pacote TCP for *descartado,* tudo será interrompido até que o Tempo de Retransmissão (RTO) expire e o pacote ausente possa ser retransmitido. Se um pacote ficar fora de ordem, tudo será interrompido até que os outros pacotes cheguem e possam ser remontados em ordem. Ambos levam a falhas perceptíveis no áudio (lembre-se de Max Headroom?) e vídeo (você clicou em algo... oh, lá está) e levar a um desempenho ruim e uma experiência de usuário ruim. E lembre-se do que eu colocar acima sobre proxies? Quando você força um cliente Teams usar um proxy, força-o a usar o TCP. Agora você está causando impactos negativos no desempenho duas vezes.

### <a name="split-tunneling-may-seem-scary"></a>O túnel dividido pode parecer assustador

Mas não é. Todas as conexões Office 365 são por TLS. Estamos oferecendo o TLS 1.2 há algum tempo e desabilitaremos versões mais antigas em breve porque os clientes herdadas ainda as usam e isso é um risco.

Forçar uma conexão TLS, ou 32 delas, a passar por cima de uma VPN antes de ir para o serviço não adiciona segurança. Ele adiciona latência e reduz a taxa de transferência geral. Em algumas soluções VPN, ele até força o UDP a fazer um túnel através do TCP, que novamente terá um impacto muito negativo no tráfego de streaming. E, a menos que você esteja fazendo a inspeção TLS, não há nenhum lado positivo, tudo em desvantagem. Um tema muito comum entre os clientes, agora que a maior parte de sua força de trabalho é remota, é que eles estão vendo impactos significativos na largura de banda e no desempenho de fazer com que todos os usuários se conectem usando uma VPN, em vez de configurar o túnel dividido para acessar os pontos de extremidade otimizar a [categoria Office 365](../enterprise/microsoft-365-network-connectivity-principles.md#new-office-365-endpoint-categories)pontos de extremidade .

É uma correção fácil de fazer o túnel dividido e é uma que você deve fazer. Para saber mais, confira Otimizar Office 365 conectividade para usuários remotos usando o [túnel dividido de VPN.](../enterprise/microsoft-365-vpn-split-tunnel.md)

## <a name="the-sins-of-the-past"></a>Os erros do passado

Muitas vezes, o motivo pelo qual escolhas ruins são feitas vem de uma combinação de (1) não saber como o serviço funciona, (2) tentar aderir às políticas da empresa que foram escritas antes de adotar a nuvem e (3) equipes de segurança que podem não ser facilmente convencer de que há mais de uma maneira de atingir suas metas. Esperamos que o acima e os links abaixo ajudem com o primeiro. O patrocínio executivo pode ser necessário para passar do segundo. O endereçamento das metas das políticas de segurança, em vez de seus métodos, ajuda com o terceiro. Desde o acesso condicional à moderação de conteúdo, DLP à proteção de informações, validação de ponto de extremidade a ameaças de dia zero — qualquer meta final que uma política de segurança razoável possa ter pode ser realizada com o que está disponível no Office 365 e sem qualquer dependência sobre a engrenagem de rede local, túnel vpn forçado e quebra e inspeção TLS.

Outras vezes, o hardware que foi dimensionado e comprado antes da organização começar a se mover para a nuvem simplesmente não pode ser dimensionado para lidar com os novos padrões de tráfego e cargas. Se você realmente deve rotear todo o tráfego por meio de um único ponto de saída e/ou proxy, esteja preparado para atualizar o equipamento de rede e a largura de banda de acordo. Monitore cuidadosamente a utilização em ambos, pois a experiência não diminuirá lentamente à medida que mais usuários integram. Tudo ficará bem até que o ponto de inflexão seja atingido e todos sofrerão.

## <a name="exceptions-to-the-rules"></a>Exceções às regras

Se sua [](/azure/active-directory/manage-apps/tenant-restrictions)organização exigir restrições de locatários, você precisará usar um proxy com TLS para quebrar e inspecionar para forçar algum tráfego através do proxy, mas você não precisa forçar todo o tráfego por ele.  Não é uma proposta de tudo ou nada, portanto, preste atenção ao que precisa ser modificado pelo proxy.

Se você vai permitir o túnel dividido, mas também usar um proxy para tráfego Web geral, certifique-se de que seu arquivo PAC defina o que deve ser direto, bem como como definir o tráfego interessante para o que passa pelo túnel VPN. Oferecemos arquivos PAC de exemplo [https://aka.ms/ipaddrs](../enterprise/urls-and-ip-address-ranges.md) que facilitarão o gerenciamento.

## <a name="conclusion"></a>Conclusão

Dezenas de milhares de organizações, incluindo quase toda a Fortune 500, usam Office 365 todos os dias para suas funções críticas de missão. Eles fazem isso com segurança e fazem isso pela Internet.

Não importa quais metas de segurança você tenha em jogo, há maneiras de fazer com que elas não exigem conexões VPN, servidores proxy, TLS quebram e inspecionam ou egressam na Internet centralizada para tirar o tráfego de seus usuários da rede e para a nossa o mais rápido possível, o que oferece o melhor desempenho, se sua rede é a sede da empresa , um escritório remoto ou esse usuário trabalhando em casa. Nossas diretrizes se baseiam em como os serviços Office 365 são construídos e para garantir uma experiência de usuário segura e performant.

## <a name="further-reading"></a>Leitura posterior

[Os Office 365 de conectividade de rede](../enterprise/microsoft-365-network-connectivity-principles.md)

[URLs e intervalos de endereços IP do Office 365](../enterprise/urls-and-ip-address-ranges.md)

[Gerenciar pontos de extremidade do Office 365](../enterprise/managing-office-365-endpoints.md)

[URL do serviço Web e endereço IP do Office 365](../enterprise/microsoft-365-ip-web-service.md)

[Avaliando a conectividade de rede do Office 365](../enterprise/assessing-network-connectivity.md)

[Rede do Office 365 e ajuste de desempenho](../enterprise/network-planning-and-performance.md)

[Avaliando a conectividade de rede do Office 365](../enterprise/assessing-network-connectivity.md)

[Ajuste de desempenho do Office 365 usando linhas de base e histórico de desempenho](../enterprise/performance-tuning-using-baselines-and-history.md)

[Plano de solução de problemas de desempenho do Office 365](../enterprise/performance-troubleshooting-plan.md)

[Redes de Distribuição de Conteúdo](../enterprise/content-delivery-networks.md)

[Teste de conectividade do Microsoft 365](https://connectivity.office.com/)

[Como a Microsoft cria sua rede global confiável e rápida](https://azure.microsoft.com/blog/how-microsoft-builds-its-fast-and-reliable-global-network/)

[Blog de rede do Office 365](https://techcommunity.microsoft.com/t5/office-365-networking/bd-p/Office365Networking)

[Office 365 conectividade para usuários remotos usando o túnel dividido de VPN](../enterprise/microsoft-365-vpn-split-tunnel.md)