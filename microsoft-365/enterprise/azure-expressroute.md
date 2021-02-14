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

Saiba como o Azure ExpressRoute é usado com o Office 365 e como planejar o projeto de implementação de rede que será necessário se você estiver implantando o Azure ExpressRoute para uso com o Office 365. Serviços de infraestrutura e plataforma em execução no Azure geralmente se beneficiarão abordando considerações de desempenho e arquitetura de rede. Recomendamos o ExpressRoute para Azure nesses casos. As ofertas de software como serviço, como o Office 365 e o Dynamics 365, foram criadas para serem acessadas de forma segura e confiável pela Internet. Você pode ler sobre desempenho e segurança da Internet e quando considerar o Azure ExpressRoute para Office 365 no artigo Avaliando a conectividade de rede do [Office 365.](assessing-network-connectivity.md)

> [!NOTE]
> A autorização da Microsoft é necessária para usar o ExpressRoute para o Office 365. A Microsoft analisa cada solicitação de cliente e autoriza o ExpressRoute para uso do Office 365 quando um requisito regulatório do cliente requer conectividade direta. Se você tiver esses requisitos, forneça o trecho de texto e o link da Web para a regulamentação que você interpreta para significar que a conectividade direta é necessária no ExpressRoute para o Formulário de Solicitação do [Office 365](https://aka.ms/O365ERReview) para iniciar uma revisão da Microsoft. Assinaturas não autorizadas que tentam criar filtros de rota para o Office 365 receberão uma mensagem [de erro.](https://support.microsoft.com/kb/3181709)

Agora você pode adicionar uma conexão de rede direta ao Office 365 para o tráfego de rede selecionado do Office 365. O Azure ExpressRoute oferece uma conexão direta, desempenho previsível e vem com um SLA de tempo de atividade de 99,95% para os componentes de rede da Microsoft. Você ainda exigirá uma conexão com a Internet para serviços que não são suportados pelo Azure ExpressRoute.

## <a name="planning-azure-expressroute-for-office-365"></a>Planejamento do Azure ExpressRoute para Office 365

Além da conectividade com a Internet, você pode optar por encaminhar um subconjunto do tráfego de rede do Office 365 por uma conexão direta que ofereça previsibilidade e um SLA de 99,95% de tempo de atividade para os componentes de rede da Microsoft. O Azure ExpressRoute fornece esta conexão de rede dedicada ao Office 365 e a outros serviços de nuvem da Microsoft.

Independentemente de você ter uma WAN MPLS existente, o ExpressRoute pode ser adicionado à sua arquitetura de rede de uma das três maneiras; por meio de um provedor de co-local de troca de nuvem com suporte, um provedor de conexão ponto a ponto Ethernet ou por meio de um provedor de conexão MPLS. Veja quais [provedores estão disponíveis em sua região.](https://azure.microsoft.com/documentation/articles/expressroute-locations/) A conexão direta do ExpressRoute habilitará a conectividade com os aplicativos descritos em Quais serviços do [Office 365 estão incluídos?](azure-expressroute.md#BKMK_WhatDoIGet) Abaixo. O tráfego de rede para todos os outros aplicativos e serviços continuará a atravessar a Internet.

Considere o diagrama de rede de alto nível a seguir, que mostra um cliente típico do Office 365 se conectando aos datacenters da Microsoft pela Internet para acessar todos os aplicativos da Microsoft, como o Office 365, o Windows Update e o TechNet. Os clientes usam um caminho de rede semelhante, independentemente de eles se conectarem a partir de uma rede local ou de uma conexão independente com a Internet.

![Conectividade de rede do Office 365](../media/9d8bc622-4a38-4a3b-a0f3-68657712d460.png)

Agora, veja o diagrama atualizado que representa um cliente do Office 365 que usa a Internet e o ExpressRoute para se conectar ao Office 365. Observe que algumas conexões, como DNS público e nós de Rede de Distribuição de Conteúdo, ainda exigem a conexão pública com a Internet. Observe também que os usuários do cliente que não estão localizados no edifício conectado ao ExpressRoute estão se conectando pela Internet.

![Conectividade do Office 365 com o ExpressRoute](../media/251788c4-0937-4584-9b2c-df08e11611fc.png)

Ainda deseja mais informações? Saiba como gerenciar o tráfego de rede com o [Azure ExpressRoute para Office 365](https://support.office.com/article/e1da26c6-2d39-4379-af6f-4da213218408) e como configurar o [Azure ExpressRoute para Office 365.](https://azure.microsoft.com/documentation/articles/expressroute-faqs/) Também gravamos uma série de 10 partes do [Azure ExpressRoute](https://channel9.msdn.com/series/aer) para Treinamento do Office 365 no Channel 9 para ajudar a explicar os conceitos mais detalhadamente.

## <a name="what-office-365-services-are-included"></a>Quais serviços do Office 365 estão incluídos?
<a name="BKMK_WhatDoIGet"> </a>

A tabela a seguir lista os serviços do Office 365 com suporte no ExpressRoute. Revise o artigo de pontos de extremidade do [Office 365](https://aka.ms/o365endpoints) para entender quais solicitações de rede para esses aplicativos exigem conectividade com a Internet.

|**Aplicativos incluídos**|
|:-----|
|Exchange Online<sup>1</sup> <br/> Proteção do Exchange Online<sup>1</sup> <br/> Delve<sup>1</sup> <br/> |
|Skype for Business Online<sup>1</sup> <br/> Microsoft Teams <sup>1</sup> <br/> |
|SharePoint Online<sup>1</sup> <br/> OneDrive for Business<sup>1</sup> <br/> Project Online<sup>1</sup> <br/> |
|Portal e<sup>1 compartilhado</sup> <br/> Azure Active Directory (Azure AD) <sup>1</sup> <br/> Azure AD Connect<sup>1</sup> <br/> Office<sup>1</sup> <br/> |

<sup>1</sup> Cada um desses aplicativos tem requisitos de conectividade com a Internet não suportados pelo ExpressRoute, consulte o artigo de pontos de extremidade do [Office 365](https://aka.ms/o365endpoints) para obter mais informações.

Os serviços que não estão incluídos no ExpressRoute para Office 365 são downloads de cliente do Microsoft 365 Apps para empresas, Entrada do Provedor de Identidade Local e serviço do Office 365 (operado pela 21 Vianet) na China.

## <a name="implementing-expressroute-for-office-365"></a>Como implementar o ExpressRoute para o Office 365

Implementar o ExpressRoute requer o envolvimento dos proprietários de rede e aplicativos e requer um planejamento cuidadoso para determinar a nova arquitetura de roteamento de [rede,](https://support.office.com/article/e1da26c6-2d39-4379-af6f-4da213218408)requisitos de largura de banda, onde a segurança será implementada, alta disponibilidade e assim por diante. Para implementar o ExpressRoute, você precisará:

1. Entenda totalmente a necessidade de que o ExpressRoute atenda ao seu planejamento de conectividade do Office 365. Entenda quais aplicativos usarão a Internet ou o ExpressRoute e planejarão totalmente suas necessidades de capacidade de rede, segurança e alta disponibilidade no contexto de uso da Internet e do ExpressRoute para tráfego do Office 365.

2. Determine os locais de saída e de pares para o tráfego da Internet e do ExpressRoute<sup>1.</sup>

3. Determine a capacidade necessária nas conexões da Internet e do ExpressRoute.

4. Ter um plano para implementar a segurança e outros controles de perímetro padrão<sup>1</sup>.

5. Ter uma conta válida do Microsoft Azure para se inscrever no ExpressRoute.

6. Selecione um modelo de conectividade e um [provedor aprovado.](https://azure.microsoft.com/documentation/articles/expressroute-locations/) Lembre-se de que os clientes podem selecionar vários modelos ou parceiros de conectividade e o parceiro não precisa ser o mesmo que seu provedor de rede existente.

7. Valide a implantação antes de direcionar o tráfego para o ExpressRoute.

8. Opcionalmente, [implemente a QoS e](https://support.office.com/article/ExpressRoute-and-QoS-in-Skype-for-Business-Online-20c654da-30ee-4e4f-a764-8b7d8844431d) avalie a expansão regional.

<sup>1</sup> Considerações de desempenho importantes. As decisões aqui podem afetar drasticamente a latência, o que é fundamental para aplicativos como o Skype for Business.

Para referências adicionais, use nosso guia [de roteamento,](https://support.office.com/article/Routing-with-ExpressRoute-for-Office-365-e1da26c6-2d39-4379-af6f-4da213218408) além da [documentação do ExpressRoute.](https://azure.microsoft.com/documentation/articles/expressroute-introduction/)

Para adquirir o ExpressRoute para o Office 365, você precisará trabalhar com um ou mais provedores [aprovados](https://azure.microsoft.com/documentation/articles/expressroute-locations/) para provisionar os circuitos de número e tamanho desejados com uma assinatura do ExpressRoute Premium. Não há licenças adicionais para comprar no Office 365.

Aqui está um link curto que você pode usar para voltar: [https://aka.ms/expressrouteoffice365](https://aka.ms/expressrouteoffice365)

Pronto para se inscrever no [ExpressRoute para Office 365?](https://aka.ms/ert)

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
