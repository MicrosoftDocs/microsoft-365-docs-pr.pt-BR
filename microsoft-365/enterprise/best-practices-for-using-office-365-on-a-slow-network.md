---
title: Práticas recomendadas para usar o Office 365 em uma rede lenta
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
description: Este artigo orienta você pelas práticas recomendadas que você pode adotar para usar o Office 365 em uma rede lenta.
ms.openlocfilehash: a0a15191fa0240f24cecc5e595de9a259cacc9f9
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46687330"
---
# <a name="best-practices-for-using-office-365-on-a-slow-network"></a>Práticas recomendadas para usar o Office 365 em uma rede lenta

Não seria ótimo se sua conexão com a Internet fosse sempre rápida e nunca para baixo? Talvez esse dia venha. Mas, nesse meio tempo, há coisas práticas que você pode fazer para contornar uma rede do balky e ainda obter o trabalho diário concluído. Embora o Office 365 seja um serviço baseado em nuvem, ele também fornece várias maneiras de trabalhar com o conteúdo offline e para manter suas alterações sincronizadas. Além disso, às vezes é mais eficiente trabalhar com o conteúdo offline apenas porque os aplicativos são executados com mais rapidez e a interface do usuário é mais responsiva. O ponto é: o Office 365 oferece o melhor de ambos os mundos. Confira aqui como aproveitar isso. 
  
> [!TIP]
> Deseja ver a lentidão (ou rápida) sua conexão de rede? Experimente o [ teste de velocidade do OOKLA ](https://www.speedtest.net/) ou o [aplicativo de teste de velocidade da rede](https://www.windowsphone.com/store/app/network-speed-test/9b9ae06b-2961-41ef-987d-b09567cffe70). 

## <a name="why-is-my-network-so-slow"></a>Por que minha rede está lenta?

Embora você não tenha controle sobre o desempenho da rede, ele ajuda a entender o que está acontecendo nos bastidores. A Internet é imensamente complexa, mas há alguns conceitos que podem ajudá-lo a entender a situação muito melhor. Seguir as práticas recomendadas neste artigo pode ajudar a solucionar problemas de desempenho e reduzir a frustração.
  
**Principais fatores que afetam o desempenho da rede**

![Fatores de desempenho de rede](../media/62a94322-3f1a-4d2d-bbdc-2aa0722d2d96.png)
  
 **Largura de banda e latência** As duas medidas mais importantes do desempenho da rede são a largura de banda e a latência: 
  
- Largura de banda é a taxa de taxa de transferência em bits por segundo. Maior é melhor. A largura de banda é como um tubo de água. Quanto maior o tubo, mais água você pode "colocar".

- Latência é o tempo que o conteúdo leva para ser obtido de um servidor ou serviço para seu dispositivo e é medido em milissegundos. Mais rápido é melhor. A latência pode ser causada por vários fatores, incluindo pouca largura de banda, uma conexão esparsa ou um tempo de transmissão.

 **Problemas comuns** Além de largura de banda e latência, outros problemas têm um impacto no desempenho da rede e costumam ser imprevisíveis. O desempenho da rede pode flutuar com base na hora do dia ou no local físico. A rede pode ser saturada quando determinados eventos ocorrem, o que é o pico de uso da Internet, como um desastre natural ou um evento público principal. O tamanho e a complexidade da página que está sendo carregada e o número e o tamanho dos arquivos que estão sendo transferidos têm um rumo direto sobre o desempenho. Uma conexão WiFi pode degradar temporariamente: por exemplo, você sondar uma reunião de conferência grande de milhares solicitando a todos os tweets ao mesmo tempo. 
  
 **Considerações para uma rede de satélite** Uma rede de satélite é útil quando uma rede terrestre não é viável, como o país de fundo, um navio de cruzeiro ou uma área científica remota. Essas redes dependem de satélites posicionados em uma órbita geosíncrona de 22.000 milhas acima do Equador. No entanto, uma transmissão realmente viaja cerca de 90.000 milhas e, portanto, uma rede de satélite tem uma latência mais lenta (500 MS ou mais) do que uma rede terrestre (20 a 50ms). Sob as melhores condições, você pode não notar essa latência, mas para baixar arquivos grandes, transmitir vídeos e jogar, você provavelmente vai. Outro problema é "Fade-chuva" no qual o clima pesado, como thunderstorms e Blizzards, pode interromper temporariamente a transmissão de satélite.
  
## <a name="are-you-sure-its-the-network"></a>Você tem certeza de que é a rede?

Sempre que você enfrentar problemas de desempenho, primeiro certifique-se de que o dispositivo não é a causa raiz do problema. Há duas coisas que você pode fazer que podem fazer um grande aperfeiçoamento:
  
- Verifique se o dispositivo está funcionando bem e se não há malware no computador.

- Se possível, compre mais memória. Adicionar memória é a maneira mais simples e freqüentemente mais eficaz de melhorar o desempenho no seu dispositivo. É especialmente útil quando se trabalha com arquivos e vídeos grandes.

Para obter mais informações, consulte [ desempenho e manutenção do Windows ](https://windows.microsoft.com/windows/performance-maintenance-help#performance-maintenance-help) e [dicas para melhorar o desempenho do PC no Windows 10](https://support.microsoft.com/en-za/help/4002019/windows-10-improve-pc-performance).

## <a name="best-practices-for-using-your-browser"></a>Práticas recomendadas para o uso do navegador

Seu navegador é o seu gateway para o Office 365, portanto, ele pode ter um impacto no desempenho, especialmente com o tempo que leva para carregar uma página e a frequência de ida e volta para o serviço do Office 365.
  
 **Navegadores em geral**
  
Veja algumas sugestões de navegadores em geral:
  
- Desabilitar Complementos do navegador que podem afetar o desempenho ou que você não realmente precisa.

- Aumente o tamanho do cache para seus arquivos temporários da Internet.

- Depois de entrar em sua conta corporativa ou de estudante, mantenha a janela do navegador aberta durante o dia. Você pode abrir outras guias e janelas sem entrar novamente. Se você precisar entrar em outra conta, use a navegação privada. 

- Depois que cada página é baixada e aberta, mantenha-as abertas usando guias. É fácil navegar entre guias e usar a página posteriormente no dia. Atualize uma página somente se precisar dos dados mais recentes nessa página.

- Se uma página estiver demorando muito para abrir, interrompa o download da página (pressione ESC) e atualize a página (pressione F5). 

-  Quando possível, reduza o round trips para o Office 365. Por exemplo, em vez de paginação por meio de listas ou bibliotecas, use a pesquisa para localizar arquivos em uma grande biblioteca e filtragem em uma lista para obter diretamente os resultados desejados. Ou crie modos de exibição que minimizem o tempo de carregamento da página. Para obter mais informações, consulte [gerenciar grandes listas e bibliotecas no Office 365](https://support.office.com/article/b4038448-ec0e-49b7-b853-679d3d8fb784#BKMK_PAGES).

- Se o desempenho do vídeo for ruim, você poderá baixar o vídeo e observá-lo em seu dispositivo. Um link de download pode estar disponível ou você pode clicar com o botão direito do mouse no link de vídeo e selecionar **Salvar destino como**.

 **Específico do navegador**
  
Veja algumas sugestões para seu navegador específico:
  
- **Internet Explorer** Atualize para o Internet Explorer versão 11 ou posterior para obter melhorias substanciais de desempenho em relação às versões anteriores. Para obter mais informações, consulte o [Guia de solução de problemas para o Internet Explorer](https://support.microsoft.com/help/2437121/troubleshooting-guide-for-internet-explorer-when-you-access-office-365).

- **Firefox** Para obter mais informações, consulte o [Firefox está lento ou para de funcionar](https://support.mozilla.org/products/firefox/fix-problems/slowness-or-hanging).

- **Safari** Para obter mais informações, consulte [Apple-Safari](https://www.apple.com/safari/).

- **Chrome** Para obter mais informações, consulte [ajuda do Chrome](https://support.google.com/chrome/?hl=en).
  
## <a name="best-practices-for-using-outlook-and-outlook-web-app"></a>Práticas recomendadas para usar o Outlook e o Outlook Web App

Ler, gravar e organizar emails é uma parte grande do dia de todos. O Outlook e o Outlook Web App (OWA) oferecem suporte offline. O uso de um aplicativo de email em seu telefone inteligente é outra alternativa útil. Use as seguintes opções que melhor atendam às suas necessidades:
  
- Atualize para a versão mais recente do Outlook para obter melhorias substanciais de desempenho em relação às versões anteriores. 

-  O Outlook Web App permite que você crie mensagens offline, contatos e eventos de calendário que são carregados quando o OWA é capaz de se conectar ao Office 365. Para obter mais informações sobre a configuração e o uso do OWA no modo offline, consulte [using Outlook Web App offline](https://support.office.com/article/3214839c-0604-4162-8a97-6856b4c27b36).

- O Outlook permite que você trabalhe no modo em cache, no qual ele se conecta automaticamente sempre que possível. Você pode fazer com que o Outlook Baixe toda a sua caixa de correio ou apenas uma parte dela. Para obter mais informações, consulte [ativar o modo cache do Exchange](https://support.office.com/article/7885af08-9a60-4ec3-850a-e221c1ed0c1c) e [trabalhar offline no Outlook](https://support.office.com/article/f3a1251c-6dd5-4208-aef9-7c8c9522d633).

- O Outlook também oferece um modo offline. Para usar isso, primeiro você deve configurar o modo em cache para que as informações da sua conta sejam copiadas para o computador. No modo offline, o Outlook tentará se conectar usando as configurações de envio e recebimento ou quando você defini-la manualmente para trabalhar online. Para saber mais, confira [trabalhar offline para evitar cobranças de conexão de dados](https://support.office.com/article/827fe51f-5609-4062-82b4-3578057f9282), [alterar as configurações de envio e recebimento quando você trabalhar offline](https://support.office.com/article/f681ec10-cb14-40cb-8709-1909a13c304a)e [alternar entre trabalhar offline para online](https://support.office.com/article/2460e4a8-16c7-47fc-b204-b1549275aac9).

- Se você tiver um telefone inteligente, poderá usá-lo para fazer a triagem de seu email e calendário pela rede da operadora de telefonia.

> [!NOTE]
> Veja a seguir algumas orientações sobre quando usar o Outlook ou o OWA. Se o espaço em disco não for um problema no seu dispositivo, o Outlook tem um conjunto completo de recursos e pode funcionar melhor para você. Se o espaço em disco for um problema no seu dispositivo, considere usar o OWA que tenha um subconjunto de recursos, mas que também funcione melhor em uma situação online. Claro, você pode usar o, pois eles funcionam bem juntos.
  
## <a name="best-practices-for-using-onedrive-for-business"></a>Práticas recomendadas para usar o OneDrive for Business

O OneDrive for Business foi projetado desde o início para trabalhar com seus arquivos online e offline. Depois de configurado, a sincronização das alterações ocorre automaticamente e de forma confiável, onde e quando você fizer isso. Se a rede estiver lenta, você poderá trabalhar com a versão offline dos arquivos.
  
O aplicativo de sincronização do OneDrive for Business vem com uma assinatura do SharePoint Online e do Office 365 Business, ou você pode [baixar](https://support.microsoft.com/kb/2903984) o aplicativo de sincronização do onedrive for Business gratuitamente. Esse aplicativo também é mais rápido do que usar os comandos **abrir no Explorer** ou **carregar** . Para obter mais informações, consulte [Configurar o computador para sincronizar seus arquivos do onedrive for Business no Office 365](https://support.office.com/article/23e1f12b-d896-4cb1-a238-f91d19827a16).
  
Veja a seguir algumas orientações adicionais para usar o aplicativo de sincronização do OneDrive for Business:
  
- Se você estiver sincronizando uma biblioteca grande pela primeira vez, inicie a sincronização fora do horário do expediente, por exemplo, durante a noite.

- Você pode usar a [parada de sincronização de uma biblioteca com o recurso de aplicativo do onedrive for Business](https://support.office.com/article/a7e41f1f-3a98-4ca7-9443-f10250688330) para interromper temporariamente as atualizações de sincronização. No entanto, use esse recurso para breves períodos, como algumas horas de cada vez, para evitar o enfileiramento de grandes números de atualizações e minimizar o risco de conflitos de mesclagem se várias pessoas trabalharem no mesmo documento.
  
## <a name="best-practices-for-using-onenote"></a>Práticas recomendadas para usar o OneNote

Cada site de equipe do SharePoint tem um bloco de anotações interno do OneNote e você pode facilmente criar seus próprios. O OneNote é uma ótima maneira de coletar informações oportunas de que você precisa todos os dias para realizar tarefas. Por exemplo, muitas equipes usam o OneNote como um ponto de coleção para reuniões semanais, notas de projeto, ideias, planos e relatórios de status. Você pode organizar as informações distintas usando páginas, seções e guias.
  
A beleza do OneNote é que você pode acessar o conteúdo de praticamente qualquer dispositivo, seja um computador de mesa, um laptop, um Tablet ou um Smart Phone. E você não precisa se preocupar em salvar ou sincronizar porque o OneNote faz isso para você.
  
Para obter mais informações, consulte [Microsoft OneNote](https://office.microsoft.com/onenote).

## <a name="best-practices-for-using-skype-for-business-and-lync-online"></a>Práticas recomendadas para usar o Skype for Business e o Lync Online

Veja a seguir as diretrizes gerais para usar o Skype for Business ou o Lync Online quando a rede estiver lenta:

- Use o sistema de mensagens instantâneas sempre que possível, pois ele funciona bem em uma rede lenta.

- Evite fazer chamadas telefônicas em conexões de rede virtual privada (VPN) ou serviço de acesso remoto (RAS).

- Certifique-se de que o dispositivo de áudio foi aprovado. Para obter mais informações, consulte [telefones e dispositivos qualificados para o Microsoft Lync](https://docs.microsoft.com/skypeforbusiness/lync-cert/ip-phones).

- Ao usar o PowerPoint em uma apresentação online, reduza o tamanho e a complexidade dos slides. Para obter mais informações, consulte [dicas para melhorar o desempenho da sua apresentação](https://support.office.com/article/34c82835-5f23-4bf0-98cc-72235bbd2949).

- O desempenho de vídeo depende muito do desempenho da rede. Evite usar o vídeo se a rede estiver lenta.

Para obter mais informações, consulte [qualidade de vídeo ou áudio ruim no Lync Online](https://support.microsoft.com/kb/2386655)ou como [solucionar problemas de conexão no Skype for Business](https://support.office.com/article/troubleshoot-connection-issues-in-skype-for-business-ca302828-783f-425c-bbe2-356348583771).
  
## <a name="best-practices-for-using-sharepoint-lists"></a>Práticas recomendadas para o uso de listas do SharePoint

Trabalhar com dados de lista offline para "depurar", analisar ou relatar dados é uma ótima maneira de minimizar o impacto de uma rede lenta. Você pode ler e escrever a maioria das listas do Microsoft Access 2019 e do Microsoft Access 2016 ao vinculá-las. Você também pode exportar uma lista para uma tabela do Excel, que cria uma conexão de dados unidirecional entre a tabela do Excel e a lista. Saiba como [trabalhar offline com tabelas vinculadas às listas do SharePoint](https://support.office.com/article/work-offline-with-tables-that-are-linked-to-sharepoint-lists-5d66594a-6176-4a25-a198-320f13ccf41e).
  
Para saber mais, confira a seção "mais informações sobre como gerenciar grandes listas" em [gerenciar grandes listas e bibliotecas no Office 365](https://support.office.com/article/b4038448-ec0e-49b7-b853-679d3d8fb784).
  
## <a name="best-practices-for-customizing-web-pages"></a>Práticas recomendadas para personalizar páginas da Web

Ao personalizar uma página da Web, você pode inadvertidamente prejudicar o desempenho da página. Vários fatores podem ter impacto, como a complexidade e o tamanho da página, quantas Web Parts são adicionadas, quantos itens de lista ou biblioteca são exibidos inicialmente e a maneira como você codifica a página.
  
Para obter mais informações, consulte [ajustar o desempenho do SharePoint Online](tune-sharepoint-online-performance.md).
  
## <a name="best-practices-for-using-project-online"></a>Práticas recomendadas para usar o Project online

As diretrizes a seguir podem ajudar a melhorar o desempenho da rede.
  
- O Project online e o SharePoint Online exigem sincronização, o que pode ser demorado. Se suas equipes de projeto tiverem baixa rotatividade, desabilite a sincronização de site de projeto para melhorar o desempenho de publicação do projeto e das páginas de detalhes do projeto. Limitar a sincronização do Active Directory para grupos de recursos que realmente precisam usar o sistema e monitorar quaisquer possíveis problemas de permissão após a sincronização de grupos grandes.

- Se sua organização usa sites de projeto, crie-os por demanda, em vez de automaticamente. Isso acelera a primeira experiência de publicação e evita a criação de sites e conteúdo desnecessários.

- As páginas de detalhes do projeto (PDP) podem acionar um recálculo de todo o projeto e iniciar as ações de fluxo de trabalho, e ambas podem ser operações de desempenho intensa. Para evitar o disparo de dois processos de atualização ao mesmo tempo no mesmo PDP, evite atualizar os campos de calendário (data de início, data de término, data de status e data atual) e os campos não agendados (nome do projeto, descrição e proprietário).

- Reduza o número de Web Parts e campos personalizados exibidos em cada PDP. Crie um PDP dedicado com os únicos campos que precisam de atualização para melhorar a carga e poupar tempo.

- Ao usar o OData para relatórios, limite a quantidade de dados que você consulta no tempo de execução usando a filtragem no servidor.

Para obter mais informações, consulte [ajustar o desempenho do Project online](https://support.office.com/article/12ba0ebd-c616-42e5-b9b6-cad570e8409c).
  
## <a name="whats-the-best-way-to-report-problems"></a>Qual é a melhor maneira de relatar problemas?

A Microsoft aprimora continuamente o desempenho geral do Office 365 monitorando a rede, medindo a largura de banda e a latência, melhorando o tempo de carregamento da página, reduzindo a e/s de disco, reformulando as páginas para usar a estratégia de download mínimo, adicionando hardware a data centers e adicionando mais data centers. Para obter mais informações sobre como verificar o status atual e os problemas de relatório, consulte [como verificar a integridade do serviço do Office 365](view-service-health.md).
  
## <a name="see-also"></a>Confira também

[Planejamento de rede e ajuste de desempenho para o Office 365](network-planning-and-performance.md)
  
[Princípios de conectividade de rede do Office 365](microsoft-365-network-connectivity-principles.md)
  
[Gerenciar pontos de extremidade do Office 365](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)
  
[Perguntas frequentes sobre pontos de extremidade do Office 365](https://support.office.com/article/d4088321-1c89-4b96-9c99-54c75cae2e6d)
 
