---
title: Avaliando a conectividade de rede do Microsoft 365
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 6/23/2020
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: 64b420ef-0218-48f6-8a34-74bb27633b10
description: Microsoft 365 foi projetado para permitir que clientes em todo o mundo se conectem ao serviço usando uma conexão com a Internet. À medida que o serviço evolui, a segurança, o desempenho e a confiabilidade da Microsoft 365 são aprimoradas com base nos clientes que usam a Internet para estabelecer uma conexão com o serviço.
ms.openlocfilehash: 4d80bdf5642b2456ac8293291c720429f7f18fb1
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905471"
---
# <a name="assessing-microsoft-365-network-connectivity"></a>Avaliando a conectividade de rede do Microsoft 365

*Esse artigo se aplica ao Microsoft 365 Enterprise e ao Office 365 Enterprise.*

Microsoft 365 foi projetado para permitir que clientes em todo o mundo se conectem ao serviço usando uma conexão com a Internet. À medida que o serviço evolui, a segurança, o desempenho e a confiabilidade da Microsoft 365 são aprimoradas com base nos clientes que usam a Internet para estabelecer uma conexão com o serviço.
  
Os clientes que planejam usar Microsoft 365 devem avaliar suas necessidades de conectividade de Internet existentes e previstas como parte do projeto de implantação. Para implantações de classe empresarial, a conectividade de internet confiável e dimensionada adequadamente é uma parte essencial do consumo Microsoft 365 recursos e cenários.
  
As avaliações de rede podem ser realizadas por muitas pessoas e organizações diferentes, dependendo de seu tamanho e preferências. O escopo de rede da avaliação também pode variar dependendo de onde você está no processo de implantação. Para ajudá-lo a entender melhor o que é necessário para executar uma avaliação de rede, produzimos um guia de avaliação de rede para ajudá-lo a entender as opções disponíveis para você. Essa avaliação determinará quais etapas e recursos precisam ser adicionados ao projeto de implantação para permitir que você adote Microsoft 365.
  
Uma avaliação abrangente de rede fornecerá possíveis soluções para desafios de design de rede, juntamente com detalhes de implementação. Algumas avaliações de rede mostrarão que a conectividade de rede ideal Microsoft 365 pode ser acomodada com pequenas alterações de configuração ou design para a infraestrutura de saída de rede e internet existente.

Algumas avaliações indicarão que a conectividade de rede Microsoft 365 exigirá investimentos adicionais em componentes de rede. Por exemplo, redes corporativas que abrangem filiais e várias regiões geográficas podem exigir investimentos em soluções SD-WAN ou infraestrutura de roteamento otimizada para dar suporte à conectividade com a Internet para Microsoft 365. Ocasionalmente, uma avaliação indicará que Microsoft 365 de rede é influenciada por requisitos de regulamentação ou desempenho para cenários como [Skype for Business qualidade de mídia online.](https://support.office.com/article/Media-Quality-and-Network-Connectivity-Performance-in-Skype-for-Business-Online-5fe3e01b-34cf-44e0-b897-b0b2a83f0917) Esses requisitos adicionais podem levar a investimentos em infraestrutura de conectividade com a Internet, otimização de roteamento e conectividade direta especializada.

Alguns recursos para ajudá-lo a avaliar sua rede:

- Consulte [Microsoft 365 visão geral de](microsoft-365-networking-overview.md) conectividade de rede para obter informações conceituais sobre Microsoft 365 rede.
- Consulte [Microsoft 365 Princípios](./microsoft-365-network-connectivity-principles.md) de Conectividade de Rede para entender os princípios de conectividade para gerenciar com segurança Microsoft 365 tráfego e obter o melhor desempenho possível.
- Inscreva-se [no Microsoft FastTrack para](https://www.microsoft.com/fasttrack) assistência guiada Microsoft 365 planejamento, design e implantação. 
- Consulte a [seção Microsoft 365](assessing-network-connectivity.md#the-microsoft-365-connectivity-test) de teste de conectividade abaixo para executar testes básicos de conectividade que fornecem orientações específicas sobre melhorias de conectividade de rede que podem ser feitas entre um determinado local do usuário e Microsoft 365.

> [!NOTE]
> A autorização da Microsoft é necessária para usar o ExpressRoute para Office 365. A Microsoft revisa todas as solicitações do cliente e autoriza apenas o ExpressRoute para Office 365 uso quando o requisito regulatório do cliente determina a conectividade direta. Se você tiver esses requisitos, forneça o trecho de texto e o link da Web para a regulamentação que você interpreta para significar que a conectividade direta é necessária no [ExpressRoute](https://aka.ms/O365ERReview) para Office 365 Formulário de Solicitação para iniciar uma revisão da Microsoft. Assinaturas não autorizadas que tentam criar filtros de rota para Office 365 receberão uma [mensagem de erro](https://support.microsoft.com/kb/3181709).
  
Principais pontos a considerar ao planejar sua avaliação de rede para Microsoft 365:
  
- Microsoft 365 é um serviço seguro, confiável e de alto desempenho que é executado pela internet pública. Continuamos investindo para aprimorar esses aspectos do serviço. Todos os Microsoft 365 estão disponíveis por meio da conectividade com a Internet.

- Estamos otimizando continuamente os principais aspectos da Microsoft 365, como disponibilidade, alcance global e desempenho para conectividade baseada na Internet. Por exemplo, muitos serviços Microsoft 365 aproveitam um conjunto em expansão de nós de borda voltados para a Internet. Essa rede de borda oferece a melhor proximidade e desempenho para conexões que vêm pela Internet.

- Ao considerar o uso do Microsoft 365 para qualquer um dos serviços incluídos, como recursos de voz, vídeo ou reunião do Teams ou Skype for Business Online, os clientes devem concluir a avaliação de rede de ponta a ponta e atender aos requisitos de conectividade usando o [Microsoft FastTrack](https://www.microsoft.com/fasttrack).

Se você estiver avaliando Microsoft 365 e não tiver certeza de onde começar com a avaliação de rede ou tiver encontrado desafios de design de rede que você precisa de assistência para superar, trabalhe com sua equipe de conta da Microsoft.

## <a name="the-microsoft-365-connectivity-test"></a>O Microsoft 365 de conectividade

O [Microsoft 365](https://aka.ms/netonboard) de conectividade é uma ferramenta de avaliação de rede (POC) de prova de conceito que executa testes básicos de conectividade em seu locatário Microsoft 365 e faz recomendações específicas de design de rede para um desempenho Microsoft 365 ideal. A ferramenta realça as opções comuns de design de perímetro de rede corporativa grande, que são úteis para a navegação na Web da Internet, mas impactam o desempenho de grandes aplicativos SaaS, como Microsoft 365.

A ferramenta Integração de Rede faz o seguinte:

- Detecta sua localização ou você pode especificar um local a ser testado
- Verifica o local da saída da rede
- Testa o caminho de rede para a porta de Microsoft 365 de serviço mais próxima
- Fornece testes avançados usando um aplicativo Windows 10 que faz recomendações de design de rede de perímetro relacionadas a servidores proxy, firewalls e DNS. A ferramenta também executa testes de desempenho para Skype for Business Online, Microsoft Teams, SharePoint Online e Exchange Online.

A ferramenta tem dois componentes: uma interface do usuário baseada em navegador que coleta informações básicas de conectividade e um aplicativo de Windows 10 baixável que executa testes avançados e retorna dados de avaliação adicionais.

A ferramenta baseada no navegador exibe as seguintes informações:

- Guia Resultados e impacto
  - O local em um mapa da porta de entrada do serviço em uso
  - O local em um mapa de outras portas de frente de serviço que forneceriam conectividade ideal
  - Desempenho relativo em comparação com outros clientes Microsoft 365 próximos a você
- Guia Detalhes e soluções
  - Localização do usuário por cidade e país
  - Localização de saída de rede por cidade, estado e país
  - Distância de saída de usuário para rede
  - Microsoft 365 Exchange Online local da porta da frente do serviço
  - Porta Microsoft 365 Exchange Online de serviço ideal para localização do usuário
  - Clientes em sua área de metro com melhor desempenho

O aplicativo baixável testes avançados fornece as seguintes informações adicionais:

- Guia Detalhes e soluções (anexada)
  - Gateway padrão do usuário
  - Servidor DNS cliente
  - Resolvedor recursivo DNS do cliente
  - Exchange Online Servidor DNS
  - SharePoint Servidor DNS Online
  - Identificação do servidor proxy
  - Verificação de conectividade de mídia
  - Perda de pacotes de qualidade de mídia
  - Latência de qualidade de mídia
  - Tremidação de qualidade de mídia
  - Reordenamento de pacotes de qualidade de mídia
- Testes de conectividade em vários pontos de extremidade específicos do recurso
- Diagnósticos de caminho de rede que incluem dados de rastreamento e latência para os serviços Exchange Online, SharePoint Online e Teams

Você pode ler sobre o teste de Microsoft 365 conectividade e fornecer comentários no [poc](https://techcommunity.microsoft.com/t5/Office-365-Networking/Updated-Office-365-Network-Onboarding-Tool-POC-with-new-network/m-p/711130#M130) de teste de conectividade Microsoft 365 atualização com nova postagem de recomendações de design de rede. Informações sobre atualizações futuras para essa ferramenta e outras Microsoft 365 de rede serão publicadas no blog Office 365 [Rede.](https://techcommunity.microsoft.com/t5/Office-365-Networking/bd-p/Office365Networking)
  
Aqui está um link curto que você pode usar para voltar: [ https://aka.ms/o365networkconnectivity .](./microsoft-365-network-connectivity-principles.md)
  
## <a name="related-topics"></a>Tópicos relacionados

[Visão Geral da Conectividade de Rede do Microsoft 365](microsoft-365-networking-overview.md)

[Princípios de Conectividade de Rede do Microsoft 365](./microsoft-365-network-connectivity-principles.md)

[Gerenciar pontos de extremidade do Office 365](managing-office-365-endpoints.md)

[URLs e intervalos de endereços IP do Office 365](urls-and-ip-address-ranges.md)

[URL do serviço Web e endereço IP do Office 365](microsoft-365-ip-web-service.md)

[Microsoft 365 rede e ajuste de desempenho](network-planning-and-performance.md)

[Visão geral do Microsoft 365 Enterprise](microsoft-365-overview.md)