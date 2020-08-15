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
description: Saiba como verificar o histórico de suas conexões de computador cliente para ajudá-lo a detectar problemas emergentes cedo.
ms.openlocfilehash: 2337b14542f894e9a62037b2f032632147e45e09
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46687184"
---
# <a name="office-365-performance-tuning-using-baselines-and-performance-history"></a>Ajuste de desempenho do Office 365 usando linhas de base e histórico de desempenho

Há algumas maneiras simples de verificar o desempenho da conexão entre o Office 365 e sua empresa, que permitirá estabelecer uma linha de base aproximada da conectividade. Conhecer o histórico de desempenho de suas conexões de computador cliente pode ajudá-lo a detectar problemas emergentes antecipadamente, identificar e prever problemas.
  
Se você não é usado para trabalhar com problemas de desempenho, este artigo foi projetado para ajudá-lo a considerar algumas perguntas comuns, como você sabe o problema que está vendo é um problema de desempenho e não um incidente do serviço do Office 365? Como você pode planejar o bom desempenho, longo prazo? Como você pode ficar atento ao desempenho? Se sua equipe ou seus clientes estiverem vendo um desempenho lento ao usar o Office 365 e você se perguntou de qualquer uma dessas perguntas, leia.
  
> [!IMPORTANT]
> **Tem um problema de desempenho entre o cliente e o Office 365 agora?** Siga as etapas descritas no plano de [solução de problemas de desempenho do Office 365](performance-troubleshooting-plan.md). 
    
## <a name="something-you-should-know-about-office-365-performance"></a>Algo que você deve saber sobre o desempenho do Office 365

O Office 365 mora dentro de uma rede Microsoft dedicada de alta capacidade que é monitorada de forma estável não apenas pela automação, mas por pessoas reais. Parte da função de manutenção da nuvem do Office 365 é o ajuste de desempenho de construção e a simplificação de onde é possível. Como os clientes da nuvem do Office 365 precisam se conectar pela Internet, há um esforço contínuo para ajustar o desempenho em todos os serviços do Office 365. Os aprimoramentos de desempenho nunca são realmente interrompidos na nuvem, e há uma grande quantidade de experiência acumulada com manutenção rápida e saudável da nuvem. Se você tiver um problema de desempenho se conectando de seu local ao Office 365, é melhor não começar com e aguardar, um caso de suporte. Em vez disso, você deve começar a investigar o problema de ' o Inside Out '. Ou seja, comece dentro da sua rede e trabalhe com o caminho para o Office 365. Antes de abrir um caso com o suporte do Office 365, você pode coletar dados e realizar ações que explorarão e poderão resolver o problema.
  
> [!IMPORTANT]
> Esteja ciente do planejamento de capacidade e dos limites no Office 365. Essas informações serão colocadas em frente da curva ao tentar resolver um problema de desempenho. Veja um link para as [descrições de serviço do Microsoft 365 e do Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-service-descriptions-technet-library). Este é um hub central, e todos os serviços oferecidos pelo Office 365 têm um link que vai para suas descrições de serviço. Isso significa que, se você precisar ver os limites padrão do SharePoint Online, por exemplo, clique em [Descrição do serviço do SharePoint Online](https://technet.microsoft.com/library/sharepoint-online-service-description.aspx) e localize sua [seção limites do SharePoint Online](https://go.microsoft.com/fwlink/p/?LinkID=856113). 
  
Certifique-se de que você vai para a solução de problemas com o entendimento de que o desempenho é uma escala deslizante, não está prestes a obter um valor ideal e mantê-lo permanentemente (se acreditar que isso seja tão importante, as tarefas ocasionais de largura de banda, como a incorporação de um grande número de usuários ou a realização de grandes migrações de dados serão muito estressadas, Você pode e deve ter uma ideia de seus objetivos de desempenho, mas muitas variáveis são executadas no desempenho, portanto, o desempenho varia. Essa é a natureza do desempenho. 
  
A solução de problemas de desempenho não está prestes a atender metas específicas e manter esses números indefinidamente, trata-se de melhorar as atividades existentes, dadas todas as variáveis. 
  
## <a name="okay-what-does-a-performance-problem-look-like"></a>Ok, qual é a aparência de um problema de desempenho?

Primeiro, você precisa certificar-se de que o que você está enfrentando é realmente um problema de desempenho e não um incidente de serviço. Um problema de desempenho é diferente de um incidente de serviço no Office 365. Confira aqui como diferenciá-los.
  
Se o serviço do Office 365 estiver com problemas, isso é um incidente de serviço. Você verá ícones vermelhos ou amarelos sob **integridade atual** no centro de administração do Microsoft 365, você também pode notar um desempenho lento em computadores clientes que se conectam ao Office 365. Por exemplo, se a integridade atual relatar um ícone vermelho e você vir a **investigar** ao lado do Exchange, também poderá receber uma série de chamadas de pessoas em sua organização que reclamam que as caixas de correio de cliente que usam o Exchange Online estão funcionando incorretamente. Nesse caso, é razoável supor que seu desempenho do Exchange Online se tornou uma vítima de problemas no serviço. 
  
![O painel de integridade do Office 365 com todas as cargas de trabalho mostrando o verde, exceto o Exchange, que mostra o serviço restaurado.](../media/ec7f0325-9e61-4e1a-bec0-64b87f4469be.PNG)
  
Neste ponto, você, o administrador do Office 365, deve verificar a **integridade atual** e, em seguida, **Exibir detalhes e histórico**, frequentemente, para manter-se atualizado sobre a manutenção que executamos no sistema. O painel de **integridade atual** foi feito para atualizar você sobre alterações em e problemas no, o serviço. As notas e explicações escritas no histórico de saúde, administrador para administração, estão lá para ajudá-lo a avaliar seu impacto e a manter o trabalho em andamento. 
  
![Uma imagem do painel de integridade do Office 365 explicando que o serviço do Exchange Online foi restaurado e por quê.](../media/66609554-426a-4448-8be6-ea09817f41ba.PNG)
  
Um problema de desempenho não é um incidente de serviço, mesmo que os incidentes possam causar um desempenho lento. Um problema de desempenho tem a seguinte aparência:
  
- Um problema de desempenho ocorre independentemente da **integridade atual** do centro de administração estar relatando para o serviço. 
    
-  Um comportamento que costumava ser relativamente perfeito demora muito para ser concluído ou nunca é concluído. 
    
- Você pode replicar o problema também ou, pelo menos, saberá que acontecerá se você fizer a série de etapas corretas.
    
-  Se o problema for intermitente, ainda haverá um padrão, por exemplo, se você souber que, pelo 10:00, você terá chamadas de usuários que não podem acessar o Office 365 de forma confiável e que as chamadas serão desativadas ao redor do meio-dia. 
    
Isso provavelmente parece familiar; Talvez seja muito familiar. Quando você sabe que é um problema de desempenho, a pergunta se torna "o que fazer em seguida?" O restante deste artigo ajuda você a determinar exatamente isso.
  
## <a name="how-to-define-and-test-the-performance-problem"></a>Como definir e testar o problema de desempenho

Problemas de desempenho geralmente surgem ao longo do tempo, portanto, pode ser desafiador definir o problema real. Você precisa criar uma boa declaração de problema e um bom conceito de contexto de problema e, em seguida, precisa repetir as etapas de teste repetidas para ganhar o dia. Caso contrário, por nenhuma falha por conta própria, você poderá perder. Por quê? Bem, aqui estão alguns exemplos de instruções de problemas que não fornecem informações suficientes:
  
- Mudar de minha caixa de entrada para meu calendário costumava ser algo que eu não percebi, e agora é uma lanchonete. Você pode fazê-lo funcionar da mesma forma que costumava?
    
- Carregar meus arquivos no SharePoint Online está demorando para sempre. Por que ele é lento na tarde, mas em qualquer momento, é rápido? Não pode ser tão rápido?
    
Há vários grandes desafios representados pelas declarações problemáticas acima. Especificamente, há muitas ambigüidades com as quais lidar. por exemplo:
  
- Não está claro como alternar entre a caixa de entrada e o calendário usados para agir no laptop.
    
- Quando o usuário diz, "não pode simplesmente ser rápido", o que é "rápido"?
    
- Quanto tempo é "para sempre"? É um processo de vários segundos ou minutos, ou o usuário vai para almoçar e termina dez minutos após o retorno do usuário?
    
Tudo isso é sem considerar que o administrador e a solução de problemas não podem estar cientes de muitos detalhes de instruções de problemas como essas. Por exemplo, quando o problema começou a ocorrer; Que o usuário trabalha em casa e só vê o comutação mais lenta enquanto estiver em uma rede doméstica; Que o usuário deve executar vários outros aplicativos intensivos de RAM no cliente local ou que o usuário esteja executando um sistema operacional mais antigo ou não tenha executado atualizações recentes.
  
Quando os usuários relatam um problema de desempenho, há muitas informações a serem coletadas. A coleta dessas informações faz parte de um processo chamado escopo do problema ou de investigação. Veja a seguir uma lista básica de escopo que você pode usar para coletar informações sobre o problema de desempenho. Essa lista não é exaustiva, mas é um local para iniciar uma de suas próprias: 
  
- Em que data o problema aconteceu e em torno da hora do dia ou da noite?
    
- Que tipo de computador cliente você estava usando e como ele se conecta à rede corporativa (VPN, com fio, sem fio)?
    
- Você estava trabalhando remotamente ou estava no escritório?
    
- Você tentou as mesmas ações em outro computador e vê o mesmo comportamento?
    
- Percorra as etapas que estão dando a você o problema para que você possa escrever as ações que você tomar.
    
- Quão lenta em segundos ou minutos é o desempenho?
    
- Em que local do mundo está localizado?
    
Algumas dessas perguntas são mais óbvias que outras. A maioria das pessoas entenderá que a solução de problemas precisa de etapas exatas para reproduzir o problema. Afinal, de que outra forma é possível registrar o que há de errado e como você pode testar se o problema foi corrigido? Menos óbvias são coisas como "que data e hora você vê o problema?" e "onde no mundo estão localizados?", informações que podem ser usadas em conjunto. Dependendo de quando o usuário estava trabalhando, algumas horas de diferença podem significar que a manutenção já está em andamento em partes da rede da sua empresa. Se, por exemplo, sua empresa tem uma implementação híbrida, como uma pesquisa híbrida do SharePoint, que pode consultar índices de pesquisa no SharePoint Online e em uma instância do SharePoint Server 2013 local, as atualizações podem estar em andamento no farm local. Se sua empresa estiver em nuvem, a manutenção do sistema poderá incluir a adição ou remoção de hardware de rede, a distribuição de atualizações que são de toda a empresa ou a realização de alterações no DNS ou em outra infraestrutura principal.
  
Quando você está solucionando um problema de desempenho, é um pouco como uma cena de crime, você precisa ser preciso e observant para desenhar qualquer conclusões da evidência. Para fazer isso, você deve obter uma boa instrução problemática coletando evidências. Ele deve incluir o contexto do computador, o contexto do usuário, quando o problema começou e as etapas exatas que expuseram o problema de desempenho. Essa instrução de problema deve ser e permanecer, a página superior nas suas anotações. Ao percorrer a declaração do problema novamente depois de trabalhar com a resolução, você executará as etapas para testar e provar se as ações tomadas resolveram o problema. Isso é fundamental para saber quando seu trabalho, lá, está concluído.
  
## <a name="do-you-know-how-performance-used-to-look-when-it-was-good"></a>Você sabe como o desempenho costumava ser procurado quando era bom?

Se você estiver de sorte, ninguém sabe. Ninguém tinha números. Isso significa que ninguém pode responder a pergunta simples "sobre quantos segundos você costumava tomar para exibir uma caixa de entrada no Office 365?" ou "quanto tempo costumava ser feito quando os executivos tinham uma reunião do Lync Online?", que é um cenário comum para muitas empresas.
  
O que falta aqui é uma linha de base de desempenho.
  
As linhas de base fornecem um contexto para seu desempenho. Você deve levar uma linha de base às vezes, dependendo das necessidades da sua empresa. Se você é uma empresa maior, sua equipe de operações pode usar linhas de base para o seu ambiente local já. Por exemplo, se você corrigir todos os servidores do Exchange na primeira segunda-feira do mês e todos os seus servidores do SharePoint na segunda segunda-feira, sua equipe de operações provavelmente terá uma lista de tarefas e cenários que executa post-patch, para provar que as funções críticas estão operacionais. Por exemplo, abrir a caixa de entrada, clicar em enviar/receber e verificar se as pastas estão atualizadas ou, no SharePoint, navegando na página principal do site, entrando na página de pesquisa da empresa e fazendo uma pesquisa que retorne resultados.
  
Se seus aplicativos estiverem no Office 365, algumas das linhas de base mais fundamentais que você pode medir o tempo (em milissegundos) de um computador cliente dentro da rede, para um ponto de saída ou para o ponto em que você sai da rede e vá para o Office 365. Aqui estão algumas linhas de base úteis que podem ser investigadas e registradas:
  
- Identifique os dispositivos entre o computador cliente e o ponto de saída, por exemplo, seu servidor proxy.
    
  - Você precisa saber seus dispositivos para ter contexto (endereços IP, tipo de dispositivo, et cetera) para problemas de desempenho que surgem.
    
  - Os servidores proxy são pontos de egresso comuns, portanto, você pode verificar seu navegador da Web para ver qual servidor de proxy está definido para usar, se houver algum.
    
  - Há ferramentas de terceiros que podem descobrir e mapear sua rede, mas a maneira mais segura de saber seus dispositivos é solicitar um membro da sua equipe de rede.
    
- Identifique seu provedor de serviços de Internet (ISP), anote suas informações de contato e Pergunte quantos circuitos quanta de largura de banda você tem.
    
- Dentro da sua empresa, identifique os recursos para os dispositivos entre seu cliente e o ponto de egresso ou identifique um contato de emergência para falar sobre problemas de rede.
    
Aqui estão algumas linhas de base que os testes simples com as ferramentas podem calcular para você:
  
- Hora do computador cliente para o ponto de saída em milissegundos
    
- Hora do seu ponto de saída para o Office 365 em milissegundos
    
- Local no mundo do servidor que resolve as URLS para o Office 365 ao navegar
    
- A velocidade da resolução DNS do seu ISP em milissegundos, inconsistências na chegada de pacotes (tremulação de rede), tempos de carregamento e download em milissegundos
    
Se você não estiver familiarizado com o modo de realizar essas etapas, vamos nos aprofundar mais neste artigo. 
  
## <a name="what-is-a-baseline"></a>O que é uma linha de base?

Você saberá o impacto quando ele ficar ruim, mas se você não souber seus dados de desempenho históricos, não é possível ter um contexto de quanto o mau pode ter se tornado e quando. Portanto, sem uma linha de base, você não tem a pista principal para resolver o quebra-cabeça: a imagem na caixa de quebra-cabeça. Na solução de problemas de desempenho, você precisa de um ponto de  *comparação*  . Não é difícil realizar as linhas de base de desempenho simples. Sua equipe de operações pode ter a tarefa de realizar essas tarefas em um cronograma. Por exemplo, digamos que a conexão tenha a seguinte aparência: 
  
![Um gráfico de rede básico mostrando o cliente, o proxy e o Office 365 Cloud.](../media/c6ca7140-09f9-4c2d-a775-dbf2820eaa0c.PNG)
  
Isso significa que você verificou a equipe da sua rede e descobriu que você deixou sua empresa para a Internet por meio de um servidor proxy e que o proxy cuida de todas as solicitações que seu computador cliente envia para a nuvem. Nesse caso, você deve desenhar uma versão simplificada da sua conexão que lista todos os dispositivos intervenientes. Agora, insira ferramentas que você pode usar para testar o desempenho entre o cliente, o ponto de saída (onde você sai da rede para a Internet) e a nuvem do Office 365.
  
![Rede básica com cliente, proxy e nuvem, e ferramentas sugestões de PSPing, TraceTCP e rastreamentos de rede.](../media/627bfb77-abf7-4ef1-bbe8-7f8cbe48e1d2.png)
  
As opções são listadas como **simples** e **avançadas** por causa da quantidade de conhecimento necessária para localizar os dados de desempenho. Um rastreamento de rede levará muito tempo, comparado à execução de ferramentas de linha de comando, como PsPing e TraceTCP. Essas duas ferramentas de linha de comando foram escolhidas porque não usam pacotes ICMP, que serão bloqueados pelo Office 365, e como eles fornecem o tempo em milissegundos que é necessário para deixar o computador cliente ou servidor proxy (se você tiver acesso) e chegar ao Office 365. Cada salto individual de um computador para outro terminará com um valor de tempo, e isso é ótimo para as linhas de base! Da mesma forma, essas ferramentas de linha de comando permitem que você adicione um número de porta ao comando, isso é útil porque o Office 365 se comunica pela porta 443, que é a porta usada pela camada de soquetes seguros e pela segurança da camada de transporte (SSL e TLS). No entanto, outras ferramentas de terceiros podem ser soluções melhores para a sua situação. A Microsoft não dá suporte a todas essas ferramentas, portanto, se, por algum motivo, você não puder obter o PsPing e o TraceTCP funcionando, vá para um rastreamento de rede com uma ferramenta como Netmon. 
  
Você pode obter uma linha de base antes do horário comercial, novamente durante o uso pesado e, em seguida, novamente após as horas. Isso significa que você pode ter uma estrutura de pastas parecida com esta:
  
![Gráfico que propõe uma maneira de organizar seus dados de desempenho em pastas.](../media/13e01ffa-f0f2-4d10-b89d-d5980ec89fae.png)
  
Você também deve escolher uma Convenção de nomenclatura de seus arquivos. Aqui estão alguns exemplos:
  
- Feb_09_2015_9amPST_PerfBaseline_Netmon_ClientToEgress_Normal
    
- Jan_10_2015_3pmCST_PerfBaseline_PsPing_ClientToO365_bypassProxy_SLOW
    
- Feb_08_2015_2pmEST_PerfBaseline_BADPerf
    
- Feb_08_2015_8-30amEST_PerfBaseline_GoodPerf
    
Há várias maneiras diferentes de fazer isso, mas usar o formato **\<dateTime\>\<what's happening in the test\>** é um bom ponto de partida. Ser uma boa relação isso ajudará muito quando você estiver tentando solucionar problemas mais tarde. Mais tarde, você poderá dizer "Eu usei dois rastreamentos em fevereiro de 8, um mostrou um bom desempenho e um que mostrou mau, para que possamos compará-los". Isso é extremamente útil para a solução de problemas. 
  
Você precisa ter uma maneira organizada para manter suas linhas de base históricas. Neste exemplo, os métodos simples produziram três saídas de linha de comando e os resultados foram coletados como capturas de tela, mas você pode ter arquivos de captura de rede. Use o método que funciona melhor para você. Armazene suas linhas de base históricas e consulte-as em pontos em que você observa alterações no comportamento de serviços online. 
  
## <a name="why-collect-performance-data-during-a-pilot"></a>Por que coletar dados de desempenho durante um piloto?

Não há mais tempo para começar a criar linhas de base do que durante um piloto do serviço do Office 365. Seu escritório pode ter milhares de usuários, centenas de milhares ou pode ter cinco, mas até mesmo com um pequeno número de usuários, você pode executar testes para medir flutuações no desempenho. No caso de uma grande empresa, um exemplo representativo de várias centenas de usuários do Office 365 pode ser projetado para fora de vários milhares, para que você saiba onde podem surgir problemas antes que eles ocorram.
  
No caso de uma pequena empresa, em que a integração com o usuário significa que todos os usuários acessam o serviço ao mesmo tempo e não há nenhum piloto, mantenha medidas de desempenho para que você tenha dados a serem exibidos para qualquer pessoa que possa ter que solucionar uma operação incorreta. Por exemplo, se você notar que todos os tempos repentinos podem encaminhar o edifício no tempo necessário para carregar um gráfico de tamanho médio, onde costumava ocorrer muito rapidamente.
  
## <a name="how-to-collect-baselines"></a>Como coletar linhas de base

Para todos os planos de solução de problemas, você precisa identificar essas coisas no mínimo:
  
- O computador cliente que você está usando (o tipo de computador ou dispositivo, um endereço IP e as ações que causaram o problema)
    
- Onde o computador cliente está localizado no mundo (por exemplo, se esse usuário em uma VPN para a rede, trabalhando remotamente ou na intranet da empresa)
    
- O ponto de egresso que o computador cliente usa da sua rede (o ponto em que o tráfego deixa sua empresa para um ISP ou para a Internet)
    
 Você pode descobrir o layout da sua rede do administrador de rede. Se você estiver em uma rede pequena, confira os dispositivos que conectam você à Internet e chame seu ISP se você tiver dúvidas sobre o layout. Crie um gráfico do layout final da referência. 
  
Esta seção é dividida em ferramentas e métodos de linha de comando simples e opções de ferramentas mais avançadas. Abordaremos métodos simples primeiro. Mas se você tiver um problema de desempenho no momento, deverá saltar para os métodos avançados e testar o plano de ação desempenho da solução de problemas.
  
### <a name="simple-methods"></a>Métodos simples

O objetivo desses métodos simples é aprender a tomar, compreender e armazenar adequadamente as linhas de base de desempenho simples com o passar do tempo, para que você seja informado sobre o desempenho do Office 365. Este é o diagrama muito simples para simples, como você já viu:
  
![Rede básica com cliente, proxy e nuvem, e ferramentas sugestões de PSPing, TraceTCP e rastreamentos de rede.](../media/627bfb77-abf7-4ef1-bbe8-7f8cbe48e1d2.png)
  
> [!NOTE]
> O TraceTCP está incluído nesta captura de tela porque é uma ferramenta útil para exibição, em milissegundos, quanto tempo uma solicitação demora para ser processada e quantos saltos de rede, ou conexões de um computador para o próximo, que a solicitação leva para atingir um destino. TraceTCP também pode fornecer os nomes de servidores usados durante saltos, que podem ser úteis para uma solução de problemas do Microsoft Office 365 no suporte. > comandos TraceTCP podem ser muito simples, como: >  `tracetcp.exe outlook.office365.com:443`> Lembre-se de incluir o número da porta no comando! > O [TraceTCP](https://simulatedsimian.github.io/tracetcp_download.html) é um download gratuito, mas se baseia no Wincap. Wincap é uma ferramenta que também é usada e instalada pelo Netmon. Também usamos o Netmon na seção métodos avançados. 
  
 Se você tiver vários escritórios, precisará manter um conjunto de dados de um cliente em cada um desses locais também. Esse teste mede a latência, que, nesse caso, é um valor de número que descreve a quantidade de tempo entre um cliente enviando uma solicitação para o Office 365, e o Office 365 responder à solicitação. O teste é originado dentro do seu domínio em um computador cliente e procura medir uma viagem de dentro da sua rede, através de um ponto de egresso, através da Internet para o Office 365 e de volta. 
  
Há algumas maneiras de lidar com o ponto de egresso, nesse caso, o servidor proxy. Você pode rastrear de 1 a 2 e, em seguida, 2 a 3 e, em seguida, adicionar os números em milissegundos para obter um total final da borda da sua rede. Ou você pode configurar a conexão para ignorar o proxy para endereços do Office 365. Em uma rede maior com um firewall, um proxy reverso ou uma combinação dos dois, talvez seja necessário fazer exceções no servidor proxy, permitindo que o tráfego passe por muitas URLs. Para obter a lista de pontos de extremidade usados pelo Office 365, confira [URLs e intervalos de endereços IP do office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2). Se você tiver um proxy de autenticação, comece testando as exceções para o seguinte:
  
- Portas 80 e 443
    
- TCP e HTTPs
    
- Conexões que são de saída para qualquer uma destas URLs:
    
- \*. microsoftonline.com
    
- \*. microsoftonline-p.com
    
- \*.sharepoint.com
    
- \*. outlook.com
    
- \*. lync.com
    
- osub.microsoft.com
    
Todos os usuários precisam ter permissão para acessar esses endereços sem interferência de proxy ou autenticação. Em uma rede menor, você deve adicioná-los à sua lista de bypass de proxy no seu navegador da Web. 
  
Para adicioná-los à sua lista de proxies de proxy no Internet Explorer, vá para **ferramentas** \> **Opções da Internet** de \> **conexões** de \> **LAN** \> **avançadas**. A guia Avançado também é onde você encontrará seu servidor proxy e a porta do servidor proxy. Talvez seja necessário clicar na caixa de seleção **usar um servidor proxy para sua LAN**, para acessar o botão **avançado** . Você deve verificar se a opção **ignorar servidor proxy para endereços locais** está marcada. Depois de clicar em **avançado**, você verá uma caixa de texto onde você pode inserir exceções. Separe as URLs curinga listadas acima com ponto-e-vírgula, por exemplo:
  
\*. microsoftonline.com; \*. SharePoint.com
  
Depois de ignorar seu proxy, você deve ser capaz de usar ping ou PsPing diretamente em uma URL do Office 365. A próxima etapa será testar o ping **Outlook.office365.com**. Ou, se você estiver usando o PsPing ou outra ferramenta que permita que você forneça um número de porta ao comando, PsPing contra o **Portal.microsoftonline.com:443** para ver o tempo médio de ida e volta em milissegundos. 
  
O tempo de ida e volta, ou RTT, é um valor de número que mede quanto tempo leva para enviar uma solicitação HTTP para um servidor como o outlook.office365.com e obter uma resposta que reconheça o servidor sabe que você fez isso. Às vezes, você verá isso abreviado como RTT. Este deve ser um período relativamente curto.
  
Você precisa usar o [PSPing](https://technet.microsoft.com/sysinternals/jj729731.aspx) ou outra ferramenta que não use pacotes ICMP que são bloqueados pelo Office 365 para fazer esse teste. 
  
 **Como usar o PsPing para obter um tempo de ida e volta geral em milissegundos diretamente de uma URL do Office 365**
  
1. Execute um prompt de comando com privilégios elevados executando estas etapas:
    
1. Clique em **Iniciar**.
    
2. Na caixa **Iniciar pesquisa** , digite cmd e pressione Ctrl + Shift + Enter.
    
3. Se a caixa de diálogo **controle de conta de usuário** for exibida, confirme se a ação exibida é o que você deseja e clique em **continuar**.
    
2. Navegue até a pasta onde a ferramenta (neste caso, PsPing) está instalada e teste estas URLs do Office 365:
    
  - psping portal.office.com:443
    
  - psping microsoft-my.sharepoint.com:443
    
  - psping outlook.office365.com:443
    
  - psping www.yammer.com:443
    
    ![O comando PSPing indo para a porta 443 do microsoft-my.sharepoint.com.](../media/3258f620-4513-4e82-95c9-06b387fc3a82.PNG)
  
Certifique-se de incluir o número de porta de 443. Lembre-se de que o Office 365 funciona em um canal criptografado. Se você PsPing sem o número da porta, sua solicitação falhará. Após efetuar ping na lista curta, procure o tempo médio em milissegundos (MS). É o que você deseja gravar!
  
![Gráfico que mostra uma ilustração de PSPing de cliente para proxy com um tempo de ida e volta de 2,8 milissegundos.](../media/96901aea-1093-4f1b-b5a3-6078e9035e6c.png)
  
Se você não está familiarizado com o bypass de proxy e prefere realizar as coisas passo a passo, você precisa primeiro descobrir o nome do seu servidor proxy. No Internet Explorer, vá para **ferramentas** \> **Opções da Internet** \> **as** \> **configurações de LAN** \> **avançadas**. A guia **avançado** é onde você verá seu servidor proxy listado. Execute o ping no servidor proxy em um prompt de comando completando esta tarefa: 
  
 **Para executar ping no servidor proxy e obter um valor de ida e volta em milissegundos para o estágio 1 e 2**
  
1. Execute um prompt de comando com privilégios elevados executando estas etapas:
    
1. Clique em **Iniciar**.
    
2. Na caixa **Iniciar pesquisa** , digite cmd e pressione Ctrl + Shift + Enter.
    
3. Se a caixa de diálogo **controle de conta de usuário** for exibida, confirme se a ação exibida é o que você deseja e clique em **continuar**.
    
2. Digite ping \<the name of the proxy server your browser uses, or the IP address of the proxy server\> e pressione Enter. Se você tiver o PsPing ou alguma outra ferramenta instalada, poderá optar por usar essa ferramenta em vez disso. 
    
    O comando pode ser semelhante a um destes exemplos: 
    
  - ping ourproxy.ourdomain.industry.business.com
    
  - ping 155.55.121.55
    
  - ping ourproxy
    
  - psping ourproxy.ourdomain.industry.business.com:80
    
  - psping 155.55.121.55:80
    
  - psping ourproxy: 80
    
3. Quando o rastreamento parar de enviar pacotes de teste, você receberá um pequeno resumo que lista uma média, em milissegundos, e esse é o valor que você está fazendo. Faça uma captura de tela do prompt e salve-o usando sua Convenção de nomenclatura. Neste ponto, também pode ajudar a preencher o diagrama com o valor.
    
Talvez você tenha obtido um rastreamento na manhã inicial e seu cliente possa acessar o proxy (ou qualquer servidor de egresso que saia na Internet) rapidamente. Nesse caso, seus números podem ter a seguinte aparência:
  
![Gráfico que mostra o tempo de ida e volta de um cliente para um proxy de 2,8 milissegundos.](../media/1bd03544-23fc-47d4-bbae-c1feb466a5d8.PNG)
  
Se o computador cliente é um dos servidores selecionados com acesso ao proxy (ou Egresso), você pode executar o próximo trecho do teste conectando-se remotamente a esse computador, executando o prompt de comando para PsPing a uma URL do Office 365 de lá. Se você não tiver acesso a esse computador, poderá entrar em contato com seus recursos de rede para obter ajuda com o próximo trecho e obter os números exatos dessa forma. Se isso não for possível, confira PsPing sobre a URL do Office 365 em questão e compare-o com o PsPing ou o tempo de ping em relação ao servidor proxy. 
  
Por exemplo, se você tiver 51,84 milissegundos do cliente para a URL do Office 365 e tiver 2,8 milissegundos do cliente para o proxy (ou ponto de saída), você terá 49, 4 milissegundos da saída para o Office 365. Da mesma forma, se você tiver um PsPing de 12,25 milissegundos do cliente para o proxy durante a altura do dia e 62, 1 milissegundos do cliente para a URL do Office 365, o valor médio para a saída do proxy para a URL do Office 365 será de 49,76 milissegundos.
  
![Elemento gráfico adicional que mostra o ping em milissegundos do cliente para o proxy ao lado do cliente para o Office 365, de modo que os valores possam ser subtraídos.](../media/cd764e77-5154-44ba-a5cd-443a628eb2d9.PNG)
  
Em termos de solução de problemas, você pode achar algo interessante apenas de manter essas linhas de base. Por exemplo, se você achar que geralmente tem cerca de 40 a 59 milissegundos de latência do proxy ou ponto de saída para a URL do Office 365, e ter um cliente para a latência de proxy ou ponto de saída de cerca de 3 a 7 milissegundos (dependendo da quantidade de tráfego de rede que você está vendo durante esse horário do dia), você provavelmente saberá que algo é problemático se as suas últimas três cliente para a linha de base de proxy ou egresso mostrarem uma latência de 45 milissegundos.
  
### <a name="advanced-methods"></a>Métodos avançados

Se você realmente deseja saber o que está acontecendo com suas solicitações da Internet para o Office 365, você precisa se familiarizar com os rastreamentos de rede. Não importa quais ferramentas você prefere para esses rastreamentos, HTTPWatch, Netmon, analisador de mensagens, Wireshark, Fiddler, ferramenta de painel do desenvolvedor ou qualquer outra função, e o que a ferramenta pode capturar e filtrar o tráfego de rede. Você verá nesta seção que é benéfico executar mais de uma dessas ferramentas para obter uma imagem mais completa do problema. Quando você estiver testando, algumas dessas ferramentas também atuarão como proxies em seus próprios direitos. As ferramentas usadas no artigo complementar, [plano de solução de problemas de desempenho do Office 365](performance-troubleshooting-plan.md), incluem [Netmon 3,4](https://www.microsoft.com/download/details.aspx?id=4865), [HTTPWatch](https://www.httpwatch.com/download/)ou [Wireshark](https://www.wireshark.org/).
  
A realização de uma linha de base de desempenho é a parte simples desse método, e muitas das etapas são as mesmas que quando você soluciona um problema de desempenho. Os métodos mais avançados de criação de linhas de base para o desempenho exigem que você faça e armazene os rastreamentos de rede. A maioria dos exemplos neste artigo usam o SharePoint Online, mas você deve desenvolver uma lista de ações comuns nos serviços do Office 365 para os quais você se inscreveu para testar e registrar. Veja a seguir um exemplo de linha de base:
  
- Lista de linha de base para SPO-* * etapa 1: * * Navegue na home page do site do SPO e faça um rastreamento de rede. Salve o rastreamento. 
    
- Lista de linha de base para SPO- **etapa 2:** procurar um termo (como o nome da sua empresa) via pesquisa corporativa e fazer um rastreamento de rede. Salve o rastreamento. 
    
- Lista de linha de base para SPO- **etapa 3:** carregar um arquivo grande para uma biblioteca de documentos do SharePoint Online e fazer um rastreamento de rede. Salve o rastreamento. 
    
- Lista de linha de base para SPO- **etapa 4:** navegar pela Home Page do site do onedrive e fazer um rastreamento de rede. Salve o rastreamento. 
    
Essa lista deve incluir as ações comuns mais importantes que os usuários levam em relação ao SharePoint Online. Observe que a última etapa, para rastrear o OneDrive for Business, cria uma comparação entre a carga da home page do SharePoint Online (que é freqüentemente personalizada por empresas) e a home page do OneDrive for Business, que raramente é personalizada. Este é um teste muito básico quando se trata de um site do SharePoint Online com carregamento lento. Você pode criar um registro desta diferença em seus testes.
  
Se você estiver no meio de um problema de desempenho, muitas das etapas são as mesmas que ao obter uma linha de base. Os rastreamentos de rede se tornam críticos, portanto,  *vamos lidar com*  os principais rastreamentos a seguir. 
  
Para resolver um problema de desempenho,  *agora*  , você precisará fazer um rastreamento no momento em que estiver enfrentando o problema de desempenho. Você precisa ter as ferramentas adequadas disponíveis para coletar logs e precisa de um plano de ação, ou seja, uma lista de ações de solução de problemas a serem executadas para coletar as melhores informações que você pode. A primeira coisa a fazer é registrar a data e a hora do teste para que os arquivos possam ser salvos em uma pasta que reflita o intervalo. Em seguida, Refine as etapas do problema. Estas são as etapas exatas que você usará para testar. Não se esqueça dos conceitos básicos: se o problema for apenas com o Outlook, registre que o comportamento do problema ocorre em apenas um serviço do Office 365. Limitar o escopo desse problema ajudará você a se concentrar em algo que você pode resolver. 
  
## <a name="see-also"></a>Confira também

[Gerenciar pontos de extremidade do Office 365](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)

