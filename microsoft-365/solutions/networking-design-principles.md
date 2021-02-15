---
title: Rede (para a nuvem) — arquitetura de um arquiteto
description: Saiba como otimizar sua rede para conectividade de nuvem evitando as armadilhas mais comuns.
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
ms.openlocfilehash: 175903949b639740ad00b29013d5748b99bdb2de
ms.sourcegitcommit: ddfb4f3e34deb733e8625e845e4dfd1fcc066ceb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/06/2021
ms.locfileid: "49771842"
---
# <a name="networking-up-to-the-cloudone-architects-viewpoint"></a>Rede (para a nuvem) — arquitetura de um arquiteto

Neste artigo, [Ed Fisher](https://www.linkedin.com/in/edfisher/), Arquiteto de Conformidade e Segurança & da Microsoft, descreve como otimizar sua rede para conectividade com a nuvem, evitando as armadilhas mais comuns. 

## <a name="about-the-author"></a>Sobre o autor

![Foto de Ed Fisher](../media/solutions-architecture-center/ed-fisher-networking.jpg) 

Atualmente, sou um especialista técnico principal na região Do Sul, concentrando-me na conformidade com & segurança. Eu tenho trabalhado com clientes que mudaram para o Office 365 nos últimos 10 anos. Eu tenho trabalhado com lojas menores com alguns locais para agências governamentais e empresas com milhões de usuários distribuídos em todo o mundo e muitos outros clientes entre eles, com a maioria tendo dezenas de milhares de usuários, vários locais em várias partes do mundo, a necessidade de um maior grau de segurança e uma infinidade de requisitos de conformidade. Eu ajudando centenas de empresas e milhões de usuários a se mover para a nuvem com segurança.

Com uma experiência nos últimos 25 anos que inclui segurança, infraestrutura e engenharia de rede e ter movido dois de meus empregadores anteriores para o Office 365 antes de ingressar na Microsoft, eu estou do seu lado várias vezes e lembre-se de como é isso. Embora nenhum cliente seja o mesmo, a maioria tenha necessidades semelhantes e ao consumir um serviço padronizado, como qualquer plataforma SaaS ou PaaS, as melhores abordagens tendem a ser as mesmas.

## <a name="its-not-the-networkits-how-youre-misusing-it"></a>Não é a rede, é como você está (usando insupo)!

Não importa quantas vezes isso aconteça, nunca  falha em me lembrar como as equipes de segurança e as equipes de rede criativos tentam se conectar aos serviços de nuvem da Microsoft. Sempre há uma política de segurança, um padrão de conformidade ou uma maneira melhor de eles se envolverem no  uso, sem estarem dispostos a participar de uma conversa sobre o que estão tentando realizar ou como são melhores, mais fáceis, mais econômicas e mais eficientes de fazer isso.

Quando esse tipo de coisa é escalonado para mim, geralmente estou disposto a pegar o desafio e explicar como e o motivo e levá-los para onde eles precisam estar. Mas se eu estiver sendo completamente franco, preciso compartilhar que, às vezes, quero apenas permitir que eles fazem o que quiserem e voltar a dizer que eu te disse isso quando eles finalmente concedem que não funciona. Às vezes, talvez eu queira fazer isso, *mas não quero.* O que eu faço é tentar explicar tudo o que incluirei nesta postagem. Independentemente da sua função, se a sua organização quiser usar os serviços de nuvem da Microsoft, provavelmente há algumas perguntas sobre o que vem a seguir que podem ajudá-lo.

## <a name="guiding-principles"></a>Princípios de orientação

Vamos começar com algumas regras básicas sobre o que estamos fazendo aqui. Estamos discutendo como se conectar com segurança aos serviços de nuvem para garantir a complexidade mínima e o desempenho máximo, mantendo a segurança real. Nada disso é um contador para nada disso, mesmo que você ou seu cliente não use seu servidor proxy favorito para tudo.

- **Só porque você pode, isso não** significa que você deve: ou para frases de parafraseado Dr. Dra Mera do filme "... Sim, sim, mas sua equipe de segurança estava tão ocupada com a dúvida de que não parou para pensar se deveria".
- **A segurança não significa complexidade:** você não é mais seguro só porque gasta mais dinheiro, encaminha por mais dispositivos ou clica em mais botões.
- **O Office 365** é acessado pela Internet: mas o Office 365 não é o mesmo que a Internet. É um serviço SaaS gerenciado pela Microsoft e administrado por você. Ao contrário dos sites que você visita na Internet, na verdade, você pode conhecer os bastidores e aplicar os controles necessários para atender às suas políticas e aos padrões de conformidade, desde que compreenda que, embora possa cumprir seus objetivos, talvez seja necessário fazê-los de uma maneira diferente.
- Os pontos de interrupção mal **localizados** são bons: todos sempre querem reformular todo o tráfego da Internet para todos os usuários até um ponto central, geralmente para que possam monitorá-lo e impor políticas, mas geralmente porque é mais barato do que provisionar o acesso à Internet em todos os seus locais ou é apenas como eles fazem. Mas esses pontos de redução são exatamente esse... pontos em que o tráfego se desdova. Não há nada de errado em impedir que seus usuários navegarem até o Videos ou transmitir vídeos de gatos, mas não trate seu tráfego crítico de aplicativos de negócios da mesma maneira.
- Se o DNS não estiver **satisfeito,** não há nada de bom: a rede melhor projetada pode ser prejudicada pelo DNS ruim, seja recursando solicitações a servidores em outras áreas do mundo ou usando os servidores DNS do SEU ISP ou outros servidores DNS públicos que armazenam em cache as informações de resolução de DNS.
- **Só porque era** assim que você costumava fazer isso, isso não significa que você deve fazer isso agora: a tecnologia muda constantemente e o Office 365 não é uma exceção. A aplicação de medidas de segurança que foram desenvolvidas e implantadas para serviços locais ou para controlar a implantação da Web não fornecerá o mesmo nível de garantia de segurança e pode ter um impacto negativo significativo sobre o desempenho.
- **O Office 365 foi** criado para ser acessado pela Internet: isso é tudo. Independentemente do que você deseja fazer entre seus usuários e sua borda, o tráfego ainda passa pela Internet assim que ele sai da rede e antes de chegar à nossa. Mesmo que você use o Azure ExpressRoute para rotear algum tráfego sensível à latência de sua rede diretamente para a nossa, a conectividade com a Internet é absolutamente necessária. Aceite-a. Não o sobressuce.

## <a name="where-bad-choices-are-often-made"></a>Onde escolhas ruins são geralmente feitas

Embora haja muitos lugares em que decisões ruins são tomadas em nome da segurança, esses são os que eu vejo com mais frequência com os clientes. Muitas conversas do cliente envolvem todas elas ao mesmo tempo.

### <a name="insufficient-resources-at-the-edge"></a>Recursos insuficientes na borda

Poucos clientes estão implantando ambientes de campo verde e têm anos de experiência com a forma como seus usuários trabalham e como é a saída da Internet. Se os clientes têm servidores proxy ou permitem o acesso direto e simplesmente o tráfego de saída NAT, eles fazem isso há anos e não consideram quanto mais começarão a se movimentar pela borda enquanto movem aplicativos tradicionalmente internos para a nuvem.

A largura de banda é sempre uma preocupação, mas os dispositivos NAT podem não ter poder suficiente para lidar com a carga aumentada e podem começar a fechar conexões prematuramente para liberar recursos. A maioria dos softwares clientes que se conecta ao Office 365 espera conexões persistentes e um usuário que utiliza totalmente o Office 365 pode ter 32 ou mais conexões simultâneas. Se o dispositivo NAT os estiver soltando prematuramente, esses aplicativos poderão ficar sem resposta à medida que tentarem usar as conexões que não estão mais lá. Quando eles deem e tentarem estabelecer novas conexões, eles colocam ainda mais carga na engrenagem da rede.

### <a name="localized-breakout"></a>Breakout localizado

O resto desta lista resume-se a uma coisa: sair da rede e da nossa o mais rápido possível. O backhauling do tráfego dos usuários para um ponto de saída central, especialmente quando esse ponto de saída está em outra região do que a de seus usuários, introduz latência desnecessária e afeta a experiência do cliente e as velocidades de download. A Microsoft tem pontos de presença em todo o mundo com front-ends para todos os nossos serviços e o ponto estabelecido com praticamente todos os PRINCIPAIS ISP, portanto, rotear o tráfego de seus usuários *localmente* garante que ele entre em nossa rede rapidamente com latência mínima.

### <a name="dns-resolution-traffic-should-follow-the-internet-egress-path"></a>O tráfego de resolução DNS deve seguir o caminho de saída da Internet

Obviamente, para um cliente encontrar qualquer ponto de extremidade, ele precisa usar DNS. Os servidores DNS da Microsoft avaliam a origem das solicitações DNS para garantir que retornemos a resposta, em termos da Internet, mais próxima da origem da solicitação. Certifique-se de que seu DNS está configurado para que as solicitações de resolução de nomes saiam do mesmo caminho que o tráfego dos usuários, para que você dê a eles saída local, mas para um ponto de extremidade em outra região. Isso significa permitir que os servidores DNS locais "acessem a raiz" em vez de encaminhar para servidores DNS em data centers remotos. E fique atento aos serviços DNS públicos e privados, que podem armazenar em cache os resultados de uma parte do mundo e atender a solicitações de outras partes do mundo.

### <a name="to-proxy-or-not-to-proxy-that-is-the-question"></a>Para fazer proxy ou não para proxy, essa é a pergunta

Uma das primeiras coisas a considerar é se as conexões dos usuários são proxy para o Office 365. Essa é fácil; não fazer proxy. O Office 365 é acessado pela Internet, mas não pela Internet. É uma extensão dos seus serviços principais e deve ser tratada como tal. Tudo o que você pode querer que um proxy faça, como DLP ou antimalware ou inspeção de conteúdo, já está disponível para você no serviço e pode ser usado em escala e sem a necessidade de descobrir conexões criptografadas por TLS. Mas se você realmente quiser fazer proxy de tráfego que não pode controlar de outra forma, preste atenção às nossas diretrizes e às categorias [https://aka.ms/pnc](https://aka.ms/pnc) de tráfego em [https://aka.ms/ipaddrs](https://aka.ms/ipaddrs) . Temos três categorias de tráfego para o Office 365. Otimizar e Permitir realmente devem ser diretos e ignorar seu proxy. O padrão pode ser com proxique. Os detalhes estão nesses documentos... lê-los.

A maioria dos clientes que resistem ao uso de um proxy, quando realmente olha para o que está fazendo, percebe que, quando o cliente faz uma solicitação HTTP CONNECT para o proxy, o proxy agora é apenas um roteador extra caro. Os protocolos em uso, como MAPI e RTC, nem mesmo são protocolos que os proxies da Web entendem, portanto, mesmo com a falha do TLS, você não está recebendo segurança extra. Você *está* recebendo latência extra. Veja [https://aka.ms/pnc](https://aka.ms/pnc) mais sobre isso, incluindo as categorias Otimizar, Permitir e Padrão para o tráfego do Microsoft 365.

Por fim, considere o impacto geral no proxy e sua resposta correspondente para lidar com esse impacto. À medida que mais e mais conexões estão sendo feitas por meio do proxy, isso pode diminuir o Fator de Escala TCP para que ele não tenha que fazer o buffer de muito tráfego. Vi clientes em que seus proxies estavam tão sobrecarregados que estavam usando um Fator de Escala 0. Como o Fator de Escala é um valor exponencial e queremos usar 8, cada redução no valor do Fator de Escala é um enorme impacto negativo na taxa de transferência.

Inspeção TLS significa SEGURANÇA! Mas não é verdade! Muitos clientes com proxies querem usá-los para inspecionar todo o tráfego, o que significa que o TLS "quebra e inspeção". Quando você faz isso para um site acessado por HTTPS (questões de privacidade, não obstante), seu proxy pode ter que fazer isso por 10 ou até mesmo 20 fluxos simultâneos por algumas centenas de milissegundos. Se houver um download grande ou talvez um vídeo envolvido, uma ou mais dessas conexões poderão durar muito mais, mas, em geral, a maioria dessas conexões estabelece, transfere e fecha muito rapidamente. Fazer pausa e inspecionar significa que o proxy deve fazer o dobro do trabalho. Para cada conexão do cliente com o proxy, o proxy também deve fazer uma conexão separada de volta ao ponto de extremidade. Portanto, 1 torna-se 2, 2 torna-se 4, 32 torna-se 64... veja onde estou indo? Você provavelmente dimensionou sua solução de proxy muito bem para sites típicos, mas ao tentar fazer o mesmo para conexões de cliente com o Office 365, o número de conexões simultâneas de longa duração pode ser maior do que o tamanho das conexões simultâneas e de longa duração.

### <a name="streaming-isnt-important-except-that-it-is"></a>Streaming não é importante, exceto que *é*

Os únicos serviços no Office 365 que usam UDP são o Skype (em breve será retirado) e o Microsoft Teams. O Teams usa UDP para tráfego de streaming, incluindo áudio, vídeo e compartilhamento de apresentação. O tráfego de streaming está em tempo real, como quando você está tendo uma reunião online com voz, vídeo e apresentação de apresentações ou demonstrações. Eles usam UDP porque, se os pacotes são descartados ou chegam fora de ordem, ele é praticamente inatingível pelo usuário e o fluxo pode continuar.

Quando você não permite o tráfego UDP de saída de clientes para o serviço, eles podem voltar a usar o TCP. Porém, se um pacote TCP for *descartado,* tudo será interrompido até que o Tempo Final de Retransmissão (RTO) expire e o pacote ausente possa ser retransmitido. Se um pacote chegar fora de ordem, tudo será interrompido até que os outros pacotes cheguem e possam ser reavaliados em ordem. Ambos levam a falhas perceptíveis no áudio (lembra-se de Max Headroom?) e vídeo (você clicou em algo... oh, there is) and lead to poor performance and a bad user experience. E lembre-se do que eu disse acima sobre proxies? Ao forçar um cliente teams a usar um proxy, você o força a usar TCP. Agora você está causando impactos negativos no desempenho duas vezes.

### <a name="split-tunneling-may-seem-scary"></a>O túnel dividido pode parecer estranho

Mas não é. Todas as conexões com o Office 365 são por TLS. Estamos oferecendo o TLS 1.2 há algum tempo e desabilitaremos versões mais antigas em breve porque os clientes herdadas ainda as usam e isso é um risco.

Forçar uma conexão TLS, ou 32 delas, a passar por uma VPN antes de ir para o serviço não adiciona segurança. Ele adiciona latência e reduz a taxa de transferência geral. Em algumas soluções VPN, ele até força o UDP a fazer o túnel por meio de TCP, o que terá um impacto muito negativo sobre o tráfego de streaming. E, a menos que você esteja fazendo a inspeção TLS, não há nenhuma vantagem, todas as desvantagens. Um tema muito comum entre os clientes, agora que a maioria de sua força de trabalho é remota, é que eles estão vendo impactos significativos na largura de banda e no desempenho ao fazer com que todos os seus usuários se conectem usando uma VPN, em vez de configurar o túnel dividido para acessar os pontos de extremidade do [Office 365](https://docs.microsoft.com/microsoft-365/enterprise/microsoft-365-network-connectivity-principles#new-office-365-endpoint-categories)da categoria Otimizar.

É uma correção fácil de fazer com o túnel dividido, e é uma solução que você deve fazer. Para saber mais, certifique-se de revisar a otimização da conectividade do [Office 365](https://docs.microsoft.com/microsoft-365/enterprise/microsoft-365-vpn-split-tunnel)para usuários remotos usando o túnel dividido de VPN.

## <a name="the-sins-of-the-past"></a>Os erros do passado

Muitas vezes, o motivo pelo qual são feitas escolhas ruins vem de uma combinação de (1) não saber como o serviço funciona, (2) tentar aderir às políticas da empresa que foram escritas antes de adotar a nuvem e (3) equipes de segurança que podem não ser facilmente conscientes de que há mais de uma maneira de atingir suas metas. Esperamos que o acima e os links abaixo ajudarão com o primeiro. Talvez seja necessário ter apoio executivo para passar do segundo. Abordar as metas das políticas de segurança, em vez de seus métodos, ajuda com o terceiro. Desde o acesso condicional à moderação de conteúdo, DLP à proteção de informações, validação de ponto de extremidade a ameaças de dia zero — qualquer meta final que uma política de segurança razoável possa ter pode ser realizada com o que está disponível no Office 365 e sem nenhuma dependência de engrenagem de rede local, túnel VPN forçado e interrupção e inspeção TLS.

Em outras ocasiões, o hardware que foi dimensionado e comprado antes de a organização começar a se mover para a nuvem simplesmente não pode ser dimensionado para lidar com os novos padrões de tráfego e cargas. Se você realmente precisa rotear todo o tráfego por um único ponto de saída e/ou proxy, esteja preparado para atualizar o equipamento de rede e a largura de banda de acordo. Monitore cuidadosamente a utilização em ambos, pois a experiência não diminuirá lentamente à medida que mais usuários se integrarem. Tudo ficará bem até que o ponto de desleição seja atingido e todos sejam prejudicados.

## <a name="exceptions-to-the-rules"></a>Exceções às regras

Se a [](https://docs.microsoft.com/azure/active-directory/manage-apps/tenant-restrictions)sua organização exigir restrições de locatário, você precisará usar um proxy com quebra de TLS e inspeção para forçar algum tráfego por meio do proxy, mas não é necessário forçar todo o tráfego por meio dele.  Não é uma proposta de tudo ou nada, portanto, preste atenção no que precisa ser modificado pelo proxy.

Se você for permitir o tunelamento dividido, mas também usar um proxy para o tráfego da Web geral, certifique-se de que seu arquivo PAC defina o que deve ser direto, bem como definirá o tráfego interessante para o que passa pelo túnel VPN. Oferecemos arquivos PAC de exemplo [https://aka.ms/ipaddrs](https://aka.ms/ipaddrs) para facilitar o gerenciamento.

## <a name="conclusion"></a>Conclusão

Dezenas de milhares de organizações, incluindo quase todas as empresas da Fortune 500, usam o Office 365 todos os dias para suas funções críticas de missão. Eles fazem isso com segurança, e fazem isso pela Internet.

Independentemente das metas de segurança que você tenha em jogo, existem maneiras de fazer isso, que não exigem conexões VPN, servidores proxy, quebra e inspeção de TLS ou saída centralizada da Internet para tirar o tráfego dos usuários da rede e para a nossa o mais rápido possível, o que oferece o melhor desempenho, seja sua rede seja a sede da empresa, um escritório remoto ou que o usuário que trabalha em casa. Nossas diretrizes são baseadas em como os serviços do Office 365 são construídos e para garantir uma experiência de usuário segura e com desempenho.

## <a name="further-reading"></a>Leituras posteriores

[Os princípios de conectividade de rede do Office 365](https://docs.microsoft.com/microsoft-365/enterprise/microsoft-365-network-connectivity-principles)

[URLs e intervalos de endereços IP do Office 365](https://docs.microsoft.com/microsoft-365/enterprise/urls-and-ip-address-ranges)

[Gerenciar pontos de extremidade do Office 365](https://docs.microsoft.com/microsoft-365/enterprise/managing-office-365-endpoints)

[URL do serviço Web e endereço IP do Office 365](https://docs.microsoft.com/microsoft-365/enterprise/microsoft-365-ip-web-service)

[Avaliando a conectividade de rede do Office 365](https://docs.microsoft.com/microsoft-365/enterprise/assessing-network-connectivity)

[Rede do Office 365 e ajuste de desempenho](https://docs.microsoft.com/microsoft-365/enterprise/network-planning-and-performance)

[Avaliando a conectividade de rede do Office 365](https://docs.microsoft.com/microsoft-365/enterprise/assessing-network-connectivity)

[Ajuste de desempenho do Office 365 usando linhas de base e histórico de desempenho](https://docs.microsoft.com/microsoft-365/enterprise/performance-tuning-using-baselines-and-history)

[Plano de solução de problemas de desempenho do Office 365](https://docs.microsoft.com/microsoft-365/enterprise/performance-troubleshooting-plan)

[Redes de Distribuição de Conteúdo](https://docs.microsoft.com/microsoft-365/enterprise/content-delivery-networks)

[Teste de conectividade do Microsoft 365](https://connectivity.office.com/)

[Como a Microsoft cria sua rede global confiável e rápida](https://azure.microsoft.com/blog/how-microsoft-builds-its-fast-and-reliable-global-network/)

[Blog de rede do Office 365](https://techcommunity.microsoft.com/t5/office-365-networking/bd-p/Office365Networking)

[Conectividade do Office 365 para usuários remotos usando túnel dividido de VPN](https://docs.microsoft.com/microsoft-365/enterprise/microsoft-365-vpn-split-tunnel)


