---
title: Etapa 2. Rede ideal para locatários do Microsoft 365 para empresas
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
- m365solution-tenantmanagement
ms.custom:
- Ent_Solutions
description: Otimize o acesso à rede para seus locatários do Microsoft 365.
ms.openlocfilehash: 1e57911a6e8c51af3ae00ff0f9053bf9273e0e17
ms.sourcegitcommit: 99a7354e6a6b4d9d5202674ef57852d52a43fef6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/20/2021
ms.locfileid: "49908454"
---
# <a name="step-2-optimal-networking-for-your-microsoft-365-for-enterprise-tenants"></a>Etapa 2. Rede ideal para locatários do Microsoft 365 para empresas

O Microsoft 365 para empresas inclui aplicativos de produtividade na nuvem, como o Teams e o Exchange Online, e o Microsoft Intune, juntamente com muitos serviços de identidade e segurança do Microsoft Azure. Todos esses serviços baseados em nuvem dependem da segurança, do desempenho e da confiabilidade das conexões de dispositivos cliente em sua rede local ou em qualquer local na Internet. 

Para otimizar o acesso à rede para seu locatário, você precisa:

- Otimize o caminho entre seus usuários locais e o local mais próximo da Rede Global da Microsoft.
- Otimize o acesso à Rede Global da Microsoft para seus usuários remotos que estão usando uma solução VPN de acesso remoto.
- Use o Network Insights para projetar o perímetro de rede para seus locais de escritório.
- Otimize o acesso a ativos específicos hospedados em sites do SharePoint com a CDN do Office 365.
- Configure dispositivos de borda de rede e proxy para ignorar o processamento do tráfego confiável do Microsoft 365 com a lista de pontos de extremidade e automatizar a atualização da lista à medida que as alterações são feitas.

## <a name="enterprise-on-premises-workers"></a>Funcionários locais corporativos

Para redes corporativas, você deve otimizar a experiência do usuário final habilitando o acesso de rede de melhor desempenho entre clientes e os pontos de extremidade mais próximos do Microsoft 365. A qualidade da experiência do usuário final está diretamente relacionada ao desempenho e à capacidade de resposta do aplicativo que o usuário está usando. Por exemplo, o Microsoft Teams depende de baixa latência para que as chamadas telefônicas, conferências e colaborações de tela compartilhada do usuário não sejam falhas.

O principal objetivo no design de rede deve ser minimizar a latência reduzindo o tempo de ida e volta (RTT) dos dispositivos cliente para a Rede Global da Microsoft, o backbone de rede pública da Microsoft que interconecta todos os datacenters da Microsoft com baixa latência, pontos de entrada de aplicativos em nuvem de alta disponibilidade, conhecidos como portas frontal, espalhados pelo mundo.

Aqui está um exemplo de uma rede corporativa tradicional.

![Uma rede corporativa tradicional com acesso central à Internet](../media/tenant-management-overview/tenant-management-networking-traditional.png)

Nesta ilustração, as filiais se conectam a um escritório central por meio de dispositivos wan e backbone de WAN. O acesso à Internet é por meio de um dispositivo proxy ou de segurança na borda de rede do escritório central e de um provedor de serviços de Internet (ISP). Na Internet, a Rede Global da Microsoft tem uma série de portas frontales em regiões ao redor do mundo. As organizações também podem usar locais intermediários para processamento adicional de pacotes e segurança para o tráfego. O locatário do Microsoft 365 de uma organização está localizado na Rede Global da Microsoft.

Os problemas com essa configuração para os serviços de nuvem do Microsoft 365 são:

- Para usuários em filiais, o tráfego é enviado para portas frontales não locais, aumentando a latência.
- O envio de tráfego para locais intermediários cria hairpins de rede que executam processamento de pacotes duplicado em tráfego confiável, aumentando a latência.
- Os dispositivos de borda de rede executam processamento de pacotes não éneido e duplicado em tráfego confiável, aumentando a latência.

Otimizar o desempenho de rede do Microsoft 365 não precisa ser complicado. Você pode obter o melhor desempenho possível seguindo alguns princípios principais:

- Identifique o tráfego de rede do Microsoft 365, que é um tráfego confiável destinado aos serviços de nuvem da Microsoft.
- Permitir a saída de filial local do tráfego de rede do Microsoft 365 para a Internet de cada local onde os usuários se conectam ao Microsoft 365.
- Evite hairpins de rede.
- Permitir que o tráfego do Microsoft 365 ignore proxies e dispositivos de inspeção de pacotes.

Se você implementar esses princípios, obterá uma rede corporativa otimizada para o Microsoft 365.

![Uma rede corporativa otimizada para o Microsoft 365](../media/tenant-management-overview/tenant-management-networking-optimized.png)

Nesta ilustração, as filiais têm sua própria conexão com a Internet por meio de um dispositivo WAN definido por software (SDWAN), que envia tráfego confiável do Microsoft 365 para a porta de entrada mais próxima regionalmente. No escritório central, o tráfego confiável do Microsoft 365 ignora a segurança ou o dispositivo proxy e os dispositivos intermediários não são mais usados.

Veja como a configuração otimizada resolve os problemas de latência de uma rede corporativa tradicional:

- O tráfego confiável do Microsoft 365 ignora o backbone da WAN e é enviado para portas frontales locais para todos os escritórios, diminuindo a latência.
- Hairpins de rede que executam processamento de pacotes duplicado são ignorados para o tráfego confiável do Microsoft 365, diminuindo a latência.
- Os dispositivos de borda de rede que executam o processamento de pacotes não éneido e duplicado são ignorados para o tráfego confiável do Microsoft 365, diminuindo a latência.

Para saber mais, confira a visão geral da conectividade de rede do [Microsoft 365.](../enterprise/microsoft-365-networking-overview.md)

## <a name="remote-workers"></a>Trabalhadores remotos

Se os seus funcionários remotos estiverem usando um cliente VPN tradicional para obter acesso remoto à rede da organização, verifique se o cliente VPN possui suporte para túnel dividido. Sem o túnel dividido, todo o seu tráfego de trabalho remoto é enviado pela conexão VPN, onde deve ser encaminhado para os dispositivos de borda da sua organização, processado e enviado na Internet. Veja um exemplo.

![Tráfego de rede de clientes VPN sem túnel dividido](../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-before-tunneling.png)

Nesta ilustração, o tráfego do Microsoft 365 deve seguir uma rota indireta através de sua organização, que pode ser encaminhada para uma porta frontal da Rede Global da Microsoft distante do local físico do cliente VPN. Esse caminho indireto adiciona latência ao tráfego da rede e diminui o desempenho geral. 

Com o túnel dividido, você pode configurar seu cliente VPN para impedir que tipos específicos de tráfego sejam enviados à rede da organização pela conexão VPN.

Para otimizar o acesso aos recursos de nuvem do Microsoft 365, configure seus clientes VPN de túnel dividido para excluir o tráfego nos pontos de extremidade do Microsoft 365 da categoria **Otimizar** pela conexão VPN. Para saber mais, confira as categorias [](../enterprise/microsoft-365-vpn-implement-split-tunnel.md#implement-vpn-split-tunneling) de ponto de extremidade do [Office 365](../enterprise/microsoft-365-network-connectivity-principles.md#new-office-365-endpoint-categories) e as listas de pontos de extremidade de categoria Otimizar para túnel dividido.

Este é o fluxo de tráfego resultante para o túnel dividido, no qual a maior parte do tráfego para aplicativos de nuvem do Microsoft 365 ignora a conexão VPN.

![Tráfego de rede de clientes VPN com túnel dividido](../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-after-tunneling.png)

Nesta ilustração, o cliente VPN envia e recebe o tráfego crucial do serviço de nuvem do Microsoft 365 diretamente pela Internet e para a porta frontal mais próxima da Rede Global da Microsoft.

Para obter mais informações e orientações, confira [Otimizar a conectividade do Office 365 para usuários remotos usando o túnel dividido da VPN](../enterprise/microsoft-365-vpn-split-tunnel.md).

## <a name="using-network-insights-preview"></a>Usando o Network Insights (visualização)

As informações de rede são métricas de desempenho coletadas do locatário do Microsoft 365 que ajudam você a projetar perímetros de rede para seus locais de escritório. Cada visão fornece detalhes ao vivo sobre as características de desempenho de um problema específico para cada local geográfico onde os usuários locais estão acessando seu locatário.

Há duas percepções de rede no nível do locatário que podem ser mostradas para o locatário:

- [Conexões amostradas do Exchange impactadas por problemas de conectividade](../enterprise/office-365-network-mac-perf-insights.md#exchange-sampled-connections-impacted-by-connectivity-issues)
- [Conexões amostradas do SharePoint impactadas por problemas de conectividade](../enterprise/office-365-network-mac-perf-insights.md#sharepoint-sampled-connections-impacted-by-connectivity-issues)

Estas são as informações de rede específicas para cada local de escritório:

- [Saída de rede em backhauled](../enterprise/office-365-network-mac-perf-insights.md#backhauled-network-egress)
- [Melhor desempenho detectado para clientes próximos a você](../enterprise/office-365-network-mac-perf-insights.md#better-performance-detected-for-customers-near-you)
- [Uso de uma porta frontal de serviço do Exchange Online não ideal](../enterprise/office-365-network-mac-perf-insights.md#use-of-a-non-optimal-exchange-online-service-front-door)
- [Uso de uma porta de frente de serviço do SharePoint Online não ideal](../enterprise/office-365-network-mac-perf-insights.md#use-of-a-non-optimal-sharepoint-online-service-front-door)
- [Baixa velocidade de download da porta frontal do SharePoint](../enterprise/office-365-network-mac-perf-insights.md#low-download-speed-from-sharepoint-front-door)
- [Saída de rede ideal do usuário da China](../enterprise/office-365-network-mac-perf-insights.md#china-user-optimal-network-egress)

>[!IMPORTANT]
>Insights de rede, recomendações de desempenho e avaliações no Centro de administração do Microsoft 365 estão atualmente no status de visualização. Ele só está disponível para locatários do Microsoft 365 que foram inscritos no programa de visualização de recursos.

Para saber mais, confira [o Microsoft 365 Network Insights.](../enterprise/office-365-network-mac-perf-insights.md)

## <a name="sharepoint-performance-with-the-office-365-cdn"></a>Desempenho do SharePoint com a CDN do Office 365

Uma CDN (Rede de Distribuição de Conteúdo) baseada em nuvem permite reduzir o tempo de carregamento, economizar largura de banda e velocidade de resposta. Uma CDN melhora o desempenho armazenando em cache ativos estáticos, como arquivos gráficos ou de vídeo, mais próximos dos navegadores que os solicitam, o que ajuda a acelerar os downloads e reduzir a latência. Você pode usar a Rede de Distribuição de Conteúdo (CDN) interna do Office 365, incluída no SharePoint no Microsoft 365 E3 e E5, para hospedar ativos estáticos para fornecer melhor desempenho para suas páginas do SharePoint.

A CDN do Office 365 é composta por várias CDNs que permitem que você hospede ativos estáticos em vários locais ou _origens_ e sirva-os de redes globais de alta velocidade. Dependendo do tipo de conteúdo que você deseja hospedar na CDN  do Office 365, você pode adicionar origens públicas,  origens privadas ou ambas.

Quando implantada e configurada, a CDN do Office 365 carrega ativos de origens públicas e privadas e os disponibiliza para acesso rápido a usuários localizados na Internet.

![CDN do Office 365 implantada para usuários](../media/O365-CDN/o365-cdn-flow-transparent.svg "CDN do Office 365 implantada para usuários")

Para saber mais, confira [Usar a CDN do Office 365 com o SharePoint Online.](../enterprise/use-microsoft-365-cdn-with-spo.md)

## <a name="automated-endpoint-listing"></a>Listagem automatizada de pontos de extremidade

Para que seus clientes locais, dispositivos de borda e serviços de análise de pacotes baseados em nuvem ignorem o processamento de tráfego confiável do Microsoft 365, você deve configurá-los com o conjunto de pontos de extremidade (intervalos de endereços IP e nomes DNS) correspondentes aos serviços do Microsoft 365. Esses pontos de extremidade podem ser configurados manualmente em firewalls e outros dispositivos de segurança de borda, arquivos PAC para computadores cliente para ignorar proxies ou dispositivos SD-WAN em filiais. No entanto, os pontos de extremidade mudam ao longo do tempo, exigindo manutenção manual contínua das listas de pontos de extremidade nesses locais.

Para automatizar a listagem e o gerenciamento de alterações para os pontos de extremidade do Microsoft 365 em seus arquivos PAC do cliente e dispositivos de rede, use o endereço IP do [Office 365](../enterprise/microsoft-365-ip-web-service.md)e o serviço Web baseado em REST de URL. Esse serviço ajuda a identificar e diferenciar melhor o tráfego de rede do Microsoft 365, facilitando a avaliação, a configuração e a se manter atualizado com as alterações mais recentes.

Você pode usar o PowerShell, Python ou outras linguagens para determinar as alterações nos pontos de extremidade ao longo do tempo e configurar seus arquivos PAC e dispositivos de rede de borda.

O processo básico é:

1. Use o endereço IP do Office 365 e o serviço Web de URL e o mecanismo de configuração de sua escolha para configurar seus arquivos PAC e dispositivos de rede com o conjunto atual de pontos de extremidade do Microsoft 365.
2. Execute uma recorrente diária para verificar se há alterações nos pontos de extremidade ou use um método de notificação.
3. Quando as alterações são detectadas, regenere e redistribua o arquivo PAC para computadores cliente e faça as alterações em seus dispositivos de rede.

Para saber mais, confira o endereço [IP do Office 365 e o serviço Web de URL.](../enterprise/microsoft-365-ip-web-service.md)

## <a name="results-of-step-2"></a>Resultados da Etapa 2

Para o locatário do Microsoft 365 com rede ideal, você determinou:

- Como otimizar o desempenho da rede para usuários locais adicionando conexões com a Internet a todas as filiais e eliminando hairpins de rede.
- Como implementar a listagem automatizada de pontos de extremidade confiáveis para seus arquivos PAC baseados no cliente e seus dispositivos e serviços de rede, incluindo atualizações contínuas (mais adequadas para redes corporativas).
- Como dar suporte ao acesso de funcionários remotos a recursos locais.
- Como usar o Network Insights
- Como implantar a CDN do Office 365.

Aqui está um exemplo de uma organização corporativa e seu locatário com rede ideal.

![Exemplo de um locatário com rede ideal](../media/tenant-management-overview/tenant-management-tenant-build-step2.png)

[Ver uma versão maior desta imagem](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/tenant-management-overview/tenant-management-tenant-build-step2.png)

Nesta ilustração, o locatário dessa organização corporativa tem:

- Acesso à Internet local para cada filial com um dispositivo SDWAN que encaminha o tráfego confiável do Microsoft 365 para uma porta frontal local.
- Sem hairpins de rede.
- Dispositivos de borda proxy e de segurança do escritório central que encaminham o tráfego confiável do Microsoft 365 para uma porta frontal local.

## <a name="ongoing-maintenance-for-optimal-networking"></a>Manutenção contínua para rede ideal

Em uma base contínua, talvez seja necessário:

- Atualize seus dispositivos de borda e implantou arquivos PAC para alterações nos pontos de extremidade ou verifique se o processo automatizado funciona corretamente.
- Gerencie seus ativos na CDN do Office 365.
- Atualize a configuração de túnel dividido em seus clientes VPN para alterações nos pontos de extremidade.

## <a name="next-step"></a>Próxima etapa

[![Etapa 3. Sincronizar suas identidades e impor logins seguros](../media/tenant-management-overview/tenant-management-step-grid-identity.png)](tenant-management-identity.md)

Continue com [a identidade](tenant-management-identity.md) para sincronizar suas contas e grupos locais e impor logins de usuário seguros.
