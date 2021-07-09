---
title: Ajuste de desempenho do Office 365 usando linhas de base e histórico de desempenho
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 07/08/2021
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
description: Saiba como verificar o histórico das conexões do computador cliente para ajudá-lo a detectar problemas emergentes mais cedo.
ms.openlocfilehash: 460bde30a0b292569b045c339066df2860c50989
ms.sourcegitcommit: 5db5047c24b56f3af90c2bc5c830a7a13eeeccad
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/09/2021
ms.locfileid: "53341575"
---
# <a name="office-365-performance-tuning-using-baselines-and-performance-history"></a>Ajuste de desempenho do Office 365 usando linhas de base e histórico de desempenho

Existem algumas maneiras simples de verificar o desempenho da conexão entre Office 365 e sua empresa que permitirão que você estabeleça uma linha de base aproximada de sua conectividade. Conhecer o histórico de desempenho de suas conexões de computador cliente pode ajudá-lo a detectar problemas emergentes no início, identificar e prever problemas.
  
Se você não estiver acostumado a trabalhar em problemas de desempenho, este artigo foi projetado para ajudá-lo a considerar algumas perguntas comuns. Como você sabe que o problema que você está vendo é um problema de desempenho e não um Office 365 de serviço? Como planejar um bom desempenho, a longo prazo? Como você pode manter um olho no desempenho? Se sua equipe ou clientes estão vendo um desempenho lento durante o uso Office 365 e você se pergunta sobre qualquer uma dessas perguntas, continue a leitura.
  
> [!IMPORTANT]
> **Tem um problema de desempenho entre seu cliente e Office 365 agora?** Siga as etapas descritas no [plano de solução](performance-troubleshooting-plan.md)de problemas de desempenho para Office 365 . 
    
## <a name="something-you-should-know-about-office-365-performance"></a>Algo que você deve saber sobre Office 365 desempenho

Office 365 vive dentro de uma rede da Microsoft dedicada de alta capacidade que é monitorada pela automação e por pessoas reais. Parte da manutenção da nuvem Office 365 de desempenho é ajustar e ajustar o desempenho sempre que possível. Como os clientes da Office 365 de nuvem têm que se conectar pela Internet, há um esforço contínuo para ajustar o desempenho em todos os serviços Office 365 também.

As melhorias de desempenho nunca param na nuvem, portanto, nem a experiência em manter a nuvem saudável e rápida. Se você tiver um problema de desempenho ao se conectar do seu local ao Office 365, é melhor não começar ou aguardar um caso de Suporte. Em vez disso, você deve começar a investigar o problema de "de dentro para fora". Ou seja, comece dentro de sua rede e trabalhe até Office 365. Antes de abrir um caso com o Suporte, você pode coletar dados e tomar ações que explorarão e poderão resolver o problema.
  
> [!IMPORTANT]
> Esteja ciente do planejamento de capacidade e dos limites Office 365. Essas informações o colocarão à frente da curva ao tentar resolver um problema de desempenho. Aqui está um link para as descrições Microsoft 365 [e Office 365 serviço.](/office365/servicedescriptions/office-365-service-descriptions-technet-library) Este é um hub central e todos os serviços oferecidos pela Office 365 têm um link que vai para suas próprias Descrições de Serviço a partir daqui. Isso significa que, se você precisar ver os limites padrão para o SharePoint Online, por exemplo, você clicaria em [SharePoint Descrição](/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-service-description) do Serviço Online e [localizaria sua seção](/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits)Limites do SharePoint Online.
  
Certifique-se de entrar em sua solução de problemas com a compreensão de que o desempenho é uma escala de deslizamento. Não se trata de alcançar um valor idealizado e mantê-lo permanentemente. Tarefas ocasionais de alta largura de banda, como o internamento de um grande número de usuários, ou a realização de grandes migrações de dados serão estressantes, portanto, *planeje* os impactos no desempenho. Você deve ter uma ideia aproximada de suas metas de desempenho, mas muitas variáveis têm desempenho, portanto, o desempenho varia.
  
A solução de problemas de desempenho não se trata de cumprir metas específicas e manter esses números indefinidamente, trata-se de melhorar as atividades existentes, considerando todas as variáveis. 
  
## <a name="okay-what-does-a-performance-problem-look-like"></a>Ok, qual é a aparência de um problema de desempenho?

Primeiro, você precisa certificar-se de que o que você está enfrentando é realmente um problema de desempenho e não um incidente de serviço. Um problema de desempenho é diferente de um incidente de serviço Office 365. Veja como diferencia-los.
  
Incidentes de serviço ocorrem quando o Office 365 em si está com problemas. Você pode ver ícones vermelhos ou amarelos em **Saúde** atual no Centro de administração do Microsoft 365. Você pode observar que o desempenho em computadores cliente que se conectam Office 365 é lento. Por exemplo, se a saúde atual  relata um ícone vermelho e você vê Investigando ao lado Exchange, você também pode receber chamadas de pessoas em sua organização que reclamam que as caixas de correio do cliente usando Exchange Online são lentas. Nesse caso, é razoável supor que seu desempenho Exchange Online foi uma vítima de problemas de Serviço.
  
![O Office 365 health com todas as cargas de trabalho mostrando verde, exceto Exchange, que mostra Service Restored.](../media/ec7f0325-9e61-4e1a-bec0-64b87f4469be.PNG)
  
Neste ponto, você, o administrador Office 365,  deve verificar a saúde atual e, em seguida, Exibir detalhes e histórico **,** com frequência, para manter-se atualizado sobre a manutenção no sistema. O **painel de saúde** atual foi feito para atualizá-lo sobre alterações e problemas no serviço. As anotações e explicações escritas no histórico de saúde, administrador para administrador, estão lá para ajudá-lo a avaliar e para mantê-lo postado sobre o trabalho contínuo.
  
![Uma imagem do painel de Office 365 de saúde explicando que o serviço Exchange Online foi restaurado e por quê.](../media/66609554-426a-4448-8be6-ea09817f41ba.PNG)
  
Um problema de desempenho não é um incidente de serviço, mesmo que os incidentes possam causar um desempenho lento. Um problema de desempenho tem esta aparência:
  
- Ocorre um problema de desempenho, independentemente do que o centro de administração **Atual está** relatando para o serviço.
    
-  Um comportamento usado para fluir leva muito tempo para ser concluído ou nunca concluído.
    
- Você também pode replicar o problema ou saber se isso acontecerá se você fizer a série correta de etapas.
    
-  Se o problema for intermitente, ainda pode haver um padrão. Por exemplo, você sabe que às 10:00 você terá chamadas de usuários que nem sempre podem acessar Office 365. As chamadas terminarão por volta do meio-dia.
    
Essa lista provavelmente parece familiar; talvez muito familiar. Quando você está ciente de que é um problema de desempenho, a pergunta se torna: "O que você fará em seguida?" O restante deste artigo ajuda você a determinar exatamente isso.
  
## <a name="how-to-define-and-test-the-performance-problem"></a>Como definir e testar o problema de desempenho

Problemas de desempenho geralmente surgem ao longo do tempo, portanto, pode ser um desafio definir o problema real. Crie uma boa instrução problem com uma boa ideia de contexto de problema e, em seguida, você precisa repetir as etapas de teste. Aqui estão alguns exemplos de instruções de problemas que não fornecem informações suficientes:
  
- Mudar da minha Caixa de Entrada para o meu Calendário era algo que eu não tinha notado e agora é uma pausa para café. Você pode fazer com que ele aja como antes?
    
- Carregar meus arquivos para SharePoint Online está demorando muito. Por que é lento à tarde, mas a qualquer outro momento, é rápido? Não pode ser rápido?
    
Há vários grandes desafios colocados pelas instruções de problema acima. Especificamente, há muitas ambiguidades para lidar. por exemplo:
  
- Não está claro como a alternação entre Caixa de Entrada e Calendário era usada para agir no laptop.
    
- Quando o usuário diz, "Não pode ser rápido", o que é "rápido"?
    
- Quanto tempo é "para sempre"? São vários segundos? Ou muitos minutos? Ou o usuário poderia fazer o almoço e a ação terminaria 10 minutos depois de voltar?
    
O administrador e o solucionador de  problemas não podem estar cientes dos detalhes do problema de instruções gerais como estas. Por exemplo, eles não sabem quando o problema começou a acontecer. O solucionador de problemas pode não saber que o usuário trabalha em casa e só vê a alternação lenta enquanto estiver em sua rede local. Ou que o usuário executa outros aplicativos intensivos de RAM no cliente local. Os administradores podem não saber que o usuário está executando um sistema operacional mais antigo ou que não executaram atualizações recentes.
  
Quando os usuários relatam um problema de desempenho, há muitas informações a coletar. Obter e gravar informações é chamado de escolhamento do problema. Aqui está uma lista básica de scoping que você pode usar para coletar informações sobre problemas de desempenho. Esta lista não é exaustiva, mas é um local para começar:
  
- Em que data o problema aconteceu e em que hora do dia ou da noite?
    
- Que tipo de computador cliente você estava usando e como ele se conecta à rede de negócios (VPN, Com fio, Sem fio)?
    
- Estava trabalhando remotamente ou estava no escritório?
    
- Você tentou as mesmas ações em outro computador e viu o mesmo comportamento?
    
- Ande pelas etapas que estão lhe dando problemas para que você possa escrever as ações que você faz.
    
- Quão lento em segundos ou minutos é o desempenho?
    
- Onde no mundo você está localizado?
    
Algumas dessas perguntas são mais óbvias do que outras. A maioria das pessoas compreenderá que um solucionador de problemas precisa das etapas exatas para reproduzir o problema. Afinal, de que outra forma você pode registrar o que há de errado e como testar se o problema foi corrigido? Menos óbvias são as coisas como "Qual data e hora você viu o problema?", e "Onde no mundo você está localizado?", informações que podem ser usadas em tandem. Dependendo de quando o usuário estava trabalhando, algumas horas de diferença de tempo podem significar que a manutenção já está em andamento em partes da rede da sua empresa. Se, por exemplo, sua empresa tiver uma implementação híbrida, como uma Pesquisa de SharePoint híbrida, que pode consultar índices de pesquisa no SharePoint Online e em uma instância local do SharePoint Server 2013, as atualizações podem estar em andamento no farm local. Se a sua empresa estiver toda na nuvem, a manutenção do sistema pode incluir a adição ou remoção de hardware de rede, a implantação de atualizações em toda a empresa ou a fazer alterações no DNS ou em outra infraestrutura principal.
  
Quando você está solucionando um problema de desempenho, é um pouco como uma cena de crime, você precisa ser preciso e observador para tirar conclusões das evidências. Para fazer isso, você deve obter uma boa declaração de problema coletando evidências. Ele deve incluir o contexto do computador, o contexto do usuário, quando o problema começou e as etapas exatas que expusem o problema de desempenho. Esta instrução de problema deve ser, e permanecer, a página mais alta em suas anotações. Ao passar pela instrução problem novamente depois de trabalhar na resolução, você está tomando as etapas para testar e provar se as ações realizadas resolveram o problema. Isso é fundamental para saber quando seu trabalho, lá, é feito.
  
## <a name="do-you-know-how-performance-used-to-look-when-it-was-good"></a>Você sabe como o desempenho era quando era bom?

Se você não tiver sorte, ninguém saberá. Ninguém tinha números. Isso significa que ninguém pode responder à pergunta simples "Sobre quantos segundos foi usado para trazer uma Caixa de Entrada no Office 365?", ou "Quanto tempo demorava quando os Executivos tinham uma reunião do Lync Online?", que é um cenário comum para muitas empresas.
  
O que está faltando aqui é uma linha de base de desempenho.
  
As linhas de base dão a você um contexto para seu desempenho. Você deve fazer uma linha de base ocasionalmente com frequência, dependendo das necessidades da sua empresa. Se você for uma empresa maior, sua equipe de Operações poderá ter linhas de base para seu ambiente local. Por exemplo, se você corrigir todos os servidores Exchange na primeira segunda-feira do mês e todos os servidores SharePoint na terceira segunda-feira, sua equipe de Operações provavelmente terá uma lista de tarefas e cenários que executa após o patch, para provar que as funções críticas estão operacionais. Por exemplo, abrindo a Caixa de Entrada, clicando em Enviar/Receber e fazendo com que as pastas atualizem ou, em SharePoint, navegando pela página principal do site, entrando na página de Pesquisa corporativa e fazendo uma pesquisa que retorna resultados.
  
Se seus aplicativos estão em Office 365, algumas das linhas de base mais fundamentais que você pode medir o tempo (em milissegundos) de um computador cliente dentro de sua rede, até um ponto de saída, ou o ponto em que você sai da rede e sai para Office 365. Aqui estão algumas linhas de base úteis que você pode investigar e registrar:
  
- Identifique os dispositivos entre seu computador cliente e seu ponto de saída, por exemplo, seu servidor proxy.
    
  - Você precisa conhecer seus dispositivos para que você tenha contexto (endereços IP, tipo de dispositivo, etc.) para problemas de desempenho que surgem.
    
  - Os servidores proxy são pontos de saída comuns, portanto, você pode verificar o navegador da Web para ver qual servidor proxy ele está definido para usar, se for o caso.
    
  - Há ferramentas de terceiros que podem descobrir e mapear sua rede, mas a maneira mais segura de saber seus dispositivos é perguntar a um membro da sua equipe de rede.
    
- Identifique seu provedor de serviços de Internet (ISP), anote suas informações de contato e pergunte quantos circuitos você tem.
    
- Dentro da sua empresa, identifique recursos para os dispositivos entre seu cliente e o ponto de saída ou identifique um contato de emergência com o qual falar sobre problemas de rede.
    
Aqui estão algumas linhas de base que testes simples com ferramentas podem calcular para você:
  
- Tempo do computador cliente para o ponto de saída em milissegundos
    
- O tempo de saída aponta para Office 365 milissegundos
    
- Local no mundo do servidor que resolve as URLS para Office 365 quando você navega
    
- A velocidade da resolução DNS do SEU ISP em milissegundos, inconsistências na chegada de pacotes (tremida de rede), tempos de carregamento e download em milissegundos
    
Se você não estiver familiarizado com como executar essas etapas, entraremos em mais detalhes neste artigo. 
  
## <a name="what-is-a-baseline"></a>O que é uma linha de base?

Você conhecerá o impacto quando ele ficar ruim, mas se você não conhecer seus dados de desempenho histórico, não será possível ter um contexto de quão ruim ele pode ter se tornado e quando. Portanto, sem uma linha de base, você está perdendo a dica-chave para resolver o quebra-cabeça: a imagem na caixa do quebra-cabeça. Na solução de problemas de desempenho, você precisa de um ponto de  *comparação*  . Linhas de base de desempenho simples não são difíceis de aceitar. Sua equipe de Operações pode ter a tarefa de realizar isso em um cronograma. Por exemplo, digamos que sua conexão seja assim: 
  
![Um gráfico de rede básico mostrando cliente, proxy e Office 365 nuvem.](../media/c6ca7140-09f9-4c2d-a775-dbf2820eaa0c.PNG)
  
Isso significa que você verificou com sua equipe de rede e descobriu que você deixou sua empresa para a Internet por meio de um servidor proxy e que o proxy lida com todas as solicitações que seu computador cliente envia para a nuvem. Nesse caso, você deve desenhar uma versão simplificada da sua conexão que lista todos os dispositivos interveniáveis. Agora, insira ferramentas que você pode usar para testar o desempenho entre o cliente, o ponto de saída (onde você deixa sua rede para a Internet) e a Office 365 nuvem.
  
![A rede básica com cliente, proxy e nuvem e sugestões de ferramentas PSPing, TraceTCP e rastreamentos de rede.](../media/627bfb77-abf7-4ef1-bbe8-7f8cbe48e1d2.png)
  
As opções são listadas como **Simples** e **Avançada** devido à quantidade de experiência necessária para encontrar os dados de desempenho. Um rastreamento de rede levará muito tempo, em comparação com a execução de ferramentas de linha de comando, como PsPing e TraceTCP. Essas duas ferramentas de linha de comando foram escolhidas porque não usam pacotes ICMP, que serão bloqueados pelo Office 365 e porque eles dão o tempo em milissegundos necessários para sair do computador cliente ou do servidor proxy (se você tiver acesso) e chegar ao Office 365. Cada salto individual de um computador para outro terminará com um valor de tempo, e isso é ótimo para linhas de base! Assim como o mais importante, essas ferramentas de linha de comando permitem adicionar um número de porta ao comando, isso é útil porque o Office 365 se comunica pela porta 443, que é a porta usada pelo Secure Sockets Layer and Transport Layer Security (SSL e TLS). No entanto, outras ferramentas de terceiros podem ser melhores soluções para sua situação. A Microsoft não dá suporte a todas essas ferramentas, portanto, se, por algum motivo, você não conseguir fazer o PsPing e TraceTCP funcionarem, vá para um rastreamento de rede com uma ferramenta como Netmon. 
  
Você pode fazer uma linha de base antes do horário comercial, novamente durante o uso intenso e, em seguida, novamente após o horário. Isso significa que você pode ter uma estrutura de pasta que se parece um pouco com esta no final:
  
![Gráfico que propõe uma maneira de organizar seus dados de desempenho em pastas.](../media/13e01ffa-f0f2-4d10-b89d-d5980ec89fae.png)
  
Você também deve escolher uma convenção de nomenissar seus arquivos. Aqui estão alguns exemplos:
  
- Feb_09_2015_9amPST_PerfBaseline_Netmon_ClientToEgress_Normal
    
- Jan_10_2015_3pmCST_PerfBaseline_PsPing_ClientToO365_bypassProxy_SLOW
    
- Feb_08_2015_2pmEST_PerfBaseline_BADPerf
    
- Feb_08_2015_8-30amEST_PerfBaseline_GoodPerf
    
Há muitas maneiras diferentes de fazer isso, mas usar o formato **\<dateTime\>\<what's happening in the test\>** é um bom lugar para começar. Ser diligente sobre isso ajudará muito quando você estiver tentando solucionar problemas mais tarde. Mais tarde, você poderá dizer "Eu fiz dois rastreamentos em 8 de fevereiro, um mostrou bom desempenho e outro mostrou mau desempenho, para que possamos compará-los". Isso é extremamente útil para solucionar problemas. 
  
Você precisa ter uma maneira organizada de manter suas linhas de base históricas. Neste exemplo, os métodos simples produziram três saídas de linha de comando e os resultados foram coletados como capturas de tela, mas você pode ter arquivos de captura de rede. Use o método que funciona melhor para você. Armazene suas linhas de base históricas e consulte-as em pontos em que você nota alterações no comportamento dos serviços online. 
  
## <a name="why-collect-performance-data-during-a-pilot"></a>Por que coletar dados de desempenho durante um piloto?

Não há tempo melhor para começar a fazer linhas de base do que durante um piloto do Office 365 serviço. Seu escritório pode ter milhares de usuários, centenas de milhares ou pode ter cinco, mas mesmo com um pequeno número de usuários, você pode realizar testes para medir flutuações no desempenho. No caso de uma grande empresa, um exemplo representativo de várias centenas de usuários pilotando Office 365 pode ser projetado para fora para vários milhares para que você saiba onde podem surgir problemas antes que eles aconteçam.
  
No caso de uma pequena empresa, em que a abordagem significa que todos os usuários vão para o serviço ao mesmo tempo e não há piloto, mantenha medidas de desempenho para que você tenha dados para mostrar a qualquer pessoa que possa ter que solucionar problemas de uma operação com mau desempenho. Por exemplo, se você observar que, de repente, você pode dar a volta ao seu edifício no tempo necessário para carregar um gráfico de tamanho médio onde ele costumava acontecer muito rapidamente.
  
## <a name="how-to-collect-baselines"></a>Como coletar linhas de base

Para todos os planos de solução de problemas, você precisa identificar essas coisas no mínimo:
  
- O computador cliente que você está usando (o tipo de computador ou dispositivo, um endereço IP e as ações que causaram o problema)
    
- Onde o computador cliente está localizado no mundo (por exemplo, se esse usuário em uma VPN para a rede, trabalhando remotamente ou na intranet da empresa)
    
- O ponto de saída que o computador cliente usa da sua rede (o ponto no qual o tráfego deixa sua empresa para um ISP ou a Internet)
    
 Você pode descobrir o layout da rede do administrador de rede. Se você estiver em uma rede pequena, dê uma olhada nos dispositivos que o conectam à Internet e chame seu ISP se tiver dúvidas sobre o layout. Crie um gráfico do layout final para sua referência. 
  
Esta seção é dividida em ferramentas e métodos simples de linha de comando e opções de ferramentas mais avançadas. Primeiro, vamos abranger métodos simples. Mas, se você tiver um problema de desempenho agora, você deve ir para métodos avançados e experimentar o plano de ação de solução de problemas de desempenho de exemplo.
  
### <a name="simple-methods"></a>Métodos simples

O objetivo desses métodos simples é aprender a tomar, entender e armazenar adequadamente linhas de base de desempenho simples ao longo do tempo para que você seja informado sobre Office 365 desempenho. Aqui está o diagrama muito simples para simples, como você já viu antes:
  
![A rede básica com cliente, proxy e nuvem e sugestões de ferramentas PSPing, TraceTCP e rastreamentos de rede.](../media/627bfb77-abf7-4ef1-bbe8-7f8cbe48e1d2.png)
  
> [!NOTE]
> TraceTCP está incluído nesta captura de tela porque é uma ferramenta útil para mostrar, em milissegundos, quanto tempo uma solicitação leva para processar e quantos saltos de rede ou conexões de um computador para o próximo, que a solicitação leva para chegar a um destino. TraceTCP também pode dar os nomes dos servidores usados durante saltos, o que pode ser útil para um Microsoft Office 365 solução de problemas em Support. > comandos TraceTCP podem ser muito simples, como: >> Lembre-se de incluir  `tracetcp.exe outlook.office365.com:443` o número da porta no comando! > [TraceTCP](https://simulatedsimian.github.io/tracetcp_download.html) é um download gratuito, mas depende do Wincap. O Wincap é uma ferramenta que também é usada e instalada pelo Netmon. Também usamos Netmon na seção métodos avançados. 
  
 Se você tiver vários escritórios, também precisará manter um conjunto de dados de um cliente em cada um desses locais. Este teste mede a latência, que, nesse caso, é um valor de número que descreve a quantidade de tempo entre um cliente que envia uma solicitação para Office 365 e Office 365 respondendo à solicitação. O teste se origina dentro do seu domínio em um computador cliente e procura medir uma viagem de ida e volta de dentro de sua rede, através de um ponto de saída, através da Internet para Office 365 e voltar. 
  
Há algumas maneiras de lidar com o ponto de saída, nesse caso, o servidor proxy. Você pode rastrear de 1 a 2 e, em seguida, de 2 a 3 e, em seguida, adicionar os números em milissegundos para obter um total final à borda da rede. Ou, você pode configurar a conexão para ignorar o proxy para Office 365 endereços. Em uma rede maior com um firewall, proxy reverso ou alguma combinação dos dois, talvez seja necessário fazer exceções no servidor proxy que permitirão que o tráfego passe por muitas URLs. Para ver a lista de pontos de extremidade usados pelo Office 365, [consulte Office 365 URLs e intervalos de endereços IP.](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2) Se você tiver um proxy de autenticação, comece testando exceções para o seguinte:
  
- Portas 80 e 443
    
- TCP e HTTPs
    
- Conexões que são de saída para qualquer uma dessas URLs:
    
- \*.microsoftonline.com
    
- \*.microsoftonline-p.com
    
- \*.sharepoint.com
    
- \*.outlook.com
    
- \*.lync.com
    
- osub.microsoft.com
    
Todos os usuários precisam ter permissão para chegar a esses endereços sem qualquer interferência de proxy ou autenticação. Em uma rede menor, você deve adicioná-los à sua lista de bypass de proxy no navegador da Web. 
  
Para adicioná-los à sua lista de desvios de proxy no Internet Explorer, acesse **Ferramentas** \> **Opções da Internet** \> **Configurações** de LAN \> **avançadas** \> . A guia avançada também é onde você encontrará o servidor proxy e a porta do servidor proxy. Talvez seja necessário clicar na caixa de seleção **Use um servidor proxy para sua LAN**, para acessar o **botão** Avançado. Você deve verificar se o servidor **proxy bypass para endereços locais** está verificado. Depois de clicar **em Avançado,** você verá uma caixa de texto onde poderá inserir exceções. Separe as URLs curinga listadas acima com ponto-e-vírgula, por exemplo:
  
\*.microsoftonline.com; \*.sharepoint.com
  
Depois de ignorar seu proxy, você poderá usar ping ou PsPing diretamente em uma URL Office 365. A próxima etapa será testar o ping **outlook.office365.com**. Ou, se você estiver usando PsPing ou outra ferramenta que permitirá fornecer um número de porta para o comando, psPing contra **portal.microsoftonline.com:443** para ver o tempo médio de viagem de ida e volta em milissegundos. 
  
O tempo de ida e volta, ou RTT, é um valor de número que mede quanto tempo leva para enviar uma solicitação HTTP para um servidor como outlook.office365.com e obter uma resposta de volta que confirme que o servidor sabe que você fez isso. Às vezes, você verá isso abreviado como RTT. Esse deve ser um período de tempo relativamente curto.
  
Você precisa usar [PSPing](/sysinternals/downloads/psping) ou outra ferramenta que não use pacotes ICMP bloqueados por Office 365 para fazer esse teste. 
  
 **Como usar o PsPing para obter um tempo geral de viagem de ida e volta em milissegundos diretamente de uma URL Office 365 url**
  
1. Execute um prompt de comando com elevação concluindo estas etapas:
    
1. Clique em **Iniciar**.
    
2. Na caixa **Iniciar Pesquisa,** digite cmd e pressione CTRL+SHIFT+ENTER.
    
3. Se a **caixa de diálogo** Controle de Conta de Usuário for exibida, confirme se a ação exibida é o que você deseja e clique em **Continuar**.
    
2. Navegue até a pasta onde a ferramenta (neste caso, PsPing) está instalada e teste essas URLs Office 365:
    
  - psping admin.microsoft.com:443
    
  - psping microsoft-my.sharepoint.com:443
    
  - psping outlook.office365.com:443
    
  - psping www.yammer.com:443
    
    ![O comando PSPing microsoft-my.sharepoint.com porta 443.](../media/3258f620-4513-4e82-95c9-06b387fc3a82.PNG)
  
Certifique-se de incluir o número de porta 443. Lembre-se Office 365 funciona em um canal criptografado. Se você PsPing sem o número da porta, sua solicitação falhará. Depois de fazer o ping da sua lista curta, procure o tempo médio em milissegundos (ms). Isso é o que você deseja gravar!
  
![Gráfico que mostra uma ilustração do cliente para proxy PSPing com um tempo de ida e volta de 2,8 milissegundos.](../media/96901aea-1093-4f1b-b5a3-6078e9035e6c.png)
  
Se você não estiver familiarizado com o bypass de proxy e preferir fazer as coisas passo a passo, primeiro você precisará descobrir o nome do seu servidor proxy. No Internet Explorer, acesse **Ferramentas** \> **Opções da Internet Configurações** de LAN \>  \> **avançadas** \> . A **guia Avançado** é onde você verá seu servidor proxy listado. Ping that proxy server at a command prompt by completing this task: 
  
 **Para pingar o servidor proxy e obter um valor de ida e volta em milissegundos para o estágio 1 a 2**
  
1. Execute um prompt de comando com elevação concluindo estas etapas:
    
1. Clique em **Iniciar**.
    
2. Na caixa **Iniciar Pesquisa,** digite cmd e pressione CTRL+SHIFT+ENTER.
    
3. Se a **caixa de diálogo** Controle de Conta de Usuário for exibida, confirme se a ação exibida é o que você deseja e clique em **Continuar**.
    
2. Digite ping \<the name of the proxy server your browser uses, or the IP address of the proxy server\> e pressione ENTER. Se você tiver o PsPing ou outra ferramenta instalada, poderá optar por usar essa ferramenta. 
    
    Seu comando pode ter a aparência de qualquer um desses exemplos: 
    
  - ping ourproxy.ourdomain.industry.business.com
    
  - ping 155.55.121.55
    
  - ping ourproxy
    
  - psping ourproxy.ourdomain.industry.business.com:80
    
  - psping 155.55.121.55:80
    
  - psping ourproxy:80
    
3. Quando o rastreamento parar de enviar pacotes de teste, você obterá um pequeno resumo que lista uma média, em milissegundos, e esse é o valor que você está procurando. Tire uma captura de tela do prompt e salve-o usando sua convenção de nomenis. Neste ponto, ele também pode ajudar a preencher o diagrama com o valor.
    
Talvez você tenha feito um rastreamento no início da manhã e seu cliente possa chegar ao proxy (ou qualquer servidor de saída para a Internet) rapidamente. Nesse caso, seus números podem ter esta aparência:
  
![Gráfico que mostra o tempo de ida e volta de um cliente para um proxy de 2,8 milissegundos.](../media/1bd03544-23fc-47d4-bbae-c1feb466a5d8.PNG)
  
Se o computador cliente for um dos poucos selecionados com acesso ao servidor proxy (ou saída), você poderá executar a próxima etapa do teste conectando-se remotamente a esse computador, executando o prompt de comando para PsPing para uma URL de Office 365 a partir daí. Se você não tiver acesso a esse computador, entre em contato com seus recursos de rede para obter ajuda com a próxima etapa e obter números exatos dessa forma. Se isso não for possível, leve um PsPing contra a URL Office 365 em questão e compare-a com o tempo de PsPing ou Ping em relação ao seu servidor proxy. 
  
Por exemplo, se você tiver 51,84 milissegundos do cliente para a URL do Office 365 e tiver 2,8 milissegundos do cliente para o proxy (ou ponto de saída), você terá 49,04 milissegundos da saída para Office 365. Da mesma forma, se você tiver um PsPing de 12,25 milissegundos do cliente para o proxy durante a altura do dia e 62,01 milissegundos do cliente para a URL do Office 365, seu valor médio para o proxy egressar para a URL do Office 365 é 49,76 milissegundos.
  
![Gráfico adicional que mostra o ping em milissegundos de cliente para proxy ao lado do cliente Office 365 para que os valores possam ser subtraídos.](../media/cd764e77-5154-44ba-a5cd-443a628eb2d9.PNG)
  
Em termos de solução de problemas, você pode encontrar algo interessante apenas por manter essas linhas de base. Por exemplo, se você descobrir que geralmente tem cerca de 40 a 59 milissegundos de latência do proxy ou ponto de saída para a URL Office 365, e ter um cliente para proxy ou latência de ponto de saída de cerca de 3 a 7 milissegundos (dependendo da quantidade de tráfego de rede que você está vendo durante essa hora do dia), então você certamente saberá que algo é problemático se seus últimos três clientes para proxy ou linhas de base de saída mostrarem uma latência de 45 milissegundos.
  
### <a name="advanced-methods"></a>Métodos avançados

Se você realmente quiser saber o que está acontecendo com suas solicitações de Internet para Office 365, você precisa se familiarizar com rastreamentos de rede. Não importa quais ferramentas você prefere para esses rastreamentos, HTTPWatch, Netmon, Analisador de Mensagens, Wireshark, Fiddler, Ferramenta de Painel de Desenvolvedor ou qualquer outra, contanto que essa ferramenta possa capturar e filtrar o tráfego de rede. Você verá nesta seção que é útil executar mais de uma dessas ferramentas para obter uma imagem mais completa do problema. Quando você está testando, algumas dessas ferramentas também agem como proxies por conta própria. Ferramentas usadas no artigo de parceiro, [Plano](performance-troubleshooting-plan.md)de solução de problemas de desempenho para Office 365 , incluem [Netmon 3.4](https://www.microsoft.com/download/details.aspx?id=4865), [HTTPWatch](https://www.httpwatch.com/download/)ou [WireShark](https://www.wireshark.org/).
  
Fazer uma linha de base de desempenho é a parte simples deste método, e muitas das etapas são as mesmas que quando você soluciona um problema de desempenho. Os métodos mais avançados de criação de linhas de base para desempenho exigem que você pegue e armazene rastreamentos de rede. A maioria dos exemplos neste artigo usa o SharePoint Online, mas você deve desenvolver uma lista de ações comuns nos serviços Office 365 aos quais você se inscreve para testar e gravar. Aqui está um exemplo de linha de base:
  
- Lista de linha de base para SPO - ** Etapa 1: ** Navegue pela home page do site do SPO e faça um rastreamento de rede. Salve o rastreamento. 
    
- Lista de linha de base para SPO - Etapa **2:** Pesquisar um termo (como o nome da sua empresa) por meio Enterprise Pesquisar e fazer um rastreamento de rede. Salve o rastreamento. 
    
- Lista de linha de base para SPO - Etapa **3:** Upload um arquivo grande para uma biblioteca de documentos SharePoint Online e faça um rastreamento de rede. Salve o rastreamento. 
    
- Lista de linha de base para SPO - Etapa **4:** navegue pela home page do site OneDrive site e faça um rastreamento de rede. Salve o rastreamento. 
    
Essa lista deve incluir as ações comuns mais importantes que os usuários têm contra SharePoint Online. Observe que a última etapa, para rastrear indo para OneDrive for Business, cria uma comparação entre a carga da home page do SharePoint Online (que geralmente é personalizada pelas empresas) e OneDrive for Business home page, que raramente é personalizada. Este é um teste muito básico quando se trata de um site SharePoint Online de carregamento lento. Você pode criar um registro dessa diferença em seu teste.
  
Se você estiver no meio de um problema de desempenho, muitas das etapas serão as mesmas ao fazer uma linha de base. Os rastreamentos de rede tornam-se críticos, portanto, trataremos  *como*  seguir os rastreamentos importantes. 
  
Para resolver um problema de  *desempenho,*  agora , você precisa fazer um rastreamento no momento em que está enfrentando o problema de desempenho. Você precisa ter as ferramentas adequadas disponíveis para coletar logs e precisa de um plano de ação, ou seja, uma lista de ações de solução de problemas a ser tomada para coletar as melhores informações que puder. A primeira coisa a fazer é gravar a data e a hora do teste para que os arquivos possam ser salvos em uma pasta que reflita o tempo. Em seguida, reduza as etapas do problema por conta própria. Estas são as etapas exatas que você usará para testes. Não se esqueça das noções básicas: se o problema estiver apenas com Outlook, certifique-se de registrar que o comportamento do problema acontece em apenas um serviço Office 365. Restringir o escopo desse problema ajudará você a se concentrar em algo que você pode resolver. 
  
## <a name="see-also"></a>Confira também

[Gerenciar pontos de extremidade do Office 365](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)