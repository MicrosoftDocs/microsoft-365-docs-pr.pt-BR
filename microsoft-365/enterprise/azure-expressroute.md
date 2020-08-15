---
title: Rota Expressa do Azure para Office 365
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 6/5/2019
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: 6d2534a2-c19c-4a99-be5e-33a0cee5d3bd
description: Saiba como usar o Azure ExpressRoute com o Office 365 e planejar o projeto de implementação de rede se você estiver implantando com ele.
ms.openlocfilehash: 3691161767aba784039cbf317a51429c9ee6444c
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46686908"
---
# <a name="azure-expressroute-for-office-365"></a>Rota Expressa do Azure para Office 365

*Esse artigo se aplica ao Microsoft 365 Enterprise e ao Office 365 Enterprise.*

Saiba como o Azure ExpressRoute é usado com o Office 365 e como planejar o projeto de implementação de rede que será necessário se você estiver implantando o Azure ExpressRoute para uso com o Office 365. Os serviços de infraestrutura e plataforma em execução no Azure geralmente se beneficiam com a abordagem de desempenho e arquitetura da rede. Recomendamos o ExpressRoute para o Azure nesses casos. Software como uma oferta de serviço como o Office 365 e o Dynamics 365 foram criados para serem acessados com segurança e confiança através da Internet. Você pode ler sobre o desempenho e a segurança da Internet e quando você pode considerar o Azure ExpressRoute para Office 365 no artigo [avaliando a conectividade de rede do Office 365](assessing-network-connectivity.md).

> [!NOTE]
> A autorização da Microsoft é necessária para usar o ExpressRoute para o Office 365. A Microsoft revisa cada solicitação de cliente e autoriza o uso do ExpressRoute para o Office 365 quando o requisito normativo de um cliente exige conectividade direta. Se você tiver esses requisitos, forneça o trecho de texto e o link da Web para a regulamentação que você interpreta para indicar que a conectividade direta é necessária no [formulário de solicitação do ExpressRoute para Office 365](https://aka.ms/O365ERReview) para começar a análise da Microsoft. Assinaturas não autorizadas tentando criar filtros de roteamento para o Office 365 receberão uma [mensagem de erro](https://support.microsoft.com/kb/3181709).

Agora você pode adicionar uma conexão de rede direta ao Office 365 para o tráfego de rede do Office 365 selecionado. O Azure ExpressRoute oferece uma conexão direta, desempenho previsível e inclui um SLA de tempo de atividade de 99,95% para os componentes de rede da Microsoft. Você ainda precisará de uma conexão com a Internet para serviços que não são compatíveis com o Azure ExpressRoute.

## <a name="planning-azure-expressroute-for-office-365"></a>Planejando o Azure ExpressRoute para Office 365

Além da conectividade com a Internet, você pode optar por direcionar um subconjunto do tráfego de rede do Office 365 por uma conexão direta que oferece previsibilidade e um SLA de tempo de atividade de 99,95% para os componentes de rede da Microsoft. O Azure ExpressRoute fornece essa conexão de rede dedicada ao Office 365 e outros serviços de nuvem da Microsoft.

Independentemente de você ter uma WAN MPLS existente, o ExpressRoute pode ser adicionado à sua arquitetura de rede de uma das três maneiras; por meio de um provedor de cooperação de local de nuvem com suporte, um provedor de conexão ponto a ponto de Ethernet ou por um provedor de conexão MPLS. Veja quais [provedores estão disponíveis em sua região](https://azure.microsoft.com/documentation/articles/expressroute-locations/). A conexão do ExpressRoute direto permitirá a conectividade para os aplicativos descritos nos [quais os serviços do Office 365 estão incluídos?](azure-expressroute.md#BKMK_WhatDoIGet) abaixo. O tráfego de rede para todos os outros aplicativos e serviços continuará a atravessar a Internet.

Considere o seguinte diagrama de rede de alto nível, que mostra um cliente típico do Office 365 conectando-se aos datacenters da Microsoft pela Internet para acesso a todos os aplicativos da Microsoft, como o Office 365, o Windows Update e o TechNet. Os clientes usam um caminho de rede semelhante independentemente de estarem se conectando de uma rede local ou de uma conexão independente com a Internet.

![Conectividade de rede do Office 365](../media/9d8bc622-4a38-4a3b-a0f3-68657712d460.png)

Agora, examine o diagrama atualizado, que representa um cliente do Office 365 que usa a Internet e o ExpressRoute para se conectar ao Office 365. Observe que algumas conexões, como os nós de rede de DNS e de entrega de conteúdo públicos ainda exigem a conexão pública com a Internet. Observe também que os usuários do cliente que não estão localizados em seus prédios conectados ao ExpressRoute estão se conectando pela Internet.

![Conectividade do Office 365 com o ExpressRoute](../media/251788c4-0937-4584-9b2c-df08e11611fc.png)

Ainda deseja obter mais informações? Saiba como [gerenciar o tráfego de rede com o Azure expressroute para office 365](https://support.office.com/article/e1da26c6-2d39-4379-af6f-4da213218408) e saiba como [Configurar o Azure expressroute para Office 365](https://azure.microsoft.com/documentation/articles/expressroute-faqs/). Também registramos uma série de 10 peças do [Azure ExpressRoute para o Office 365 Training](https://channel9.msdn.com/series/aer) no Channel 9 para ajudar a explicar os conceitos de mais detalhes.

## <a name="what-office-365-services-are-included"></a>Quais serviços do Office 365 estão incluídos?
<a name="BKMK_WhatDoIGet"> </a>

A tabela a seguir lista os serviços do Office 365 que são compatíveis com o ExpressRoute. Revise o [artigo de pontos de extremidade do Office 365](https://aka.ms/o365endpoints) para entender quais solicitações de rede desses aplicativos exigem conectividade com a Internet.

|**Aplicativos incluídos**|
|:-----|
|Exchange Online<sup>1</sup> <br/> Proteção do Exchange Online<sup>1</sup> <br/> Delve<sup>1</sup> <br/> |
|Skype for Business Online<sup>1</sup> <br/> Microsoft Teams <sup>1</sup> <br/> |
|SharePoint Online<sup>1</sup> <br/> OneDrive for Business<sup>1</sup> <br/> Project online<sup>1</sup> <br/> |
|Portal e compartilhado<sup>1</sup> <br/> Azure Active Directory (Azure AD) <sup>1</sup> <br/> Azure AD Connect<sup>1</sup> <br/> Office<sup>1</sup> <br/> |

<sup>1</sup> cada um desses aplicativos tem requisitos de conectividade com a Internet não suportados no ExpressRoute, consulte o artigo sobre os [pontos de extremidade do Office 365](https://aka.ms/o365endpoints) para obter mais informações.

Os serviços que não estão incluídos no ExpressRoute para o Office 365 são aplicativos da Microsoft 365 para downloads de cliente corporativo, entrada do provedor de identidade local e serviço do Office 365 (operado pelo 21 vianet) na China.

## <a name="implementing-expressroute-for-office-365"></a>Como implementar o ExpressRoute para o Office 365

A implementação do ExpressRoute requer o envolvimento dos proprietários de rede e de aplicativos e requer um planejamento cuidadoso para determinar a nova [arquitetura de roteamento de rede](https://support.office.com/article/e1da26c6-2d39-4379-af6f-4da213218408), os requisitos de largura de banda, onde a segurança será implementada, alta disponibilidade e assim por diante. Para implementar o ExpressRoute, você precisará:

1. Entenda totalmente que a necessidade do ExpressRoute atende ao seu planejamento de conectividade do Office 365. Entenda quais aplicativos usarão a Internet ou o ExpressRoute e planeje totalmente a capacidade de rede, a segurança e as necessidades de alta disponibilidade no contexto de uso da Internet e do tráfego do ExpressRoute para Office 365.

2. Determine os locais de egresso e de emparelhamento para tráfego de Internet e ExpressRoute<sup>1</sup>.

3. Determine a capacidade necessária na Internet e nas conexões ExpressRoute.

4. Ter um plano em vigor para implementar a segurança e outros controles de perímetro padrão<sup>1</sup>.

5. Ter uma conta válida do Microsoft Azure para inscrever-se no ExpressRoute.

6. Selecione um modelo de conectividade e um [provedor aprovado](https://azure.microsoft.com/documentation/articles/expressroute-locations/). Tenha em mente que os clientes podem selecionar vários modelos ou parceiros de conectividade, e o parceiro não precisa ser o mesmo que seu provedor de rede existente.

7. Valide a implantação antes de direcionar o tráfego para o ExpressRoute.

8. Opcionalmente, [implementar QoS](https://support.office.com/article/ExpressRoute-and-QoS-in-Skype-for-Business-Online-20c654da-30ee-4e4f-a764-8b7d8844431d) e avaliar a expansão regional.

<sup>1</sup> considerações importantes de desempenho. As decisões aqui podem afetar drasticamente a latência, o que é crítico para aplicativos como o Skype for Business.

Para obter referências adicionais, use o [Guia de roteamento](https://support.office.com/article/Routing-with-ExpressRoute-for-Office-365-e1da26c6-2d39-4379-af6f-4da213218408) além da [documentação do ExpressRoute](https://azure.microsoft.com/documentation/articles/expressroute-introduction/).

Para comprar o ExpressRoute para o Office 365, você precisará trabalhar com um ou mais [provedores aprovados](https://azure.microsoft.com/documentation/articles/expressroute-locations/) para provisionar o número desejado e os circuitos de tamanho com uma assinatura do ExpressRoute Premium. Não há licenças adicionais a serem compradas do Office 365.

Aqui está um link curto que você pode usar para voltar: [https://aka.ms/expressrouteoffice365](https://aka.ms/expressrouteoffice365)

Pronto para se inscrever no [ExpressRoute para o Office 365](https://aka.ms/ert)?

## <a name="related-topics"></a>Tópicos Relacionados

[Avaliando a conectividade de rede do Office 365](assessing-network-connectivity.md)

[Como gerenciar o ExpressRoute para a conectividade do Office 365](managing-expressroute-for-connectivity.md)

[Como rotear com o ExpressRoute para Office 365](routing-with-expressroute.md)

[Planejamento de rede com o ExpressRoute para Office 365](network-planning-with-expressroute.md)

[Como implementar o ExpressRoute para Office 365](implementing-expressroute.md)

[Usando comunidades BGP no ExpressRoute para cenários do Office 365](bgp-communities-in-expressroute.md)

[Qualidade da mídia e desempenho de conectividade de rede no Skype for Business Online](https://support.office.com/article/5fe3e01b-34cf-44e0-b897-b0b2a83f0917)

[Ajuste de desempenho do Office 365 usando linhas de base e histórico de desempenho](performance-tuning-using-baselines-and-history.md)

[Plano de solução de problemas de desempenho do Office 365](performance-troubleshooting-plan.md)

[URLs e intervalos de endereços IP do Office 365](urls-and-ip-address-ranges.md)

[Rede do Office 365 e ajuste de desempenho](network-planning-and-performance.md)

## <a name="see-also"></a>Confira também

[Visão geral do Microsoft 365 Enterprise](microsoft-365-overview.md)
