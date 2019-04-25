---
title: Visão geral da Contoso Corporation
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 09/13/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Compreenda a Contoso Corporation como uma empresa e a estrutura hierárquica de seus escritórios em todo o mundo.
ms.openlocfilehash: 751f75bd2a5d1e0df401c1d3aa54a0fd5afec8f7
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32289352"
---
# <a name="overview-of-the-contoso-corporation"></a>Visão geral da Contoso Corporation

**Resumo:** entender a Contoso Corporation como uma empresa e a estrutura hierárquica de seus escritórios em todo o mundo.

A Contoso Corporation é uma empresa multinacional com sede em Paris, França. A Contoso é um conglomerado de fabricação, vendas e organização de suporte com mais de 100 mil produtos.

![](./media/contoso-overview/contoso-icon.png)

## <a name="contoso-around-the-world"></a>Contoso em todo o mundo

A Figura 1 mostra a matriz em Paris e hubs regionais e filiais em vários continentes.

![](./media/contoso-overview/contoso-overview-fig1.png)

**Figura 1: escritórios da Contoso em todo o mundo**
 
Os escritórios da Contoso no mundo todo seguem um design de três camadas.

- Sede

  A sede da Contoso Corporation é um grande campus corporativo nos arredores de Paris com dezenas de prédios com instalações administrativas, de fabricação e de engenharia. Todos os datacenters da Contoso e sua presença na Internet estão hospedados na sede de Paris.

  A matriz tem 25 mil trabalhadores.

- Hubs regionais

  Escritórios de hubs regionais atendem uma região específica do mundo com 60% da equipe de vendas e suporte. Cada hub regional está conectado à sede de Paris com link WAN de largura de banda alta.

  Cada hub regional tem uma média de 2 mil trabalhadores.

- Filiais

  As filiais têm 80% de equipe de vendas e suporte e oferecem uma presença local para os clientes da Contoso nas principais cidades ou sub-regiões. Cada filial está conectada a um hub regional com um link WAN de largura de banda alta.

  Cada filial tem uma média de 250 funcionários.

25% da força de trabalho da Contoso é somente móvel, com um percentual maior de funcionários apenas móveis nos hubs regionais e nas filiais. Fornecer suporte melhor para trabalhadores somente móveis é uma importante meta de negócios da Contoso.

## <a name="design-considerations-for-microsoft-365-enterprise"></a>Considerações de design para o Microsoft 365 Enterprise

Os arquitetos de TI da Contoso identificaram as seguintes considerações de design durante a implantação do Microsoft 365 Enterprise: 

- Vários locais geográficos com normas locais e requisitos de conformidade
- Um data center central de intranet na matriz e servidores de aplicativos regionais que hospedam uma linha interna de aplicativos de negócios
- Uma infraestrutura existente do System Center Configuration Manager
- Uma mistura de dispositivos de computação cliente, incluindo Windows, Mac e Linux
- Uma mistura de dispositivos móveis de propriedade da empresa e pessoais, incluindo tablets e smartphones Android e iOS (iPhone e iPad)
- Muitos trabalhadores remotos e móveis
- Vários parceiros de negócios
- Uma grande quantidade de dados do cliente e de identificação pessoal
- Uma grande quantidade de propriedade intelectual importante na forma de especificações de design de produtos e segredos comerciais de manufatura

## <a name="next-step"></a>Próxima etapa

[Saiba](contoso-infra-needs.md) mais sobre a infraestrutura de TI local da Contoso Corporation e de que forma as necessidades comerciais podem ser corrigidas com o Microsoft 365 Enterprise.

## <a name="see-also"></a>Confira também

[Guia de implantação](deploy-microsoft-365-enterprise.md)

[Guias de laboratório de teste](m365-enterprise-test-lab-guides.md)



