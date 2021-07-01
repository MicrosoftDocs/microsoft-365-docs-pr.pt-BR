---
title: Plano de solução de problemas de desempenho do Office 365
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 5/10/2019
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
ms.assetid: e241e5d9-b1d8-4f1d-a5c8-4106b7325f8c
ms.collection:
- M365-security-compliance
- Ent_O365
description: Este artigo pode ajudá-lo a solucionar Office 365 problemas de desempenho e até mesmo corrigir alguns dos problemas mais comuns.
ms.openlocfilehash: 6ef459d6469881c71ea7d1da3a32eb42eb3ead6b
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/30/2021
ms.locfileid: "53229930"
---
# <a name="performance-troubleshooting-plan-for-office-365"></a>Plano de solução de problemas de desempenho do Office 365

Você precisa saber as etapas a serem tomadas para identificar e corrigir atrasos, travas e desempenho lento entre o SharePoint Online, OneDrive for Business, Exchange Online ou Skype for Business Online e seu computador cliente? Antes de chamar o suporte, este artigo pode ajudá-lo Office 365 problemas de desempenho e até mesmo corrigir alguns dos problemas mais comuns.

Este artigo é, na verdade, um plano de ação de exemplo que você pode usar para capturar dados valiosos sobre seu problema de desempenho enquanto ele está acontecendo. Alguns problemas principais também estão incluídos neste artigo.

Se você é novo no desempenho da rede e deseja fazer um plano de longo prazo para monitorar o desempenho entre suas máquinas cliente e o Office 365, confira Office 365 solução de problemas e ajuste de desempenho [-](performance-tuning-using-baselines-and-history.md)Administrador e ti Pro .

## <a name="sample-performance-troubleshooting-action-plan"></a>Exemplo de plano de ação de solução de problemas de desempenho

Este plano de ação contém duas partes; uma fase de preparação e uma fase de registro em log. Se você tiver um problema de desempenho agora e precisar fazer a coleta de dados, poderá começar a usar esse plano imediatamente.

### <a name="prepare-the-client-computer"></a>Preparar o computador cliente

- Encontre um computador cliente que possa reproduzir o problema de desempenho. Esse computador será usado durante a solução de problemas.
- Anote as etapas que causam o problema de desempenho para que você esteja pronto na hora de testar.
- Instalar ferramentas para coletar e gravar informações:
  - Instale [o Netmon 3.4](https://www.microsoft.com/download/details.aspx?id=4865) (ou use uma ferramenta de rastreamento de rede equivalente).
  - Instale a edição básica gratuita [do HTTPWatch](https://www.httpwatch.com/download/) (ou use uma ferramenta de Rastreamento de rede equivalente).
  - Use um gravador de tela ou execute o Gravador de Etapas (PSR.exe) que vem com o Windows Vista e posterior, para manter um registro das etapas que você executar durante o teste.

### <a name="log-the-performance-issue"></a>Registrar o problema de desempenho

- Feche todos os navegadores da Internet.
- Inicie o Gravador de Etapas ou outro gravador de tela.
- Inicie a captura netmon (ou ferramenta de rastreamento de rede).
- Limpe seu cache DNS no computador cliente da linha de comando digitando ipconfig /flushdns.
- Inicie uma nova sessão do navegador e a turn on HTTPWatch.
- Opcional: se você estiver testando Exchange Online, execute Exchange ferramenta analisador de desempenho do cliente Office 365 console de administração.
- Reproduza as etapas exatas que causam o problema de desempenho.
- Pare o rastreamento do Netmon ou de outra ferramenta.
- Na linha de comando, execute uma rota de rastreamento para sua assinatura Office 365 digitando o seguinte comando e pressionando ENTER:

  ``` cmd
  tracert <subscriptionname>.onmicrosoft.com
  ```

- Pare o Gravador de Etapas e salve o vídeo. Certifique-se de incluir a data e a hora da captura e se ela demonstra um desempenho bom ou ruim.
- Salve os arquivos de rastreamento. Novamente, certifique-se de incluir a data e a hora da captura e se ela demonstra um desempenho bom ou ruim.

Se você não estiver familiarizado com a execução das ferramentas mencionadas neste artigo, não se preocupe porque fornecemos essas etapas em seguida. Se você estiver acostumado a fazer esse tipo de captura de rede, poderá pular para [Como](performance-tuning-using-baselines-and-history.md#how-to-collect-baselines)coletar linhas de base , que descreve a filtragem e a leitura dos logs.

### <a name="flush-the-dns-cache-first"></a>Liberar primeiro o Cache DNS

Por quê? Ao liberar o cache DNS, você está iniciando seus testes com uma lousa limpa. Limpando o cache, você está redefinindo o conteúdo do resolvedor DNS para as entradas mais atualizadas. Lembre-se de que uma liberação não remove entradas de arquivo HOSTs. Se você usar entradas de arquivo HOST extensivamente, copie essas entradas para um arquivo em outro diretório e esvazie o arquivo HOST.

#### <a name="flush-your-dns-resolver-cache"></a>Liberar seu cache de resolver DNS

1. Abra o prompt de comando ( **iniciar** \> **executar** \> **cmd** ou **Windows** \> **tecla cmd**).
2. Digite o comando a seguir e pressione ENTER:

    ``` cmd
    ipconfig /flushdns
    ```

## <a name="netmon"></a>Netmon

A ferramenta de Monitoramento de Rede da Microsoft ([Netmon](https://www.microsoft.com/download/details.aspx?id=4865)) analisa pacotes, ou seja, o tráfego, que passa entre computadores em redes. Usando o Netmon para rastrear o tráfego com Office 365 você pode capturar, exibir e ler os headers de pacotes, identificar dispositivos intervenintes, verificar configurações importantes no hardware de rede, procurar pacotes descartados e seguir o fluxo de tráfego entre computadores em sua rede corporativa e Office 365. Como o corpo real do tráfego é criptografado, ou seja, ele (viaja na porta 443 via SSL/TLS, não é possível ler os arquivos que estão sendo enviados. Em vez disso, você recebe um rastreamento não filtrado do caminho que o pacote leva, o que pode ajudá-lo a rastrear o comportamento do problema.

Certifique-se de não aplicar um filtro no momento. Em vez disso, execute as etapas e demonstre o problema antes de parar o rastreamento e salvar.

Depois de instalar o Netmon 3.4, abra a ferramenta e tome estas etapas:

### <a name="take-a-netmon-trace-and-reproduce-the-issue"></a>Fazer um rastreamento netmon e reproduzir o problema

1. Iniciar Netmon 3.4.
Há três painéis  na página Iniciar: **Capturas** Recentes, **Selecionar Redes** e o Monitor de Rede da **Microsoft 3.4. Observe**. O painel Selecionar Redes também lhe dará uma lista das redes padrão das quais você pode capturar. Certifique-se de que os cartões de rede estão selecionados aqui.

2. Clique **em Nova Captura** na parte superior da **página** Iniciar. Isso adiciona uma nova guia ao lado da guia **Página** Inicial chamada **Captura 1**.
![A interface do usuário do Netmon com os botões Nova Captura, Início e Parada realçadas.](../media/d4527d84-62ec-4301-82d5-e0166ff71f20.PNG)

3. Para fazer uma captura simples, clique **em Iniciar** na barra de ferramentas.

4. Reproduza as etapas que apresentam um problema de desempenho.

5. Clique **em Parar** Salvar \> **Arquivo** \> **como**. Lembre-se de dar a data e hora com o fuso horário e mencionar se ele demonstra um desempenho ruim ou bom.

## <a name="httpwatch"></a>HTTPWatch

[HTTPWatch](https://www.httpwatch.com/download/) é cobrado e uma edição gratuita. A edição básica gratuita abrange tudo o que você precisa para este teste. HTTPWatch monitora o tráfego de rede e o tempo de carregamento da página desde a janela do navegador. HTTPWatch é um plug-in para o Internet Explorer que descreve graficamente o desempenho. A análise pode ser salva e exibida no HTTPWatch Studio.

> [!NOTE]
> Se você usar outro navegador, como Firefox, Google Chrome ou se não puder instalar HTTPWatch no Internet Explorer, abra uma nova janela do navegador e pressione F12 no teclado. Você deve ver o pop-up ferramenta de desenvolvedor na parte inferior do navegador. Se você usar o Opera, pressione CTRL+SHIFT+I  para Web Inspector e clique na guia Rede e conclua o teste descrito abaixo. As informações serão ligeiramente diferentes, mas os tempos de carga ainda serão exibidos em milissegundos. > HTTPWatch também é muito útil para problemas com SharePoint de carga de página online.

### <a name="run-httpwatch-and-reproduce-the-issue"></a>Executar HTTPWatch e reproduzir o problema

HTTPWatch é um plug-in do navegador, portanto, expor a ferramenta no navegador é um pouco diferente para cada versão do Internet Explorer. Normalmente, você pode encontrar HTTPWatch na barra Comandos no navegador do Internet Explorer. Se você não vir o plug-in HTTPWatch na janela do navegador,  verifique a versão do navegador clicando em Ajuda Sobre ou em versões posteriores do Internet Explorer, clique no símbolo de engrenagem e sobre \> o **Internet Explorer**. Para iniciar a barra **comandos,** clique com o botão direito do mouse na barra de menus no Internet Explorer e clique **em Barra de Comandos.**

No passado, HTTPWatch foi associado aos comandos e às barras explorer, portanto, depois de instalar, se você não vir imediatamente o ícone (mesmo depois da reinicialização), verifique **Ferramentas** e suas barras de ferramentas para o ícone. Lembre-se de que as barras de ferramentas podem ser personalizadas e as opções podem ser adicionadas a elas.

![Barra de ferramentas Comando do Internet Explorer com o ícone HTTPWatch exibido.](../media/198590b0-d7b1-4bff-a6ad-e4ec3a1e83df.png)

1. Iniciar HTTPWatch em uma janela de navegador do Internet Explorer. Ele aparecerá encaixado no navegador na parte inferior dessa janela. Clique **em Registro**.

2. Reproduza as etapas exatas envolvidas no problema de desempenho. Clique no **botão Parar** em HTTPWatch.

3. **Salve** HTTPWatch ou **Enviar por Email.** Lembre-se de nomear o arquivo para que ele inclua informações de data e hora e uma indicação de se seu Relógio contém uma demonstração de bom ou ruim desempenho.

![HTTPWatch mostrando a guia Rede para um carregamento de página da home page do Office 365.](../media/021a2c64-d581-49fd-adf4-4c364f589d75.PNG)

Esta captura de tela é da Professional versão do HTTPWatch. Você pode abrir os rastreamentos feitos na Versão Básica em um computador com uma versão Professional e lê-la lá. Informações adicionais podem estar disponíveis a partir do rastreamento por meio desse método.

## <a name="problem-steps-recorder"></a>Gravador de Etapas do Problema

Steps Recorder, ou PSR.exe, permite que você grave problemas à medida que eles estão ocorrendo. É uma ferramenta muito útil e muito simples de ser executado.

### <a name="run-problem-steps-recorder-psrexe-to-record-your-work"></a>Executar o Gravador de Etapas de Problemas (PSR.exe) para gravar seu trabalho

1. Use **Start** \> **Run type** \> **PSR.exe** \> **OK** ou,  \>  \> clique no tipo de tecla Windows teclaPSR.exepressione ENTER.

2. Quando a janela PSR.exe pequena for exibida, clique em **Iniciar Registro** e reproduza as etapas que reproduzem o problema de desempenho. Você pode adicionar comentários conforme necessário, clicando em **Adicionar Comentários**.

3. Clique **em Parar Registro** quando tiver concluído as etapas. Se o problema de desempenho for uma renderização de página, aguarde a renderização da página antes de interromper a gravação.

4. Clique em **Salvar**.

![Uma captura de tela do Gravador de Etapas ou PSR.exe.](../media/8542b0aa-a3ff-4718-8dc4-43f5521c6c34.PNG)

A data e a hora são gravadas para você. Isso vincula seu PSR ao rastreamento netmon e HTTPWatch a tempo e ajuda na solução de problemas de precisão. A data e a hora no registro PSR podem mostrar que um minuto passou entre o logon e a navegação da URL e a renderização parcial do site de administração, por exemplo.

## <a name="read-your-traces"></a>Ler seus rastreamentos

Não é possível ensinar tudo sobre a solução de problemas de rede e desempenho que alguém precisaria saber por meio de um artigo. Obter bom desempenho requer experiência e conhecimento de como sua rede funciona e normalmente é bem-desempenho. Mas é possível arredondar uma lista de principais problemas e mostrar como as ferramentas podem facilitar a eliminação dos problemas mais comuns.

Se você quiser escolher habilidades de leitura de rastreamentos de rede para seus sites Office 365, não há professor melhor do que criar rastreamentos de cargas de página regularmente e ganhar experiência lendo-os. Por exemplo, quando você tiver uma chance, carregue um serviço Office 365 e rastree o processo. Filtre o rastreamento para o tráfego DNS ou pesquise o FrameData para o nome do serviço que você navegueu. Scan the trace to get a idea of the steps that occur when the service loads. Isso ajudará você a saber como deve ser a carga de página normal e, no caso de solução de problemas, especialmente em relação ao desempenho, comparar bons a rastreamentos ruins pode ensinar muito.

Netmon usa o Microsoft Intellisense no campo Exibir filtro. Intellisense, ou conclusão inteligente de código, é aquele truque em que você digita um ponto e todas as opções disponíveis são exibidas em uma caixa de seleção listada. Se, por exemplo, você estiver preocupado com o dimensionamento da janela TCP, poderá encontrar seu caminho para um filtro (como  `.protocol.tcp.window < 100` ) por esse meio.

![Captura de tela de Netmon mostrando que o campo Filtro de Exibição usa o intellisense.](../media/75a56c11-9a60-47ee-a100-aabdfb1ba10f.PNG)

Rastreamentos de Netmon podem ter muito tráfego neles. Se você não tiver experiência em lê-los, é provável que você fique sobrecarregado abrindo o rastreamento da primeira vez. A primeira coisa a fazer é separar o sinal do ruído em segundo plano no rastreamento. Você testou Office 365, e esse é o tráfego que você deseja ver. Se você estiver acostumado a navegar por rastreamentos, talvez não precise dessa lista.

O tráfego entre seu cliente e Office 365 viaja via TLS, o que significa que o corpo do tráfego será criptografado e não acessível em um rastreamento Netmon genérico. Sua análise de desempenho não precisa saber os detalhes das informações no pacote. No entanto, ele está muito interessado nos headers de pacotes e nas informações que eles contêm.

### <a name="tips-to-get-a-good-trace"></a>Dicas obter um bom rastreamento

- Saiba o valor do endereço IPv4 ou IPv6 do computador cliente. Você pode obter isso no prompt de comando digitando **IPConfig** e pressionando ENTER. Saber esse endereço permitirá que você diga rapidamente se o tráfego no rastreamento envolve diretamente o computador cliente. Se houver um proxy conhecido, ping-lo e obter seu endereço IP também.

- Flush your DNS resolve cache and, if possible, close all browsers except the one in which you are running your tests. Se você não conseguir fazer isso, por exemplo, se o suporte estiver usando alguma ferramenta baseada em navegador para ver a área de trabalho do computador cliente, esteja preparado para filtrar seu rastreamento.

- Em um rastreamento de ocupado, localize o Office 365 serviço que você está usando. Se você nunca viu ou raramente o tráfego antes, essa é uma etapa útil para separar o problema de desempenho de outros ruídos de rede. Há algumas maneiras de fazer isso. Diretamente antes do teste, você pode usar _ping_ ou _PsPing_ na URL do serviço específico ( `ping outlook.office365.com` ou , por `psping -4 microsoft-my.sharepoint.com:443` exemplo). Você também pode facilmente encontrar esse ping ou PsPing em um rastreamento Netmon (pelo nome do processo). Isso lhe dará um lugar para começar a procurar.

Se você estiver usando apenas o rastreamento netmon no momento do problema, tudo bem também. Para se orientar, use um filtro como `ContainsBin(FrameData, ASCII, "office")` ou `ContainsBin(FrameData, ASCII, "outlook")` . Você pode gravar o número do quadro do arquivo de rastreamento. Você também pode querer rolar o painel _Resumo_ de Quadros até a direita e procurar a coluna ID da Conversa. Há um número indicado lá para a ID dessa conversa específica que você também pode registrar e olhar em isolamento posteriormente. Lembre-se de remover esse filtro antes de aplicar qualquer outra filtragem.

> [!TIP]
> Netmon tem muitos filtros integrados úteis. Experimente o **botão Filtro de** Carga na parte superior do painel _Filtro_ de Exibição.

![Encontre seu IP usando PSPing na linha de comando no computador cliente.](../media/4c43ac67-e28e-4536-842d-7add7aa28847.PNG)

![Rastreamento netmon do cliente mostrando o mesmo comando PSPing por meio do TCP do filtro. Flags.Syn == 1.](../media/0ae7ef7d-e003-4d01-a006-dc49bd1fcef2.PNG)

Familiarize-se com seu tráfego e aprenda a localizar as informações necessárias. Por exemplo, saiba como determinar qual pacote no rastreamento tem a primeira referência ao serviço Office 365 que você está usando (como "Outlook").

Tendo Office 365 Outlook Online como exemplo, o tráfego começa algo assim:

- Consulta Padrão DNS e Resposta DNS para outlook.office365.com com QueryIDs correspondentes. É importante observar o deslocamento de tempo para esse turn-around, bem como onde, no mundo, o DNS global Office 365 envia a solicitação de resolução de nome. Idealmente, o mais localmente possível, em vez de metade do mundo.

- Uma Solicitação GET HTTP cujo relatório de status foi movido permanentemente (301)

- Tráfego RWS incluindo Conexão RWS e Conexão respostas. (Este é Remote Winsock fazendo uma conexão para você.)

- Uma conversa TCP SYN e TCP SYN/ACK. Muitas das configurações nesta conversa impactam seu desempenho.

- Em seguida, uma série de tráfego TLS:TLS que é onde o handshake TLS e conversas de certificado TLS ocorrem. (Lembre-se de que os dados são criptografados via SSL/TLS.)

Todas as partes do tráfego são importantes e conectadas, mas pequenas partes do rastreamento contêm informações particularmente importantes em termos de solução de problemas de desempenho, portanto, vamos nos concentrar nessas áreas. Além disso, como já fizemos o suficiente Office 365 solução de problemas de desempenho na Microsoft para compilar uma lista Top Ten de problemas comuns, vamos nos concentrar nesses problemas e como usar as ferramentas que precisamos para enraizar a seguir.

Se você não tiver instalado todos eles prontos, a matriz abaixo usará várias ferramentas. Sempre que possível. Links são fornecidos para os pontos de instalação. A lista inclui ferramentas comuns de rastreamento de rede, como [Netmon](https://www.microsoft.com/download/details.aspx?id=4865) e [Wireshark](https://www.wireshark.org/), mas use qualquer ferramenta de rastreamento com a qual você esteja confortável e na qual você está acostumado a filtrar o tráfego de rede. Ao testar, lembre-se:

- *Feche seus navegadores e teste com apenas um navegador*  em execução - Isso reduzirá o tráfego geral que você capturar. Isso faz com que um rastreamento menos ocupado.
- *Flush your DNS resolve cache on the client computer*  - This will give you a clean slate when you start to take your capture, for a cleaner trace.

## <a name="common-issues"></a>Problemas comuns

Alguns problemas comuns que você pode enfrentar e como encontrá-los em seu rastreamento de rede.

### <a name="tcp-windows-scaling"></a>Dimensionamento Windows TCP

Encontrado no SYN - SYN/ACK. O hardware herdado ou antigo pode não tirar proveito do dimensionamento de janelas TCP.  Sem configurações de dimensionamento de janelas TCP adequadas, o buffer padrão de 16 bits em headers TCP preenche milissegundos.  O tráfego não pode continuar a ser enviado até que o cliente receba um reconhecimento de que os dados originais foram recebidos, causando atrasos.

#### <a name="tools"></a>Ferramentas

- Netmon
- Wireshark

#### <a name="what-to-look-for"></a>O que procurar

Procure o tráfego SYN - SYN/ACK em seu rastreamento de rede.  Em Netmon, use um filtro como  `tcp.flags.syn == 1` . Esse filtro é o mesmo em Wireshark.

![Filtrar em Netmon ou Wireshark para pacotes Syn para ambas as ferramentas: TCP. Flags.Syn == 1.](../media/4b9a12a1-c915-43c8-ac2f-a679d0435a29.PNG)

Observe que para cada SYN há um número de porta de origem (SrcPort) que é corresponder na porta de destino (DstPort) do reconhecimento relacionado (SYN/ACK).

Para ver o valor Windows dimensionamento usado pela conexão de rede, expanda primeiro o SYN e, em seguida, o SYN/ACK relacionado.

![Gráfico que mostra como corresponder SrcPort a DstPort em um rastreamento, para obter o delta de tempo.](../media/6a4ca573-0253-4fbd-93e8-92821ee1c351.png)

### <a name="tcp-idle-time-settings"></a>Tempo ocioso TCP Configurações

Historicamente, a maioria das redes de perímetro é configurada para conexões transitórias, o que significa que as conexões ociosas geralmente são encerradas. As sessões TCP ociosas podem ser encerradas por proxies e firewalls com mais de 100 a 300 segundos. Isso é problemático para o Outlook Online porque ele cria e usa conexões de longo prazo, sejam elas ociosas ou não.

Quando as conexões são encerradas por dispositivos de proxy ou firewall, o cliente não é informado, e uma tentativa de usar o Outlook Online significa que um computador cliente tentará, repetidamente, reavivar a conexão antes de fazer uma nova. Você pode ver travas no produto, prompts ou desempenho lento na carga da página.

#### <a name="tools"></a>Ferramentas

- Netmon
- Wireshark

#### <a name="what-to-look-for"></a>O que procurar

Em Netmon, veja o campo Deslocamento de Tempo para uma viagem de ida e volta. Uma viagem de ida e volta é o tempo entre o cliente enviar uma solicitação para o servidor e receber uma resposta de volta. Verifique entre o Cliente e o ponto de saída (ex. Cliente - \> Proxy) ou o Cliente a Office 365 (Cliente - \> Office 365). Você pode ver isso em vários tipos de pacotes.

Como exemplo, o filtro em Netmon pode ter a aparência  `.Protocol.IPv4.Address == 10.102.14.112 AND .Protocol.IPv4.Address == 10.201.114.12` , ou, em Wireshark,  `ip.addr == 10.102.14.112 &amp;&amp; ip.addr == 10.201.114.12` .

> [!TIP]
> Não sabe se o endereço IP em seu rastreamento pertence ao seu servidor DNS? Tente procurá-lo na linha de comando. Clique **em Iniciar** \> **Executar** e digite \> **cmd** ou pressione **Windows Tecla** e digite \> **cmd**. No prompt, digite  `nslookup <the IP address from the network trace>` . Para testar, use nslookup no endereço IP do seu próprio computador. > Para ver uma lista de intervalos IP da Microsoft, [consulte Office 365 URLs e intervalos de endereços IP](./urls-and-ip-address-ranges.md).

Se houver um problema, espere que deslocamentos de tempo longo apareçam, nesse caso (Outlook Online), particularmente em pacotes TLS:TLS que mostram a passagem dos Dados do Aplicativo (por exemplo, no Netmon, você pode encontrar pacotes de dados de aplicativo via `.Protocol.TLS AND Description == "TLS:TLS Rec Layer-1 SSL Application Data"` ). Você deve ver uma progressão suave no tempo durante a sessão. Se você vir atrasos longos ao atualizar seu Outlook Online, isso pode ser causado por um alto grau de redefinições que estão sendo enviadas.

### <a name="latencyround-trip-time"></a>Tempo de latência/ida e volta

Latência é uma medida que pode mudar muito dependendo de muitas variáveis, como atualizar dispositivos de envelhecimento, adicionar um grande número de usuários a uma rede e a porcentagem de largura de banda geral consumida por outras tarefas em uma conexão de rede.

Há calculadoras de largura de banda para Office 365 disponíveis nesta página planejamento de rede e ajuste de desempenho [para Office 365](network-planning-and-performance.md) página.

Precisa medir a velocidade da sua conexão ou a largura de banda da sua conexão ISP? Experimente este site (ou sites como ele): [Acelere o Site Oficial](https://www.speedtest.net/)ou consulte seu mecanismo de pesquisa favorito para o teste de velocidade **da frase.**

#### <a name="tools"></a>Ferramentas

- Ping
- PsPing
- Netmon
- Wireshark

#### <a name="what-to-look-for"></a>O que procurar

Para rastrear a latência em um rastreamento, você se beneficiará de ter gravado o endereço IP do computador cliente e o endereço IP do servidor DNS no Office 365. Isso serve para facilitar a filtragem de rastreamento. Se você se conectar por meio de um proxy, precisará do endereço IP do computador cliente, do endereço IP proxy/saída e do endereço IP Office 365 DNS para facilitar o trabalho.

Uma solicitação de ping enviada outlook.office365.com o nome do datacenter que recebe a solicitação, mesmo que  *o*  ping possa não ser capaz de se conectar para enviar pacotes ICMP consecutivos da marca registrada. Se você usar o PsPing (uma ferramenta gratuita para download) e específica a porta (443) e talvez usar IPv4 (-4), você receberá uma média de ida e volta para pacotes enviados. Isso funcionará para outras URLs nos serviços Office 365, como `psping -4 yourSite.sharepoint.com:443` . Na verdade, você pode especificar um número de pings para obter um exemplo maior para sua média, tente algo como `psping -4 -n 20 yourSite-my.sharepoint.com:443` .

> [!NOTE]
> O PsPing não envia pacotes ICMP. Ele pings com pacotes TCP em uma porta específica, para que você possa usar qualquer um que você saiba que está aberto. No Office 365, que usa SSL/TLS, tente anexar a porta :443 ao seu PsPing.

![Captura de tela que mostra um ping resolvendo outlook.office365.com e um PSPing com o 443 fazendo o mesmo, mas também relatando um RTT médio de 6,5ms.](../media/c64339f2-2c96-45b8-b168-c2a060430266.PNG)

Se você carregou a página de Office 365 de desempenho lento durante um rastreamento de rede, você deve filtrar um rastreamento Netmon ou Wireshark para `DNS` . Este é um dos IPs que estamos procurando.

Aqui estão as etapas a serem tomadas para filtrar seu Netmon para obter o endereço IP (e dar uma olhada na Latência DNS). Este exemplo usa outlook.office365.com, mas também pode usar a URL de um locatário SharePoint Online (hithere.sharepoint.com por exemplo).

1. Ping a URL e, nos resultados, grave o nome e o endereço IP do servidor DNS para o que a solicitação `ping outlook.office365.com` de ping foi enviada.
2. Rastreamento de rede abrindo a página ou fazendo a ação que oferece o problema de desempenho ou, se você vir uma alta latência no ping, rastreá-la.
3. Abra o rastreamento em Netmon e filtre para DNS (esse filtro também funciona em Wireshark, mas é sensível a caso `-- dns` ). Como você sabe o nome do servidor DNS do seu ping, você também pode filtrar mais rapidamente no Netmon assim: , o que se parece com isso no dns do Wireshark e o quadro contém `DNS AND ContainsBin(FrameData, ASCII, "namnorthwest")` "namnorthwest".<br/>Abra o pacote de resposta e, na janela Detalhes do **Quadro** netmon, clique em **DNS** para expandir para obter mais informações. Nas informações DNS, você encontrará o endereço IP do servidor DNS para o Office 365. Você precisará desse endereço IP para a próxima etapa (a ferramenta PsPing). Remova o filtro, clique com o botão direito do mouse na Resposta DNS no Netmon **(** Resumo de Quadros Encontrar Conversas DNS ) para ver a Consulta DNS e a Resposta \>  \> lado a lado.
4. No Netmon, observe também a coluna Deslocamento de Tempo entre a Solicitação DNS e a Resposta. Na próxima etapa, a ferramenta [PsPing](/sysinternals/downloads/psping) fácil de instalar e usar é muito útil, tanto porque o ICMP costuma ser bloqueado em Firewalls e porque o PsPing rastreia com elegância a latência em milissegundos. O PsPing conclui uma conexão TCP com um endereço e uma porta (no nosso caso, porta aberta 443).
5. Instalar o PsPing.
6. Abra um prompt de comando (cmd do tipo Start Run ou Windows Tipo de chave) e altere o diretório para o diretório onde você instalou o PsPing para executar o \> \> comando \> PsPing. Em meus exemplos, você pode ver que eu fiz uma pasta 'Perf' na raiz de C. Você pode fazer o mesmo para acesso rápido.
7. Digite o comando para que você esteja fazendo seu PsPing no endereço IP do servidor DNS Office 365 do rastreamento Netmon anterior, incluindo o número da porta, como `psping -n 20 132.245.24.82:445` . Isso lhe dará uma amostragem de 20 pings e a latência média quando o PsPing for interrompido.

Se você estiver indo para Office 365 por meio de um servidor proxy, as etapas são um pouco diferentes. Primeiro, psPing para seu servidor proxy para obter um valor médio de latência em milissegundos para proxy/saída e voltar e, em seguida, executar PsPing no proxy ou em um computador com uma conexão direta com a Internet para obter o valor ausente (aquele para Office 365 e voltar).

Se você optar por executar o PsPing no proxy, terá dois valores de milissegundos: computador cliente para servidor proxy ou ponto de saída e servidor proxy para Office 365. E você terminou! Bem, gravando valores, de qualquer maneira.

Se você executar o PsPing em outro computador cliente que tenha uma conexão direta com a Internet, ou seja, sem um proxy, você terá dois valores de milissegundos: computador cliente para servidor proxy ou ponto de saída e computador cliente para Office 365. Nesse caso, subtraia o valor do computador cliente para o servidor proxy ou ponto de saída do valor do computador cliente para o Office 365, e você terá os números RTT do seu computador cliente para o servidor proxy ou ponto de saída, e do servidor proxy ou saída apontar para Office 365.

No entanto, se você puder encontrar um computador cliente no local afetado diretamente conectado ou ignorar o proxy, você poderá optar por ver se o problema se reproduz para começar e testá-lo posteriormente.

Latência, como visto em um rastreamento Netmon, esses milissegundos extras podem ser acrescentados, se houver o suficiente em qualquer sessão.

![Latência geral no Netmon, com a coluna de Intervalo de Tempo padrão do Netmon adicionada ao Resumo do Quadro.](../media/7ad17380-8527-4bc2-9b9b-6310cf19ba6b.PNG)

> [!NOTE]
> Seu endereço IP pode ser diferente dos IPs mostrados aqui, por exemplo, seu ping pode retornar algo mais parecido com 157.56.0.0/16 ou um intervalo semelhante. Para uma lista de intervalos usados por Office 365, confira [Office 365 URLs e intervalos de endereços IP.](./urls-and-ip-address-ranges.md)

Lembre-se de expandir todos os nós (há um botão na parte superior para isso) se você quiser pesquisar, por exemplo, 132.245.

### <a name="proxy-authentication"></a>Autenticação proxy

Isso só se aplica a você se você estiver passando por um servidor proxy. Caso não seja, você pode ignorar essas etapas. Ao trabalhar corretamente, a autenticação de proxy deve ocorrer em milissegundos, de forma consistente. Você não deve ver um desempenho intermitente ruim durante os períodos de uso de pico (por exemplo).

Se a autenticação de proxy estiver em, cada vez que você fizer uma nova conexão TCP para Office 365 obter informações, precisará passar por um processo de autenticação nos bastidores. Portanto, por exemplo, ao alternar de Calendário para Email no Outlook Online, você autenticará. E no SharePoint Online, se uma página exibir mídia ou dados de vários sites ou locais, você será autenticado para cada conexão TCP diferente necessária para renderizar os dados.

No Outlook Online, você pode experimentar tempos de carga lentos sempre que alternar entre Calendário e sua caixa de correio ou carregar páginas lentas no SharePoint Online. No entanto, há outros sintomas não listados aqui.

Autenticação de proxy é uma configuração no servidor proxy de saída. Se estiver causando um problema de desempenho com Office 365, consulte sua equipe de rede.

#### <a name="tools"></a>Ferramentas

- Netmon
- Wireshark

#### <a name="what-to-look-for"></a>O que procurar

A autenticação de proxy ocorre sempre que uma nova sessão TCP deve ser girada, geralmente para solicitar arquivos ou informações do servidor ou para fornecer informações. Por exemplo, você pode ver a autenticação de proxy em torno de solicitações HTTP GET ou HTTP POST. Se você quiser ver os quadros onde você está autenticando solicitações em seu rastreamento, adicione a coluna 'Resumo do NTLMSSP' ao Netmon e filtre  `.property.NTLMSSPSummary` para . Para ver quanto tempo a autenticação está demorando, adicione a coluna Delta do Tempo.

Para adicionar uma coluna ao Netmon:

1. Clique com o botão direito do mouse em uma coluna como **Descrição**.
2. Clique **em Escolher Colunas**.
3. Localize _o Resumo do NTLMSSP_ e o _Delta_ de Tempo na lista e clique em **Adicionar**.
4. Mova as novas colunas para o lugar antes ou atrás da coluna _Descrição_ para que você possa lê-las lado a lado.
5. Clique em **OK**.

Mesmo que você não adicione a coluna, o filtro Netmon funcionará. Mas sua solução de problemas será muito mais fácil se você puder ver em qual estágio de autenticação você está.

Ao procurar instâncias de Autenticação de Proxy, certifique-se de estudar todos os quadros onde há um Desafio NTLM ou uma Mensagem autenticada está presente. Se necessário, clique com o botão direito do mouse na parte específica do tráfego e encontre conversas \> TCP. Esteja ciente dos valores delta de tempo nessas conversas.

![Rastreamento netmon mostrando autenticação de proxy, filtrada por conversa.](../media/b640f176-0a52-4bbb-972e-60fb3d6aece2.PNG)

Um atraso de quatro segundos na autenticação de proxy, conforme visto em Wireshark. O **delta de hora** da coluna de quadro exibido anterior foi feita clicando com o botão direito do mouse no campo do mesmo nome nos detalhes do quadro e selecionando Adicionar como Coluna.  <br/> ![Em Wireshark, a coluna "Delta de tempo do quadro exibido anterior" pode ser feita clicando com o botão direito do mouse no campo do mesmo nome nos detalhes do quadro e selecionando Adicionar como Coluna.](../media/f5b7bde4-8067-4ee0-bc7f-e9062ce1ba6f.PNG)

### <a name="dns-performance"></a>Desempenho DNS

A resolução de nomes funciona melhor e mais rapidamente quando ocorre o mais próximo possível do país do cliente.

Se a resolução de nome DNS estiver ocorrendo no exterior, ela poderá adicionar segundos a cargas de página. Idealmente, a resolução de nomes acontece em menos de 100 ms. Caso não seja, você deve fazer uma investigação posterior.

> [!TIP]
> Não tem certeza de como a Conectividade do Cliente funciona Office 365? Confira o documento referência de conectividade do cliente [aqui](/previous-versions//dn741250(v=technet.10)).

#### <a name="tools"></a>Ferramentas

- Netmon
- Wireshark
- PsPing

#### <a name="what-to-look-for"></a>O que procurar

Analisar o desempenho dns normalmente é outro trabalho para um rastreamento de rede. No entanto, o PsPing também é útil para descartar ou descartar uma possível causa.

O tráfego DNS é baseado em solicitações e respostas TCP e UDP são claramente marcadas com uma ID que ajudará a corresponder uma solicitação específica com sua resposta específica. Você verá o tráfego DNS quando, por exemplo, SharePoint Online usa um nome de rede ou URL em uma página da Web. Como regra geral, a maior parte desse tráfego, exceto ao transferir zonas, passa por cima do UDP.

No Netmon e no Wireshark, o filtro mais básico que permitirá que você veja o tráfego DNS é simplesmente `dns` . Certifique-se de usar uma caixa inferior ao especificar o filtro. Lembre-se de liberar o cache do resolver DNS antes de começar a reproduzir o problema no computador cliente. Por exemplo, se você tiver uma carga de página SharePoint Online lenta para a Home page, deverá fechar todos os navegadores, abrir um novo navegador, iniciar o rastreamento, liberar o cache do resolver DNS e navegar até o site SharePoint Online. Depois que a página inteira é resolvida, você deve parar e salvar o rastreamento.

![No Netmon, um filtro básico para DNS é DNS.](../media/1bebc118-ca13-45f3-803f-ab73e7af401d.png)

Você deseja ver o deslocamento de tempo aqui. E pode ser útil adicionar a coluna **Delta** do Tempo ao Netmon, o que você pode fazer concluindo estas etapas:

1. Clique com o botão direito do mouse em uma coluna como **Descrição**.
2. Clique **em Escolher Colunas**.
3. Localize _o Delta_ do Tempo na lista e clique em **Adicionar**.
4. Mova a nova coluna para o lugar antes ou atrás da coluna _Descrição_ para que você possa lê-la lado a lado.
5. Clique em **OK**.

Se você encontrar uma consulta de interesse, considere isola-la clicando com o botão direito do mouse nessa consulta no painel de detalhes do quadro, escolhendo **Encontrar Conversas** \> **DNS**. Observe que o painel Conversas de Rede salta direto para a conversa específica em seu log de tráfego UDP.

![Um rastreamento netmon de Outlook online filtrado por DNS e usando Localizar Conversas e DNS para restringir os resultados.](../media/763cf20e-7b48-4a37-9449-c9978cfe118b.PNG)

No Wireshark, você pode fazer uma coluna para o tempo DNS. Pegue seu rastreamento (ou abra um rastreamento) em Wireshark e filtre por , ou, de forma mais `dns` útil,  `dns.time` . Clique em qualquer consulta DNS e, no painel mostrando detalhes, expanda os  `Domain Name System (response)` detalhes. Você verá um campo por tempo (por exemplo, `[Time: 0.001111100 seconds]` . Clique com o botão direito do mouse desta vez e selecione **Aplicar como Coluna**. Isso lhe dará uma **coluna Time** para uma classificação mais rápida do rastreamento. Clique na nova coluna para classificar por valores decrescentes para ver qual chamada DNS levou mais tempo para ser resolvida.

[Uma procura do SharePoint Online filtrada no Wireshark por dns.time (minúsculas), com o tempo dos detalhes transformado em uma coluna e classificado em ordem crescente.](../media/1439dcc2-12ff-4ee2-9ef3-1484cf79c384.PNG)

Se você quiser fazer mais investigações sobre o tempo de resolução dns, tente um PsPing na porta DNS usada pelo TCP (por exemplo,  `psping <IP address of DNS server>:53` ) . Você ainda vê um problema de desempenho? Se você fizer isso, o problema será mais provável que seja um problema de rede mais amplo do que um problema específico do aplicativo DNS que você está atingindo para fazer a resolução. Também vale a pena mencionar, novamente, que um ping para outlook.office365.com irá dizer onde a resolução de nome DNS para Outlook Online está ocorrendo (por exemplo, outlook-namnorthwest.office365.com).

Se o problema parece ser específico do DNS, talvez seja necessário entrar em contato com seu departamento de IT para analisar as configurações dns e os encaminhadores DNS para investigar ainda mais esse problema.

### <a name="proxy-scalability"></a>Escalabilidade de proxy

Serviços como Outlook Online em Office 365 conceder aos clientes várias conexões de longo prazo. Portanto, cada usuário pode usar mais conexões que exigem uma vida mais longa.

#### <a name="tools"></a>Ferramentas

Matemática

#### <a name="what-to-look-for"></a>O que procurar

Não há nenhum rastreamento de rede ou ferramenta de solução de problemas específica para isso. Em vez disso, ele se baseia nos cálculos de largura de banda dadas limitações e outras variáveis.

### <a name="tcp-max-segment-size"></a>Tamanho máximo do segmento TCP

Encontrado no SYN - SYN/ACK.  Faça essa verificação em qualquer rastreamento de rede de desempenho que você tenha feito para garantir que os pacotes TCP sejam configurados para carregar a quantidade máxima de dados possível.

O objetivo é ver um MSS de 1460 bytes para transmissão de dados. Se você estiver por trás de um proxy ou estiver usando um NAT, lembre-se de executar esse teste do cliente para proxy/saída/NAT e de proxy/saída/NAT para Office 365 para melhores resultados! São sessões TCP diferentes.

#### <a name="tools"></a>Ferramentas

Netmon

#### <a name="what-to-look-for"></a>O que procurar

O MSS (Tamanho máximo de Segmento TCP) é outro parâmetro do handshake de três vias no rastreamento de rede, ou seja, você encontrará os dados necessários no pacote SYN - SYN/ACK. O MSS é realmente muito simples de ver.

Abra qualquer rastreamento de rede de desempenho que você tenha e encontre a conexão que você está curioso ou que demonstre o problema de desempenho.

> [!NOTE]
> Se você estiver olhando para um rastreamento e precisar encontrar o tráfego relevante para sua conversa, filtre pelo IP do Cliente ou pelo IP do servidor proxy ou ponto de saída, ou ambos. Indo diretamente, você precisará pingar a URL que você está testando para o endereço IP de Office 365 no rastreamento e filtre por ele.

Olhando para o rastreamento de segunda mão? Tente usar filtros para orientar a si mesmo. No Netmon, execute uma pesquisa com base na URL, como `Containsbin(framedata, ascii, "sphybridExample")` , anote o número do quadro.

Em Wireshark, use algo como  `frame contains "sphybridExample"` . Se você observar que encontrou o tráfego RWS (Remote Winsock) (ele pode aparecer como um [PSH, ACK] no Wireshark), lembre-se de que as versões RWS podem ser vistas pouco antes do SYN - SYN/ACKs relevante, conforme discutido anteriormente.

Neste ponto, você pode gravar o número do quadro, soltar o filtro, clicar em **Todo** o Tráfego na janela Conversas de Rede no Netmon para ver o SYN mais próximo.

Importante, se você não recebeu nenhuma das informações de endereço IP no momento do rastreamento, localizar sua URL no rastreamento (parte de , por exemplo), dará a você endereços IP para `sphybridExample-my.sharepoint.com` filtrar.

Localize a conexão no rastreamento que você está interessado em ver. Você pode fazer isso digitalizando o rastreamento, filtrando por endereços IP ou selecionando IDs de Conversa específicas usando a janela Conversas de Rede no Netmon. Depois de encontrar o pacote SYN, expanda o TCP (em Netmon) ou o Protocolo de Controle de Transmissão (em Wireshark) no painel Detalhes do Quadro. Expanda opções TCP e MaxSegmentSize. Localize o quadro SYN-ACK relacionado e expanda opções TCP e MaxSegmentSize. O menor dos dois valores será o tamanho máximo do segmento. Nesta imagem, faço uso da Coluna interna no Netmon chamada Solução de Problemas TCP.

![Rastreamento de rede filtrado em Netmon usando as colunas internas.](../media/e073df13-71f8-497a-83b4-bb9f70bd9833.PNG)

A coluna embutida está na parte superior do painel **Detalhes do** Quadro. (Para alternar de volta para seu modo de exibição normal, clique em **Colunas** novamente e escolha **Fuso Horário**.)

![Onde encontrar a lista suspensa Colunas para a opção Solução de Problemas de TCP (na parte superior do Resumo do Quadro).](../media/64fd4baa-a872-4f07-b959-752d7d37fd62.PNG)

Aqui está um rastreamento filtrado em Wireshark. Há um filtro específico para o valor MSS ( `tcp.options.mss` ). Os quadros de um SYN, SYN/ACK, handshake ACK são vinculados na parte inferior do Wireshark equivalente a Detalhes do Quadro (portanto, o quadro 47 ACK, links para 46 SYN/ACK, links para 43 SYN) para facilitar esse tipo de trabalho.

![Rastreamento filtrado em Wireshark por tcp.options.mss para Max Segment Size (MSS).](../media/51e278db-801b-48bc-9b68-87cf92f03fd6.PNG)

Se você precisar verificar **o Reconhecimento Seletivo** (próximo tópico nesta matriz), não feche o rastreamento!

### <a name="selective-acknowledgment"></a>Reconhecimento Seletivo

Encontrado no SYN - SYN/ACK. Deve ser relatado como Permitido em SYN e SYN/ACK. O Reconhecimento Seletivo (SACK) permite uma retransmissão mais suave de dados quando um pacote ou pacotes desaparece. Os dispositivos podem desabilitar esse recurso, o que pode levar a problemas de desempenho.

Se você estiver por trás de um proxy ou estiver usando um NAT, lembre-se de executar esse teste do cliente para proxy/saída/NAT e de proxy/saída/NAT para Office 365 para melhores resultados! São sessões TCP diferentes.

#### <a name="tools"></a>Ferramentas

Netmon

#### <a name="what-to-look-for"></a>O que procurar

Reconhecimento Seletivo (SACK) é outro parâmetro no handshake SYN-SYN/ACK. Você pode filtrar seu rastreamento para SYN - SYN/ACK de várias maneiras.

Localize a conexão no rastreamento que você está interessado em ver, digitalizando o rastreamento, filtrando por endereços IP ou clicando em uma ID de Conversa usando a janela Conversas de Rede no Netmon. Depois de encontrar o pacote SYN, expanda o TCP no Netmon ou o Protocolo de Controle de Transmissão em Wireshark na seção Detalhes do Quadro. Expanda opções TCP e, em seguida, o SACK. Localize o quadro SYN-ACK relacionado e expanda opções TCP e seu campo SACK. Certifique-se de que o SACK seja permitido em SYN e SYN/ACK. Aqui estão os valores SACK, conforme visto em Netmon e Wireshark.

![Reconhecimento Seletivo (SACK) em Netmon como resultado de tcp.flags.syn == 1.](../media/216f556f-5031-4ed2-b066-a0d9b3251fa2.PNG)

![SACK como visto no Wireshark com o filtro tcp.flags.syn == 1.](../media/0a6e26e5-43dc-403b-adc9-3349a55f4e4b.PNG)

### <a name="dns-geolocation"></a>Localização Geográfica DNS

No mundo em que Office 365 tenta resolver sua chamada DNS afeta a velocidade da conexão.

No Outlook Online, após a conclusão da primeira pesquisa DNS, o local desse DNS será usado para se conectar ao datacenter mais próximo. Você será conectado a um Outlook CAS Online, que usará a rede backbone para se conectar ao datacenter (dC) onde seus dados são armazenados. Isso é mais rápido.

Ao acessar o SharePoint Online, um usuário que viaja para o exterior será direcionado para seu datacenter ativo , que é o dC cuja localização é baseada na base do locatário SPO (portanto, um dC nos EUA se o usuário se baseado nos EUA).

O Lync online tem nós ativos em mais de um dC por vez. Quando as solicitações são enviadas para instâncias do Lync online, o DNS da Microsoft determinará de onde a solicitação veio e retornará endereços IP do dC regional mais próximo onde o Lync online está ativo.

> [!TIP]
> Precisa saber mais sobre como os clientes se conectam a Office 365? Confira o artigo de referência de [Conectividade do](/previous-versions//dn741250(v=technet.10)) Cliente (e seus gráficos úteis).

#### <a name="tools"></a>Ferramentas

- Ping
- PsPing

#### <a name="what-to-look-for"></a>O que procurar

As solicitações de resolução de nome dos servidores DNS do cliente para os servidores DNS da Microsoft devem, na maioria dos casos, resultar em DNS da Microsoft retornando o endereço IP de um datacenter regional (dC). O que isso significa para você? Se sua sede estiver em Bangalore, na Índia, mas você estiver viajando nos Estados Unidos, quando o navegador fizer uma solicitação para o Outlook Online, os servidores DNS da Microsoft devem lhe entregar endereços IP para datacenters nos Estados Unidos, um datacenter regional. Se o email for necessário Outlook, esses dados percorrerão a rede de backbone rápido da Microsoft entre os datacenters.

O DNS funciona mais rápido quando a resolução de nome é feita o mais próximo possível do local do usuário. Se você estiver na Europa, você deseja ir para um DNS da Microsoft na Europa e (idealmente) lidar com um datacenter na Europa. O desempenho de um cliente na Europa indo para DNS e um datacenter na América será mais lento.

Execute a ferramenta Ping em outlook.office365.com para determinar para onde sua solicitação DNS está sendo roteada no mundo. Se você estiver na Europa, deverá ver uma resposta de algo como outlook-emeawest.office365.com. Nas Américas, espere algo como outlook-namnorthwest.office365.com.

Abra o prompt de comando no computador cliente (por meio do cmd Start \> Run ou Windows tipo de tecla \> \> cmd). Digite ping outlook.office365.com pressione ENTER. Lembre-se de especificar -4 se quiser especificar ping via IPv4. Você pode não receber uma resposta dos pacotes ICMP, mas deve ver o nome do DNS para o qual a solicitação foi roteada. Se você quiser ver os números de latência para essa conexão, tente PsPing para o endereço IP do servidor retornado por ping.

![Ping de outlook.office365.com mostrando a resolução em outlook-namnorthwest.](../media/06c944d5-6159-43ec-aa31-757770695e8b.PNG)

![PSPing para o endereço IP retornado pelo ping para outlook.office365.com mostrando latência média de 28 milissegundos.](../media/f2b25a75-1a87-4479-b8a7-fa4375683507.PNG)

### <a name="office-365-application-troubleshooting"></a>Office 365 Solução de problemas de aplicativos

#### <a name="tools"></a>Ferramentas

- Netmon
- HTTPWatch
- Console F12 no navegador

Não abrangemos ferramentas usadas em solução de problemas específicas do aplicativo neste artigo específico da rede. Mas você encontrará recursos que  *podem ser*  utilizados [nesta página](https://support.office.com/article/Network-planning-and-performance-tuning-for-Office-365-e5f1228c-da3c-4654-bf16-d163daee8848).

## <a name="related-topics"></a>Tópicos Relacionados

[Gerenciar pontos de extremidade do Office 365](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)

[Perguntas frequentes sobre pontos de extremidade do Office 365](https://support.office.com/article/d4088321-1c89-4b96-9c99-54c75cae2e6d)