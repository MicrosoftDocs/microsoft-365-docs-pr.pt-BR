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
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Compreenda a Contoso Corporation como uma empresa e a estrutura hierárquica de seus escritórios em todo o mundo.
ms.openlocfilehash: fd354b4159ee22e65e04afba33af2e90bd49b622
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/28/2018
ms.locfileid: "26865029"
---
# <a name="overview-of-the-contoso-corporation"></a>Visão geral da Contoso Corporation

**Resumo:** entender a Contoso Corporation como uma empresa e a estrutura hierárquica de seus escritórios em todo o mundo.

A Contoso Corporation é uma empresa multinacional sediada em Paris, França. É uma organização de conglomerado de fabricação, vendas e suporte com mais de 100 mil produtos.

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

  Os escritórios do hub regional escritórios atendem a uma região específica do mundo com 60% de equipe de vendas e suporte. Cada hub regional está conectado à sede Paris por um link WAN de ampla largura de banda.

  Cada hub regional tem uma média de 2 mil trabalhadores.

- Filiais

  As filiais têm 80% de equipe de vendas e suporte e oferecem uma presença e local para os clientes da Contoso nas principais cidades ou sub-regiões. Cada filial está conectada a um hub regional por um link WAN ampla largura de banda.

  Cada filial tem uma média de 250 funcionários.

25% de força de trabalho da Contoso trabalha somente fora do escritório, com uma porcentagem mais alta desses funcionários nos hubs regionais e filiais. Fornecer suporte aprimorado para esses funcionários é uma meta de negócios importante para a Contoso.

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



