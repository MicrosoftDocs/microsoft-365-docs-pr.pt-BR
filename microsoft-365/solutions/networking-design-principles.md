---
title: Rede (para a nuvem) — ponto de vista de um arquiteto
description: Descrição.
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
ms.openlocfilehash: 778693787c3d26806b02a2ffbde57e3347326d87
ms.sourcegitcommit: 0f71042edc7c3a7f10a7b92e1943abf51532cbf5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/29/2020
ms.locfileid: "46522260"
---
# <a name="networking-up-to-the-cloud--one-architects-viewpoint"></a>Rede (para a nuvem) — ponto de vista de um arquiteto

Neste artigo, [Ed Fisher](https://www.linkedin.com/in/edfisher/), Security & arquiteto de conformidade da Microsoft, descreve como otimizar sua rede para conectividade de nuvem, evitando as armadilhas mais comuns. 

## <a name="about-the-author"></a>Sobre o autor

![Foto Fisher de Ed](../media/solutions-architecture-center/ed-fisher-networking.jpg) 

No momento, sou especialista técnico principal na região sul leste com foco em segurança & conformidade. Trabalhei com clientes migrando para o Office 365 nos últimos dez anos. Trabalhei com lojas menores com vários locais para agências governamentais e empresas com milhões de usuários distribuídos em todo o mundo, e muitos outros clientes entre o, com a maioria com dezenas de milhares de usuários, vários locais em várias partes do mundo, a necessidade de um nível maior de segurança e uma infinidade de requisitos de conformidade. Eu ajudei centenas de empresas e milhões de usuários a migrar para a nuvem de forma segura e segura.

Com um plano de fundo nos últimos 25 anos, que inclui segurança, infraestrutura e engenharia de rede, e ter movido dois dos meus empregadores anteriores para o Office 365 antes de ingressar na Microsoft, estou no seu lado da tabela há muito tempo e lembrar o que é como. Embora dois clientes nunca sejam os mesmos, a maioria tem necessidades semelhantes e, ao consumir um serviço padronizado, como qualquer plataforma SaaS ou PaaS, as melhores abordagens tendem a ser as mesmas.



## <a name="its-not-the-network--its-how-youre-misusing-it"></a>Não é a rede, é assim que você está (MIS) usando!

Independentemente de quantas vezes isso acontecer, ele nunca falhará em Amaze comigo como equipes de segurança e equipes de rede *Creative* tentam saber como eles acham que devem se conectar aos serviços do Microsoft Cloud. Há sempre uma política de segurança, um padrão de conformidade ou uma maneira melhor que eles insistem em usar, sem a necessidade de participar de uma conversa sobre o que está tentando realizar, ou *como* elas são melhores, mais fáceis, mais econômicas e mais econômicos, e mais maneiras de fazer isso. 

Quando esse tipo de coisa é escalonado para mim, eu geralmente desejo pegar o desafio e orientá-lo pelo hows e pelo Whys e obtê-los para onde eles precisam ser. No entanto, se eu estiver sendo totalmente Francisco, eu preciso compartilhar isso algumas vezes quero permitir que eles façam o que eles desejam e volte a dizer que eu o informaria quando finalmente concede não funcionarem. Convém fazer isso às vezes, mas *não*consigo. O que eu faço é tentar explicar tudo o que eu vou incluir nesta postagem. Independentemente de sua função, se sua organização quiser usar os serviços de nuvem da Microsoft, provavelmente há algo em que a seguir pode ajudá-lo.


## <a name="guiding-principles"></a>Princípios de orientação
Vamos começar com algumas regras básicas em torno do que estamos fazendo aqui. Estamos discutindo como se conectar com segurança aos serviços em nuvem para garantir a complexidade mínima e o desempenho máximo, mantendo a segurança real. Nenhum dos itens a seguir é contador para qualquer um deles, mesmo se você ou seu cliente, não terá que usar seu servidor de proxy favorito para tudo.

- **Só porque você pode, não significa que você deve** ou parafraser o Dr. Ian Malcolm do Jurassic Park Movie ". . . Sim, sim, mas sua equipe de segurança foi, portanto, desocupada com o fato de não ter sido ou não de que eles parem de pensar se deveriam. "    
- A **segurança não significa complexidade** , pois você não é mais seguro apenas porque você gasta mais dinheiro, roteia mais dispositivos ou clica em mais botões.
- O **office 365 é acessado pela Internet** , mas não é a mesma coisa que o Office 365 é a Internet. É um serviço SaaS gerenciado pela Microsoft e administrado por você. Ao contrário dos sites que você visita na Internet, você realmente pode exibir o Curtain e aplicar os controles de que precisa para atender às suas políticas e aos seus padrões de conformidade, contanto que entenda que, enquanto você pode atender aos seus objetivos, você pode simplesmente fazer isso de uma maneira diferente.
- **Chokepoints são bons, as intervisões localizadas são boas** , todas as pessoas sempre querem backhaulr todo o tráfego da Internet para todos os seus usuários para um ponto central, geralmente para que eles possam monitorá-lo e impor a política, mas geralmente porque ele é mais barato do que provisionar o acesso à Internet em todos os seus locais ou é apenas como eles fazem isso. Mas esses chokepoints são exatamente isso... pontos onde os obstruções de tráfego. Não há nada errado para impedir que os usuários naveguem para vídeos de Instagram ou de gato de streaming, mas não tratem seu tráfego de aplicativos de negócios de missão crítica da mesma maneira.
- **Se o DNS Ain't estiver satisfeito, ain't nada feliz** – a melhor rede projetada pode ser HAMSTRUNG por DNS ruim, seja por meio de recorrência de solicitações para servidores em outras áreas do mundo ou usando servidores DNS do seu ISP ou outros servidores DNS públicos que armazenam informações de resolução de DNS. 
- **Só porque é assim que você costumava fazer isso, não significa que é assim que você deve fazer isso agora** — a tecnologia muda constantemente e o Office 365 não é uma exceção. A aplicação de medidas de segurança que foram desenvolvidas e implantadas para os serviços locais ou para controlar a navegação na Web não fornece o mesmo nível de garantia de segurança e pode ter um impacto negativo significativo sobre o desempenho.
- **O Office 365 foi criado para ser acessado pela Internet** , isso é resumido. Não importa o que você queira fazer entre seus usuários e sua borda, o tráfego ainda passará pela Internet quando ele deixar sua rede e antes de chegar ao nosso. Mesmo que você esteja usando o Azure ExpressRoute para rotear o tráfego sensível à latência da sua rede diretamente para o nosso, a conectividade com a Internet é absolutamente necessária. Aceitá-lo. Não pense nisso.

## <a name="where-bad-choices-are-often-made"></a>Onde as opções ruins costumam ser feitas

Embora haja muitas casas em que as decisões ruins são feitas no nome da segurança, essas são as que eu encontrei com mais frequência com os clientes. Muitas conversas de clientes envolvem todas elas ao mesmo tempo.

### <a name="insufficient-resources-at-the-edge"></a>Recursos insuficientes na borda
Muito poucos clientes estão implantando ambientes do Greenfield e têm anos de experiência com a forma como os usuários trabalham e qual é o egresso da Internet. Se os clientes têm servidores proxy ou permitem o acesso direto e o tráfego de saída de NAT, eles estão fazendo isso por anos e não considerem o quanto mais eles começarão por toda a sua borda à medida que moverem os aplicativos internos tradicionalmente para a nuvem.

A largura de banda é sempre uma preocupação, mas os dispositivos NAT podem não ter potência suficiente para lidar com a carga elevada e começar a fechar prematuramente as conexões para liberar recursos. A maior parte do software cliente que se conecta ao Office 365 espera que as conexões persistentes e um usuário usando totalmente o Office 365 podem ter 32 ou mais conexões simultâneas. Se o dispositivo NAT estiver descartando-o prematuramente, esses aplicativos podem não responder à medida que tentarem usar as conexões que não estão mais lá. Quando eles desistir e tentar estabelecer novas conexões, eles colocam ainda mais carga no seu equipamento de rede.

### <a name="localized-breakout"></a>Debates localizada
Tudo o que mais nesta lista se resume a um único motivo: a desativação da sua rede e em nossas coisas o mais rápido possível. A reversão do tráfego dos usuários para um ponto de saída central, especialmente quando esse ponto de egresso está em outra região do que os usuários estão, apresenta latência desnecessária e impacta tanto a experiência do cliente quanto as velocidades de download. A Microsoft tem pontos de presença em todo o mundo com front-ends para todos os nossos serviços e emparelhamento estabelecido com quase todos os principais ISPs, portanto, o roteamento do tráfego dos usuários *localmente* garante que ele chegue à nossa rede rapidamente com latência mínima. 

### <a name="dns-resolution-traffic-should-follow-the-internet-egress-path"></a>O tráfego de resolução de DNS deve seguir o caminho de egresso da Internet
Obviamente, para um cliente localizar qualquer ponto de extremidade, ele precisa usar o DNS. Os servidores DNS da Microsoft avaliam a origem das solicitações de DNS para garantir que possamos retornar a resposta, em termos da Internet, mais próximo da origem da solicitação. Certifique-se de que o DNS está configurado de modo que as solicitações de resolução de nome tenham o mesmo caminho que o tráfego dos seus usuários, Lest você forneça a saída local, mas para um ponto de extremidade em outra região. Isso significa permitir que os servidores DNS locais "Vá para raiz" em vez de encaminhar para servidores DNS em data centers remotos. E tome cuidado com os serviços DNS públicos e privados, que podem armazenar em cache os resultados de uma parte do mundo e servir a solicitações de outras partes do mundo.

### <a name="to-proxy-or-not-to-proxy-that-is-the-question"></a>Para proxy ou não para proxy, esta é a pergunta
Uma das primeiras coisas a considerar é se as conexões dos usuários de proxy para o Office 365. Essa é uma tarefa fácil; Não proxy. O Office 365 é acessado pela Internet, mas não é a Internet. É uma extensão de seus serviços principais e deve ser tratada como tal. Tudo o que você pode desejar para fazer um proxy, como DLP ou Antimalware ou inspeção de conteúdo, já está disponível para você no serviço e pode ser usado em escala e sem a necessidade de violar as conexões criptografadas por TLS. Mas se você realmente quiser o tráfego de proxy que não é possível controlar, preste atenção às nossas diretrizes em [https://aka.ms/pnc](https://aka.ms/pnc) e nas categorias de tráfego em [https://aka.ms/ipaddrs](https://aka.ms/ipaddrs) . Temos três categorias de tráfego para o Office 365. Otimizar e permitir realmente deve ir direto e ignorar seu proxy. O padrão pode ser de proxy. Os detalhes estão nesses documentos. . . lê-los.

A maioria dos clientes que insistim em usar um proxy, quando eles realmente confiram o que estão fazendo, se você perceber que quando o cliente faz uma solicitação de conexão HTTP para o proxy, o proxy agora é apenas um roteador adicional caro. Os protocolos em uso como MAPI e RTC não são nem mesmo protocolos que os proxies da Web entendem, portanto, mesmo com o uso de TLS, você não está obtendo nenhuma segurança extra. Você *está* obtendo uma latência extra. Confira [https://aka.ms/pnc](https://aka.ms/pnc) mais informações sobre isso, incluindo as categorias otimizar, permitir e padrão para o tráfego do Microsoft 365.

Por fim, considere o impacto geral no proxy e sua resposta correspondente para lidar com esse impacto. À medida que mais e mais conexões são feitas por meio do proxy, ela pode diminuir o fator de escala TCP para que não seja necessário armazenar em buffer tantos tráfego. Já vi clientes onde seus proxies estavam muito sobrecarregados que estavam usando um fator de escala de 0. Como o fator de escala é um valor exponencial e gostaríamos de usar 8, cada redução no valor do fator de escala é um impacto negativo significativo para a taxa de transferência.

A inspeção de TLS significa segurança! Mas não realmente! Muitos clientes com proxies desejam usá-los para inspecionar todo o tráfego e isso significa "quebrar e inspecionar" TLS. Quando você faz isso para um site acessado via HTTPS (preocupações com privacidade não obstante), seu proxy pode ter que fazer isso para dez ou até vinte fluxos simultâneos por algumas centenas de milissegundos. Se houver um grande download ou talvez um vídeo envolvido, uma ou mais dessas conexões podem durar muito mais, mas no todo, a maioria das conexões estabelece, transfere e fechou muito rapidamente. Executar Break e inspecionar significa que o proxy deve fazer o dobro do trabalho. Para cada conexão do cliente com o proxy, o proxy também deve fazer uma conexão separada de volta para o ponto de extremidade. Portanto, se tornar dois, dois se tornará quatro, 32 se tornará 64. . . Confira onde estou indo? Você provavelmente já dimensionou sua solução de proxy para uma navegação típica na Web, mas quando tenta fazer o mesmo para conexões de cliente com o Office 365, o número de conexões simultâneas e de longa duração pode ser uma ordem maior do que o que você dimensiona para.

### <a name="streaming-isnt-important-except-that-it-is"></a>O streaming não é importante, exceto que *é*
Os únicos serviços no Office 365 que usam UDP são o Skype (em breve a ser desativado) e o Microsoft Teams. O Microsoft Teams usa o UDP para tráfego de streaming, incluindo compartilhamento de áudio, vídeo e apresentação. O tráfego de streaming é dinâmico, como quando você está tendo uma reunião online com voz, vídeo e apresentação de slides ou executando demonstrações. Eles usam UDP porque, se os pacotes são descartados ou enviados fora da ordem, eles são praticamente não percebidos pelo usuário, e o fluxo pode simplesmente continuar indo. 

Quando você não permite o tráfego UDP de saída dos clientes para o serviço, eles podem retornar ao uso do TCP. Mas, se um pacote TCP for descartado, *tudo parará* até que o tempo limite de retransmissão (RTO) expire e o pacote ausente possa ser retransmitido. Se um pacote chegar fora de ordem, tudo será interrompido até que os outros pacotes cheguem e possam ser remontados em ordem. Ambos levam a problemas perobservados no áudio (Lembre-se de espaço máximo?) e vídeo (você clicar em someth. . . Ah, é possível) e levar a um desempenho ruim e uma experiência de usuário ruim. E lembra o que eu coloquei acima sobre proxies? Ao forçar um cliente do teams a usar um proxy, você o força a usar TCP. Portanto, agora você está causando impactos de desempenho negativos duas vezes.

### <a name="split-tunneling-may-seem-scary"></a>O tunelamento dividido pode parecer assustador
Mas não é. Todas as conexões com o Office 365 estão em TLS. Temos o TLS 1,2 por um tempo tão demorado e estará desabilitando versões mais antigas em breve, já que os clientes herdados ainda as usam e isso é um risco.

Forçar uma conexão TLS ou 32 delas, para passar por uma VPN antes de ir para o serviço não adiciona segurança. Ele adiciona latência e reduz a produtividade geral. Em algumas soluções VPN, isso força o UDP a encapsular por meio do TCP, que novamente terá um impacto muito negativo no tráfego de streaming. E, a menos que você esteja fazendo a inspeção de TLS, não há nenhuma vantagem. Um tema muito comum entre os clientes do presente, agora que a maior parte de sua força de vida é remota, é o fato de que eles estão obtendo grandes larguras de banda e impactos de desempenho para fazer com que todos os usuários se conectem usando uma VPN, em vez de configurar o encapsulamento de divisão para acesso [otimizando os pontos de extremidade do Office 365](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#new-office-365-endpoint-categories).

É uma correção fácil de fazer o tunelamento dividido e é um que você deve fazer. Para saber mais, não se esqueça de revisar [otimizar a conectividade do Office 365 para usuários remotos usando o túnel dividido VPN](https://docs.microsoft.com/office365/enterprise/office-365-vpn-split-tunnel).


## <a name="the-sins-of-the-past"></a>O capitais do passado
Muitas vezes, o motivo pelo qual as escolhas ruins são feitas é proveniente de uma combinação de (1) não saber como funciona o serviço, (2) a tentativa de cumprir as políticas da empresa que foram escritas antes de adotar a nuvem e (3) equipes de segurança que talvez não consigam ser facilmente contratados de uma maneira de atingir seus objetivos. Espero que o acima e os links abaixo ajudem a usar o primeiro. O patrocínio executivo pode ser necessário para obter o segundo. Atender às metas de políticas de segurança, em vez de seus métodos, ajuda no terceiro. Do acesso condicional à moderação do conteúdo, DLP para proteção de informações, validação de ponto de extremidade para ameaças de zero dias — qualquer objetivo final, uma política de segurança razoável pode ter sido realizada com o que está disponível no Office 365 e sem qualquer dependência sobre o equipamento de rede local, túneis VPN forçados e interrupção e inspeção de TLS. 

Outros horários, hardware que foram dimensionados e comprados antes da organização começar a migrar para a nuvem simplesmente não podem ser dimensionados para lidar com os novos padrões e cargas de tráfego. Se você realmente deve encaminhar todo o tráfego por um único ponto de egresso e/ou proxy, esteja preparado para atualizar o equipamento de rede e a largura de banda de acordo. Monitore cuidadosamente a utilização em ambos, pois a experiência não diminuirá lentamente à medida que mais usuários. Tudo ficará bem até que o ponto de concessão seja atingido, e todos sofrem. 

## <a name="exceptions-to-the-rules"></a>Exceções às regras

Se sua organização exigir [restrições de locatário](https://docs.microsoft.com/azure/active-directory/manage-apps/tenant-restrictions), você precisará usar um proxy com interrupção de TLS e inspecionar para forçar algum tráfego por meio do proxy, mas não é necessário forçar todo o tráfego por meio dele.  Não se trata de uma proposta de tudo ou nada, portanto, preste atenção ao que precisa ser modificado pelo proxy. 

Se você for permitir o tunelamento dividido, mas também usar um proxy para tráfego da Web geral, certifique-se de que o arquivo de PAC define o que deve ser direto e como definir o tráfego interessante para o que passa pelo túnel VPN. Oferecemos exemplos de arquivos de PAC [https://aka.ms/ipaddrs](https://aka.ms/ipaddrs) que facilitarão o gerenciamento.

## <a name="conclusion"></a>Conclusão

Dezenas de milhares de organizações, incluindo quase toda a Fortune 500, usam o Office 365 diariamente para suas funções de missão crítica. Eles fazem isso de forma segura e fazem isso através da Internet.

 Não importa as metas de segurança que você tem em jogo, há maneiras de realizá-las que não exigem conexões VPN, servidores de proxy, interrupção de TLS e inspecionar, ou saída de Internet centralizada para obter o tráfego de seus usuários para fora da rede e para o nosso, de forma mais rápida possível, o que oferece o melhor desempenho, seja a rede Headquarters, um escritório remoto ou que o usuário esteja trabalhando em casa. Nossas diretrizes são baseadas em como os serviços do Office 365 são criados e para garantir uma experiência de usuário segura e com desempenho.

## <a name="further-reading"></a>Leitura adicional

[Os princípios de conectividade de rede do Office 365](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles)

[URLs e intervalos de endereços IP do Office 365](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges?redirectSourcePath=%252fen-us%252farticle%252fOffice-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2)

[Gerenciar pontos de extremidade do Office 365](https://docs.microsoft.com/office365/enterprise/managing-office-365-endpoints)

[URL do serviço Web e endereço IP do Office 365](https://docs.microsoft.com/office365/enterprise/office-365-ip-web-service)

[Avaliando a conectividade de rede do Office 365](https://docs.microsoft.com/office365/enterprise/assessing-network-connectivity)

[Rede do Office 365 e ajuste de desempenho](https://docs.microsoft.com/office365/enterprise/network-planning-and-performance)

[Avaliando a conectividade de rede do Office 365](https://docs.microsoft.com/office365/enterprise/assessing-network-connectivity)

[Ajuste de desempenho do Office 365 usando linhas de base e histórico de desempenho](https://docs.microsoft.com/office365/enterprise/performance-tuning-using-baselines-and-history)

[Plano de solução de problemas de desempenho do Office 365](https://docs.microsoft.com/office365/enterprise/performance-troubleshooting-plan)

[Redes de Distribuição de Conteúdo](https://docs.microsoft.com/office365/enterprise/content-delivery-networks)

[Teste de conectividade do Microsoft 365](https://connectivity.office.com/)

[Como a Microsoft cria sua rede global rápida e confiável](https://azure.microsoft.com/blog/how-microsoft-builds-its-fast-and-reliable-global-network/)

[Blog de rede do Office 365](https://techcommunity.microsoft.com/t5/office-365-networking/bd-p/Office365Networking)

[Conectividade do Office 365 para usuários remotos usando o túnel dividido VPN](https://docs.microsoft.com/office365/enterprise/office-365-vpn-split-tunnel)


