---
title: Recomendações de desempenho de rede no centro de administração do Microsoft 365 (versão prévia)
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 04/21/2020
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
description: Visão geral das recomendações de desempenho de rede no centro de administração do Microsoft 365 (versão prévia)
ms.openlocfilehash: 03064f4919949659d7fb272c96b540c74ac3aca8
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46695321"
---
# <a name="network-performance-recommendations-in-the-microsoft-365-admin-center-preview"></a>Recomendações de desempenho de rede no centro de administração do Microsoft 365 (versão prévia)

O centro de administração do Microsoft 365 agora inclui métricas de desempenho ao vivo coletadas do seu locatário do Microsoft 365 e disponíveis para visualização apenas por usuários administrativos em seu locatário. as **informações de rede e as recomendações de desempenho** e as avaliações de **rede** são exibidas no centro de administração do Microsoft 365 em <https://portal.microsoft.com/adminportal/home#/networkperformance> . Você pode encontrar a página no painel de navegação em **Health | Desempenho da rede**.

![Página desempenho da rede](../media/m365-mac-perf/m365-mac-perf-page-nav.png)

Ao navegar pela primeira vez para a página desempenho da rede, você verá um painel Visão geral contendo um mapa de desempenho de rede global, uma avaliação de rede com escopo para o locatário inteiro e uma lista de problemas atuais. Na visão geral, você pode fazer uma busca detalhada para exibir as métricas e os problemas específicos de desempenho da rede por local. Para obter mais informações, consulte [Network Performance Overview no centro de administração do Microsoft 365](#network-performance-overview-in-the-microsoft-365-admin-center).

## <a name="pre-requisites-for-connectivity-measurements-to-appear"></a>Pré-requisitos para que as medições de conectividade apareçam

Para que as medições de conectividade apareçam, você deve ter pelo menos dois computadores executando em cada local do escritório que ofereçam suporte aos pré-requisitos. O cliente de sincronização do OneDrive for Business versão 19,232 ou superior deve estar instalado em cada computador. Para obter mais informações, consulte as [notas de versão do onedrive](https://support.office.com/article/onedrive-release-notes-845dcf18-f921-435e-bf28-4e24b95e5fc0).

O serviço de localização do Windows deve ser consentido nas máquinas. Você pode testar isso executando o aplicativo **Maps** e localizando-se. Ela pode ser habilitada em um único computador com o local de privacidade **das configurações**,  ->  **Privacy**  ->  **Location** onde a configuração "permitir que os aplicativos acessem seu local" deve estar habilitada. O consentimento dos serviços de localização do Windows pode ser implantado em computadores usando o MDM ou a política de grupo com a configuração _LetAppsAccessLocation_.

As máquinas devem ter redes Wi-Fi, em vez de um cabo Ethernet. As máquinas com um cabo Ethernet não têm informações precisas sobre o local.

Os exemplos de medidas e locais do Office devem começar a aparecer 24 horas após os pré-requisitos terem sido atendidos.

## <a name="how-do-i-use-this-information"></a>Como usar essas informações?

Os **insights de rede**, suas recomendações de desempenho relacionadas e avaliações de rede têm a finalidade de ajudar na criação de perímetros de rede para seus locais do Office. Cada informação fornece detalhes ao vivo sobre as características de desempenho para um problema comum específico para cada localização geográfica onde os usuários acessam seu locatário. **Recomendações de desempenho** para cada percepção de rede oferecem alterações de design específicas de arquitetura de rede que você pode fazer para melhorar a experiência do usuário relacionada à conectividade de rede do Microsoft 365. A avaliação de rede mostra como a conectividade de rede impacta a experiência do usuário, permitindo a comparação de diferentes conexões de rede de local de usuário.

As **avaliações de rede** separam uma agregação de muitas métricas de desempenho de rede em um instantâneo da integridade da rede corporativa, representado por um valor de pontos de 1-100. As avaliações de rede têm o escopo para o locatário inteiro e para cada localização geográfica a partir da qual os usuários se conectam ao seu locatário, fornecendo aos administradores da Microsoft 365 uma maneira fácil de obter instantaneamente um Gestalt da integridade da rede da empresa e rapidamente se aprofundam em um relatório detalhado de qualquer local do escritório global.

As empresas complexas com vários locais do Office e arquiteturas de perímetro de rede não triviais podem se beneficiar dessas informações durante a integração inicial com o Microsoft 365 ou para corrigir problemas de desempenho de rede descobertos com o aumento do uso. Em geral, isso não é necessário para pequenas empresas que usam o Microsoft 365 ou qualquer empresa que já tenha conectividade de rede simples e direta. Empresas com mais de 500 usuários e vários locais do Office são mais beneficiadas.

>[!IMPORTANT]
>Os insights de rede, as recomendações de desempenho e as avaliações no centro de administração do Microsoft 365 estão atualmente no status de visualização e só estão disponíveis para os locatários do Microsoft 365 que foram registrados no programa de visualização de recurso.

## <a name="enterprise-network-connectivity-challenges"></a>Desafios de conectividade de rede corporativa

![Rede de cliente para nuvem](../media/m365-mac-perf/m365-mac-perf-first-last-mile.png)

Muitas empresas têm configurações de perímetro de rede que cresceram com o passar do tempo e foram basicamente projetadas para acomodar o acesso ao site da Internet para funcionários, onde a maioria dos sites não é conhecida e não é confiável. O foco predominante e necessário é evitar ataques de malware e pesca desses sites desconhecidos. Essa estratégia de configuração de rede, embora útil para fins de segurança, pode levar à degradação do desempenho do usuário do Microsoft 365 e da experiência do usuário.

## <a name="how-we-can-solve-these-challenges"></a>Como podemos resolver esses desafios

As empresas podem melhorar a experiência geral do usuário e proteger seu ambiente, seguindo os [princípios de conectividade do Office 365](https://aka.ms/pnc) e usando o recurso de desempenho de rede do centro de administração do Microsoft 365. Na maioria dos casos, seguir esses princípios gerais terá um impacto positivo significativo sobre a latência do usuário final, a confiabilidade do serviço e o desempenho geral do Microsoft 365.

Às vezes, a Microsoft é solicitada a investigar problemas de desempenho da rede com o Microsoft 365 para clientes de grandes empresas, e essas muitas vezes têm uma causa raiz relacionada à infraestrutura de egresso da rede do cliente. Quando uma causa raiz comum de um problema de perímetro de rede do cliente for encontrada, procuraremos a identificação de medidas de teste simples que a identificam. Um teste com um limite de medida que identifica um problema específico é importante porque podemos testar a mesma medição em qualquer local, diga se essa causa raiz está presente e compartilhe-a como uma percepção de rede com o administrador.

Alguns insights de rede simplesmente indicarão um problema que precisa de investigação adicional. Uma percepção de rede onde temos testes suficientes para mostrar uma ação de correção específica para corrigir a causa raiz é listada como uma **ação recomendada**. Essas recomendações, com base em métricas de Live, que revelam valores que estão fora de um limite pré-determinado, são muito mais valiosas que o Conselho geral de práticas recomendadas, uma vez que eles são específicos para seu ambiente e mostrarão o aprimoramento real depois que as alterações recomendadas forem feitas.

## <a name="network-performance-overview-in-the-microsoft-365-admin-center"></a>Visão geral do desempenho da rede no centro de administração do Microsoft 365

A Microsoft tem medidas de rede existentes de vários clientes da Web e da área de trabalho do Office que dão suporte à operação do Microsoft 365. Essas medidas estão sendo usadas agora para fornecer insights de design de arquitetura de rede e uma avaliação de desempenho de rede que são mostrados na página **desempenho da rede** no centro de administração do Microsoft 365.

Por padrão, as informações aproximadas de local associadas às medições de rede identificam a cidade onde os dispositivos cliente estão localizados. A avaliação de rede em cada local é mostrada com cores e o número relativo de usuários em cada local é representado pelo tamanho do círculo.

![Mapa de visão geral de insights de rede](../media/m365-mac-perf/m365-mac-perf-overview-map.png)

A página Visão geral também mostra a avaliação de rede para o cliente como uma média ponderada em todos os locais do Office.

![Avaliação de rede](../media/m365-mac-perf/m365-mac-perf-overview-score.png)

## <a name="specific-office-location-network-performance-summary-and-insights"></a>Resumo de desempenho da rede de local específico do Office e insights

Selecionar um local do Office abre uma página de resumo específica do local mostrando detalhes da saída da rede que foi identificada por meio de medidas para esse local do escritório.

![Detalhes da Network insights por local](../media/m365-mac-perf/m365-mac-perf-locations-plan-overview.png)

A página de Resumo de local do Office também mostra a avaliação de rede do local, o histórico de avaliação de rede, uma comparação entre a avaliação desse local e outros clientes na mesma cidade e uma lista de ideias e recomendações específicas que você pode tomar para melhorar o desempenho e a confiabilidade da rede. Os locais com recomendações específicas também podem incluir uma melhoria de latência potencial estimada.

As comparações entre os clientes na mesma cidade têm como base a expectativa de que todos os clientes tenham acesso igual aos provedores de serviços de rede, à infraestrutura de telecomunicações e aos pontos de presença da rede Microsoft próximos.

![Locais do insights de rede](../media/m365-mac-perf/m365-mac-perf-locations.png)

A guia detalhes na página local do Office mostra os resultados de medição específicos que foram usados para surgir com as ideias, recomendações e avaliação de rede. Isso é fornecido para que os engenheiros de rede possam validar as recomendações e o fator em qualquer restrição ou especificações em seu ambiente.

![Detalhes específicos do local](../media/m365-mac-perf/m365-mac-perf-locations-plan-details-all.png)

Para clientes que desejam melhorar a precisão de métricas e recomendações específicas de local, permitimos mais informações específicas a serem inseridas. Isso pode reduzir as aproximações inerentes às informações de local disponíveis para medições de rede. Para editar o endereço de um local específico do Office, <functionality not there yet> .

## <a name="import-undiscovered-office-locations"></a>Importar locais do Office não descobertos

A guia **locais** de desempenho da rede mostra uma lista de locais descobertos automaticamente da telemetria de rede. Esses locais do Office são cidades descobertas. Você pode adicionar manualmente mais locais específicos dentro dessas cidades se elas não aparecerem automaticamente na lista importando-as de um arquivo CSV. Se os locais do Office não aparecerem, você deve solucionar o problema de como as medições da rede não aparecem em vez de apenas adicionar o local aqui. Você também pode atualizar o valor de endereço de locais existentes do Office.

No arquivo CSV o local da cidade descoberto aA é rotulado como **cidade**, e um local do escritório adicionado manualmente é um **local**rotulado.

1. Na janela principal _conectividade com o Microsoft 365_ , clique na guia **locais** .
1. Clique no botão **importar** , logo acima da lista locais. O submenu **importar locais do Office** aparecerá.

   ![Mensagem de erro de importação de CSV](../media/m365-mac-perf/m365-mac-perf-import.png)

1. Clique no link **baixar locais atuais do Office (. csv)** para exportar a lista de locais atuais para um arquivo CSV e salvá-lo no disco rígido local. Isso lhe fornecerá um CSV formatado corretamente para o qual você pode adicionar locais. Você pode deixar os locais exportados como estão; Eles não serão duplicados quando você importar o CSV atualizado. Se você quiser alterar o endereço de um local existente, ele será atualizado quando você importar o CSV. Não é possível alterar o endereço de uma cidade descoberta.
1. Abra o CSV e adicione seus locais preenchendo os campos a seguir em uma nova linha para cada local que você deseja adicionar. Deixe todos os outros campos em branco; os valores inseridos em outros campos serão ignorados.
   1. **Endereço** (obrigatório): o endereço físico do Office
   1. **Latitude** (opcional): preenchido da pesquisa de mapas do Bing se estiver em branco
   1. **Longitude** (opcional): preenchida da pesquisa de mapas do Bing se estiver em branco
   1. **Intervalos de endereços IP de egresso 1-5** (opcional): para cada intervalo, insira o nome do circuito seguido por uma lista separada por espaço de endereços válidos IPv4 ou IPv6. Esses valores são usados somente quando você habilita a integração do SDWAN para um determinado local do escritório.
1. Após adicionar os locais do Office e salvar o arquivo, clique no botão **procurar** ao lado do campo **carregar o concluído** e selecione o arquivo CSV salvo.
1. O arquivo será validado automaticamente. Se houver erros de validação, você verá a mensagem de erro _há alguns erros no arquivo de importação. Revise os erros, corrija o arquivo de importação e tente novamente._ Clique no link **abrir detalhes do erro** para obter uma lista de erros de validação de campo específicos.

   ![Mensagem de erro de importação de CSV](../media/m365-mac-perf/m365-mac-perf-import-error.png)

1. Se não houver erros no arquivo, você verá a mensagem _de que o relatório está pronto. Encontrados x locais para adicionar e x locais para atualizar._ Clique no botão **importar** para carregar o CSV.

   ![Mensagem de importação pronta para CSV](../media/m365-mac-perf/m365-mac-perf-import-ready.png)

## <a name="faq"></a>PERGUNTAS FREQÜENTES

### <a name="what-is-a-microsoft-365-service-front-door"></a>O que é uma porta frontal de serviço do Microsoft 365?

O Microsoft 365 Service front door é um ponto de entrada na rede global da Microsoft, onde os clientes e serviços do Office terminam suas conexões de rede. Para uma conexão de rede ideal para o Microsoft 365, é recomendável que sua conexão de rede seja encerrada na porta frontal mais próxima do Microsoft 365 em sua cidade ou metro.

>[!NOTE]
>O Microsoft 365 Service front door não tem relação direta com o produto de serviço do Azure front door disponível no Azure Marketplace.

### <a name="what-is-an-optimal-microsoft-365-service-front-door"></a>Qual é a melhor porta de serviço do Microsoft 365?

Uma das melhores portas de serviço do Microsoft 365 é aquela mais próxima à sua rede de egresso, geralmente na cidade ou na área de metrô. Use o [teste de conectividade do microsoft 365](office-365-network-mac-perf-onboarding-tool.md) para determinar o local da porta de entrada do Microsoft 365 Service e da porta frontal de serviço ideal. Se a ferramenta determina que sua porta frontal de uso é ideal, então, você está se conectando de forma ideal à rede global da Microsoft.

### <a name="what-is-an-internet-egress-location"></a>O que é um local de egresso na Internet?

O local de egresso de Internet é o local onde o tráfego de rede sai da rede corporativa e se conecta à Internet. Isso também é identificado como o local onde você tem um dispositivo NAT (conversão de endereço de rede) e, em geral, onde você se conecta com um provedor de serviços de Internet (ISP). Se você vir uma longa distância entre o local e o local de saída da Internet, isso poderá indicar um backhaul WAN significativo.

## <a name="related-topics"></a>Tópicos relacionados

[Microsoft 365 Network insights (versão prévia)](office-365-network-mac-perf-insights.md)

[Avaliação de rede do Microsoft 365 (versão prévia)](office-365-network-mac-perf-score.md)

[Teste de conectividade do Microsoft 365 no centro de administração do M365 (versão prévia)](office-365-network-mac-perf-onboarding-tool.md)

[Serviços de local de conectividade de rede da Microsoft 365 (versão prévia)](office-365-network-mac-location-services.md)
