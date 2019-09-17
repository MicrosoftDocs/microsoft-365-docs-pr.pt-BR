---
title: 'Fase 1: Infraestrutura de rede para o Microsoft 365 Enterprise'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 10/31/2018
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Etapas para implantar a infraestrutura de rede do Microsoft 365 Enterprise.
ms.openlocfilehash: 35c65515854bb0c47a45e48d8e3c6af6a80d907c
ms.sourcegitcommit: 91ff1d4339f0f043c2b43997d87d84677c79e279
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/14/2019
ms.locfileid: "36982792"
---
# <a name="phase-1-networking-infrastructure-for-microsoft-365-enterprise"></a>Fase 1: Infraestrutura de rede para o Microsoft 365 Enterprise

![](./media/deploy-foundation-infrastructure/networking_icon.png)

O Microsoft 365 Enterprise inclui o Office 365, o Microsoft Intune e vários serviços de identidade e segurança do Microsoft Azure. Todos esses serviços baseados em nuvem dependem da segurança, desempenho e confiabilidade das conexões de dispositivos clientes pela Internet ou circuitos dedicados. Para hospedar esses serviços e disponibilizá-los para clientes em todo o mundo, a Microsoft desenvolveu uma infraestrutura de rede que enfatiza o desempenho e a integração. 

Nesta fase, você vai examinar as principais considerações para criar uma conexão eficaz com os serviços de nuvem do Microsoft 365 Enterprise. Para obter uma visão geral, consulte os [princípios de rede do Office 365](https://techcommunity.microsoft.com/t5/Office-365-Blog/Getting-the-best-connectivity-and-performance-in-Office-365/ba-p/124694).

>[!Note]
>Se você já tem uma infraestrutura de rede implantada, consulte os [critérios de saída](networking-exit-criteria.md) para esta fase a fim de garantir que sua rede atende às condições obrigatórias e opcionais do Microsoft 365 Enterprise.

## <a name="plan-and-deploy-your-microsoft-365-enterprise-networking-infrastructure"></a>Planejar e implantar a infraestrutura de rede do Microsoft 365 Enterprise 

Siga as etapas a seguir para criar sua infraestrutura de rede de acordo com os requisitos e recursos do Microsoft 365 Enterprise.

|||
|:-------|:-----|
|![](./media/stepnumbers/Step1.png)|[Preparar sua rede para o Microsoft 365](networking-provide-bandwidth-cloud-services.md)|
|![](./media/stepnumbers/Step2.png)|[Configurar conexões locais com a Internet para cada escritório](networking-dns-resolution-same-location.md)|
|![](./media/stepnumbers/Step3.png)|[Evitar hairpins de rede](networking-avoid-network-hairpins.md)|
|![](./media/stepnumbers/Step4.png)|[Configurar o bypass de tráfego](networking-configure-proxies-firewalls.md)|
|![](./media/stepnumbers/Step5.png)|[Otimizar o desempenho do serviço entre o cliente e o Office 365](networking-optimize-tcp-performance.md)|


Após concluir essas etapas, consulte os [critérios de saída](networking-exit-criteria.md) para esta fase a fim de garantir que sua rede atende às condições obrigatórias e opcionais do Microsoft 365 Enterprise.

## <a name="how-microsoft-does-microsoft-365-enterprise"></a>Como a Microsoft desenvolve o Microsoft 365 Enterprise

Dê uma olhada na Microsoft e saiba como a empresa [otimizou a rede da Microsoft para serviços de nuvem](https://www.microsoft.com/pt-BR/itshowcase/deploying-and-managing-microsoft-365#primaryR4).

## <a name="how-contoso-did-microsoft-365-enterprise"></a>Como a Contoso desenvolveu o Microsoft 365 Enterprise

Veja como a Contoso Corporation, uma empresa multinacional fictícia, mas representativa, [otimizou seus dispositivos de rede e a conexão à internet](contoso-networking.md) para os serviços de nuvem do Microsoft 365.

![](./media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a>Próxima etapa

|||
|:-------|:-----|
|![](./media/stepnumbers/Step1.png)|[Preparar sua rede para o Microsoft 365](networking-provide-bandwidth-cloud-services.md)|

