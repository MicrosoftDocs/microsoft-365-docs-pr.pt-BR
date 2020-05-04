---
title: Fase 4 - Microsoft 365 Apps para empresas
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 10/23/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-modern-desktop
- Strat_O365_Enterprise
ms.custom: ''
description: Etapas para implantar a infraestrutura do Microsoft 365 Apps para empresas do Microsoft 365 Enterprise.
ms.openlocfilehash: 5143ef8872a7ebd119e77c6148288828a39e20d9
ms.sourcegitcommit: bd8d55f82ca008af1b93a9bb4d1545f68e8188ad
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/04/2020
ms.locfileid: "44011942"
---
# <a name="phase-4-microsoft-365-apps-for-enterprise"></a>Fase 4 - Microsoft 365 Apps para empresas

![Fase 4 - Microsoft 365 Apps para empresas](../media/deploy-foundation-infrastructure/O365proplus_icon.png)

*Estes critérios aplicam-se às versões E3 e E5 do Microsoft 365 Enterprise e Microsoft 365 Education*

O Microsoft 365 para empresas inclui o Microsoft 365 Apps, a versão de assinatura do Office. Como o Office 2019, o Microsoft 365 Apps para empresas inclui todos os aplicativos do Office, e esses aplicativos são instalados diretamente nos dispositivos clientes. Diferentemente do Office 2019, o Microsoft 365 Apps para empresas é atualizado regularmente com novos recursos e possui um modelo de licenciamento baseado no usuário que permite que as pessoas instalem o Office em vários dispositivos. Para obter mais detalhes, confira [Sobre o Microsoft 365 Apps para empresas](https://docs.microsoft.com/deployoffice/about-microsoft-365-apps).

Nesta fase, você implantará o Microsoft 365 Apps para empresas em dispositivos cliente como parte do Microsoft 365 Enterprise. Além destas instruções, recomendamos usar o [Microsoft FastTrack](https://fasttrack.microsoft.com/office) para ajudar com sua implantação. 

Se você já implantou o Microsoft 365 Apps para empresas, veja os [critérios de saída](office365proplus-exit-criteria.md) para esta fase para garantir que sua rede atenda às condições obrigatórias do Microsoft 365 Enterprise.

>[!Note]
>Para implantar o Windows 10 Enterprise e o Microsoft 365 Apps para empresas juntos, confira o [Centro de Implantação do Computador](desktop-deployment-center-home.md).
>

## <a name="step-1-assess-your-environment"></a>Etapa 1: Avaliar seu ambiente

Antes de implantar o Microsoft 365 Apps para empresas, siga as instruções em [Avaliar seu ambiente e requisitos para a implantação do Microsoft 365 Apps](https://docs.microsoft.com/DeployOffice/assess-microsoft-365-apps). Essa avaliação inclui requisitos do sistema, detalhes dos seus dispositivos cliente (como arquiteturas e idiomas necessários), requisitos de licenciamento, capacidade de rede e compatibilidade do aplicativo. Concluir a avaliação ajudará você a tomar decisões importantes como parte do planejamento da sua implantação.

## <a name="step-2-plan-your-deployment"></a>Etapa 2: Planejar sua implantação

Após a avaliação do ambiente, siga as orientações em [Planejar sua implantação do Microsoft 365 Apps](https://docs.microsoft.com/DeployOffice/plan-microsoft-365-apps) para criar um plano de implantação. Esse plano inclui as seguintes decisões: 

- Como implantar o Office, incluindo qual ferramenta usar (como o Microsoft Endpoint Configuration Manager ou a Ferramenta de Implantação do Office) e a partir de onde instalar o Office
- Como gerenciar as atualizações do Office
- Quais canais de atualização utilizar (os canais de atualização do Office controlam a frequência com a qual seus usuários recebem atualizações de recursos para os aplicativos do Office)
- Os pacotes de instalação e grupos de implantação do Office que você deseja usar, incluindo quais aplicativos do Office e idiomas devem ser instalados para quais usuários

O [artigo de planejamento](https://docs.microsoft.com/DeployOffice/plan-microsoft-365-apps) contém as práticas recomendadas para todas essas opções, incluindo como gerenciar sua implantação, gerenciar suas atualizações, definir os pacotes de instalação e criar grupos de implantação. 

## <a name="step-3-deploy"></a>Etapa 3: Implantar

Com base no seu plano de implantação, escolha como deseja implantar:

- **[Implantar o Microsoft 365 Apps com o Gerenciador de Configurações](https://docs.microsoft.com/deployoffice/deploy-microsoft-365-apps-configuration-manager):** gerencie sua implantação com o Gerenciador de Configurações e baixe e implante o Office a partir de pontos de distribuição na sua rede

- **[Implantar o Microsoft 365 Apps da nuvem](https://docs.microsoft.com/deployoffice/deploy-microsoft-365-apps-cloud):** gerencie sua implantação com a ODT e instale o Office em dispositivos clientes diretamente da CDN do Office
 
- **[Instale o Microsoft 365 Apps para empresas por conta própria pelo portal do Office](https://docs.microsoft.com/deployoffice/manage-software-download-settings-office-365):** Gerencie sua implantação pelo portal do Office e peça que seus usuários instalem o Office nos dispositivos cliente deles diretamente do portal

Muitas organizações usarão uma combinação dessas opções para diferentes usuários. Por exemplo, uma organização pode usar o Configuration Manager para implantar o Office para a maioria de seus usuários, mas permitir que um pequeno grupo de funcionários que não estejam conectados à rede interna com frequência instalem o Office por conta própria. 

Se sua organização usar o Configuration Manager, é recomendável atualizar para o Branch Atual e obter a versão mais recente. Para saber mais, confira [Qual branch do Configuration Manager devo usar?](https://docs.microsoft.com/mem/configmgr/core/understand/which-branch-should-i-use)

## <a name="how-microsoft-does-microsoft-365-enterprise"></a>Como a Microsoft desenvolve o Microsoft 365 Enterprise

Saiba como os especialistas da Microsoft estão [implantando e gerenciando as atualizações para o Microsoft 365 Apps para empresas](https://www.microsoft.com/itshowcase/deploying-and-managing-microsoft-365#primaryR7).

## <a name="how-contoso-did-microsoft-365-enterprise"></a>Como a Contoso desenvolveu o Microsoft 365 Enterprise

Veja como a Contoso Corporation, uma empresa multinacional fictícia mas representativa, [implantou o Microsoft 365 Apps para empresas](contoso-o365pp.md).

![A Contoso Corporation](../media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a>Próxima etapa

[Critérios de saída da infraestrutura Microsoft 365 Apps para empresas](office365proplus-exit-criteria.md)
