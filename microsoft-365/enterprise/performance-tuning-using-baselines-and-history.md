---
title: Ajuste de desempenho do Office 365 usando linhas de base e histórico de desempenho
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 8/31/2017
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: 1492cb94-bd62-43e6-b8d0-2a61ed88ebae
ms.collection:
- M365-security-compliance
- Ent_O365
- SPO_Content
description: Saiba como verificar o histórico de suas conexões de computador cliente para ajudá-lo a detectar problemas emergentes mais cedo.
ms.openlocfilehash: 2337b14542f894e9a62037b2f032632147e45e09
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46687184"
---
# <a name="office-365-performance-tuning-using-baselines-and-performance-history"></a>Ajuste de desempenho do Office 365 usando linhas de base e histórico de desempenho

Há algumas maneiras simples de verificar o desempenho da conexão entre o Office 365 e sua empresa que permitirão que você estabeleça uma linha de base aproximada de sua conectividade. Conhecer o histórico de desempenho de suas conexões de computador cliente pode ajudá-lo a detectar problemas emergentes com início antecipado, identificar e prever problemas.
  
Se você não estiver acostumado a trabalhar em problemas de desempenho, este artigo foi projetado para ajudá-lo a considerar algumas perguntas comuns, como como saber se o problema que está vendo é um problema de desempenho e não um incidente de serviço do Office 365? Como planejar um bom desempenho, longo prazo? Como você pode manter um olho no desempenho? Se sua equipe ou clientes estão vendo um desempenho lento ao usar o Office 365 e você quer saber mais sobre qualquer uma dessas perguntas, continue lendo.
  
> [!IMPORTANT]
> **Tem um problema de desempenho entre seu cliente e o Office 365 no momento?** Siga as etapas descritas no plano [de solução de problemas de desempenho do Office 365.](performance-troubleshooting-plan.md) 
    
## <a name="something-you-should-know-about-office-365-performance"></a>Algo que você deve saber sobre o desempenho do Office 365

O Office 365 reside em uma rede da Microsoft dedicada de alta capacidade que é monitorada constantemente não apenas pela automação, mas por pessoas reais. Parte da função de manter a nuvem do Office 365 é criar ajuste de desempenho e alinhá-lo onde for possível. Como os clientes da nuvem do Office 365 têm que se conectar pela Internet, há um esforço contínuo para ajustar o desempenho nos serviços do Office 365 também. As melhorias de desempenho nunca param na nuvem, e há muita experiência acumulada com a manutenção da nuvem saudável e rápida. Caso você tenha um problema de desempenho ao se conectar de sua localização ao Office 365, é melhor não começar com e aguardar um caso de suporte. Em vez disso, você deve começar a investigar o problema "de dentro para fora". Ou seja, comece dentro de sua rede e saia do Office 365. Antes de abrir um caso com o Suporte do Office 365, você pode coletar dados e tomar ações que explorarão e poderão resolver seu problema.
  
> [!IMPORTANT]
> Esteja ciente do planejamento de capacidade e dos limites no Office 365. Essas informações o colocarão à frente da curva ao tentar resolver um problema de desempenho. Aqui está um link para as descrições de serviço do [Microsoft 365 e Office 365.](https://docs.microsoft.com/office365/servicedescriptions/office-365-service-descriptions-technet-library) Este é um hub central e todos os serviços oferecidos pelo Office 365 têm um link que vai para suas próprias Descrições de Serviço a partir daqui. Isso significa que, caso precise ver os limites padrão do SharePoint Online, por exemplo, você clicaria em Descrição do Serviço do [SharePoint Online](https://technet.microsoft.com/library/sharepoint-online-service-description.aspx) e localizaria sua seção limites do [SharePoint Online.](https://go.microsoft.com/fwlink/p/?LinkID=856113) 
  
Certifique-se de entrar em sua solução de problemas com a compreensão de que o desempenho é uma escala de deslizamento, não se trata de atingir um valor fixo e mantê-lo permanentemente (se você acredita que isso é assim, então tarefas ocasionais de alta largura de banda, como a reativação de um grande número de usuários ou a realização de grandes migrações de dados, serão muito difíceis ; portanto, planeje impactos no desempenho então). Você pode e deve ter uma ideia aproximada de suas metas de desempenho, mas muitas variáveis têm desempenho, portanto, o desempenho varia. Essa é a natureza do desempenho. 
  
A solução de problemas de desempenho não se trata de cumprir metas específicas e manter esses números indefinidamente, mas sim melhorar as atividades existentes, considerando todas as variáveis. 
  
## <a name="okay-what-does-a-performance-problem-look-like"></a>Qual é a aparência de um problema de desempenho?

Primeiro, você precisa certificar-se de que o que você está enfrentando é realmente um problema de desempenho e não um incidente de serviço. Um problema de desempenho é diferente de um incidente de serviço no Office 365. Veja como diferencia-los.
  
Se o serviço do Office 365 estiver com problemas, isso é um incidente de serviço. Você verá ícones vermelhos ou amarelos em Current **health** in the Microsoft 365 admin center, you may also notice slow performance on client computers connecting to Office 365. Por exemplo, se a saúde atual  relata um ícone vermelho e você vir Investigando ao lado do Exchange, você também pode receber várias chamadas de pessoas em sua organização que reclamam que as caixas de correio do cliente que usam o Exchange Online estão com desempenho ruim. Nesse caso, é razoável presumir que seu desempenho do Exchange Online acabou de se tornar uma vítima de problemas dentro do Serviço. 
  
![O painel De saúde do Office 365 com todas as cargas de trabalho em verde, exceto o Exchange, que mostra o Serviço Restaurado.](../media/ec7f0325-9e61-4e1a-bec0-64b87f4469be.PNG)
  
Neste ponto, você, o administrador do Office  365, deve verificar a saúde atual e, em seguida, exibir detalhes e **histórico,** frequentemente, para se manter atualizado sobre a manutenção que executamos no sistema. O **painel de** saúde Atual foi feito para atualizá-lo sobre alterações e problemas no serviço. As anotações e explicações escritas no histórico de saúde, administrador para administrador, estão lá para ajudá-lo a medir seu impacto e para mantê-lo postado sobre o trabalho contínuo. 
  
![Uma imagem do painel de saúde do Office 365 explicando que o serviço do Exchange Online foi restaurado e por quê.](../media/66609554-426a-4448-8be6-ea09817f41ba.PNG)
  
Um problema de desempenho não é um incidente de serviço, mesmo que os incidentes possam causar um desempenho lento. Um problema de desempenho tem esta aparência:
  
- Ocorre um problema de desempenho, independentemente do que o centro de administração **Atual está** relatando para o serviço. 
    
-  Um comportamento que costumava ser relativamente contínuo leva muito tempo para ser concluído ou nunca é concluído. 
    
- Você também pode replicar o problema ou, pelo menos, você sabe que isso acontecerá se você fizer a série de etapas correta.
    
-  Se o problema for intermitente, ainda haverá um padrão, por exemplo, você sabe que, às 10:00, você terá chamadas de usuários que não podem acessar o Office 365 de forma confiável e que as chamadas vão cair ao redor do meio-dia. 
    
Isso provavelmente parece familiar; talvez muito familiar. Depois de saber que é um problema de desempenho, a pergunta será: "O que fazer em seguida?" O restante deste artigo ajuda você a determinar exatamente isso.
  
## <a name="how-to-define-and-test-the-performance-problem"></a>Como definir e testar o problema de desempenho

Problemas de desempenho geralmente surgem ao longo do tempo, portanto, pode ser desafiador definir o problema real. Você precisa criar uma boa declaração de problema e uma boa ideia do contexto do problema e, em seguida, você precisa realizar etapas de teste repetidos para ganhar o dia. Caso contrário, por sua própria falha, você poderá ser perdido. Por quê? Aqui estão alguns exemplos de declarações de problemas que não fornecem informações suficientes:
  
- Alternar da minha Caixa de Entrada para o Meu Calendário costumava ser algo que eu não notei e agora é uma pausa para café. Você pode fazê-lo agir como antes?
    
- Carregar meus arquivos no SharePoint Online está demorando muito. Por que é lento na ocasião, mas a qualquer momento, ela é rápida? Não pode ser apenas rápido?
    
Há vários desafios grandes colocados pelas instruções de problema acima. Especificamente, há muitas ambiguidades com as que lidar. por exemplo:
  
- Não está claro como alternar entre a Caixa de Entrada e o Calendário usado para agir no laptop.
    
- Quando o usuário diz, "Não pode ser apenas rápido", o que é "rápido"?
    
- Quanto tempo é "para sempre"? Isso é de vários segundos ou minutos, ou o usuário pode ir para o almoço e terminaria dez minutos depois que o usuário voltasse?
    
Tudo isso sem considerar que o administrador e a solução de problemas não podem estar cientes de muitos detalhes de declarações do problema como estas. Por exemplo, quando o problema começou a acontecer; Que o usuário trabalha em casa e só vê uma troca lenta enquanto estiver em uma rede local; Que o usuário deve executar vários outros aplicativos intensivos de RAM no cliente local, ou que o usuário está executando um sistema operacional mais antigo ou não tenha executado atualizações recentes.
  
Quando os usuários relatam um problema de desempenho, há muitas informações a coletar. Coletar essas informações faz parte de um processo chamado de definição de esquema ou investigação. Veja a seguir uma lista básica de avaliação que você pode usar para coletar informações sobre seu problema de desempenho. Essa lista não é exaustiva, mas é um local para iniciar uma de suas próprias: 
  
- Em qual data o problema ocorreu e em que hora do dia ou da noite?
    
- Que tipo de computador cliente você estava usando e como ele se conecta à rede comercial (VPN, com fio, sem fio)?
    
- Você estava trabalhando remotamente ou estava no escritório?
    
- Você tentou as mesmas ações em outro computador e viu o mesmo comportamento?
    
- Dê um passo a passo das etapas que estão lhe dando problemas para que você possa escrever as ações tomadas.
    
- O desempenho é lento em segundos ou em minutos?
    
- Onde você está localizado no mundo?
    
Algumas dessas perguntas são mais óbvias do que outras. A maioria das pessoas compreenderá que uma solução de problemas precisa das etapas exatas para reproduzir o problema. Afinal, de que outra forma você pode registrar o que há de errado e como você pode testar se o problema foi corrigido? Menos óbvio são coisas como "Qual data e hora você viu o problema?" e "Onde no mundo você está localizado?", informações que podem ser usadas em tandem. Dependendo de quando o usuário estava trabalhando, algumas horas de diferença de tempo podem significar que a manutenção já está em andamento em partes da rede da empresa. Se, por exemplo, sua empresa tiver uma implementação híbrida, como uma Pesquisa híbrida do SharePoint, que pode consultar índices de pesquisa no SharePoint Online e em uma instância do SharePoint Server 2013 local, as atualizações podem estar em andamento no farm local. Se sua empresa estiver toda na nuvem, a manutenção do sistema pode incluir a adição ou remoção de hardware de rede, a implantação de atualizações que abrangem toda a empresa, ou alterações no DNS ou outra infraestrutura principal.
  
Quando você está solucionando um problema de desempenho, é um pouco como uma cena de crime, você precisa ser preciso e observável para tirar conclusões da evidência. Para fazer isso, você deve obter uma boa declaração de problema coletando evidências. Ele deve incluir o contexto do computador, o contexto do usuário, quando o problema começou e as etapas exatas que exporam o problema de desempenho. Essa instrução do problema deve ser e permanecer na página superior em suas anotações. Ao passar pela declaração do problema novamente depois de trabalhar na resolução, você está tomando as medidas necessárias para testar e provar se as ações realizadas resolveram o problema. Isso é fundamental para saber quando seu trabalho é feito.
  
## <a name="do-you-know-how-performance-used-to-look-when-it-was-good"></a>Você sabe como o desempenho costumava ser quando era bom?

Se você estiver com medo, ninguém saberá. Ninguém tinha números. Isso significa que ninguém pode responder à pergunta simples "Sobre quantos segundos demorava para abrir uma Caixa de Entrada no Office 365?" ou "Quanto tempo demorava quando os executivos tinham uma reunião do Lync Online?", que é um cenário comum para muitas empresas.
  
O que está faltando aqui é uma linha de base de desempenho.
  
As linhas de base lhe dão um contexto para seu desempenho. Você deve fazer uma linha de base ocasionalmente com frequência, dependendo das necessidades da sua empresa. Se você for uma empresa maior, sua equipe de Operações pode já ter linhas de base para seu ambiente local. Por exemplo, se você corrigir todos os servidores do Exchange na primeira segunda-feira do mês e todos os servidores do SharePoint na terceira segunda-feira, sua equipe de Operações provavelmente terá uma lista de tarefas e cenários que executa após o patch, para provar que funções críticas estão operacionais. Por exemplo, abrir a Caixa de Entrada, clicar em Enviar/Receber e certificar-se de que as pastas são atualizadas ou, no SharePoint, navegar pela página principal do site, entrar na página De pesquisa corporativa e fazer uma pesquisa que retorna resultados.
  
Se seus aplicativos estão no Office 365, algumas das linhas de base mais fundamentais que você pode medir o tempo (em milissegundos) de um computador cliente dentro de sua rede, até um ponto de saída ou o ponto em que você sai da rede e vai para o Office 365. Aqui estão algumas linhas de base úteis que você pode investigar e registrar:
  
- Identifique os dispositivos entre o computador cliente e o ponto de saída, por exemplo, seu servidor proxy.
    
  - Você precisa conhecer seus dispositivos para que tenha contexto (endereços IP, tipo de dispositivo, etc.) para problemas de desempenho que surjam.
    
  - Os servidores proxy são pontos de saída comuns, portanto, você pode verificar seu navegador da Web para ver qual servidor proxy ele está definido para usar, se for o caso.
    
  - Há ferramentas de terceiros que podem descobrir e mapear sua rede, mas a maneira mais segura de saber seus dispositivos é pedir a um membro da sua equipe de rede.
    
- Identifique seu provedor de serviços de Internet (ISP), anote suas informações de contato e pergunte quantos circuitos você tem de largura de banda.
    
- Dentro de sua empresa, identifique recursos para os dispositivos entre seu cliente e o ponto de saída ou identifique um contato de emergência para falar sobre problemas de rede.
    
Aqui estão algumas linhas de base que os testes simples com ferramentas podem calcular para você:
  
- Tempo do computador cliente para o ponto de saída em milissegundos
    
- Tempo de sua saída para o Office 365 em milissegundos
    
- Local no mundo do servidor que resolve as URLs do Office 365 quando você navega
    
- A velocidade da resolução DNS do SEU ISP em milissegundos, inconsistências na chegada de pacotes (tremidos de rede), tempos de carregamento e download em milissegundos
    
Se você não estiver familiarizado com como executar essas etapas, entraremos em mais detalhes neste artigo. 
  
## <a name="what-is-a-baseline"></a>O que é uma linha de base?

Você conhecerá o impacto quando ele ficar ruim, mas se você não conhece seus dados históricos de desempenho, não é possível ter um contexto sobre o quão ruim isso pode ter sido e quando. Portanto, sem uma linha de base, você não tem a dica principal para resolver o quebra-cabeça: a imagem na caixa do quebra-cabeça. Na solução de problemas de desempenho, você precisa de um ponto de *comparação.* Linhas de base de desempenho simples não são difíceis de levar. Sua equipe de Operações pode ser a tarefa de realizar essas tarefas em um cronograma. Por exemplo, digamos que sua conexão se pareça com esta: 
  
![Um gráfico de rede básico mostrando o cliente, o proxy e a nuvem do Office 365.](../media/c6ca7140-09f9-4c2d-a775-dbf2820eaa0c.PNG)
  
Isso significa que você verificou com sua equipe de rede e descobriu que saiu da empresa para a Internet por meio de um servidor proxy, e esse proxy lida com todas as solicitações que seu computador cliente envia para a nuvem. Nesse caso, você deve desenhar uma versão simplificada da conexão que lista todos os dispositivos interveniáveis. Agora, insira as ferramentas que você pode usar para testar o desempenho entre o cliente, o ponto de saída (onde você deixa sua rede para a Internet) e a nuvem do Office 365.
  
![Rede básica com cliente, proxy e nuvem e sugestões de ferramentas PSPing, TraceTCP e rastreamentos de rede.](../media/627bfb77-abf7-4ef1-bbe8-7f8cbe48e1d2.png)
  
As opções são listadas **como Simples** e Avançada **devido** à quantidade de experiência necessária para encontrar os dados de desempenho. Um rastreamento de rede levará muito tempo, em comparação com a execução de ferramentas de linha de comando como PsPing e TraceTCP. Essas duas ferramentas de linha de comando foram escolhidas porque não usam pacotes ICMP, que serão bloqueados pelo Office 365 e porque eles dão o tempo em milissegundos necessário para sair do computador cliente ou servidor proxy (se você tiver acesso) e chegar ao Office 365. Cada salto individual de um computador para outro terminará com um valor de tempo, o que é ótimo para linhas de base! Além disso, essas ferramentas de linha de comando permitem que você adicione um número de porta ao comando, o que é útil porque o Office 365 se comunica pela porta 443, que é a porta usada pelo Secure Sockets Layer e pelo Transport Layer Security (SSL e TLS). No entanto, outras ferramentas de terceiros podem ser melhores soluções para sua situação. A Microsoft não dá suporte a todas essas ferramentas, portanto, se, por algum motivo, você não conseguir fazer psPing e TraceTCP funcionarem, vá para um rastreamento de rede com uma ferramenta como Netmon. 
  
Você pode fazer uma linha de base antes do horário comercial, novamente durante o uso intenso e depois novamente após o expediente. Isso significa que você pode ter uma estrutura de pastas um pouco parecida com esta no final:
  
![Gráfico que propõe uma maneira de organizar seus dados de desempenho em pastas.](../media/13e01ffa-f0f2-4d10-b89d-d5980ec89fae.png)
  
Você também deve escolher uma convenção de nomen por seus arquivos. Aqui estão alguns exemplos:
  
- Feb_09_2015_9amPST_PerfBaseline_Netmon_ClientToEgress_Normal
    
- Jan_10_2015_3pmCST_PerfBaseline_PsPing_ClientToO365_bypassProxy_SLOW
    
- Feb_08_2015_2pmEST_PerfBaseline_BADPerf
    
- Feb_08_2015_8-30amEST_PerfBaseline_GoodPerf
    
Há muitas maneiras diferentes de fazer isso, mas usar o formato **\<dateTime\>\<what's happening in the test\>** é um bom lugar para começar. Estar atento a isso ajudará muito quando você estiver tentando solucionar problemas mais tarde. Mais tarde, você poderá dizer "Eu fizemos dois rastreamentos em 8 de fevereiro, um mostrou bom desempenho e outro mostrou ruim, para que possamos compará-los". Isso é extremamente útil para a solução de problemas. 
  
Você precisa ter uma maneira organizada de manter suas linhas de base históricas. Neste exemplo, os métodos simples produziram três saídas de linha de comando e os resultados foram coletados como capturas de tela, mas você pode ter arquivos de captura de rede. Use o método que funciona melhor para você. Armazene suas linhas de base históricas e consulte-as em pontos em que você perceberá alterações no comportamento dos serviços online. 
  
## <a name="why-collect-performance-data-during-a-pilot"></a>Por que coletar dados de desempenho durante um piloto?

Não há melhor momento para começar a fazer linhas de base do que durante um piloto do serviço do Office 365. Seu escritório pode ter milhares de usuários, centenas de milhares ou pode ter cinco, mas, mesmo com um pequeno número de usuários, você pode realizar testes para medir flutuações no desempenho. No caso de uma grande empresa, uma amostra representativa de várias centenas de usuários que pilotam o Office 365 pode ser projetada para fora de vários milhares para que você saiba onde podem surgir problemas antes que ocorram.
  
No caso de uma pequena empresa, em que a reingressão significa que todos os usuários vão para o serviço ao mesmo tempo e não há piloto, mantenha as medidas de desempenho para que você tenha dados para mostrar a qualquer pessoa que possa ter que solucionar problemas de uma operação com mau desempenho. Por exemplo, se você perceber que, de uma forma repentina, você pode dar uma volta ao seu edifício no tempo necessário para carregar um gráfico de tamanho médio onde isso costumava acontecer muito rapidamente.
  
## <a name="how-to-collect-baselines"></a>Como coletar linhas de base

Para todos os planos de solução de problemas, você precisa identificar estes pontos no mínimo:
  
- O computador cliente que você está usando (o tipo de computador ou dispositivo, um endereço IP e as ações que causaram o problema)
    
- Onde o computador cliente está localizado no mundo (por exemplo, se esse usuário está em uma VPN para a rede, trabalhando remotamente ou na intranet da empresa)
    
- O ponto de saída que o computador cliente usa de sua rede (o ponto em que o tráfego deixa sua empresa para um ISP ou para a Internet)
    
 Você pode descobrir o layout da sua rede por meio do administrador de rede. Se você estiver em uma rede pequena, dê uma olhada nos dispositivos que o conectam à Internet e chame seu ISP se tiver dúvidas sobre o layout. Crie um gráfico do layout final para sua referência. 
  
Esta seção é dividida em métodos e ferramentas de linha de comando simples e opções de ferramentas mais avançadas. Primeiro, vamos abranger métodos simples. Mas se você tiver um problema de desempenho agora, você deve ir para métodos avançados e experimentar o exemplo de plano de ação de solução de problemas de desempenho.
  
### <a name="simple-methods"></a>Métodos simples

O objetivo desses métodos simples é aprender a tomar, entender e armazenar corretamente linhas de base de desempenho simples ao longo do tempo para que você seja informado sobre o desempenho do Office 365. Aqui está o diagrama muito simples para ser simples, como você já viu antes:
  
![Rede básica com cliente, proxy e nuvem e sugestões de ferramentas PSPing, TraceTCP e rastreamentos de rede.](../media/627bfb77-abf7-4ef1-bbe8-7f8cbe48e1d2.png)
  
> [!NOTE]
> TraceTCP está incluído nesta captura de tela porque é uma ferramenta útil para mostrar, em milissegundos, quanto tempo uma solicitação leva para processar e quantos saltos de rede ou conexões de um computador para o próximo, que a solicitação leva para chegar a um destino. TraceTCP também pode dar os nomes dos servidores usados durante saltos, o que pode ser útil para uma solução de problemas do Microsoft Office 365 em Suporte. > comandos TraceTCP podem ser muito simples, como: >> Lembre-se de incluir o número da  `tracetcp.exe outlook.office365.com:443` porta no comando! > [TraceTCP](https://simulatedsimian.github.io/tracetcp_download.html) é um download gratuito, mas depende do Wincap. O Wincap é uma ferramenta que também é usada e instalada pelo Netmon. Também usamos o Netmon na seção métodos avançados. 
  
 Se você tiver vários escritórios, também precisará manter um conjunto de dados de um cliente em cada um desses locais. Esse teste mede a latência, que, nesse caso, é um valor de número que descreve a quantidade de tempo entre um cliente que envia uma solicitação para o Office 365 e o Office 365 respondendo à solicitação. O teste se origina dentro do seu domínio em um computador cliente e procura medir uma viagem de ida e volta de dentro da rede, por meio de um ponto de saída, pela Internet para o Office 365 e de volta. 
  
Há algumas maneiras de lidar com o ponto de saída, neste caso, o servidor proxy. Você pode rastrear de 1 a 2 e de 2 a 3 e, em seguida, adicionar os números em milissegundos para obter um total final para a borda da sua rede. Ou você pode configurar a conexão para ignorar o proxy para endereços do Office 365. Em uma rede maior com um firewall, proxy reverso ou alguma combinação dos dois, talvez seja necessário fazer exceções no servidor proxy que permitirão que o tráfego passe por muitas URLs. Para ver a lista de pontos de extremidade usados pelo Office 365, confira URLs e intervalos de [endereços IP do Office 365.](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2) Se você tiver um proxy de autenticação, comece testando exceções para o seguinte:
  
- Portas 80 e 443
    
- TCP e HTTPs
    
- Conexões que são de saída para qualquer uma destas URLs:
    
- \*.microsoftonline.com
    
- \*.microsoftonline-p.com
    
- \*.sharepoint.com
    
- \*.outlook.com
    
- \*.lync.com
    
- osub.microsoft.com
    
Todos os usuários precisam ter permissão para chegar a esses endereços sem qualquer interferência ou autenticação de proxy. Em uma rede menor, você deve adicioná-los à sua lista de bypass de proxy no navegador da Web. 
  
Para adicioná-los à sua lista  de bypass de proxy no Internet Explorer, vá para Ferramentas Opções de \> **Internet** \> **Configurações** de \> **LAN avançadas.** \>  A guia avançada também é onde você encontrará o servidor proxy e a porta do servidor proxy. Talvez seja necessário clicar na caixa de seleção Usar um servidor proxy para **sua LAN,** para acessar o **botão** Avançado. Certifique-se de que o bypass do **servidor proxy para endereços locais** está marcado. Depois de clicar **em Avançado,** você verá uma caixa de texto onde poderá inserir exceções. Separe as URLs curinga listadas acima com ponto-e-vírgula, por exemplo:
  
\*.microsoftonline.com; \*.sharepoint.com
  
Depois de ignorar seu proxy, você poderá usar ping ou PsPing diretamente em uma URL do Office 365. A próxima etapa será testar o ping **outlook.office365.com**. Ou, se você estiver usando psPing ou outra ferramenta que permitirá que você fornecer um número de porta para o comando, PsPing contra **portal.microsoftonline.com:443** para ver o tempo médio de ida e volta em milissegundos. 
  
O tempo de ida e volta, ou RTT, é um valor de número que mede quanto tempo leva para enviar uma solicitação HTTP para um servidor como o outlook.office365.com e obter uma resposta que confirme que o servidor sabe que você fez isso. Às vezes, você verá isso abreviado como RTT. Esse deve ser um período de tempo relativamente curto.
  
Você precisa usar [o PSPing](https://technet.microsoft.com/sysinternals/jj729731.aspx) ou outra ferramenta que não use pacotes ICMP bloqueados pelo Office 365 para fazer esse teste. 
  
 **Como usar o PsPing para obter um tempo de ida e volta geral em milissegundos diretamente de uma URL do Office 365**
  
1. Execute um prompt de comando com elevação concluindo estas etapas:
    
1. Clique em **Iniciar**.
    
2. Na caixa **Iniciar Pesquisa,** digite cmd e pressione CTRL+SHIFT+ENTER.
    
3. Se a **caixa de diálogo Controle** de Conta de Usuário for exibida, confirme se a ação exibida é o que você deseja e clique em **Continuar.**
    
2. Navegue até a pasta onde a ferramenta (neste caso PsPing) está instalada e teste estas URLs do Office 365:
    
  - psping portal.office.com:443
    
  - psping microsoft-my.sharepoint.com:443
    
  - psping outlook.office365.com:443
    
  - psping www.yammer.com:443
    
    ![O comando PSPing será microsoft-my.sharepoint.com porta 443.](../media/3258f620-4513-4e82-95c9-06b387fc3a82.PNG)
  
Certifique-se de incluir o número de porta 443. Lembre-se de que o Office 365 funciona em um canal criptografado. Se você usar psPing sem o número da porta, sua solicitação falhará. Depois de fazer ping na sua lista curta, procure o Tempo Médio em milissegundos (ms). Isso é o que você deseja gravar!
  
![Gráfico que mostra uma ilustração do PSPing de proxy do cliente com um tempo de ida e volta de 2,8 milissegundos.](../media/96901aea-1093-4f1b-b5a3-6078e9035e6c.png)
  
Se você não estiver familiarizado com o bypass de proxy e preferir fazer as coisas passo a passo, precisará primeiro descobrir o nome do seu servidor proxy. No Internet Explorer, vá para Ferramentas **Configurações de** \> **LAN de Conexões** com a Internet \>  \> **Avançadas.** \>  A **guia** Avançado é onde você verá seu servidor proxy listado. Faça ping nesse servidor proxy em um prompt de comando concluindo esta tarefa: 
  
 **Para fazer ping no servidor proxy e obter um valor de viagem de ida e volta em milissegundos para o estágio 1 a 2**
  
1. Execute um prompt de comando com elevação concluindo estas etapas:
    
1. Clique em **Iniciar**.
    
2. Na caixa **Iniciar Pesquisa,** digite cmd e pressione CTRL+SHIFT+ENTER.
    
3. Se a **caixa de diálogo Controle** de Conta de Usuário for exibida, confirme se a ação exibida é o que você deseja e clique em **Continuar.**
    
2. Digite ping \<the name of the proxy server your browser uses, or the IP address of the proxy server\> e pressione ENTER. Se você tiver o PsPing ou alguma outra ferramenta instalada, poderá optar por usar essa ferramenta. 
    
    Seu comando pode se parecer com qualquer um destes exemplos: 
    
  - ping ourproxy.ourdomain.industry.business.com
    
  - ping 155.55.121.55
    
  - ping ourproxy
    
  - psping ourproxy.ourdomain.industry.business.com:80
    
  - psping 155.55.121.55:80
    
  - psping ourproxy:80
    
3. Quando o rastreamento parar de enviar pacotes de teste, você obterá um pequeno resumo que lista uma média, em milissegundos, e esse é o valor que você está procurando. Take a screen shot of the prompt and save it using your naming convention. Neste ponto, ele também pode ajudar a preencher o diagrama com o valor.
    
Talvez você tenha feito um rastreamento no início da manhã, e seu cliente possa chegar ao proxy (ou qualquer servidor de saída para a Internet) rapidamente. Nesse caso, seus números podem ter esta aparência:
  
![Gráfico que mostra o tempo de ida e volta de um cliente para um proxy de 2,8 milissegundos.](../media/1bd03544-23fc-47d4-bbae-c1feb466a5d8.PNG)
  
Se o computador cliente for um dos poucos selecionados com acesso ao servidor proxy (ou saída), você poderá executar a próxima etapa do teste conectando remotamente esse computador, executando o prompt de comando para PsPing para uma URL do Office 365 a partir daí. Se você não tiver acesso a esse computador, entre em contato com seus recursos de rede para obter ajuda na próxima etapa e obter os números exatos dessa maneira. Se isso não for possível, leve um PsPing para a URL do Office 365 em questão e compare-o com o PsPing ou o Tempo de Ping em relação ao seu servidor proxy. 
  
Por exemplo, se você tiver 51,84 milissegundos do cliente para a URL do Office 365 e tiver 2,8 milissegundos do cliente para o proxy (ou ponto de saída), terá 49,04 milissegundos da saída para o Office 365. Da mesma forma, se você tiver um PsPing de 12,25 milissegundos do cliente para o proxy durante a altura do dia e 62,01 milissegundos do cliente para a URL do Office 365, seu valor médio para a saída do proxy para a URL do Office 365 é de 49,76 milissegundos.
  
![Gráfico adicional que mostra o ping em milissegundos do cliente para o proxy ao lado do cliente para o Office 365 para que os valores possam ser subtraídos.](../media/cd764e77-5154-44ba-a5cd-443a628eb2d9.PNG)
  
Em termos de solução de problemas, você pode encontrar algo interessante apenas por manter essas linhas de base. Por exemplo, se você achar que geralmente tem cerca de 40 a 59 milissegundos de latência do proxy ou da saída para a URL do Office 365, e ter um cliente para proxy ou latência de ponto de saída de cerca de 3 a 7 milissegundos (dependendo da quantidade de tráfego de rede que você está vendo durante essa hora do dia), então você vai saber que algo é problemático se seu último cliente para proxy ou linhas de base de saída mostrar uma latência de 45 milissegundos.
  
### <a name="advanced-methods"></a>Métodos avançados

Se você realmente quiser saber o que está acontecendo com suas solicitações de Internet para o Office 365, você precisa se familiarizar com rastreamentos de rede. Não importa quais ferramentas você prefira para esses rastreamentos, HTTPWatch, Netmon, Analisador de Mensagens, Wireshark, Fiddler, ferramenta Painel do Desenvolvedor ou qualquer outra fará desde que essa ferramenta possa capturar e filtrar o tráfego de rede. Você verá nesta seção que é vantajoso executar mais de uma dessas ferramentas para obter uma imagem mais completa do problema. Ao testar, algumas dessas ferramentas também atuam como proxies por conta própria. Ferramentas usadas no artigo anterior, plano de solução de problemas de desempenho para [o Office 365](performance-troubleshooting-plan.md), incluem [Netmon 3.4](https://www.microsoft.com/download/details.aspx?id=4865), [HTTPWatch](https://www.httpwatch.com/download/)ou [WireShark](https://www.wireshark.org/).
  
Fazer uma linha de base de desempenho é a parte simples desse método, e muitas das etapas são as mesmas de quando você soluciona um problema de desempenho. Os métodos mais avançados de criação de linhas de base para desempenho exigem que você tome e armazene rastreamentos de rede. A maioria dos exemplos neste artigo usa o SharePoint Online, mas você deve desenvolver uma lista de ações comuns nos serviços do Office 365 nos quais você se inscreve para testar e registrar. Veja um exemplo de linha de base:
  
- Lista de linha de base para SPO - ** Etapa 1: ** Navegue na home page do site do SPO e faça um rastreamento de rede. Salve o rastreamento. 
    
- Lista de linha de base para SPO - Etapa **2:** pesquisar um termo (como o nome da empresa) por meio da Pesquisa Corporativa e fazer um rastreamento de rede. Salve o rastreamento. 
    
- Lista de linha de base para SPO - Etapa **3: carregar** um arquivo grande em uma biblioteca de documentos do SharePoint Online e fazer um rastreamento de rede. Salve o rastreamento. 
    
- Lista de linha de base para SPO - **Etapa 4: navegue** na home page do site do OneDrive e faça um rastreamento de rede. Salve o rastreamento. 
    
Essa lista deve incluir as ações comuns mais importantes que os usuários tomarem contra o SharePoint Online. Observe que a última etapa, para rastrear indo para o OneDrive for Business, cria uma comparação entre a carga da home page do SharePoint Online (que geralmente é personalizada por empresas) e a home page do OneDrive for Business, que raramente é personalizada. Esse é um teste muito básico quando se trata de um site do SharePoint Online de carregamento lento. Você pode criar um registro dessa diferença em seu teste.
  
Se você estiver no meio de um problema de desempenho, muitas das etapas serão as mesmas de quando você está fazendo uma linha de base. Os rastreamentos de rede se tornam críticos, portanto, vamos tratar  *de*  como fazer os rastreamentos importantes em seguida. 
  
Para resolver um problema de  *desempenho,*  no momento, você precisa fazer um rastreamento no momento em que está enfrentando o problema de desempenho. Você precisa ter as ferramentas adequadas disponíveis para coletar logs e precisa de um plano de ação, ou seja, uma lista de ações de solução de problemas a ser tomada para coletar as melhores informações que você pode. A primeira coisa a fazer é registrar a data e a hora do teste para que os arquivos possam ser salvos em uma pasta que reflita o tempo. Em seguida, restria as etapas do problema por conta própria. Estas são as etapas exatas que você usará para testar. Não se esqueça do básico: se o problema for apenas com o Outlook, certifique-se de registrar que o comportamento do problema ocorre em apenas um serviço do Office 365. Reduzir o escopo desse problema ajudará você a se concentrar em algo que pode ser resolvido. 
  
## <a name="see-also"></a>Confira também

[Gerenciar pontos de extremidade do Office 365](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)

