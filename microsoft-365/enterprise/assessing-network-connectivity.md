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
description: O Microsoft 365 foi projetado para permitir que clientes em todo o mundo se conectem ao serviço usando uma conexão com a Internet. À medida que o serviço evolui, a segurança, o desempenho e a confiabilidade do Microsoft 365 são aprimorados com base nos clientes que usam a Internet para estabelecer uma conexão com o serviço.
ms.openlocfilehash: c0bca2f354d71aa2f4f0c2b6fd05cb4786368b43
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46687314"
---
# <a name="assessing-microsoft-365-network-connectivity"></a>Avaliando a conectividade de rede do Microsoft 365

*Esse artigo se aplica ao Microsoft 365 Enterprise e ao Office 365 Enterprise.*

O Microsoft 365 foi projetado para permitir que clientes em todo o mundo se conectem ao serviço usando uma conexão com a Internet. À medida que o serviço evolui, a segurança, o desempenho e a confiabilidade do Microsoft 365 são aprimorados com base nos clientes que usam a Internet para estabelecer uma conexão com o serviço.
  
Os clientes que planejam usar o Microsoft 365 devem avaliar suas necessidades de conectividade de Internet existentes e previstas como parte do projeto de implantação. Para implantações de classe corporativa confiáveis e adequadamente dimensionada, a conectividade com a Internet é uma parte essencial do consumo de recursos e cenários do Microsoft 365.
  
As avaliações de rede podem ser realizadas por muitas pessoas e organizações diferentes, dependendo de seu tamanho e preferências. O escopo de rede da avaliação também pode variar dependendo de onde você está no processo de implantação. Para ajudá-lo a entender melhor o que é necessário para executar uma avaliação de rede, produzimos um guia de avaliação de rede para ajudá-lo a entender as opções disponíveis para você. Essa avaliação determinará quais etapas e recursos precisam ser adicionados ao projeto de implantação para permitir que você adote com êxito o Microsoft 365.
  
Uma avaliação de rede abrangente fornecerá possíveis soluções para desafios de design de rede juntamente com detalhes de implementação. Algumas avaliações de rede mostrarão que a conectividade de rede ideal com o Microsoft 365 pode ser acomodada com pequenas alterações de configuração ou design para a infraestrutura de rede e saída de Internet existente.

Algumas avaliações indicarão que a conectividade de rede com o Microsoft 365 exigirá investimentos adicionais em componentes de rede. Por exemplo, redes corporativas que abrangem filiais e várias regiões geográficas podem exigir investimentos em soluções SD-WAN ou infraestrutura de roteamento otimizada para dar suporte à conectividade com a Internet para o Microsoft 365. Ocasionalmente, uma avaliação indicará que a conectividade de rede com o Microsoft 365 é influenciada por regulamentações ou requisitos de desempenho para cenários como a qualidade de mídia do [Skype for Business Online.](https://support.office.com/article/Media-Quality-and-Network-Connectivity-Performance-in-Skype-for-Business-Online-5fe3e01b-34cf-44e0-b897-b0b2a83f0917) Esses requisitos adicionais podem levar a investimentos em infraestrutura de conectividade com a Internet, otimização de roteamento e conectividade direta especializada.

Alguns recursos para ajudá-lo a avaliar sua rede:

- Confira a visão geral da conectividade de rede do [Microsoft 365](microsoft-365-networking-overview.md) para obter informações conceituais sobre a rede do Microsoft 365.
- Confira os Princípios de Conectividade de Rede do [Microsoft 365](https://aka.ms/o365networkingprinciples) para entender os princípios de conectividade para gerenciar com segurança o tráfego do Microsoft 365 e obter o melhor desempenho possível.
- Inscreva-se [no Microsoft FastTrack para](https://www.microsoft.com/fasttrack) assistência guiada com planejamento, design e implantação do Microsoft 365. 
- Confira a seção de teste de conectividade do [Microsoft 365](assessing-network-connectivity.md#the-microsoft-365-connectivity-test) abaixo para executar testes básicos de conectividade que fornecem orientações específicas sobre melhorias de conectividade de rede que podem ser feitas entre um determinado local de usuário e o Microsoft 365.

> [!NOTE]
> A autorização da Microsoft é necessária para usar o ExpressRoute para o Office 365. A Microsoft revisa cada solicitação do cliente e só autoriza o ExpressRoute para uso do Office 365 quando um requisito regulatório do cliente requer conectividade direta. Se você tiver esses requisitos, forneça o trecho de texto e o link da Web para a regulamentação que você interpreta para significar que a conectividade direta é necessária no ExpressRoute para o Formulário de Solicitação do [Office 365](https://aka.ms/O365ERReview) para iniciar uma revisão da Microsoft. Assinaturas não autorizadas que tentam criar filtros de rota para o Office 365 receberão uma mensagem [de erro.](https://support.microsoft.com/kb/3181709)
  
Principais pontos a considerar ao planejar sua avaliação de rede para o Microsoft 365:
  
- O Microsoft 365 é um serviço seguro, confiável e de alto desempenho executado pela Internet pública. Continuamos investindo para aprimorar esses aspectos do serviço. Todos os serviços do Microsoft 365 estão disponíveis por meio da conectividade com a Internet.

- We are continually optimizing core aspects of Microsoft 365 such as availability, global reach, and performance for internet based connectivity. Por exemplo, muitos serviços do Microsoft 365 aproveitam um conjunto em expansão de nós de borda voltados para a Internet. Essa rede de borda oferece a melhor proximidade e desempenho para conexões provenientes da Internet.

- Ao considerar o uso do Microsoft 365 para qualquer um dos serviços incluídos, como o Teams ou os recursos de voz, vídeo ou reunião do Skype for Business Online, os clientes devem concluir uma avaliação de rede de ponta a ponta e atender aos requisitos de conectividade usando o [Microsoft FastTrack.](https://www.microsoft.com/fasttrack)

Se você estiver avaliando o Microsoft 365 e não sabe por onde começar a avaliação de rede ou se encontrou desafios de design de rede que precisa de ajuda para superar, trabalhe com sua equipe de conta da Microsoft.

## <a name="the-microsoft-365-connectivity-test"></a>Teste de conectividade do Microsoft 365

O teste de conectividade do [Microsoft 365](https://aka.ms/netonboard) é uma ferramenta de avaliação de rede de prova de conceito (POC) que executa testes básicos de conectividade em relação ao seu locatário do Microsoft 365 e faz recomendações de design de rede específicas para obter o melhor desempenho do Microsoft 365. A ferramenta destaca as opções comuns de design de perímetro de rede corporativa de grande porte, que são úteis para navegação na Web na Internet, mas que impactam no desempenho de grandes aplicativos SaaS, como o Microsoft 365.

A ferramenta de Integração de Rede faz o seguinte:

- Detecta sua localização ou você pode especificar um local para testar
- Verifica a localização da saída da rede
- Testa o caminho de rede para a porta frontal de serviço do Microsoft 365 mais próxima
- Fornece testes avançados usando um aplicativo do Windows 10 baixável que faz recomendações de design de rede de perímetro relacionadas a servidores proxy, firewalls e DNS. A ferramenta também executa testes de desempenho para o Skype for Business Online, o Microsoft Teams, o SharePoint Online e o Exchange Online.

A ferramenta tem dois componentes: uma interface do usuário baseada em navegador que coleta informações básicas de conectividade e um aplicativo do Windows 10 baixável que executa testes avançados e retorna dados de avaliação adicionais.

A ferramenta baseada em navegador exibe as seguintes informações:

- Guia Resultados e impacto
  - A localização em um mapa da porta frontal do serviço em uso
  - A localização em um mapa de outras portas frontales de serviço que forneceriam conectividade ideal
  - Desempenho relativo em comparação com outros clientes do Microsoft 365 próximos a você
- Guia Detalhes e soluções
  - Localização do usuário por cidade e país
  - Local de saída de rede por cidade, estado e país
  - Distância de saída do usuário para a rede
  - Local da porta de entrada do serviço do Exchange Online do Microsoft 365
  - Porta frontal de serviço do Microsoft 365 Exchange Online ideal para a localização do usuário
  - Clientes em sua área de metro com melhor desempenho

O aplicativo para download de Testes Avançados fornece as seguintes informações adicionais:

- Guia Detalhes e Soluções (anexada)
  - Gateway padrão do usuário
  - Servidor DNS cliente
  - Resolvedor Recursivo de DNS do Cliente
  - Servidor DNS do Exchange Online
  - Servidor DNS do SharePoint Online
  - Identificação do servidor proxy
  - Verificação de conectividade de mídia
  - Perda de pacotes de qualidade de mídia
  - Latência de qualidade de mídia
  - Trem tremida de qualidade de mídia
  - Reordenar pacotes de qualidade de mídia
- Testes de conectividade para vários pontos de extremidade específicos do recurso
- Diagnóstico de caminho de rede que inclui dados de rastreamento e latência para os serviços do Exchange Online, SharePoint Online e Teams

Você pode ler sobre o teste de conectividade do Microsoft 365 e fornecer comentários na POC de teste de conectividade atualizada do [Microsoft 365](https://techcommunity.microsoft.com/t5/Office-365-Networking/Updated-Office-365-Network-Onboarding-Tool-POC-with-new-network/m-p/711130#M130) com a nova postagem de blog de recomendações de design de rede. As informações sobre atualizações futuras para essa ferramenta e outras atualizações de rede do Microsoft 365 serão publicadas no blog de rede do [Office 365.](https://techcommunity.microsoft.com/t5/Office-365-Networking/bd-p/Office365Networking)
  
Aqui está um link curto que você pode usar para voltar: [ https://aka.ms/o365networkconnectivity .](https://aka.ms/o365networkconnectivity)
  
## <a name="related-topics"></a>Tópicos relacionados

[Visão Geral da Conectividade de Rede do Microsoft 365](microsoft-365-networking-overview.md)

[Princípios de conectividade de rede do Microsoft 365](https://aka.ms/o365networkingprinciples)

[Gerenciar pontos de extremidade do Office 365](managing-office-365-endpoints.md)

[URLs e intervalos de endereços IP do Office 365](urls-and-ip-address-ranges.md)

[URL do serviço Web e endereço IP do Office 365](microsoft-365-ip-web-service.md)

[Ajuste de desempenho e rede do Microsoft 365](network-planning-and-performance.md)

[Visão geral do Microsoft 365 Enterprise](microsoft-365-overview.md)
