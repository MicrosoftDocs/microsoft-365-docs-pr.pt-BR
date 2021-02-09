---
title: Conectividade de rede no Centro de administração do Microsoft 365 (visualização)
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
- m365initiative-coredeploy
description: Visão geral da conectividade de rede no Centro de Administração do Microsoft 365 (visualização)
ms.openlocfilehash: 976059e1469861ea28b2a94b84e373119935fb20
ms.sourcegitcommit: 005028af7c5a6b2e95f17a0037958131484d9e73
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/08/2021
ms.locfileid: "50145386"
---
# <a name="network-connectivity-in-the-microsoft-365-admin-center-preview"></a>Conectividade de rede no Centro de administração do Microsoft 365 (visualização)

O Centro de administração do Microsoft 365 agora inclui métricas de conectividade de rede agregadas coletadas do locatário do Microsoft 365 e disponíveis para exibição somente por usuários administrativos em seu locatário.

> [!div class="mx-imgBorder"]
> ![Ferramenta de teste de conectividade de rede](../media/m365-mac-perf/m365-mac-perf-admin-center.png)

**As avaliações de rede** **e as informações de** rede são exibidas no Centro de administração do Microsoft 365 em Health **| Conectividade**.

> [!div class="mx-imgBorder"]
> ![Página de desempenho da rede](../media/m365-mac-perf/m365-mac-perf-page-nav.png)

>[!NOTE]
>A ferramenta de teste de conectividade de rede dá suporte a locatários no WW Comercial e na Alemanha, mas não na GCC Moderada, GCC Alta, DoD ou Na China.

Ao navegar pela primeira vez para a página de desempenho de rede, você verá um painel de visão geral contendo um mapa de desempenho de rede global, uma avaliação de rede com escopo para todo o locatário e uma lista de problemas atuais. Na visão geral, você pode detalhar para exibir métricas e problemas específicos de desempenho de rede por local. Para saber mais, confira [Visão geral do desempenho da rede no Centro de administração do Microsoft 365.](#network-connectivity-overview-in-the-microsoft-365-admin-center)

Você pode ser solicitado a ingressar na visualização pública desse recurso em nome da sua organização. A aceitação geralmente ocorreu imediatamente e, em seguida, você verá a página de conectividade de rede. 

Ao navegar até a página de conectividade de rede, você verá um painel de visão geral contendo um mapa de desempenho de rede global, uma avaliação de rede com escopo para todo o locatário e uma lista de problemas atuais. Para acessar esta página, você deve ser um administrador da organização no Microsoft 365. A função administrativa Leitor de Relatório terá acesso de leitura a essas informações. Para configurar locais e outros elementos de conectividade de rede, um administrador deve fazer parte de uma função de administrador de servidor, como a função de administrador de suporte de serviço. Na visão geral, você pode detalhar para exibir métricas e problemas específicos de desempenho de rede por local. Para saber mais, confira [Visão geral da conectividade de rede no Centro de administração do Microsoft 365.](#network-connectivity-overview-in-the-microsoft-365-admin-center)

## <a name="pre-requisites-for-network-connectivity-assessments-to-appear"></a>Pré-requisitos para que as avaliações de conectividade de rede apareçam

To get started, turn on your location opt-in setting to automatically collect data from devices using Windows Location Services, go to your Locations list to add or upload location data, or run the Microsoft 365 network connectivity test from your office locations. Embora a conectividade de rede possa ser avaliada em toda a organização, qualquer melhoria no design de rede precisará ser feita para locais de escritório específicos. As informações de conectividade de rede são fornecidas para cada local de escritório assim que esses locais podem ser determinados. Há três opções para obter avaliações de rede de seus locais de escritório:

### <a name="1-enable-windows-location-services"></a>1. Habilitar os Serviços de Localização do Windows

Para essa opção, você deve ter pelo menos dois computadores em execução em cada local do escritório que suportam os pré-requisitos. O OneDrive para Windows **versão 19.232** ou superior deve ser instalado em cada computador. Para saber mais sobre as versões do OneDrive, confira as notas [de versão do OneDrive.](https://support.office.com/article/onedrive-release-notes-845dcf18-f921-435e-bf28-4e24b95e5fc0) As medições de rede estão planejadas para serem adicionadas em outros aplicativos clientes do Office 365 em um futuro próximo.

O Serviço de Localização do Windows deve ser consentido nos computadores. Você pode testar isso executando o **aplicativo Mapas** e se localizando por conta própria. Ela pode ser habilitada em um único computador com **configurações | Privacidade | Local** onde a configuração _Permitir que aplicativos acessem sua localização_ deve estar habilitada. O consentimento dos Serviços de Localização do Windows pode ser implantado em computadores usando MDM ou Política de Grupo com a configuração _LetAppsAccessLocation_.

Você não precisa adicionar locais no Centro de Administração com esse método, pois eles são identificados automaticamente na resolução da cidade. Você não pode mostrar vários locais de escritório em uma cidade usando os Serviços de Localização do Windows. As informações de localização também são arredondadas para os 300 metros mais próximos por 300 metros antes de serem carregadas para que não seja possível acessar informações de localização mais precisas.

Os computadores devem ter Wi-Fi rede em vez de um cabo ethernet. Os máquinas com um cabo ethernet não têm informações de localização precisas.

Amostras de medição e locais de escritório devem começar a aparecer 24 horas depois que esses pré-requisitos foram atendidos.

### <a name="2-add-locations-and-provide-lan-subnet-information"></a>2. Adicione locais e forneça informações sobre a sub-rede da LAN

Para essa opção, os Serviços de Localização do Windows Wi-Fi são necessários. Você precisa do OneDrive para Windows **versão 20.161** ou superior instalado em cada computador no local.

Você também precisa adicionar locais na página de conectividade de rede do Centro de Administração ou importá-los de um arquivo CSV. Os locais adicionados devem incluir as informações da sub-rede da LAN do office.

Como você está adicionando os locais, pode ter vários escritórios definidos em uma cidade.

Todas as medições de teste de máquinas cliente incluem as informações da sub-rede da LAN, que são correlacionadas com os detalhes de local do escritório inseridos. Amostras de medição e locais de escritório devem começar a aparecer 24 horas depois que esses pré-requisitos foram atendidos.

### <a name="3-manually-gather-test-reports-with-the-microsoft-365-network-connectivity-test-tool"></a>3. Reúna manualmente os relatórios de teste com a ferramenta de teste de conectividade de rede do Microsoft 365

Para essa opção, você precisa identificar uma pessoa em cada local. Peça que eles naveguem até o teste de conectividade de rede do [Microsoft 365](https://connectivity.office.com) em um computador Windows no qual eles têm permissões administrativas. No site, eles precisam entrar na conta do Office 365 para a mesma organização que você deseja ver os resultados. Em seguida, eles devem clicar **em Executar teste.** Durante o teste, há um EXE de teste de conectividade baixado. Eles precisam abrir e executar isso também. Depois que os testes são concluídos, o resultado do teste é carregado para o Office 365.

Os relatórios de teste são vinculados a um local se foram adicionados com informações de sub-rede da LAN, caso contrário, eles são mostrados apenas no local da cidade.

Amostras de medição e locais de escritório devem começar a aparecer de 2 a 3 minutos após a conclusão de um relatório de teste. Para saber mais, confira o teste de conectividade de rede do [Microsoft 365 (visualização).](office-365-network-mac-perf-onboarding-tool.md)

## <a name="how-do-i-use-this-information"></a>Como usar essas informações?

**Percepções de** rede , suas recomendações de desempenho relacionadas e avaliações de rede destinam-se a ajudar no design de perímetros de rede para seus locais de escritório. Cada insight fornece detalhes sobre as características de desempenho de um problema comum específico para cada localização geográfica onde os usuários estão acessando seu locatário. **As recomendações de desempenho** para cada visão de rede oferecem alterações específicas no design da arquitetura de rede que você pode fazer para melhorar a experiência do usuário relacionada à conectividade de rede do Microsoft 365. A avaliação de rede mostra como a conectividade de rede afeta a experiência do usuário, permitindo a comparação de diferentes conexões de rede de localização do usuário.

**As avaliações** de rede agregam uma agregação de muitas métricas de desempenho de rede em um instantâneo da sua rede corporativa, representada por um valor de pontos de 0 a 100. As avaliações de rede têm como escopo todo o locatário e para cada localização geográfica a partir da qual os usuários se conectam ao seu locatário, fornecendo aos administradores do Microsoft 365 uma maneira fácil de compreender instantaneamente uma gestão da saúde da rede da empresa e detalhar rapidamente um relatório detalhado para qualquer local de escritório global.

As empresas complexas com vários locais de escritório e arquiteturas de perímetro de rede não triviais podem se beneficiar dessa informação durante a integração inicial ao Microsoft 365 ou para resolver problemas de desempenho de rede descobertos com o aumento do uso. Isso geralmente não é necessário para pequenas empresas que usam o Microsoft 365 ou para empresas que já têm conectividade de rede simples e direta. As empresas com mais de 500 usuários e vários locais de escritório devem se beneficiar mais.

>[!IMPORTANT]
>Insights de rede, recomendações de desempenho e avaliações no Centro de administração do Microsoft 365 estão atualmente no status de visualização e só estão disponíveis para locatários do Microsoft 365 que foram inscritos no programa de visualização de recursos.

## <a name="enterprise-network-connectivity-challenges"></a>Desafios de conectividade de rede corporativa

> [!div class="mx-imgBorder"]
> ![Rede do cliente para nuvem](../media/m365-mac-perf/m365-mac-perf-first-last-mile.png)

Muitas empresas têm configurações de perímetro de rede que cresceram ao longo do tempo e foram projetadas principalmente para acomodar o acesso ao site da Internet dos funcionários, onde a maioria dos sites não é conhecida com antecedência e não é não é confiança. O foco em vigor e necessário é evitar ataques de malware e de ataque a esses sites desconhecidos. Essa estratégia de configuração de rede, embora útil para fins de segurança, pode levar à degradação do desempenho do usuário do Microsoft 365 e da experiência do usuário.

## <a name="how-we-can-solve-these-challenges"></a>Como podemos resolver esses desafios

As empresas podem melhorar a experiência do usuário geral e proteger seu ambiente seguindo os princípios de conectividade do [Office 365](https://aka.ms/pnc) e usando o recurso de conectividade de rede do Centro de Administração do Microsoft 365. Na maioria dos casos, seguir esses princípios gerais terá um impacto significativo positivo sobre a latência do usuário final, a confiabilidade do serviço e o desempenho geral do Microsoft 365.

Às vezes, a Microsoft é solicitado a investigar problemas de desempenho de rede com o Microsoft 365 para clientes corporativos de grande porte, e eles frequentemente têm uma causa raiz relacionada à infraestrutura de perímetro de rede dos clientes. Quando uma causa raiz comum de um problema de perímetro de rede do cliente é encontrada, buscamos identificar medições de teste simples que a identifiquem. Um teste com um limite de medição que identifica um problema específico é valioso porque podemos testar a mesma medida em qualquer local, dizer se essa causa raiz está presente lá e compartilhá-la como um insight de rede com o administrador.

Algumas ideias de rede indicarão simplesmente um problema que precisa de mais investigação. Um insight de rede onde temos testes suficientes para mostrar uma ação de correção específica para corrigir a causa raiz é listado como uma **ação recomendada.** Essas recomendações, com base em métricas ao vivo que mostram valores que estão fora de um limite predeterminado, são muito mais valiosas do que conselhos de práticas recomendadas gerais, pois são específicas para seu ambiente e mostrarão a melhoria real depois que as alterações recomendadas foram feitas.

## <a name="network-connectivity-overview-in-the-microsoft-365-admin-center"></a>Visão geral da conectividade de rede no Centro de Administração do Microsoft 365

A Microsoft tem medições de rede existentes de vários clientes da Web e da área de trabalho do Office que suportam a operação do Microsoft 365. Essas medições agora estão sendo usadas para fornecer insights de  design de arquitetura de rede e uma avaliação de rede que são mostradas na página Conectividade de rede no Centro de Administração do Microsoft 365.

Por padrão, as informações aproximadas de localização associadas às medições de rede identificam a cidade onde os dispositivos cliente estão localizados. A avaliação de rede em cada local é mostrada com cor e o número relativo de usuários em cada local é representado pelo tamanho do círculo.

> [!div class="mx-imgBorder"]
> ![Mapa de visão geral do Network Insights](../media/m365-mac-perf/m365-mac-perf-overview-map.png)

A página de visão geral também mostra a avaliação de rede do cliente como uma média ponderada em todos os locais de escritório.

> [!div class="mx-imgBorder"]
> ![Avaliação de rede](../media/m365-mac-perf/m365-mac-perf-overview-score.png)

Você pode exibir um modo de exibição de tabela dos locais onde eles podem ser filtrados, organizados e editados na guia locais. Locais com recomendações específicas também podem incluir uma melhoria potencial estimada da latência. Isso é calculado utilizando-se a latência média dos usuários da sua organização no local e subtraindo a latência média de todas as organizações na mesma cidade.

> [!div class="mx-imgBorder"]
> ![Locais de informações de rede](../media/m365-mac-perf/m365-mac-perf-locations.png)

## <a name="specific-office-location-network-performance-summary-and-insights"></a>Resumo e insights específicos do desempenho da rede local do escritório

Selecionar um local de escritório abre uma página de resumo específica do local mostrando detalhes da saída de rede que foi identificada a partir de medições para esse local de escritório.

> [!div class="mx-imgBorder"]
> ![Detalhes de informações de rede por local](../media/m365-mac-perf/m365-mac-perf-locations-plan-overview.png)

Um mapa da rede de perímetro para os usuários da sua organização no local é mostrado com alguns ou todos esses elementos:

- **Local do** Escritório - O local do escritório da página que você está olhando
- **Perímetro de** rede - O local do endereço IP de origem para conexões do local do escritório. Isso depende da precisão dos bancos de dados de localização de IP geo
- **Porta frontal de serviço ideal do Exchange** – uma das portas frontales recomendadas do serviço do Exchange à qual os usuários nesse local do escritório devem se conectar
- **Porta frontal abaixo do ideal do Exchange** - Uma porta frontal do serviço do Exchange à que os usuários estão conectados, mas não é recomendada
- **Porta frontal de serviço ideal do SharePoint** – uma das portas de frente recomendadas para o serviço do SharePoint à qual os usuários nesse local do escritório devem se conectar
- **Porta frontal de serviço abaixo** do ideal do SharePoint - Uma porta frontal de serviço do SharePoint à que os usuários estão conectados, mas não é recomendável
- **Servidor resolvedor recursivo** de DNS - A localização de um banco de dados de IP geo do resolvedor recursivo dns detectado usado para o Exchange Online (se disponível)
- **Seu servidor proxy** - a localização de um banco de dados DE IP geo do servidor proxy detectado (se disponível) 

A página de resumo do local do escritório também mostra a avaliação de rede do local, o histórico de avaliação da rede, uma comparação da avaliação desse local com outros clientes na mesma cidade e uma lista de insights e recomendações específicas que você pode realizar para melhorar o desempenho e a confiabilidade da rede.

Comparações entre clientes na mesma cidade são baseadas na expectativa de que todos os clientes tenham acesso igual aos provedores de serviços de rede, infraestrutura de telecomunicações e pontos de presença da rede Microsoft próximos.

A guia detalhes na página local do escritório mostra os resultados de medição específicos que foram usados para obter informações, recomendações e a avaliação de rede. Isso é fornecido para que os engenheiros de rede possam validar as recomendações e fatores em qualquer restrição ou especificidade em seu ambiente.

> [!div class="mx-imgBorder"]
> ![Detalhes específicos do local](../media/m365-mac-perf/m365-mac-perf-locations-plan-details-all.png)

## <a name="csv-import-for-lan-subnet-office-locations"></a>Importação CSV para locais de escritório da sub-rede da LAN

Para a identificação do escritório da sub-rede da LAN, você precisa adicionar cada local com antecedência. Em vez de adicionar locais de escritório individuais na guia **Locais,** você pode importá-los de um arquivo CSV. Você poderá obter esses dados de outros locais onde os armazenou, como o Painel de Qualidade de Chamada ou Sites e Serviços do Active Directory

No arquivo CSV, um local de cidade descoberto mostra a coluna userEntered como em branco, e um local de escritório adicionado manualmente é 1.

1. Na janela Conectividade _principal do Microsoft 365,_ clique na **guia** Locais.

1. Clique no **botão Importar** logo acima da lista de locais. O **flyout Importar locais do** escritório será exibido.

   > [!div class="mx-imgBorder"]
   > ![Mensagem de importação CSV](../media/m365-mac-perf/m365-mac-perf-import.png)

1. Clique no link Baixar locais atuais do escritório **(.csv)** para exportar a lista de locais atual para um arquivo CSV e salvá-la no disco rígido local. Isso fornecerá um CSV formatado corretamente com títulos de coluna aos quais você pode adicionar locais. Você pode deixar os locais exportados existentes como estão; eles não serão duplicados quando você importar o CSV atualizado. Se você quiser alterar o endereço de um local existente, ele será atualizado quando você importar o CSV. Você não pode alterar o endereço de uma cidade descoberta.

1. Abra o CSV e adicione seus locais preenchendo os campos a seguir em uma nova linha para cada local que você deseja adicionar. Deixe todos os outros campos em branco; os valores que você inserir em outros campos serão ignorados.

   1. **userEntered** (obrigatório): deve ser 1 para um novo local de escritório da Sub-rede da LAN
   1. **Endereço** (obrigatório): o endereço físico do escritório
   1. **Latitude** (opcional): preenchida a partir de mapas do Bing de procurar o endereço se estiver em branco
   1. **Longitude** (opcional): preenchida a partir de mapas do Bing de procurar o endereço se estiver em branco
   1. **Intervalos** de endereços IP de saída de 1 a 5 (opcional): para cada intervalo, insira o nome do circuito seguido por uma lista separada por espaços de endereços CIDR IPv4 ou IPv6 válidos. Esses valores são usados para diferenciar vários locais de escritório onde você usa os mesmos endereços IP da sub-rede da LAN. Todos os intervalos de endereços IP de saída devem ter /24 tamanho de rede e /24 não está incluído na entrada.
   1. **LanIps** (obrigatório): listar os intervalos de sub-redes da LAN em uso neste local do escritório. As IDs de sub-rede da LAN precisam ter um tamanho de rede CIDR incluído, onde o tamanho da rede pode estar entre /8 e /29. Vários intervalos de sub-redes da LAN podem ser separados por vírgula ou ponto-e-vírgula.
   
1. Quando você tiver adicionado seus locais de  escritório e salvo  o arquivo, clique no botão Procurar ao lado do campo Carregar o campo concluído e selecione o arquivo CSV salvo.

1. O arquivo será validado automaticamente. Se houver erros de validação, você verá a mensagem de erro. Existem alguns _erros no arquivo de importação. Revise os erros, corrija o arquivo de importação e tente novamente._ Clique no link **Abrir detalhes do erro para** obter uma lista de erros específicos de validação de campo.

   > [!div class="mx-imgBorder"]
   > ![Mensagem de erro de importação CSV](../media/m365-mac-perf/m365-mac-perf-import-error.png)

1. Se não houver erros no arquivo, você verá a mensagem _O relatório está pronto. Localizações x encontradas para adicionar e x locais a atualizar._ Clique no **botão Importar** para carregar o CSV.

   > [!div class="mx-imgBorder"]
   > ![Mensagem pronta para importação de CSV](../media/m365-mac-perf/m365-mac-perf-import-ready.png)

## <a name="faq"></a>Perguntas frequentes

### <a name="what-is-a-microsoft-365-service-front-door"></a>O que é uma porta de entrada de serviço do Microsoft 365?

A porta de entrada do serviço microsoft 365 é um ponto de entrada na rede global da Microsoft onde os clientes e serviços do Office encerram sua conexão de rede. Para uma conexão de rede ideal com o Microsoft 365, é recomendável que sua conexão de rede seja encerrada na porta frontal mais próxima do Microsoft 365.

>[!NOTE]
>A porta frontal do serviço do Microsoft 365 não tem relação direta com o produto do Serviço de Porta Frontal do Azure disponível no Azure Marketplace.

### <a name="what-is-an-optimal-microsoft-365-service-front-door"></a>Qual é a porta de entrada de serviço ideal do Microsoft 365?

Uma porta frontal de serviço ideal do Microsoft 365 é a mais próxima de sua saída de rede, geralmente em sua cidade ou área de metro. Use a ferramenta de teste de conectividade do [Microsoft 365 (visualização)](office-365-network-mac-perf-onboarding-tool.md) para determinar a localização da porta frontal de serviço do Microsoft 365 em uso e a porta de entrada de serviço ideal. Se a ferramenta determinar que sua porta frontal em uso é ideal, então você está se conectando de forma ideal à rede global da Microsoft.

### <a name="what-is-an-internet-egress-location"></a>O que é um local de saída da Internet?

O local de saída da Internet é o local onde o tráfego de rede sai da rede corporativa e se conecta à Internet. Isso também é identificado como o local onde você tem um dispositivo NAT (Conversão de Endereços de Rede) e, geralmente, onde você se conecta com um Provedor de Serviços de Internet (ISP). Se você vir uma longa distância entre a localização e o local de saída da Internet, isso pode indicar um backhaul de WAN significativo.

## <a name="related-topics"></a>Tópicos relacionados

[Informações de rede do Microsoft 365 (visualização)](office-365-network-mac-perf-insights.md)

[Avaliação de rede do Microsoft 365 (visualização)](office-365-network-mac-perf-score.md)

[Ferramenta de teste de conectividade do Microsoft 365 (visualização)](office-365-network-mac-perf-onboarding-tool.md)

[Serviços de Localização de Conectividade de Rede do Microsoft 365 (visualização)](office-365-network-mac-location-services.md)
