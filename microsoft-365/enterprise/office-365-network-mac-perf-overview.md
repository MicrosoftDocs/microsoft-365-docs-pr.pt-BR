---
title: Conectividade de rede no Microsoft 365 Admin Center
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
description: Visão geral da conectividade de rede no Microsoft 365 Admin Center
ms.openlocfilehash: 75451a73ed56dade796f6de288f7f4acfb147960
ms.sourcegitcommit: fb6c5e04ade1e82b26b2f911577b5ac721f1c544
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/13/2021
ms.locfileid: "52470607"
---
# <a name="network-connectivity-in-the-microsoft-365-admin-center"></a>Conectividade de rede no Microsoft 365 Admin Center

O Microsoft 365 Admin Center agora inclui métricas de conectividade de rede agregadas coletadas do seu locatário Microsoft 365 e disponíveis para exibição somente por usuários administrativos em seu locatário.

> [!div class="mx-imgBorder"]
> ![Ferramenta de teste de conectividade de rede](../media/m365-mac-perf/m365-mac-perf-admin-center.png)

**Avaliações de rede** **e percepções de rede** são exibidas no Centro de administração Microsoft 365 em Health **| Conectividade de rede**.

> [!div class="mx-imgBorder"]
> ![Página de desempenho da rede](../media/m365-mac-perf/m365-mac-perf-page-nav.png)

>[!NOTE]
>A conectividade de rede no Centro de Administração dá suporte a locatários na WW Commercial e alemanha, mas não GCC moderado, GCC Alta, DoD ou China.

Ao navegar pela primeira vez para a página de desempenho da rede, você terá que configurar seus locais para ver o mapa do desempenho global da rede, uma avaliação de rede com escopo para todo o locatário, porcentagem de seus usuários trabalhando remotamente versus local e uma lista de problemas atuais para realizar ações e/ou pesquisar mais. No painel de visão geral, você pode detalhar para exibir métricas e problemas específicos de desempenho de rede por local. Para obter mais informações, consulte [Visão geral do desempenho da rede no Microsoft 365 Admin Center](#network-connectivity-overview-in-the-microsoft-365-admin-center).

Você pode ser solicitado a ingressar na visualização pública desse recurso em nome da sua organização. A aceitação geralmente acontece imediatamente, depois da qual você verá a página de conectividade de rede.

Para acessar a página de conectividade de rede, você deve ser um administrador da organização dentro Microsoft 365. A função administrativa Leitor de Relatório terá acesso de leitura a essas informações. Para configurar locais e outros elementos de conectividade de rede, um administrador deve fazer parte de uma função de administrador de servidor, como a função de administrador de suporte do serviço.

## <a name="pre-requisites-for-network-connectivity-assessments-to-appear"></a>Pré-requisitos para que as avaliações de conectividade de rede apareçam

Para começar, acentue a configuração de aceitação de local para coletar automaticamente dados de dispositivos usando os Serviços de Localização do Windows, vá para sua lista de Locais para adicionar ou carregar dados de localização ou execute o teste de conectividade de rede Microsoft 365 de seus locais de escritório. Embora a conectividade de rede possa ser avaliada em toda a organização, quaisquer melhorias de design de rede precisarão ser feitas para locais de escritório específicos. As informações de conectividade de rede são fornecidas para cada local do escritório quando esses locais podem ser determinados. Há três opções para obter avaliações de rede de seus locais de escritório:

### <a name="1-enable-windows-location-services"></a>1. Habilitar Windows serviços de localização

Para essa opção, você deve ter pelo menos dois computadores em execução em cada local do escritório que suportam os pré-requisitos. OneDrive para Windows versão deve estar atualizada e instalada em cada computador. Para obter mais informações sobre OneDrive versões, consulte as [OneDrive de versão](https://support.office.com/article/onedrive-release-notes-845dcf18-f921-435e-bf28-4e24b95e5fc0). As medidas de rede são planejadas para serem adicionadas a outros aplicativos Office 365 cliente em um futuro próximo.

Windows O Serviço de Localização deve ser consentido nos máquinas. Você pode testar isso executando o aplicativo **Mapas** e localizando-se. Ele pode ser habilitado em um único computador com **Configurações | Privacidade | Local** onde a configuração _Permitir que aplicativos acessem sua localização_ deve estar habilitada. Windows O consentimento dos Serviços de Localização pode ser implantado em PCs usando MDM ou Política de Grupo com a configuração _LetAppsAccessLocation_.

Você não precisa adicionar locais no Centro de Administração com esse método, pois eles são identificados automaticamente na resolução da cidade. Vários locais de escritório na mesma cidade não serão mostrados ao usar Windows Serviços de Localização. As informações de local são arredondadas para os 300 metros mais próximos por 300 metros para que informações de localização mais precisas não são acessadas.

Os computadores devem ter Wi-Fi rede em vez de um cabo ethernet. Os máquinas com um cabo ethernet não têm informações de localização precisas.

Amostras de medida e locais de escritório devem começar a aparecer 24 horas depois que esses pré-requisitos foram atendidos.

### <a name="2-add-locations-and-provide-lan-subnet-information"></a>2. Adicione locais e forneça informações de sub-rede lan

Para essa opção, nem Windows serviços de localização nem Wi-Fi são necessários. Sua OneDrive para Windows versão deve estar atualizada e instalada em pelo menos um computador no local.

Você também precisa adicionar locais na página **Locais** ou importá-los de um arquivo CSV. Os locais adicionados devem incluir as informações da sub-rede lan do office.

Essa opção permite que você tenha vários escritórios definidos em uma cidade.

Todas as medidas de teste de máquinas cliente incluem as informações da sub-rede lan, que são correlacionadas com os detalhes de local do escritório inseridos. Amostras de medida e locais de escritório devem começar a aparecer 24 horas depois que esses pré-requisitos foram atendidos.

### <a name="3-manually-gather-test-reports-with-the-microsoft-365-network-connectivity-test-tool"></a>3. Coletar manualmente relatórios de teste com a ferramenta de teste Microsoft 365 de conectividade de rede

Para essa opção, você precisa identificar uma pessoa em cada local. Peça que eles naveguem [até Microsoft 365 teste](https://connectivity.office.com) de conectividade de rede em um computador Windows no qual eles têm permissões administrativas. No site, eles precisam entrar em sua conta Office 365 para a mesma organização que você deseja ver os resultados. Em seguida, eles devem clicar **em Executar teste**. Durante o teste, há um EXE de teste de conectividade baixado. Eles precisam abrir e executar isso. Depois que os testes são concluídos, o resultado do teste é carregado no Centro de Administração.

Os relatórios de teste são vinculados a um local se foram adicionados com informações de sub-rede lan, caso contrário, eles são mostrados apenas no local da cidade.

Amostras de medida e locais de escritório devem começar a aparecer 2 a 3 minutos após a conclusão de um relatório de teste. Para obter mais informações, consulte Microsoft 365 teste de conectividade [de rede (visualização)](office-365-network-mac-perf-onboarding-tool.md).

## <a name="how-do-i-use-this-information"></a>Como uso essas informações?

**Percepções de** rede , suas recomendações de desempenho relacionadas e avaliações de rede destinam-se a ajudar a projetar perímetros de rede para seus locais de escritório. Cada insight fornece detalhes sobre as características de desempenho para um problema de rede comum específico para cada local geográfico onde os usuários estão acessando seu locatário. **As recomendações de desempenho** para cada visão de rede oferecem alterações específicas de design de arquitetura de rede que você pode fazer para melhorar a experiência do usuário relacionada Microsoft 365 conectividade de rede. A avaliação de rede mostra como a conectividade de rede afeta a experiência do usuário, permitindo a comparação de diferentes conexões de rede de localização do usuário.

**As avaliações de** rede destilam um agregado de muitas métricas de desempenho de rede em um instantâneo da sua saúde de rede corporativa, representado por um valor de pontos de 0 a 100. As avaliações de rede têm escopo para todo o locatário e para cada local geográfico a partir do qual os usuários se conectam ao seu locatário, fornecendo aos administradores do Microsoft 365 uma maneira fácil de entender instantaneamente uma gestalt da saúde da rede da empresa e fazer um relatório detalhado para qualquer local de escritório global.

As empresas complexas com vários locais de escritório e arquiteturas de perímetro de rede não triviais podem se beneficiar dessa informação durante a integração inicial para o Microsoft 365 ou para resolver problemas de desempenho de rede descobertos com o crescimento do uso. Isso geralmente não é necessário para pequenas empresas usando Microsoft 365, ou para qualquer empresa que já tenha conectividade de rede simples e direta. As empresas com mais de 500 usuários e vários locais de escritório devem se beneficiar mais.

>[!IMPORTANT]
>Percepções de rede, recomendações de desempenho e avaliações no Centro de Administração do Microsoft 365 está atualmente em status de visualização e está disponível apenas para locatários de Microsoft 365 que foram inscritos no programa de visualização de recursos.

## <a name="enterprise-network-connectivity-challenges"></a>Enterprise de conectividade de rede

> [!div class="mx-imgBorder"]
> ![Rede do cliente para nuvem](../media/m365-mac-perf/m365-mac-perf-first-last-mile.png)

Muitas empresas têm configurações de perímetro de rede que cresceram com o tempo e foram projetadas principalmente para acomodar o acesso ao site da Internet dos funcionários, onde a maioria dos sites não são conhecidos com antecedência e não são falsos. O foco predominante e necessário é evitar ataques de malware e phishing desses sites desconhecidos. Essa estratégia de configuração de rede, embora útil para fins de segurança, pode levar à degradação do Microsoft 365 do usuário e da experiência do usuário.

## <a name="how-we-can-solve-these-challenges"></a>Como resolver esses desafios

As empresas podem melhorar a experiência geral [](./microsoft-365-network-connectivity-principles.md) do usuário e proteger seu ambiente seguindo Office 365 de conectividade e usando o recurso Microsoft 365 conectividade de rede do Centro de Administração. Na maioria dos casos, seguir esses princípios gerais terá um impacto positivo significativo na latência do usuário final, na confiabilidade do serviço e no desempenho geral da Microsoft 365.

Às vezes, a Microsoft é solicitado a investigar problemas de desempenho de rede com Microsoft 365 para clientes de grandes empresas, e eles frequentemente têm uma causa raiz relacionada à infraestrutura de perímetro de rede do cliente. Quando uma causa raiz comum de um problema de perímetro de rede do cliente é encontrada, buscamos identificar medições de teste simples que o identificam. Um teste com um limite de medida que identifica um problema específico é valioso porque podemos testar a mesma medida em qualquer local, dizer se essa causa raiz está presente lá e compartilhá-la como um insight de rede com o administrador.

Algumas percepções de rede indicarão apenas um problema que precisa de mais investigação. Uma visão de rede em que temos testes suficientes para mostrar uma ação de correção específica para corrigir a causa raiz é listada como uma **ação recomendada**. Essas recomendações, com base em métricas ao vivo que revelam valores que estão fora de um limite predeterminado, são muito mais valiosas do que os conselhos gerais de práticas recomendadas, pois são específicas para seu ambiente e mostrarão a melhoria real depois que as alterações recomendadas foram feitas.

## <a name="network-connectivity-overview-in-the-microsoft-365-admin-center"></a>Visão geral da conectividade de rede no Microsoft 365 Admin Center

A Microsoft tem medidas de rede existentes de vários Office desktop e web que suportam a operação de Microsoft 365. Essas medidas agora estão sendo usadas para fornecer ideias de design  de arquitetura de rede e uma avaliação de rede que são mostradas na página Conectividade de rede no Centro de administração Microsoft 365 de rede.

Por padrão, informações de localização aproximadas associadas às medições de rede identificam a cidade onde os dispositivos cliente estão localizados. A avaliação de rede em cada local é mostrada com cor e o número relativo de usuários em cada local é representado pelo tamanho do círculo.

> [!div class="mx-imgBorder"]
> ![Mapa de visão geral de insights de rede](../media/m365-mac-perf/m365-mac-perf-overview-map.png)

A página de visão geral também mostra a avaliação de rede do cliente como uma média ponderada em todos os locais do office.

> [!div class="mx-imgBorder"]
> ![Avaliação de rede](../media/m365-mac-perf/m365-mac-perf-overview-score.png)

Você pode exibir uma exibição de tabela dos locais onde eles podem ser filtrados, organizados e editados na guia **Locais.** Locais com recomendações específicas também podem incluir uma melhoria de latência potencial estimada. Isso é calculado utilizando a latência mediana dos usuários da sua organização no local e subtraindo a latência mediana para todas as organizações na mesma cidade.

> [!div class="mx-imgBorder"]
> ![Locais de insights de rede](../media/m365-mac-perf/m365-mac-perf-locations.png)

## <a name="remote-worker-assessment-and-user-connection-metrics"></a>Avaliação de trabalho remoto e métricas de conexão do usuário

Classificamos os logs de tráfego de rede como usuários remotos ou locais e mostramos suas porcentagens na seção métricas de conexão do usuário do painel de visão geral. Para cidades onde você tem usuários remotos, você encontrará a pontuação de avaliação de rede remota específica do local quando abrir a página desse local. A lista de locais terá locais de escritório e cidades de trabalho remotas, que podem ser filtradas e classificação. Fornecemos a pontuação de avaliação do trabalhador remoto, com divisão de pontos para Exchange, SharePoint e Teams.

As percepções de rede do usuário local são agregadas e relatadas no nível da cidade e limitadas a cidades com no mínimo cinco funcionários remotos. Não identificamos funcionários individuais trabalhando em casa.

Os locais são classificados automaticamente como locais ou remotos, no entanto, você tem a opção de inserir todos os seus endereços IP de saída no local manualmente para garantir uma classificação de 100%. Se você decidir ir por essa rota, você terá que verificar a caixa de seleção Inserir todos os endereços IP de saída no **local manualmente** no flyout Locations Configurações depois de adicionar todos os seus endereços IP de saída. Quando isso for feito, todos os logs de tráfego de rede de endereços IP de saída marcados como locais sempre serão classificados como escritórios e todos os outros endereços IP de saída serão classificados como remotos.

## <a name="specific-office-location-network-performance-summary-and-insights"></a>Resumo e insights específicos do desempenho da rede de localização do escritório

Selecionar um local de escritório abre uma página de resumo específica do local mostrando detalhes da saída de rede que foi identificada a partir de medidas para esse local do escritório.

> [!div class="mx-imgBorder"]
> ![Detalhes de informações de rede por local](../media/m365-mac-perf/m365-mac-perf-locations-plan-overview.png)

Um mapa da rede de perímetro para os usuários da sua organização no local é mostrado com alguns ou todos esses elementos:

- **Office local** - O local do escritório para a página que você está olhando
- **Perímetro de rede** - O local do Endereço IP de origem para conexões do local do escritório. Isso depende da precisão dos bancos de dados de localização geo-IP
- **Exchange porta de** entrada de serviço ideal - uma das portas de frente de serviço recomendadas Exchange que os usuários neste local do office devem se conectar
- Exchange porta da frente **sub-ideal** - Uma porta da frente de serviço Exchange que os usuários estão conectados, mas não é recomendável
- **SharePoint porta de** entrada de serviço ideal - uma das portas de frente de serviço recomendadas SharePoint que os usuários neste local do office devem se conectar
- **SharePoint porta** de entrada de serviço sub-ideal - Uma porta da frente de serviço SharePoint que os usuários estão conectados, mas não é recomendável
- Servidor de resolver **recursivo** DNS - O local de um banco de dados IP geografo do resolvedor recursivo DNS detectado usado para Exchange Online (se disponível)
- **Seu servidor proxy** - O local de um banco de dados IP geo do servidor proxy detectado (se disponível) 

A página de resumo de localização do escritório também mostra a avaliação de rede do local, o histórico de avaliação de rede, uma comparação da avaliação desse local com outros clientes na mesma cidade e uma lista de insights e recomendações específicas que você pode realizar para melhorar o desempenho e a confiabilidade da rede.

As comparações entre clientes na mesma cidade se baseiam na expectativa de que todos os clientes tenham acesso igual a provedores de serviços de rede, infraestrutura de telecomunicações e pontos de presença de rede da Microsoft próximos.

Os nomes de locais podem ser personalizados ao adicionar um novo local ou editar um local existente no sobrevoo de local. Isso oferece flexibilidade para personalizar seus nomes de local a qualquer momento. Além disso, ao adicionar sub-redes de LAN diretamente no sub-plano de localização, mostramos uma lista lista de sub-redes lan com conexão suave que você pode selecionar. Os nomes de circuitos para endereços IP de saída específicos do office também podem ser adicionados e editados.

A guia detalhes na página de local do office mostra os resultados de medida específicos que foram usados para obter informações, recomendações e a avaliação de rede. Isso é fornecido para que os engenheiros de rede possam validar as recomendações e o fator em quaisquer restrições ou especificações em seu ambiente. Você também encontrará o número estimado de usuários para amostras coletadas nesses locais de escritório, bem como os funcionários remotos nessa cidade.

> [!div class="mx-imgBorder"]
> ![Detalhes específicos do local](../media/m365-mac-perf/m365-mac-perf-locations-plan-details-all.png)


## <a name="sharing-network-assessment-data-with-microsoft"></a>Compartilhamento de dados de avaliação de rede com a Microsoft

Por padrão, as avaliações de rede para sua organização e as percepções de rede são compartilhadas com os funcionários da Microsoft. Isso não inclui dados pessoais de sua equipe, mas apenas as métricas de avaliação de rede e informações de rede específicas mostradas no centro de administração para seus locais de escritório. Ele também não inclui seus nomes de local do escritório ou endereços de rua, portanto, você precisaria dizer a eles a cidade e a ID de suporte do escritório que você deseja discutir. Se isso estiver desligado, os engenheiros da Microsoft com os que você está discutindo sua conectividade de rede não poderão exibir nenhuma dessas informações. Habilitar essa configuração só compartilha dados futuros a partir do dia após habilita-los.

## <a name="csv-import-for-lan-subnet-office-locations"></a>Importação de CSV para locais de office de sub-rede lan

Para a identificação do office de sub-rede lan, você precisa adicionar cada local com antecedência. Em vez de adicionar locais de escritório individuais na guia **Locais,** você pode importá-los de um arquivo CSV. Você pode ser capaz de obter esses dados de outros locais que os armazenou, como o Painel de Qualidade de Chamada ou Sites e Serviços do Active Directory

No arquivo CSV, um local da cidade descoberto mostra a coluna userEntered como em branco, e um local de escritório adicionado manualmente mostra como 1.

1. Na janela _Conectividade principal para Microsoft 365,_ clique na guia **Locais.**

1. Clique no **botão Importar** logo acima da lista de locais. O **sobrevoo Importar locais** do office aparecerá.

   > [!div class="mx-imgBorder"]
   > ![Mensagem de importação CSV](../media/m365-mac-perf/m365-mac-perf-import.png)

1. Clique no link Baixar locais atuais **do office (.csv)** para exportar a lista de locais atuais para um arquivo CSV e salvá-lo no disco rígido local. Isso fornecerá um CSV formatado corretamente com títulos de coluna aos quais você pode adicionar locais. Você pode deixar os locais exportados existentes como estão; eles não serão duplicados quando você importar o CSV atualizado. Se você quiser alterar o endereço de um local existente, ele será atualizado quando você importar o CSV. Não é possível alterar o endereço de uma cidade descoberta.

1. Abra o CSV e adicione seus locais preenchendo os campos a seguir em uma nova linha para cada local que você deseja adicionar. Deixar todos os outros campos em branco; os valores que você inserir em outros campos serão ignorados.

   1. **userEntered** (obrigatório): deve ser 1 para um novo local de escritório da Sub-rede lan que está sendo adicionado
   1. **Nome** (obrigatório): o nome do local do escritório
   1. **Endereço** (obrigatório): o endereço físico do escritório
   1. **Latitude** (opcional): preenchido de Bing mapas do endereço se estiver em branco
   1. **Longitude** (opcional): preenchido Bing mapas do endereço em branco
   1. Egress endereço IP varia **de 1** a 5 (opcional): para cada intervalo, insira o nome do circuito seguido de uma lista separada por espaço de endereços CIDR IPv4 ou IPv6 válidos. Esses valores são usados para diferenciar vários locais de escritório onde você usa os mesmos Endereços IP da sub-rede lan. Egress Todos os intervalos de endereço IP devem ter /24 tamanho de rede e /24 não está incluído na entrada.
   1. **LanIps** (obrigatório): listar os intervalos de sub-rede lan em uso neste local do escritório. As IDs de sub-rede da LAN precisam ter um tamanho de rede CIDR incluído, onde o tamanho da rede pode estar entre /8 e /29. Vários intervalos de sub-rede lan podem ser separados por uma vírgula ou um ponto e vírgula.
   
1. Quando tiver adicionado seus locais de escritório e salvo o  arquivo, clique no botão **Procurar** ao lado do Upload campo concluído e selecione o arquivo CSV salvo.

1. O arquivo será validado automaticamente. Se houver erros de validação, você verá a mensagem de erro: Há alguns _erros no arquivo de importação. Revise os erros, corrija o arquivo de importação e tente novamente._ Clique no link **Abrir detalhes de erro** para obter uma lista de erros específicos de validação de campo.

   > [!div class="mx-imgBorder"]
   > ![Mensagem de erro de importação CSV](../media/m365-mac-perf/m365-mac-perf-import-error.png)

1. Se não houver erros no arquivo, você verá a mensagem: _O relatório está pronto. Localizações x encontradas para adicionar e x locais a ser atualizados._ Clique no **botão Importar** para carregar o CSV.

   > [!div class="mx-imgBorder"]
   > ![Mensagem pronta de importação de CSV](../media/m365-mac-perf/m365-mac-perf-import-ready.png)

## <a name="faq"></a>Perguntas frequentes

### <a name="what-is-a-microsoft-365-service-front-door"></a>O que é uma Microsoft 365 de serviço?

A Microsoft 365 de serviço é um ponto de entrada na rede global da Microsoft, onde os clientes Office e serviços encerram sua conexão de rede. Para uma conexão de rede ideal Microsoft 365, é recomendável que sua conexão de rede seja encerrada na porta Microsoft 365 porta frontal mais próxima.

>[!NOTE]
>Microsoft 365 porta da frente do serviço não tem relação direta com o produto do Serviço de Porta Frontal do Azure disponível no marketplace do Azure.

### <a name="what-is-an-optimal-microsoft-365-service-front-door"></a>O que é uma porta Microsoft 365 de serviço ideal?

Uma porta Microsoft 365 de serviço ideal é a que está mais próxima da saída da rede, geralmente em sua cidade ou área de metro. Use a Microsoft 365 de teste de conectividade [(visualização)](office-365-network-mac-perf-onboarding-tool.md) para determinar o local da porta da frente de serviço Microsoft 365 serviço em uso e a porta de entrada de serviço ideal. Se a ferramenta determinar que a porta da frente em uso é ideal, você está se conectando idealmente à rede global da Microsoft.

### <a name="what-is-an-internet-egress-location"></a>O que é um local de saída da Internet?

O local de saída da Internet é o local onde o tráfego de rede sai da rede corporativa e se conecta à Internet. Isso também é identificado como o local onde você tem um dispositivo NAT (Conversão de Endereço de Rede) e geralmente onde você se conecta a um Provedor de Serviços da Internet (ISP). Se você vir uma longa distância entre sua localização e seu local de saída da Internet, isso pode indicar um backhaul WAN significativo.

### <a name="what-license-is-needed-for-this-capability"></a>Qual licença é necessária para esse recurso?

Você exige uma licença que fornece acesso ao Microsoft 365 de administração.

## <a name="related-topics"></a>Tópicos relacionados

[Microsoft 365 de rede (visualização)](office-365-network-mac-perf-insights.md)

[Microsoft 365 de rede (visualização)](office-365-network-mac-perf-score.md)

[Microsoft 365 de teste de conectividade (visualização)](office-365-network-mac-perf-onboarding-tool.md)

[Microsoft 365 Serviços de Localização de Conectividade de Rede (visualização)](office-365-network-mac-location-services.md)
