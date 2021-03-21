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
ms.openlocfilehash: 3597996a74cccc3a178f7a5a637c956e0393641b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50926113"
---
# <a name="microsoft-365-network-connectivity-test-tool-preview"></a>Ferramenta de teste de conectividade de rede do Microsoft 365 (visualização)

A ferramenta de teste de conectividade de rede do Microsoft 365 está localizada em <https://connectivity.office.com> . É uma ferramenta adjunta para a avaliação de rede e informações de insights de rede disponíveis no Centro de administração do Microsoft 365 sob o **health | Menu conectividade.**

> [!IMPORTANT]
> É importante entrar no locatário do Microsoft 365, pois todos os relatórios de teste são compartilhados com o administrador e carregados para o locatário enquanto você está dentro.

![Ferramenta de teste de conectividade](../media/m365-mac-perf/m365-mac-perf-test-tool-page.png)

>[!NOTE]
>A ferramenta de teste de conectividade de rede dá suporte a locatários na WW Commercial e alemanha, mas não GCC Moderate, GCC High, DoD ou China.

As percepções de rede no Centro de Administração do Microsoft 365 são baseadas em medidas regulares no produto para seu locatário do Microsoft 365 que são agregadas a cada dia. Em comparação, as percepções de rede do teste de conectividade de rede do Microsoft 365 são executados localmente e uma vez na ferramenta. Os testes que podem ser feitos no produto são limitados e, ao executar testes locais para o usuário, mais dados podem ser coletados, resultando em informações mais profundas. Considere então que as percepções de rede no Centro de Administração do Microsoft 365 mostrarão que há um problema de rede para uso do Microsoft 365 em um local de escritório específico. O teste de conectividade do Microsoft 365 pode ajudar a identificar a causa raiz desse problema que leva a uma ação recomendada de melhoria de desempenho de rede.

Recomendamos que elas sejam usadas em conjunto, onde o status de qualidade de rede pode ser avaliado para cada local do escritório no Centro de Administração do Microsoft 365 e mais detalhes podem ser encontrados após a implantação de testes com base no teste de conectividade do Microsoft 365.

>[!IMPORTANT]
>Insights de rede, recomendações de desempenho e avaliações no Centro de Administração do Microsoft 365 estão atualmente em status de visualização e estão disponíveis apenas para locatários do Microsoft 365 que foram inscritos no programa de visualização de recursos.

## <a name="what-happens-at-each-test-step"></a>O que acontece em cada etapa de teste

### <a name="office-location-identification"></a>Identificação de local do Office

Quando você clica no botão executar teste, mostramos a página de teste em execução e identificamos o local do escritório. Você pode digitar sua localização por cidade, estado e país ou pode detectá-lo no navegador da Web. Se você detectá-lo, solicitamos a latitude e a longitude do navegador da Web e limitamos a precisão para 300m por 300m antes do uso. Fazemos isso porque não é necessário identificar o local com mais precisão do que o edifício para o desempenho da rede. 

### <a name="javascript-tests"></a>Testes JavaScript

Após a identificação do local do escritório, executemos um teste de latência TCP no JavaScript e solicitamos dados do serviço sobre servidores de porta da frente de serviço do Office 365 em uso e recomendados. Quando eles são concluídos, mostramos no mapa e na guia detalhes onde eles podem ser exibidos antes da próxima etapa.

### <a name="download-the-advanced-tests-client-application"></a>Baixar o aplicativo cliente de testes avançados

Em seguida, iniciamos o download do aplicativo cliente de testes avançados. Confiamos no usuário para iniciar o aplicativo cliente e ele também deve ter o .NET Core instalado.

Há duas partes para o teste de conectividade de rede do Microsoft 365; o site e <https://connectivity.office.com> um aplicativo cliente do Windows baixável que executa testes avançados de conectividade de rede. A maioria dos testes exige que o aplicativo seja executado. Ele preencherá os resultados de volta à página da Web à medida que ele é executado.

Você será solicitado a baixar o aplicativo de teste do cliente avançado do site após a conclusão dos testes do navegador da Web. Abra e execute o arquivo quando solicitado.

![Aplicativo cliente de testes avançados](../media/m365-mac-perf/m365-mac-perf-open-run-file.png)

### <a name="start-the-advanced-tests-client-application"></a>Iniciar o aplicativo cliente de testes avançados

Quando o aplicativo cliente é iniciado, a página da Web será atualizada para mostrar isso e os dados de teste começarão a ser recebidos na página da Web. Ele é atualizado sempre que novos dados são recebidos e você pode revisar os dados à medida que eles chegam.

### <a name="advanced-tests-completed-and-test-report-upload"></a>Testes avançados concluídos e carregamento de relatório de teste

Depois que os testes são concluídos na página da Web, o cliente de testes avançados indicará isso e se o usuário estiver assinado no relatório de teste será carregado para o locatário dos clientes.

## <a name="sharing-your-test-report"></a>Compartilhando seu relatório de teste

O relatório de teste requer entrar na sua conta do Office 365. O administrador seleciona como compartilhar seu relatório de teste.

### <a name="sharing-your-report-with-your-administrator"></a>Compartilhar seu relatório com seu administrador

Todos os relatórios de teste enquanto você está assinado são compartilhados com o administrador.

### <a name="sharing-with-your-microsoft-account-team-support-or-other-personnel"></a>Compartilhamento com sua equipe de conta da Microsoft, suporte ou outras equipes

Os relatórios de teste que excluim qualquer identificação pessoal são compartilhados com os funcionários da Microsoft. Isso é habilitado por padrão e pode ser desabilitado pelo administrador no **Health | Página Conectividade de** Rede no Centro de Administração do Microsoft 365.

### <a name="sharing-with-other-users-who-sign-in-to-the-same-office-365-tenant"></a>Compartilhamento com outros usuários que entraram no mesmo locatário do Office 365

Você pode escolher usuários com os quais compartilhar seu relatório e isso é habilitado por padrão. Ele também pode ser desabilitado pelo administrador.

![Compartilhar um link para seus resultados de teste com um usuário](../media/m365-mac-perf/m365-mac-perf-share-to-user.png)

### <a name="sharing-with-anyone-using-a-reportid-link"></a>Compartilhamento com qualquer pessoa usando um link ReportID

Você pode compartilhar seu relatório de teste com qualquer pessoa fornecendo acesso a um link ReportID. Isso gera uma URL que você pode enviar para alguém para que ele possa trazer o relatório de teste sem entrar. Isso está desabilitado por padrão e deve ser habilitado pelo administrador.

![Compartilhando um link para seus resultados de teste](../media/m365-mac-perf/m365-mac-perf-share-link.png)

## <a name="network-connectivity-test-results"></a>Resultados do teste de conectividade de rede

Os resultados são mostrados nas guias **Resumo** **e** Detalhes. A guia resumo mostra um mapa do perímetro de rede detectado e uma comparação da avaliação de rede com outros clientes do Office 365 próximos. Ele também permite o compartilhamento do relatório de teste. Veja a aparência dos resultados de resumo.

![Resultados de resumo da ferramenta de teste de conectividade de rede](../media/m365-mac-perf/m365-mac-perf-summary-page.png)

Aqui está um exemplo da saída da guia detalhes que a ferramenta mostra. Na guia detalhes, mostramos uma marca de verificação de círculo verde se o resultado foi comparado favoravelmente a um limite. Mostraremos um ponto de exclamação de triângulo vermelho se o resultado excedeu um limite indicando um insight de rede. As seções a seguir descrevem cada uma das linhas de resultados da guia de detalhes e explica os limites usados para insights de rede.

![Exemplo de exemplo da ferramenta de teste de conectividade de rede](../media/m365-mac-perf/m365-mac-perf-all-details.png)

### <a name="your-location-information"></a>Suas informações de localização

Esta seção mostra resultados de teste relacionados à sua localização.

#### <a name="your-location"></a>Sua localização

O local do usuário é detectado no navegador da Web dos usuários ou pode ser digitado na escolha dos usuários. Ele é usado para identificar distâncias de rede para partes específicas do perímetro de rede empresarial. Somente a cidade dessa detecção de local e a distância para outros pontos de rede são salvas no relatório.

O local do escritório do usuário é mostrado no exibição de mapa.

#### <a name="network-egress-location-the-location-where-your-network-connects-to-your-isp"></a>Local de saída de rede (o local onde sua rede se conecta ao SEU ISP)

Identificamos o endereço IP de saída da rede no lado do servidor. Os bancos de dados de localização são usados para procurar o local aproximado para a saída de rede. Esses bancos de dados geralmente têm uma precisão de cerca de 90% dos endereços IP. Se o local procurado pelo endereço IP de saída da rede não for preciso, isso levaria a um resultado falso desse teste. Para validar se esse erro está ocorrendo para um endereço IP específico, você pode usar sites de localização de endereço IP de rede publicamente acessíveis para comparar com sua localização real.

#### <a name="your-distance-from-the-network-egress-location"></a>Sua distância do local de saída de rede

Determinamos a distância desse local até o local do escritório. Isso é mostrado como um insight de  rede se a distância for maior do que 800 km, pois isso provavelmente aumentará a latência TCP em mais de 25 ms e poderá afetar a experiência do usuário.

O local de saída de rede é mostrado no exibição de mapa e conectado ao local do escritório do usuário indicando o backhaul de rede dentro da WAN corporativa.

A implementação de saída de rede local e direta de locais de escritório do usuário para a Internet é recomendada para conectividade de rede do Microsoft 365. Melhorias na saída local e direta são a melhor maneira de resolver esse insight de rede.

#### <a name="proxy-server-information"></a>Informações do servidor proxy

Identificamos os servidores proxy configurados no computador local. Identificamos se algum deles está configurado no caminho da rede para otimizar o tráfego de rede da categoria Microsoft 365. Identificamos a distância do local do escritório do usuário para os servidores proxy. A distância é testada primeiro pelo ping ICMP e, se isso falhar, testamos com ping TCP e, por fim, se isso falhar, procuraremos o Endereço IP do servidor proxy em um banco de dados de localização de endereço IP. Mostraremos uma visão de rede se o servidor proxy estiver a mais de **800** milhas (800 km) do local do escritório do usuário.

#### <a name="virtual-private-network-vpn-you-use-to-connect-to-your-organization"></a>VPN (rede virtual privada) que você usa para se conectar à sua organização

Isso detecta se você está usando uma VPN para se conectar ao Office 365. Um resultado de passagem mostrará se você não tem VPN ou se você tem uma VPN com configuração de túnel dividido recomendada para o Office 365.

#### <a name="vpn-split-tunnel"></a>Túnel dividido de VPN

Cada rota de categoria otimizada para Exchange Online, SharePoint Online e Microsoft Teams é testada para ver se ela está em túnel na VPN ou não. Uma carga de trabalho dividida evita totalmente a VPN. Uma carga de trabalho em túnel é enviada por meio da VPN. Uma carga de trabalho em túnel seletiva tem algumas rotas enviadas pela VPN e algumas divididas. Um resultado de passagem mostrará se todas as cargas de trabalho são divididas ou tuneladas seletivas.

#### <a name="customers-in-your-metropolitan-area-with-better-performance"></a>Clientes em sua área metropolitana com melhor desempenho

A latência TCP de rede do local do escritório do usuário para a porta de entrada do serviço do Exchange Online é comparada a outros clientes do Microsoft 365 na mesma área de metrô. Um insight de rede é mostrado se 10% ou mais de clientes na mesma área de metro têm melhor desempenho. Isso significa que seus usuários terão melhor desempenho na interface do usuário do Microsoft 365.

Esse insight de rede é gerado com base em que todos os usuários em uma cidade têm acesso à mesma infraestrutura de telecomunicações e à mesma proximidade com os circuitos da Internet e a rede da Microsoft.

#### <a name="time-to-make-a-dns-request-on-your-network"></a>Hora de fazer uma solicitação DNS em sua rede

Isso mostra o servidor DNS configurado na máquina cliente que fez os testes. Pode ser um servidor resolvedor recursivo DNS, no entanto, isso é incomum. É mais provável que seja um servidor encaminhador DNS que armazena em cache os resultados do DNS e encaminha todas as solicitações DNS não acanhadas para outro servidor DNS.

Isso é fornecido apenas para informações e não contribui para nenhuma visão de rede.

#### <a name="your-distance-from-andor-time-to-connect-to-a-dns-recursive-resolver"></a>Sua distância de e/ou hora para se conectar a um resolvedor recursivo DNS

O Resolvedor Recursivo DNS em uso é identificado fazendo uma solicitação DNS específica e, em seguida, solicitando ao Servidor de Nomes DNS o Endereço IP do que ele recebeu a mesma solicitação. Este Endereço IP é o Resolvedor Recursivo DNS e ele será procurado nos bancos de dados de localização de endereço IP para localizar o local. A distância do local do escritório do usuário até o local do servidor resolvedor recursivo DNS é calculada. Isso é mostrado como um insight de rede se a distância for maior do que **800** km (800 km).

O local procurado pelo Endereço IP de saída da rede pode não ser preciso e isso levaria a um resultado falso desse teste. Para validar se esse erro estiver ocorrendo para um Endereço IP específico, você pode usar sites de localização de endereço IP de rede publicamente acessíveis.

Esse insight de rede afetará especificamente a seleção da porta de entrada do serviço do Exchange Online. Para lidar com essa visão de saída de rede local e direta deve ser um pré-requisito e, em seguida, o Resolvedor Recursivo DNS deve estar localizado perto dessa saída de rede.

### <a name="exchange-online"></a>Exchange Online

Esta seção mostra resultados de teste relacionados ao Exchange Online.

#### <a name="exchange-service-front-door-location"></a>Local da porta da frente do serviço exchange

A porta da frente de serviço do Exchange em uso é identificada da mesma maneira que o Outlook faz isso e medimos a latência TCP da rede do local do usuário para ele. A latência TCP é mostrada e a porta da frente do serviço exchange em uso é comparada à lista das melhores portas de serviço para o local atual. Isso é mostrado como uma visão de rede se uma das melhores portas de entrada do serviço exchange não estiver em uso.

Não usar uma das melhores portas de entrada de serviço do Exchange pode ser causada por backhaul de rede antes da saída da rede corporativa, nesse caso, recomendamos saída de rede local e direta. Também pode ser causado pelo uso de um servidor de resolver recursivo DNS remoto, nesse caso, recomendamos alinhar o servidor de resolver recursivo DNS com a saída de rede.

Calculamos uma melhoria potencial na latência TCP (ms) para a porta da frente do serviço exchange. Isso é feito analisando a latência da rede de localização do escritório do usuário testada e subtraindo a latência da rede do local atual para a porta da frente do serviço do Exchange de armários. A diferença representa a oportunidade potencial de melhoria.

#### <a name="best-exchange-service-front-doors-for-your-location"></a>Melhores portas de serviço do Exchange para sua localização

Isso lista os melhores locais de porta de entrada do serviço exchange por cidade para sua localização.

#### <a name="service-front-door-recorded-in-the-client-dns"></a>Porta da frente de serviço registrada no DNS do cliente

Isso mostra o nome DNS e o endereço IP do servidor de porta da frente do serviço Exchange para o que você foi direcionado. Ele é fornecido apenas para informações e não há informações de rede associadas.

### <a name="sharepoint-online"></a>SharePoint Online

Esta seção mostra os resultados de teste relacionados ao SharePoint Online e ao OneDrive.

#### <a name="the-service-front-door-location"></a>O local da porta da frente do serviço

A porta de entrada do serviço do SharePoint em uso é identificada da mesma forma que o cliente do OneDrive e medimos a latência TCP de rede do local do escritório do usuário para ele.

#### <a name="download-speed"></a>Velocidade de download

Medimos a velocidade de download de um arquivo de 15 Mb da porta da frente do serviço do SharePoint. O resultado é mostrado em megabytes por segundo para indicar qual arquivo de tamanho em megabytes pode ser baixado do SharePoint ou do OneDrive em **um segundo**. O número deve ser semelhante a um décimo da largura de banda de circuito mínimo em megabits por segundo. Por exemplo, se você tiver uma conexão de internet de 100 mbps, poderá esperar 10 megabytes por segundo (10MBps).

#### <a name="buffer-bloat"></a>Buffer inchado

Durante o download de 15 Mb, medimos a latência TCP para a porta da frente do serviço do SharePoint. Esta é a latência em carga e é comparada à latência quando não está sob carga. O aumento da latência quando está sob carga é frequentemente atribuível aos buffers de dispositivos de rede do consumidor que estão sendo carregados (ou inchados). Uma visão de rede é mostrada para qualquer inchada de 1.000 ou mais.

#### <a name="service-front-door-recorded-in-the-client-dns"></a>Porta da frente de serviço registrada no DNS do cliente

Isso mostra o nome DNS e o Endereço IP do servidor de porta da frente do serviço do SharePoint para o que você foi direcionado. Ele é fornecido apenas para informações e não há informações de rede associadas.

### <a name="microsoft-teams"></a>Microsoft Teams

Esta seção mostra resultados de teste relacionados ao Microsoft Teams.

#### <a name="media-connectivity-audio-video-and-application-sharing"></a>Conectividade de mídia (áudio, vídeo e compartilhamento de aplicativos)

Isso testa a conectividade UDP com a porta de entrada de serviço do Microsoft Teams. Se isso estiver bloqueado, o Microsoft Teams ainda poderá funcionar usando TCP, mas o áudio e o vídeo serão prejudicados. Leia mais sobre essas medidas de rede UDP que também se aplicam ao Microsoft Teams no Desempenho de Conectividade de Rede e Qualidade de Mídia [no Skype for Business Online](/skypeforbusiness/optimizing-your-network/media-quality-and-network-connectivity-performance)

#### <a name="packet-loss"></a>Perda de pacote

Mostra a perda de pacote UDP medida em uma chamada de áudio de teste de 10 segundos do cliente para a porta da frente do serviço do Microsoft Teams. Isso deve ser inferior a **1,00%** para uma passagem.

#### <a name="latency"></a>Latência

Mostra a latência UDP medida, que deve ser inferior a **100ms**.

#### <a name="jitter"></a>Tremidos

Mostra a tremedeira UDP medida, que deve ser inferior a **30ms**.

#### <a name="connectivity"></a>Conectividade

Testamos a conectividade HTTP do local do escritório do usuário para todos os pontos de extremidade de rede necessários do Microsoft 365. Eles são publicados em [https://aka.ms/o365ip](./urls-and-ip-address-ranges.md) . Uma visão de rede é mostrada para todos os pontos de extremidade de rede necessários que não podem ser conectados.

A conectividade pode ser bloqueada por um servidor proxy, um firewall ou outro dispositivo de segurança de rede no perímetro da rede corporativa. A conectividade com a porta TCP 80 é testada com uma solicitação HTTP e a conectividade com a porta TCP 443 é testada com uma solicitação HTTPS. Se não houver resposta, o FQDN será marcado como uma falha. Se houver um código de resposta HTTP 407, o FQDN será marcado como uma falha. Se houver um código de resposta HTTP 403, verificaremos o atributo Server da resposta e se ele parece ser um servidor proxy, marcaremos isso como uma falha. Você pode simular os testes que executamos com a ferramenta de linha de comando do Windows curl.exe.

Testamos o certificado SSL em cada ponto de extremidade de rede necessário do Microsoft 365 que está na categoria otimizar ou permitir, conforme definido em [https://aka.ms/o365ip](./urls-and-ip-address-ranges.md) . Se algum teste não encontrar um certificado SSL da Microsoft, a rede criptografada conectada deve ter sido interceptada por um dispositivo de rede intermediário. Uma visão de rede é mostrada em todos os pontos de extremidade de rede criptografados interceptados.

Quando um certificado SSL é encontrado que não é fornecido pela Microsoft, mostramos o FQDN para o teste e o proprietário do certificado SSL em uso. Esse proprietário de certificado SSL pode ser um fornecedor de servidor proxy ou pode ser um certificado auto-assinado da empresa.

#### <a name="network-path"></a>Caminho de rede

Esta seção mostra os resultados de uma traceroute ICMP para a porta da frente do serviço do Exchange Online, a porta da frente do serviço do SharePoint Online e a porta da frente do serviço do Microsoft Teams. Ele é fornecido apenas para informações e não há informações de rede associadas. Há três traceroutes fornecidos. Uma traceroute para _outlook.office365.com_, uma traceroute para os clientes  do SharePoint front-end ou para microsoft.sharepoint.com se um não foi fornecido e uma traceroute para _world.tr.teams.microsoft.com_.

## <a name="connectivity-reports"></a>Relatórios de conectividade

Ao entrar, você pode revisar relatórios anteriores executados. Você também pode compartilhá-los ou excluí-los da lista.

![Relatórios](../media/m365-mac-perf/m365-mac-perf-reports-list.png)

## <a name="network-health-status"></a>Status de saúde da rede

Isso mostra quaisquer problemas de saúde significativos com a rede global da Microsoft que possam afetar os clientes do Microsoft 365.

![Status de saúde da rede](../media/m365-mac-perf/m365-mac-perf-status-page.png)

## <a name="faq"></a>Perguntas frequentes

Aqui estão as respostas para algumas das nossas perguntas frequentes.

### <a name="is-this-tool-released-and-supported-by-microsoft"></a>Essa ferramenta é lançada e suportada pela Microsoft?

Atualmente, é uma visualização e planejamos fornecer atualizações regularmente até atingirmos o status geral de versão de disponibilidade com suporte da Microsoft. Forneça comentários para nos ajudar a melhorar. Estamos planejando publicar um guia de Integração de Rede do Office 365 mais detalhado como parte dessa ferramenta que é personalizada para a organização por seus resultados de teste.

### <a name="what-is-required-to-run-the-advanced-test-client"></a>O que é necessário para executar o cliente de teste avançado?

O cliente de teste avançado requer o .NET Core 3.1 Desktop Runtime. Se você executar o cliente de teste avançado sem esse instalado, será direcionado para a página do instalador [.NET Core 3.1](https://dotnet.microsoft.com/download/dotnet-core/3.1). Certifique-se de instalar o Tempo de Execução da Área de Trabalho e não o SDK ou o ASP.NET Core Runtime que estão mais acima na página. As permissões de administrador no computador são necessárias para instalar o .NET Core.

### <a name="what-is-microsoft-365-service-front-door"></a>O que é a porta de entrada do serviço do Microsoft 365?

A porta de entrada do serviço do Microsoft 365 é um ponto de entrada na rede global da Microsoft, onde os clientes e serviços do Office encerram sua conexão de rede. Para uma conexão de rede ideal com o Microsoft 365, é recomendável que sua conexão de rede seja encerrada na porta frontal mais próxima do Microsoft 365 em sua cidade ou no metrô.

Observação: a porta da frente de serviço do Microsoft 365 não tem relação direta com o produto do Serviço de Porta Frontal do **Azure** disponível no marketplace do Azure.

### <a name="what-is-the-best-microsoft-365-service-front-door"></a>Qual é a melhor porta de entrada de serviço do Microsoft 365?

A melhor porta de entrada de serviço do Microsoft 365 (anteriormente conhecida como porta de entrada de serviço ideal) é uma que é mais próxima da saída de sua rede, geralmente em sua cidade ou área de metro. Use a ferramenta de desempenho de rede do Microsoft 365 para determinar a localização da porta da frente de serviço do Microsoft 365 em uso e as melhores portas da frente de serviço. Se a ferramenta determinar que sua porta frontal em uso é uma das melhores, você deve esperar uma ótima conectividade na rede global da Microsoft.

### <a name="what-is-an-internet-egress-location"></a>O que é um local de saída da Internet?

O local de saída da Internet é o local onde o tráfego de rede sai da rede corporativa e se conecta à Internet. Isso também é identificado como o local onde você tem um dispositivo NAT (Conversão de Endereço de Rede) e geralmente onde você se conecta a um Provedor de Serviços da Internet (ISP). Se você vir uma longa distância entre sua localização e seu local de saída da Internet, isso poderá identificar uma backhaul WAN significativa.

## <a name="related-topics"></a>Tópicos relacionados

[Conectividade de rede no Centro de Administração do Microsoft 365 (visualização)](office-365-network-mac-perf-overview.md)

[Insights de desempenho de rede do Microsoft 365 (visualização)](office-365-network-mac-perf-insights.md)

[Avaliação de rede do Microsoft 365 (visualização)](office-365-network-mac-perf-score.md)

[Serviços de Localização de Conectividade de Rede do Microsoft 365 (visualização)](office-365-network-mac-location-services.md)