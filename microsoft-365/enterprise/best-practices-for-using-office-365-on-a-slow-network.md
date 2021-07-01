---
title: Práticas recomendadas para usar Office 365 em uma rede lenta
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 12/29/2016
audience: End User
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
search.appverid:
- MET150
- MET150
- MOP150
- MEW150
- BCS160
ms.assetid: fd16c8d2-4799-4c39-8fd7-045f06640166
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
description: Este artigo orienta você pelas práticas recomendadas que você pode adotar para usar Office 365 em uma rede lenta.
ms.openlocfilehash: d217ee8bb40898716844717e84db112f356f6672
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/30/2021
ms.locfileid: "53226018"
---
# <a name="best-practices-for-using-office-365-on-a-slow-network"></a>Práticas recomendadas para usar Office 365 em uma rede lenta

Não seria bom se sua conexão com a Internet fosse sempre rápida e nunca baixada? Talvez esse dia venha. Mas, enquanto isso, há coisas práticas que você pode fazer para trabalhar em torno de uma rede desarmada e ainda fazer seu trabalho do dia a dia. Embora Office 365 seja um serviço baseado em nuvem, ele também fornece muitas maneiras de trabalhar com seu conteúdo offline e manter suas alterações sincronizadas sem problemas. Além disso, às vezes é mais eficiente trabalhar com conteúdo offline apenas porque os aplicativos são executados mais rapidamente e a interface do usuário é mais responsiva. O ponto é este: Office 365 oferece o melhor de ambos os mundos. Veja como tirar proveito disso.

> [!TIP]
> Quer ver o quão lenta (ou rápida) sua conexão de rede é? Experimente o [teste de Velocidade OOKLA ou](https://www.speedtest.net/) o Aplicativo de Teste de Velocidade de [Rede](https://www.windowsphone.com/store/app/network-speed-test/9b9ae06b-2961-41ef-987d-b09567cffe70).

## <a name="why-is-my-network-so-slow"></a>Por que minha rede é tão lenta?

Embora você não tenha controle sobre o desempenho da rede em si, isso ajuda a entender o que está acontecendo nos bastidores. A Internet é extremamente complexa, mas há alguns conceitos que podem ajudá-lo a entender a situação muito melhor. Seguir as práticas recomendadas neste artigo pode ajudar a resolver problemas de desempenho e reduzir a frustração.

### <a name="major-factors-that-affect-network-performance"></a>Principais fatores que afetam o desempenho da rede

![Fatores de desempenho de rede](../media/62a94322-3f1a-4d2d-bbdc-2aa0722d2d96.png)

 **Largura de banda e latência**: As duas medidas mais importantes do desempenho da rede são largura de banda e latência:

- Largura de banda é a taxa de taxa de transferência medida em bits por segundo. Maior é melhor. A largura de banda é como um cano de água. Quanto maior o pipe, mais água você pode "passar" por ele.

- Latência é o tempo necessário para que o conteúdo receba de um servidor ou serviço para seu dispositivo e é medido em milissegundos. Mais rápido é melhor. A latência pode ser causada por vários fatores, incluindo baixa largura de banda, uma conexão esparsa ou o tempo de transmissão.

 **Problemas comuns**: além da largura de banda e latência, outros problemas têm impacto no desempenho da rede e são frequentemente imprevisíveis. O desempenho da rede pode oscilar com base na hora do dia ou em sua localização física. A rede pode ficar bloqueada quando determinados eventos ocorrem que aumentarão o uso da Internet, como um desastre natural ou um evento público importante. O tamanho e a complexidade da página que está sendo carregada e o número e o tamanho dos arquivos que estão sendo transferidos têm uma relação direta com o desempenho. Uma conexão WiFi pode degradar temporariamente: por exemplo, você sonda uma grande reunião de conferência de milhares solicitando que todos tweetem ao mesmo tempo.

 **Considerações para uma** rede de satélite : uma rede de satélite é útil quando uma rede terrestre não é viável, como o país de origem, um barco de navegação ou uma área científica remota. Essas redes dependem de satélites posicionados em uma órbita geossíncrona 22.000 milhas acima do equador. No entanto, uma transmissão realmente percorre cerca de 90.000 milhas e, portanto, uma rede de satélite tem uma latência mais lenta (500 ms ou mais) do que uma rede terrestre (20 a 50ms). Sob as melhores condições, você pode não notar essa latência, mas para baixar arquivos grandes, transmitir vídeos e jogar jogos, você provavelmente perceberá. Outro problema é "fade de chuva" em que o clima pesado, como trovoadas e nevascas, pode interromper temporariamente a transmissão de satélite.

## <a name="are-you-sure-its-the-network"></a>Tem certeza de que é a rede?

Sempre que você tiver problemas de desempenho, primeiro certifique-se de que seu dispositivo não seja a causa raiz do problema. Há duas coisas que você pode fazer que podem fazer uma grande melhoria:

- Certifique-se de que o dispositivo está funcionando bem e se não há malware no computador.

- Se possível, compre mais memória. Adicionar memória é a maneira mais simples e frequentemente mais eficaz de melhorar o desempenho em seu dispositivo. É especialmente útil ao trabalhar com arquivos e vídeos grandes.

Para obter mais informações, [consulte Windows Performance and maintenance](https://windows.microsoft.com/windows/performance-maintenance-help#performance-maintenance-help) and Dicas to improve pc performance in [Windows 10](https://support.microsoft.com/help/4002019/windows-10-improve-pc-performance).

## <a name="best-practices-for-using-your-browser"></a>Práticas recomendadas para usar seu navegador

Seu navegador é seu gateway para Office 365, portanto, ele pode ter um impacto no desempenho, especialmente com o tempo necessário para carregar uma página e a frequência de ida e volta para o serviço de Office 365.

### <a name="browsers-in-general"></a>Navegadores em geral

Aqui estão algumas sugestões para navegadores em geral:

- Desabilite os complementos do navegador que podem afetar o desempenho ou que você realmente não precisa.

- Aumente o tamanho do cache para seus arquivos temporários da Internet.

- Depois de entrar em sua conta de trabalho ou de estudante, mantenha a janela do navegador aberta durante todo o dia. Você pode abrir outras guias e janelas sem entrar novamente. Se você precisar entrar em outra conta, use a Navegação Privada.

- Depois que cada página for baixada e aberta, mantenha-as abertas usando guias. É fácil navegar entre guias e usar a página mais adiante no dia. Atualize uma página somente se precisar dos dados mais recentes nessa página.

- Se uma página estiver demorando muito para abrir, pare o download da página (pressione ESC) e atualize a página (pressione F5).

- Quando possível, reduza as idas e Office 365. Por exemplo, em vez de fazer pajamento por meio de listas ou bibliotecas, use a pesquisa para localizar arquivos em uma biblioteca grande e filtrar em uma lista para obter diretamente os resultados que você deseja. Ou crie exibições que minimizem o tempo de carregamento da página. Para obter mais informações, consulte [Manage large lists and libraries in Office 365](https://support.office.com/article/b4038448-ec0e-49b7-b853-679d3d8fb784#BKMK_PAGES).

- Se o desempenho do vídeo for ruim, você poderá baixar o vídeo e assisti-lo em seu dispositivo. Um link de download pode estar disponível ou você pode clicar com o botão direito do mouse no link de vídeo e selecionar **Salvar Destino como**.

### <a name="browser-specific"></a>Específico do navegador

Aqui estão algumas sugestões para seu navegador específico:

- **Internet Explorer**: atualize para o Internet Explorer Versão 11 ou posterior para melhorias substanciais de desempenho em relação às versões anteriores. Para obter mais informações, consulte [Guia de solução de problemas do Internet Explorer](https://support.microsoft.com/help/2437121/troubleshooting-guide-for-internet-explorer-when-you-access-office-365).
- **FireFox**: Para obter mais informações, consulte [Firefox is slow or stops working](https://support.mozilla.org/products/firefox/fix-problems/slowness-or-hanging).
- **Safari**: Para obter mais informações, consulte [Apple - Safari](https://www.apple.com/safari/).
- **Chrome**: Para obter mais informações, consulte [Ajuda do Chrome](https://support.google.com/chrome/?hl=en).

## <a name="best-practices-for-using-outlook-and-outlook-web-app"></a>Práticas recomendadas para usar Outlook e Outlook Web App

Ler, escrever e organizar emails é uma grande parte do dia de todos. Tanto Outlook quanto Outlook Web App (OWA) oferecem suporte offline. Usar um aplicativo de email em seu smartphone é outra alternativa útil. Use as seguintes opções que melhor se ajustam às suas necessidades:

- Atualize para a versão mais recente do Outlook para melhorias substanciais de desempenho em relação às versões anteriores.

- Outlook Web App permite criar mensagens offline, contatos e eventos de calendário que são carregados quando o OWA é o próximo capaz de se conectar ao Office 365. Para obter mais informações sobre como configurar e usar o OWA no modo offline, consulte [Using Outlook Web App offline](https://support.office.com/article/3214839c-0604-4162-8a97-6856b4c27b36).

- Outlook permite que você trabalhe no modo em cache, no qual ele se conecta automaticamente sempre que possível. Você pode fazer Outlook sua caixa de correio inteira ou apenas uma parte dela. Para obter mais informações, [consulte Ativar o modo Exchange Cache](https://support.office.com/article/7885af08-9a60-4ec3-850a-e221c1ed0c1c) e Trabalhar offline no [Outlook](https://support.office.com/article/f3a1251c-6dd5-4208-aef9-7c8c9522d633).

- Outlook também oferece um modo offline. Para usar isso, você deve primeiro configurar o modo em cache para que as informações da sua conta são copiadas para o computador. No modo offline, Outlook tentará se conectar usando as configurações de envio e recebimento ou quando você defini-lo manualmente para funcionar online. Para obter mais informações, consulte [Work offline to avoid data connection charges](https://support.office.com/article/827fe51f-5609-4062-82b4-3578057f9282), Change send and receive [settings when](https://support.office.com/article/f681ec10-cb14-40cb-8709-1909a13c304a)you work offline , and Switch from working offline to [online](https://support.office.com/article/2460e4a8-16c7-47fc-b204-b1549275aac9).

- Se você tiver um telefone inteligente, poderá usá-lo para triagem de seu email e calendário pela rede da operadora de telefonia.

> [!NOTE]
> Aqui estão algumas orientações sobre quando usar Outlook ou OWA. Se o espaço em disco não for um problema em seu dispositivo, Outlook tem um conjunto completo de recursos e pode funcionar melhor para você. Se o espaço em disco for um problema em seu dispositivo, considere usar o OWA, que tem um subconjunto de recursos, mas também funciona melhor em uma situação online. Obviamente, você pode usar porque eles funcionam bem juntos.

## <a name="best-practices-for-using-onedrive-for-business"></a>Práticas recomendadas para usar OneDrive for Business

OneDrive for Business foi projetado do zero para funcionar com seus arquivos online e offline. Depois de configurar, a sincronização de alterações ocorre automaticamente e de forma confiável em qualquer lugar e sempre que você as faz. Se a rede for lenta, você poderá trabalhar com a versão offline dos arquivos.

O OneDrive for Business de sincronização vem com uma assinatura SharePoint Online e Office 365 [](https://support.microsoft.com/kb/2903984) business, ou você pode baixar o aplicativo OneDrive for Business de sincronização gratuitamente. Este aplicativo também é mais rápido do que usar os **comandos Abrir no Explorer** **ou** Upload. Para obter mais informações, [consulte Configurar seu computador para sincronizar seus arquivos OneDrive for Business em Office 365](https://support.office.com/article/23e1f12b-d896-4cb1-a238-f91d19827a16).

Aqui estão algumas diretrizes adicionais para usar o aplicativo de sincronização OneDrive for Business de sincronização:

- Se você estiver sincronizando uma biblioteca grande pela primeira vez, inicie a sincronização durante o horário de folga, por exemplo, durante a noite.
- Você pode usar o [recurso Parar de sincronizar uma biblioteca](https://support.office.com/article/a7e41f1f-3a98-4ca7-9443-f10250688330) com o OneDrive for Business aplicativo para interromper temporariamente a sincronização de atualizações. No entanto, use esse recurso por breves períodos, como algumas horas por vez, para evitar a fila de grandes quantidades de atualizações e minimizar o risco de conflitos de mesclagem se várias pessoas trabalharem no mesmo documento.

## <a name="best-practices-for-using-onenote"></a>Práticas recomendadas para o uso OneNote

Cada SharePoint site de equipe tem um bloco de anotações OneNote e você pode criar facilmente seu próprio. OneNote é uma ótima maneira de coletar informações em tempo há tempo que você precisa todos os dias para realizar tarefas. Por exemplo, muitas equipes usam OneNote como ponto de coleta para reuniões semanais, notas de projeto, ideias, planos e relatórios de status. Você pode organizar perfeitamente essas informações diferentes usando páginas, seções e guias.

A beleza da OneNote é que você pode acessar o conteúdo de praticamente qualquer dispositivo, seja uma área de trabalho, um laptop, um tablet ou um smartphone. E você não precisa se preocupar em salvar ou sincronizar porque OneNote faz isso para você.

Para obter mais informações, [consulte Microsoft OneNote](https://office.microsoft.com/onenote).

## <a name="best-practices-for-using-skype-for-business-and-lync-online"></a>Práticas recomendadas para usar o Skype for Business e o Lync Online

A seguir estão as diretrizes gerais para usar o Skype for Business ou o Lync Online quando sua rede estiver lenta:

- Use mensagens instantâneas sempre que possível porque funciona bem em uma rede lenta.

- Evite fazer chamadas telefônicas em uma rede virtual privada (VPN) ou conexões de serviço de acesso remoto (RAS).

- Certifique-se de que seu dispositivo de áudio seja aprovado. Para obter mais informações, consulte [Telefones e dispositivos qualificados para o Microsoft Lync](/skypeforbusiness/lync-cert/ip-phones).

- Ao usar PowerPoint em uma apresentação online, reduza o tamanho e a complexidade dos slides. Para obter mais informações, [consulte Dicas para melhorar o desempenho de sua apresentação](https://support.office.com/article/34c82835-5f23-4bf0-98cc-72235bbd2949).

- O desempenho de vídeo depende muito do desempenho da rede. Evite usar vídeo se a rede estiver lenta.

Para obter mais informações, consulte Qualidade de áudio ou vídeo ruim no [Lync Online](https://support.microsoft.com/kb/2386655)ou como solucionar problemas de conexão [em Skype for Business](https://support.office.com/article/troubleshoot-connection-issues-in-skype-for-business-ca302828-783f-425c-bbe2-356348583771).

## <a name="best-practices-for-using-sharepoint-lists"></a>Práticas recomendadas para usar SharePoint listas

Trabalhar com dados de lista offline para "limpar", analisar ou relatar dados é uma ótima maneira de minimizar o impacto de uma rede lenta. Você pode ler e gravar a maioria das listas do Microsoft Access 2019 e do Microsoft Access 2016 vinculando-se a elas. Você também pode exportar uma lista para uma tabela Excel, que cria uma conexão de dados de ida e volta entre a Excel e a lista. Saiba como trabalhar [offline com tabelas vinculadas a SharePoint listas](https://support.office.com/article/work-offline-with-tables-that-are-linked-to-sharepoint-lists-5d66594a-6176-4a25-a198-320f13ccf41e).

Para obter mais informações, consulte a seção "Mais sobre como gerenciar listas grandes" em Gerenciar listas grandes e [bibliotecas em Office 365](https://support.office.com/article/b4038448-ec0e-49b7-b853-679d3d8fb784).

## <a name="best-practices-for-customizing-web-pages"></a>Práticas recomendadas para personalizar páginas da Web

Ao personalizar uma página da Web, você pode inadvertidamente causar um desempenho ruim com a página. Vários fatores podem ter impacto, como a complexidade e o tamanho da página, quantas Web Parts são adicionadas, quantos itens de lista ou biblioteca são inicialmente exibidos e a maneira como você codifica a página.

Para obter mais informações, consulte [Tune SharePoint Online performance](tune-sharepoint-online-performance.md).

## <a name="best-practices-for-using-project-online"></a>Práticas recomendadas para o uso Project Online

As diretrizes a seguir podem ajudar a melhorar o desempenho da rede.

- Project Online e SharePoint Online exigem sincronização, o que pode ser demorado. Se suas equipes de projeto têm baixa rotatividade, desabilite Project Sincronização de Sites para melhorar o desempenho Project Publicar e Project Páginas de Detalhes. Limite a sincronização do Active Directory a grupos de recursos que realmente precisam usar o sistema e monitore possíveis problemas de permissão após a sincronização de grupos grandes.

- Se sua organização usa sites de projeto, crie-os sob demanda, em vez de automaticamente. Isso acelera a primeira experiência de publicação e evita a criação de sites e conteúdo desnecessários.

- Project As Páginas de Detalhes (PDP) podem disparar um recálculo de todo o projeto e dar início a ações de fluxo de trabalho, ambas podem ser operações de alto desempenho. Para evitar a acionamento de dois processos de atualização ao mesmo tempo no mesmo PDP, evite atualizar os campos de calendário (Data de Início, Data de Concluir, Data de Status e Data Atual) e os campos não agendados (nome do projeto, descrição e proprietário).

- Reduza o número de Web Parts e campos personalizados exibidos em cada PDP. Crie um PDP dedicado com os únicos campos que exigem atualização para melhorar a carga e economizar tempo.

- Ao usar o OData para relatórios, limite a quantidade de dados consultados em tempo de execução usando a filtragem do lado do servidor.

Para obter mais informações, consulte [Tune Project Online performance](https://support.office.com/article/12ba0ebd-c616-42e5-b9b6-cad570e8409c).

## <a name="whats-the-best-way-to-report-problems"></a>Qual é a melhor maneira de relatar problemas?

A Microsoft melhora continuamente o desempenho geral do Office 365 monitorando a rede, medindo largura de banda e latência, melhorando o tempo de carregamento da página, reduzindo a E/S do disco, redesenhando páginas para usar a Estratégia de Download Mínimo, adicionando hardware a data centers e adicionando mais data centers. Para obter mais informações sobre como verificar seu status atual e problemas de relatório, consulte Como verificar a Office 365 [do serviço.](view-service-health.md)

## <a name="see-also"></a>Confira também

[Planejamento de rede e ajuste de desempenho para o Office 365](network-planning-and-performance.md)

[Princípios de conectividade de rede do Office 365](microsoft-365-network-connectivity-principles.md)

[Gerenciar pontos de extremidade do Office 365](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)

[Perguntas frequentes sobre pontos de extremidade do Office 365](https://support.office.com/article/d4088321-1c89-4b96-9c99-54c75cae2e6d)
