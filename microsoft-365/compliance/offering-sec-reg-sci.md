---
title: Valores de Securities e Exchange Commission-conformidade e integridade dos sistemas da regulamentação (SCI)
description: As regras SCI se aplicam a entidades SCI, que incluem organizações de auto-regulamentar (SROs) como ações e trocas de opções, agências de compensação registradas e sistemas de negociação alternativos (ATSs).
keywords: Microsoft 365, conformidade, ofertas
localization_priority: None
ms.prod: Microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: M365-security-compliance
hideEdit: true
titleSuffix: Microsoft Compliance
ms.openlocfilehash: 4ad74c8d4ec71587f88a80c3ee109500e230be35
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42071218"
---
# <a name="securities-and-exchange-commission-regulation-systems-compliance-and-integrity-sci"></a>Interações de títulos e do Exchange: SCI (conformidade e integridade dos sistemas regulamentares)

## <a name="about-regulation-sci"></a>Sobre a regulamentação SCI

A Comissão de títulos dos EUA e do Exchange (seg) é uma agência independente do governo federal dos EUA e do Supervisionador principal e do regulador dos mercados de títulos dos EUA. Ele controla a autoridade de fiscalização nas leis federais de títulos, propõe novas regras de títulos e supervisiona a regulamentação do mercado da indústria de títulos.

Em novembro de 2014, a SEC adotou [conformidade e integridade dos sistemas da regulamentação (SCI)](https://www.sec.gov/rules/final/2014/34-73639.pdf) (e o formato Sci para relatar eventos SCI) para reforçar a infra-estrutura de tecnologia nos mercados de títulos dos EUA. A regulamentação é projetada para reduzir a frequência de interrupções do sistema, melhorar a resiliência quando esses incidentes ocorrerem e aumentar a visão da tecnologia de mercado de títulos e a aplicação de suas regulamentações.

As regras SCI se aplicam a entidades SCI, que incluem organizações de auto-regulamentar (SROs) como ações e trocas de opções, agências de compensação registradas e sistemas de negociação alternativos (ATSs). As regras regulam principalmente os sistemas que dão suporte direto às principais funções do mercado de títulos: negociação, espaço livre e liquidação, roteamento de pedidos, dados de mercado, regulamentação de mercado e vigilância de mercado.

## <a name="microsoft-and-sec-regulation-sci"></a>Regulamentação da Microsoft e da SEC SCI

A Comissão de títulos dos EUA e do Exchange (seg) adotou regulamentação SCI para reforçar a infra-estrutura de tecnologia das organizações financeiras que operam e dão suporte aos mercados de títulos dos EUA. Sob a supervisão da SEC, seus requisitos foram projetados para garantir que esses sistemas tenham alta disponibilidade, resiliência forte e baixa latência (alto volume de mensagens com pouco atraso).

Para ajudar a orientar os clientes de serviços financeiros que precisam cumprir essa regulamentação, a Microsoft publicou o [Guia de implementação de conformidade e integridade de sistemas de conformidade e integridade dos sistemas de regulamentação do Microsoft Azure SEC](https://servicetrust.microsoft.com/ViewPage/TrustDocumentsV3?command=Download&downloadType=Document&downloadId=a69ce0c1-7b7e-44e9-9143-867241e6b2f9&tab=7f51cb60-3d6c-11e9-b2af-7bb9f5d2d913&docTab=7f51cb60-3d6c-11e9-b2af-7bb9f5d2d913_FAQ_and_White_Papers). As orientações neste documento:

- Fornece uma visão geral dos recursos gerais do Azure que dão suporte à resiliência forte, alta disponibilidade e baixa latência.
- Torna claro quais áreas de controle e aspectos normativos do Azure atendem. Este mapeamento ponto a ponto dos recursos e serviços do Azure para os requisitos SCI mede a conformidade do Azure com a estrutura reguladora. Além disso, ajuda os clientes a entender onde podem mudar as responsabilidades de segurança para o Azure que tinham sido totalmente possuídas quando operadas no local. Esses recursos são apoiados pelas promessas que a Microsoft faz nos SLAs do Azure.
- Especifica cada exigência de SCI que é a responsabilidade do cliente atender e oferece documentação e serviços do Azure para ajudá-los a lidar com essas responsabilidades.

Este documento fornece uma lista de verificação completa das áreas de foco da regulamentação de um regulamento crítico. Esta lista de verificação ajuda as organizações financeiras a entender como elas podem adotar o Azure para ajudar a garantir que seus reguladores, clientes e lideranças possam cumprir os requisitos normativos aplicáveis.

## <a name="microsoft-in-scope-cloud-services"></a>Serviços de nuvem no escopo da Microsoft

- [Azure](https://aka.ms/AzureCompliance)

## <a name="how-to-implement"></a>Como implementar

- [Guia de implementação de Sci da regulamentação](https://servicetrust.microsoft.com/ViewPage/TrustDocumentsV3?command=Download&downloadType=Document&downloadId=a69ce0c1-7b7e-44e9-9143-867241e6b2f9&tab=7f51cb60-3d6c-11e9-b2af-7bb9f5d2d913&docTab=7f51cb60-3d6c-11e9-b2af-7bb9f5d2d913_FAQ_and_White_Papers): mapeia os recursos do Azure em relação à regulamentação e detalha a responsabilidade compartilhada de conformidade.
- [Projetando aplicativos do Azure confiáveis](https://docs.microsoft.com/azure/architecture/resiliency/): uma breve visão geral de como criar a confiabilidade em cada etapa do design do aplicativo do Azure.
- [Projetando aplicativos altamente disponíveis](https://docs.microsoft.com/azure/storage/common/storage-designing-ha-apps-with-ragrs): como os desenvolvedores podem ajudar a garantir que seus aplicativos de armazenamento do Azure estejam altamente disponíveis.
- [Guia de conformidade e avaliação de risco](https://aka.ms/RiskGovernanceGuide): cria um modelo de governança para a avaliação de risco dos serviços de nuvem da Microsoft e notificações do regulador.

## <a name="frequently-asked-questions"></a>Perguntas frequentes

**O que a responsabilidade compartilhada significa ao usar a tecnologia de nuvem?**

À medida que os ambientes de computação são movidos dos datacenters no local para os da nuvem, a responsabilidade da segurança também é deslocada — o provedor de serviços de nuvem (CSP) e o cliente agora compartilham essa responsabilidade. Para todos os aplicativos e soluções, quanta responsabilidade ela cai no cliente e quanto no CSP depende do modelo do Azure que um cliente implanta: IaaS, SaaS ou PaaS. É a obrigação do cliente de entender a que grau é responsável pela implementação dos controles de segurança necessários. No entanto, a Microsoft fornece orientações para ajudar os clientes a navegarem essa dinâmica complexa. Para obter mais informações, leia as [responsabilidades compartilhadas da computação em nuvem](https://gallery.technet.microsoft.com/Shared-Responsibilities-81d0ff91).

**Quais instituições financeiras podem aproveitar o Azure para ajudar a atender aos requisitos de SCI da regulamentação?**

Organizações financeiras ou entidades SCI que estão sujeitas a essa regulamentação podem implantar o Azure. A SEC diz que sua regulamentação se aplica a ' organizações de auto-regulamentação (SROs), incluindo trocas de ações e ações, agências de limpeza registradas, FINRA e o MSRB, sistemas de negociação alternativos (ATSs), que o NMS de comércio e as ações não NMS excedem os especificados limites de volume, disseminadores de dados de mercado consolidados (processadores de plano) e determinadas agências de limpeza isentas.

## <a name="resources"></a>Recursos

- [Respostas da SEC para perguntas frequentes sobre a regulamentação SCI](https://www.sec.gov/divisions/marketreg/regulation-sci-faq.shtml)
- [Continuidade de negócios e recuperação de desastres (BCDR): regiões emparelhadas do Azure](https://docs.microsoft.com/azure/best-practices-availability-paired-regions)
- [Mapa de conformidade dos princípios normativos de computação em nuvem e dos serviços online da Microsoft](https://aka.ms/FinServ-Guide-US)
- [Programa de conformidade para serviços financeiros do Microsoft Cloud](https://aka.ms/FSCP-Print)
- [Conformidade de serviços financeiros no Azure](https://aka.ms/FinServ-Compliance-Azure)
- [Serviços financeiros da Microsoft](https://aka.ms/FinServ-Compliance)
- [Regra da Microsoft e da SEC 17a-4](offering-SEC-17a-4.md)
- [Conformidade na Central de Confiabilidade da Microsoft](https://www.microsoft.com/trust-center/compliance/compliance-overview)

## <a name="download-the-offering-backgrounder"></a>Baixar informações de oferta

Precisa do documento informativo desta oferta? Baixe o [PDF](https://download.microsoft.com/download/8/1/a/81aa04eb-3c1f-4c1a-ba7d-9d30032acc52/SEC_Reg_SCI-Compliance.pdf).
