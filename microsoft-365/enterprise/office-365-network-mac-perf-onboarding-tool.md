---
title: Ferramenta de teste de conectividade de rede do Microsoft 365 (visualização)
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 09/21/2020
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
description: Ferramenta de teste de conectividade de rede do Microsoft 365 (visualização)
ms.openlocfilehash: b29eb29cd390c3febd0992e942cf8ab39f652fb2
ms.sourcegitcommit: 26c2f01d6f88f6c288b04f9f08062d68dd1e67e1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/04/2020
ms.locfileid: "49569982"
---
# <a name="microsoft-365-network-connectivity-test-tool-preview"></a>Ferramenta de teste de conectividade de rede do Microsoft 365 (visualização)

A ferramenta de teste de conectividade de rede do Microsoft 365 está localizada em <https://connectivity.office.com> . Trata-se de uma ferramenta adjunta para a avaliação de rede e informações de informações de rede disponíveis no Centro de administração do Microsoft 365 sob o centro de **| Menu conectividade.**

> [!IMPORTANT]
> É importante entrar no locatário do Microsoft 365, pois todos os relatórios de teste são compartilhados com o administrador e carregados no locatário enquanto você está loco.

![Ferramenta de teste de conectividade](../media/m365-mac-perf/m365-mac-perf-test-tool-page.png)

>[!NOTE]
>A ferramenta de teste de conectividade de rede dá suporte a locatários no WW Comercial e na Alemanha, mas não na GCC Moderada, GCC Alta, DoD ou Na China.

As informações de rede no Centro de administração do Microsoft 365 são baseadas em medições regulares do produto para seu locatário do Microsoft 365, que são agregadas todos os dias. Em comparação, as informações de rede do teste de conectividade de rede do Microsoft 365 são executados localmente e uma vez na ferramenta. Os testes que podem ser feitos no produto são limitados e, ao executar testes locais para o usuário, mais dados podem ser coletados, resultando em informações mais aprofundadas. Considere então que as informações de rede no Centro de Administração do Microsoft 365 mostrarão que há um problema de rede para o uso do Microsoft 365 em um local específico do escritório. O teste de conectividade do Microsoft 365 pode ajudar a identificar a causa raiz desse problema, levando a uma ação recomendada de melhoria de desempenho de rede.

Recomendamos que eles sejam usados juntos, onde o status de qualidade de rede pode ser avaliado para cada local do escritório no Centro de Administração do Microsoft 365 e mais detalhes podem ser encontrados após a implantação de testes com base no teste de conectividade do Microsoft 365.

>[!IMPORTANT]
>Informações de rede, recomendações de desempenho e avaliações no Centro de administração do Microsoft 365 estão atualmente no status de visualização e só estão disponíveis para locatários do Microsoft 365 que foram inscritos no programa de visualização de recursos.

## <a name="what-happens-at-each-test-step"></a>O que acontece em cada etapa de teste

### <a name="office-location-identification"></a>Identificação de local do Office

Quando você clica no botão executar teste, mostramos a página de teste em execução e identificamos o local do escritório. Você pode digitar seu local por cidade, estado e país ou pode detectá-lo no navegador da Web. Se você detectá-lo, solicitamos a latitude e longitude do navegador da Web e limitamos a precisão a 300 m por 300 m antes de usar. Fazemos isso porque não é necessário identificar o local com mais precisão do que a construção para o desempenho da rede. 

### <a name="javascript-tests"></a>Testes de JavaScript

Após a identificação do local do escritório, executaremos um teste de latência TCP em JavaScript e solicitamos dados do serviço sobre servidores de front-door de serviço do Office 365 em uso e recomendados. Quando eles são concluídos, mostramos no mapa e na guia detalhes onde eles podem ser exibidos antes da próxima etapa.

### <a name="download-the-advanced-tests-client-application"></a>Baixar o aplicativo cliente de testes avançados

Em seguida, iniciamos o download do aplicativo cliente de testes avançados. Dependemos do usuário para iniciar o aplicativo cliente e ele também deve ter o .NET Core instalado.

Há duas partes no teste de conectividade de rede do Microsoft 365; o site e <https://connectivity.office.com> um aplicativo cliente do Windows para download que executa testes avançados de conectividade de rede. A maioria dos testes exige que o aplicativo seja executado. Ele preencherá os resultados novamente na página da Web à medida que ela é executado.

Você será solicitado a baixar o aplicativo de teste de cliente avançado do site após a conclusão dos testes do navegador da Web. Abra e execute o arquivo quando solicitado.

![Aplicativo cliente de testes avançados](../media/m365-mac-perf/m365-mac-perf-open-run-file.png)

### <a name="start-the-advanced-tests-client-application"></a>Iniciar o aplicativo cliente de testes avançados

Depois que o aplicativo cliente iniciar, a página da Web será atualizada para mostrar isso e os dados de teste começarão a ser recebidos na página da Web. Ele é atualizado sempre que novos dados são recebidos e você pode revisar os dados conforme eles chegam.

### <a name="advanced-tests-completed-and-test-report-upload"></a>Testes avançados concluídos e carregamento de relatório de teste

Depois que os testes são concluídos na página da Web e o cliente de testes avançados indicará isso e se o usuário estiver assinado no relatório de teste será carregado para o locatário do cliente.

## <a name="sharing-your-test-report"></a>Compartilhando seu relatório de teste

O relatório de teste requer entrar em sua conta do Office 365. Seu administrador seleciona como você pode compartilhar seu relatório de teste.

### <a name="sharing-your-report-with-your-administrator"></a>Compartilhar seu relatório com o administrador

Todos os relatórios de teste enquanto você está londo são compartilhados com seu administrador.

### <a name="sharing-with-your-microsoft-account-team-support-or-other-personnel"></a>Compartilhamento com sua equipe de conta da Microsoft, suporte ou outra equipe

Relatórios de teste excluindo qualquer identificação pessoal são compartilhados com os funcionários da Microsoft. Isso é habilitado por padrão e pode ser desabilitado por seu administrador no **serviço de | Página Conectividade de** Rede no Centro de Administração do Microsoft 365.

### <a name="sharing-with-other-users-who-sign-in-to-the-same-office-365-tenant"></a>Compartilhar com outros usuários que se ins dentro do mesmo locatário do Office 365

Você pode escolher os usuários com os quais compartilhar seu relatório e isso está habilitado por padrão. Ele também pode ser desabilitado pelo administrador.

![Compartilhar um link para os resultados do teste com um usuário](../media/m365-mac-perf/m365-mac-perf-share-to-user.png)

### <a name="sharing-with-anyone-using-a-reportid-link"></a>Compartilhar com qualquer pessoa usando um link ReportID

Você pode compartilhar seu relatório de teste com qualquer pessoa fornecendo acesso a um link ReportID. Isso gera uma URL que você pode enviar para alguém para que ele possa abrir o relatório de teste sem entrar. Isso é desabilitado por padrão e deve ser habilitado pelo administrador.

![Compartilhando um link para os resultados do teste](../media/m365-mac-perf/m365-mac-perf-share-link.png)

## <a name="network-connectivity-test-results"></a>Resultados do teste de conectividade de rede

Os resultados são mostrados nas **guias** Resumo **e** Detalhes. A guia de resumo mostra um mapa do perímetro de rede detectado e uma comparação da avaliação de rede com outros clientes do Office 365 próximos. Ele também permite o compartilhamento do relatório de teste. Esta é a aparência do resumo dos resultados.

![Resultados de resumo da ferramenta de teste de conectividade de rede](../media/m365-mac-perf/m365-mac-perf-summary-page.png)

Aqui está um exemplo da saída da guia de detalhes que a ferramenta mostra. Na guia detalhes, mostramos uma marca de seleção de círculo verde se o resultado foi comparado favoravelmente a um limite. Mostraremos um ponto de exclamação de triângulo vermelho se o resultado tiver excedido um limite indicando um insight de rede. As seções a seguir descrevem cada uma das linhas de resultados da guia de detalhes e explicam os limites usados para obter informações de rede.

![Exemplo de resultados de teste da ferramenta de teste de conectividade de rede](../media/m365-mac-perf/m365-mac-perf-all-details.png)

### <a name="your-location-information"></a>Suas informações de localização

Esta seção mostra os resultados do teste relacionados à sua localização.

#### <a name="your-location"></a>Sua localização

O local do usuário é detectado no navegador da Web dos usuários ou pode ser digitado à escolha dos usuários. Ele é usado para identificar distâncias de rede a partes específicas do perímetro da rede corporativa. Somente a cidade a partir dessa detecção de local e a distância até outros pontos de rede são salvas no relatório.

O local do escritório do usuário é mostrado na exibição de mapa.

#### <a name="network-egress-location-the-location-where-your-network-connects-to-your-isp"></a>Local de saída de rede (o local onde sua rede se conecta ao seu ISP)

Identificamos o endereço IP de saída de rede no lado do servidor. Os bancos de dados de localização são usados para procurar o local aproximado para a saída da rede. Esses bancos de dados geralmente têm uma precisão de cerca de 90% dos endereços IP. Se o local procurado pelo endereço IP de saída da rede não for preciso, isso levará a um resultado falso desse teste. Para validar se esse erro está ocorrendo para um endereço IP específico, você pode usar sites de local de endereço IP de rede publicamente acessíveis para comparar com seu local real.

#### <a name="your-distance-from-the-network-egress-location"></a>Sua distância do local de saída da rede

Determinamos a distância do local até o local do escritório. Isso é mostrado como um insight de rede se a distância for maior que **500** milhas (800 km) porque isso provavelmente aumentará a latência do TCP em mais de 25 ms e poderá afetar a experiência do usuário.

O local de saída de rede é mostrado na exibição de mapa e conectado ao local do escritório do usuário, indicando o backhaul de rede dentro da WAN corporativa.

A implementação da saída de rede local e direta de locais de escritório do usuário para a Internet é recomendada para a conectividade de rede do Microsoft 365. Melhorias na saída local e direta são a melhor maneira de abordar esse insight de rede.

#### <a name="proxy-server-information"></a>Informações do servidor proxy

Identificamos os servidores proxy configurados no computador local. Identificamos se algum deles está configurado no caminho de rede para otimizar o tráfego de rede da categoria do Microsoft 365. Identificamos a distância entre o local do escritório do usuário e os servidores proxy. A distância é testada primeiro pelo ping ICMP e, se isso falhar, testamos com ping TCP e, finalmente, se isso falhar, procuraremos o endereço IP do servidor proxy em um banco de dados de local de endereço IP. Mostraremos um insight de rede se o servidor proxy estiver a mais de **500** km (800 km) de distância do local do escritório do usuário.

#### <a name="virtual-private-network-vpn-you-use-to-connect-to-your-organization"></a>VPN (rede virtual privada) que você usa para se conectar à sua organização

Isso detecta se você está usando uma VPN para se conectar ao Office 365. Um resultado de passagem mostrará se você não tem VPN ou se tem uma VPN com configuração de túnel dividido recomendada para o Office 365.

#### <a name="vpn-split-tunnel"></a>Túnel dividido de VPN

Cada rota de categoria de otimização para o Exchange Online, o SharePoint Online e o Microsoft Teams é testada para ver se ela é tunelada na VPN ou não. Uma carga de trabalho dividida evita totalmente a VPN. Uma carga de trabalho em túnel é enviada pela VPN. Uma carga de trabalho de túnel seletivo tem algumas rotas enviadas pela VPN e algumas são divididas. Um resultado de aprovação mostrará se todas as cargas de trabalho são divididas ou com túnel seletivo.

#### <a name="customers-in-your-metropolitan-area-with-better-performance"></a>Clientes em sua área metropolitana com melhor desempenho

A latência TCP de rede do local do escritório do usuário com a porta frontal do serviço do Exchange Online é comparada com outros clientes do Microsoft 365 na mesma área de metro. Um insight de rede é mostrado se 10% ou mais de clientes na mesma área de área de metro têm melhor desempenho. Isso significa que os usuários terão melhor desempenho na interface do usuário do Microsoft 365.

Esse insight de rede é gerado com base em que todos os usuários em uma cidade têm acesso à mesma infraestrutura de telecomunicações e a mesma proximidade com os circuitos de Internet e a rede da Microsoft.

#### <a name="time-to-make-a-dns-request-on-your-network"></a>Tempo para fazer uma solicitação DNS em sua rede

Isso mostra o servidor DNS configurado no computador cliente que fez os testes. Pode ser um servidor resolvedor recursivo dns, no entanto, isso é incomum. É mais provável que seja um servidor encaminhador DNS que armazena em cache os resultados de DNS e encaminha quaisquer solicitações DNS não armazenadas para outro servidor DNS.

Isso é fornecido apenas para informações e não contribui para nenhum insight de rede.

#### <a name="your-distance-from-andor-time-to-connect-to-a-dns-recursive-resolver"></a>Sua distância entre e/ou tempo para se conectar a um resolvedor recursivo de DNS

O Resolvedor Recursivo de DNS em uso é identificado fazendo uma solicitação DNS específica e, em seguida, solicitando ao Servidor de Nomes DNS o endereço IP de onde ele recebeu a mesma solicitação. Esse endereço IP é o Resolvedor Recursivo dns e será procurado nos bancos de dados de localização do endereço IP para encontrar o local. A distância do local do escritório do usuário até o local do servidor resolvedor recursivo de DNS é calculada. Isso é mostrado como um insight de rede se a distância for maior que **500 milhas** (800 km).

O local procurado pelo Endereço IP de saída da rede pode não ser preciso e isso levaria a um resultado falso desse teste. Para validar se esse erro está ocorrendo para um endereço IP específico, você pode usar sites locais de endereço IP de rede acessíveis publicamente.

Esse insight de rede afetará especificamente a seleção da porta frontal do serviço do Exchange Online. Para resolver esse insight, a saída de rede local e direta deve ser um pré-requisito e, em seguida, o Resolvedor Recursivo de DNS deve estar localizado perto dessa saída de rede.

### <a name="exchange-online"></a>Exchange Online

Esta seção mostra os resultados do teste relacionados ao Exchange Online.

#### <a name="exchange-service-front-door-location"></a>Local da porta frontal do serviço do Exchange

A porta frontal do serviço Exchange em uso é identificada da mesma forma que o Outlook faz isso e nós medimos a latência TCP da rede do local do usuário até ele. A latência TCP é mostrada e a porta frontal do serviço Exchange em uso é comparada com a lista das melhores portas frontales de serviço para a localização atual. Isso é mostrado como um insight de rede se uma das melhores portas de serviço do Exchange não estiver em uso.

Não usar uma das melhores portas frontales de serviço do Exchange pode ser causado por backhaul de rede antes da saída da rede corporativa. Nesse caso, recomendamos a saída de rede local e direta. Ele também pode ser causado pelo uso de um servidor resolvedor recursivo de DNS remoto. Nesse caso, recomendamos alinhar o servidor resolvedor recursivo dns com a saída de rede.

Calculamos uma melhoria potencial na latência de TCP (ms) para a porta frontal do serviço do Exchange. Isso é feito analisando a latência da rede de localização do escritório do usuário testado e subtraindo a latência da rede do local atual para a porta frontal do serviço Exchange. A diferença representa a oportunidade potencial de melhoria.

#### <a name="best-exchange-service-front-doors-for-your-location"></a>Melhores porta frontal do serviço Exchange para sua localização

Isso lista os melhores locais de porta frontal do serviço do Exchange por cidade para sua localização.

#### <a name="service-front-door-recorded-in-the-client-dns"></a>Porta frontal do serviço registrada no DNS do cliente

Isso mostra o nome DNS e o endereço IP do servidor de front-end do serviço do Exchange para o que você foi direcionado. Ele é fornecido apenas para informações e não há informações de rede associadas.

### <a name="sharepoint-online"></a>SharePoint Online

Esta seção mostra os resultados do teste relacionados ao SharePoint Online e ao OneDrive.

#### <a name="the-service-front-door-location"></a>O local da porta frontal do serviço

A porta frontal do serviço do SharePoint em uso é identificada da mesma forma que o cliente do OneDrive e nós medimos a latência TCP da rede do local do escritório do usuário até ele.

#### <a name="download-speed"></a>Velocidade de download

Nós medimos a velocidade de download de um arquivo de 15 Mb da porta frontal do serviço do SharePoint. O resultado é mostrado em megabytes por segundo para indicar qual arquivo de tamanho em megabytes pode ser baixado do SharePoint ou do OneDrive em **um segundo.** O número deve ser semelhante a um décimo da largura de banda de circuito mínimo em megabits por segundo. Por exemplo, se você tiver uma conexão com a Internet de 100 mbps, pode esperar 10 megabytes por segundo (10 MBps).

#### <a name="buffer-bloat"></a>Buffer muito grande

Durante o download de 15 Mb, mede a latência TCP para a porta frontal do serviço do SharePoint. Essa é a latência sob carga e é comparada à latência quando não está sob carga. O aumento da latência quando sob carga geralmente é atribuível a buffers de dispositivos de rede do consumidor que estão sendo carregados (ou muito grande). Um insight de rede é mostrado para qualquer 1.000 ou mais.

#### <a name="service-front-door-recorded-in-the-client-dns"></a>Porta frontal do serviço registrada no DNS do cliente

Isso mostra o nome DNS e o endereço IP do servidor de front-end do serviço do SharePoint para o que você foi direcionado. Ele é fornecido apenas para informações e não há informações de rede associadas.

### <a name="microsoft-teams"></a>Microsoft Teams

Esta seção mostra os resultados do teste relacionados ao Microsoft Teams.

#### <a name="media-connectivity-audio-video-and-application-sharing"></a>Conectividade de mídia (áudio, vídeo e compartilhamento de aplicativos)

Isso testa a conectividade UDP com a porta de entrada do serviço do Microsoft Teams. Se isso estiver bloqueado, o Microsoft Teams ainda poderá funcionar usando TCP, mas o áudio e o vídeo estarão comprometidos. Leia mais sobre essas medições de rede UDP que também se aplicam ao Microsoft Teams em Qualidade de Mídia e Desempenho de Conectividade de [Rede no Skype for Business Online](https://docs.microsoft.com/skypeforbusiness/optimizing-your-network/media-quality-and-network-connectivity-performance)

#### <a name="packet-loss"></a>Perda de pacote

Mostra a perda de pacote UDP medida em uma chamada de áudio de teste de 10 segundos do cliente para a porta de entrada do serviço do Microsoft Teams. Isso deve ser inferior a **1,00% para** uma passagem.

#### <a name="latency"></a>Latência

Mostra a latência de UDP medida, que deve ser inferior a **100 ms.**

#### <a name="jitter"></a>Trem tremida

Mostra a trem tremida de UDP medida, que deve ser inferior a **30 ms.**

#### <a name="connectivity"></a>Conectividade

Testamos a conectividade HTTP do local do escritório do usuário para todos os pontos de extremidade de rede necessários do Microsoft 365. Eles são publicados em [https://aka.ms/o365ip](https://aka.ms/o365ip) . Um insight de rede é mostrado para todos os pontos de extremidade de rede necessários que não podem ser conectados.

A conectividade pode ser bloqueada por um servidor proxy, um firewall ou outro dispositivo de segurança de rede no perímetro da rede corporativa. A conectividade com a porta TCP 80 é testada com uma solicitação HTTP e a conectividade com a porta TCP 443 é testada com uma solicitação HTTPS. Se não houver resposta, o FQDN será marcado como uma falha. Se houver um código de resposta HTTP 407, o FQDN será marcado como uma falha. Se houver um código de resposta HTTP 403, verificaremos o atributo Server da resposta e se ele parecer ser um servidor proxy, marcamos isso como uma falha. Você pode simular os testes que executamos com a ferramenta de linha de comando do Windows curl.exe.

Testamos o certificado SSL em cada ponto de extremidade de rede necessário do Microsoft 365 que está na categoria otimizar ou permitir, conforme definido em [https://aka.ms/o365ip](https://aka.ms/o365ip) . Se algum teste não encontrar um certificado SSL da Microsoft, a rede criptografada conectada deverá ter sido interceptada por um dispositivo de rede intermediário. Um insight de rede é mostrado em todos os pontos de extremidade de rede criptografados interceptados.

Quando for encontrado um certificado SSL que não seja fornecido pela Microsoft, mostraremos o FQDN do teste e o proprietário do certificado SSL em uso. Esse proprietário de certificado SSL pode ser um fornecedor de servidor proxy ou pode ser um certificado auto-assinado empresarial.

#### <a name="network-path"></a>Caminho de rede

Esta seção mostra os resultados de um traceroute do ICMP para a porta frontal do serviço do Exchange Online, a porta frontal do serviço do SharePoint Online e a porta de entrada do serviço do Microsoft Teams. Ele é fornecido apenas para informações e não há informações de rede associadas. Há três traceroutes fornecidos. Um traceroute _para outlook.office365.com_, um traceroute para os clientes do SharePoint front-end ou para _microsoft.sharepoint.com_ se um não foi fornecido e um traceroute para world.tr.teams.microsoft.com _._

## <a name="connectivity-reports"></a>Relatórios de conectividade

Ao entrar, você pode revisar os relatórios anteriores executados. Você também pode compartilhá-los ou excluí-los da lista.

![Relatórios](../media/m365-mac-perf/m365-mac-perf-reports-list.png)

## <a name="network-health-status"></a>Status de saúde da rede

Isso mostra quaisquer problemas de saúde significativos com a rede global da Microsoft que podem afetar os clientes do Microsoft 365.

![Status de saúde da rede](../media/m365-mac-perf/m365-mac-perf-status-page.png)

## <a name="faq"></a>Perguntas frequentes

Aqui estão as respostas para algumas das nossas perguntas frequentes.

### <a name="is-this-tool-released-and-supported-by-microsoft"></a>Essa ferramenta foi lançada e tem suporte da Microsoft?

Atualmente, é uma visualização e planejamos fornecer atualizações regularmente até alcançarmos o status de versão de disponibilidade geral com o suporte da Microsoft. Forneça comentários para nos ajudar a melhorar. Estamos planejando publicar um guia mais detalhado de Integração de Rede do Office 365 como parte dessa ferramenta que é personalizada para a organização por seus resultados de teste.

### <a name="what-is-required-to-run-the-advanced-test-client"></a>O que é necessário para executar o cliente de teste avançado?

O cliente de teste avançado requer o .NET Core 3.1 Desktop Runtime. Se você executar o cliente de teste avançado sem essa instalação, será direcionado para a página [do instalador do .NET Core 3.1.](https://dotnet.microsoft.com/download/dotnet-core/3.1) Certifique-se de instalar o Tempo de Execução da Área de Trabalho e não o SDK ou o ASP.NET Core Runtime que estão mais acima na página. As permissões de administrador no computador são necessárias para instalar o .NET Core.

### <a name="what-is-microsoft-365-service-front-door"></a>O que é a porta de entrada do serviço do Microsoft 365?

A porta de entrada do serviço microsoft 365 é um ponto de entrada na rede global da Microsoft onde os clientes e serviços do Office encerram sua conexão de rede. Para obter uma conexão de rede ideal com o Microsoft 365, é recomendável que sua conexão de rede seja encerrada na porta frontal mais próxima do Microsoft 365 em sua cidade ou metro.

Observação: a porta de entrada do serviço do Microsoft 365 não tem relação direta com o produto do Serviço de Porta Frontal do **Azure** disponível no Azure Marketplace.

### <a name="what-is-the-best-microsoft-365-service-front-door"></a>Qual é a melhor porta de entrada de serviço do Microsoft 365?

A melhor porta frontal de serviço do Microsoft 365 (anteriormente conhecida como porta frontal de serviço ideal) é a mais próxima à saída da rede, geralmente na sua cidade ou área de metro. Use a ferramenta de desempenho de rede do Microsoft 365 para determinar a localização da porta frontal do serviço do Microsoft 365 em uso e as melhores portas de serviço. Se a ferramenta determinar que sua porta frontal em uso é uma das melhores, você deve esperar uma ótima conectividade com a rede global da Microsoft.

### <a name="what-is-an-internet-egress-location"></a>O que é um local de saída da Internet?

O local de saída da Internet é o local onde o tráfego de rede sai da rede corporativa e se conecta à Internet. Isso também é identificado como o local onde você tem um dispositivo NAT (Conversão de Endereços de Rede) e, geralmente, onde você se conecta com um Provedor de Serviços de Internet (ISP). Se você vir uma longa distância entre a localização e o local de saída da Internet, isso poderá identificar um backhaul de WAN significativo.

## <a name="related-topics"></a>Tópicos relacionados

[Conectividade de rede no Centro de Administração do Microsoft 365 (visualização)](office-365-network-mac-perf-overview.md)

[Percepções de desempenho de rede do Microsoft 365 (visualização)](office-365-network-mac-perf-insights.md)

[Avaliação de rede do Microsoft 365 (visualização)](office-365-network-mac-perf-score.md)

[Serviços de Localização de Conectividade de Rede do Microsoft 365 (visualização)](office-365-network-mac-location-services.md)
