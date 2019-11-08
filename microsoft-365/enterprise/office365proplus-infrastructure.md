---
title: 'Fase 4: Office 365 ProPlus'
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
description: Etapas para implantar a infraestrutura do Office 365 ProPlus para o Microsoft 365 Enterprise.
ms.openlocfilehash: 05615c4c9020326da6b2e3e97b162dbb8d132854
ms.sourcegitcommit: 70e920f76526f47fc849df615de4569e0ac2f4be
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/07/2019
ms.locfileid: "38033646"
---
# <a name="phase-4-office-365-proplus"></a>Fase 4: Office 365 ProPlus

![Fase 4: Office 365 ProPlus](./media/deploy-foundation-infrastructure/O365proplus_icon.png)

*Estes critérios aplicam-se às versões E3 e E5 do Microsoft 365 Enterprise e Microsoft 365 Education*

O Microsoft 365 Enterprise inclui o Office 365 ProPlus, a versão de assinatura do Office. Como o Office 2019, o Office 365 ProPlus inclui todos os aplicativos do Office, e esses aplicativos são instalados diretamente nos dispositivos clientes. Diferentemente do Office 2019, o Office 365 ProPlus é atualizado regularmente com novos recursos e possui um modelo de licenciamento baseado no usuário que permite que as pessoas instalem o Office em vários dispositivos. Para obter mais detalhes, consulte [Sobre o Office 365 ProPlus na empresa](https://docs.microsoft.com/deployoffice/about-office-365-proplus-in-the-enterprise).

Nesta fase, você implantará o Office 365 ProPlus em dispositivos cliente como parte do Microsoft 365 Enterprise. Além destas instruções, recomendamos usar o [Microsoft Fastrack](https://fasttrack.microsoft.com/office) para ajudar com sua implantação. 

Se você já implantou o Office 365 ProPlus, veja os [critérios de saída](office365proplus-exit-criteria.md) para esta fase para garantir que sua rede atenda às condições obrigatórias do Microsoft 365 Enterprise.

>[!Note]
>Para implantar o Windows 10 Enterprise e o Office 365 ProPlus juntos, confira o [Centro de Implantação do Computador](desktop-deployment-center-home.md).
>

## <a name="step-1-assess-your-environment"></a>Etapa 1: Avaliar seu ambiente

Antes de implantar o Office 365 ProPlus, siga as orientações em [Avaliar seu ambiente e seus requisitos para a implantação do Office 365 ProPlus](https://docs.microsoft.com/DeployOffice/assess-office-365-proplus). Essa avaliação inclui requisitos do sistema, detalhes dos seus dispositivos cliente (como arquiteturas e idiomas necessários), requisitos de licenciamento, capacidade de rede e compatibilidade do aplicativo. Concluir a avaliação ajudará você a tomar decisões importantes como parte do planejamento da sua implantação.

## <a name="step-2-plan-your-deployment"></a>Etapa 2: Planejar sua implantação

Após a avaliação do ambiente, siga as orientações em [Planejar sua implantação do Office 365 ProPlus](https://docs.microsoft.com/DeployOffice/plan-office-365-proplus) para criar um plano de implantação. Esse plano inclui as seguintes decisões: 

- Como implantar o Office, incluindo qual ferramenta usar (como o System Center Configuration Manager ou a Ferramenta de Implantação do Office) e a partir de onde instalar o Office
- Como gerenciar as atualizações do Office
- Quais canais de atualização utilizar (os canais de atualização do Office controlam a frequência com a qual seus usuários recebem atualizações de recursos para os aplicativos do Office)
- Os pacotes de instalação e grupos de implantação do Office que você deseja usar, incluindo quais aplicativos do Office e idiomas devem ser instalados para quais usuários

O [artigo de planejamento](https://docs.microsoft.com/DeployOffice/plan-office-365-proplus) contém as práticas recomendadas para todas essas opções, incluindo como gerenciar sua implantação, gerenciar suas atualizações, definir os pacotes de instalação e criar grupos de implantação. 

## <a name="step-3-deploy"></a>Etapa 3: Implantar

Com base no seu plano de implantação, escolha como deseja implantar:

- **[Implantar o Office 365 ProPlus com o System Center Configuration Manager](https://docs.microsoft.com/deployoffice/deploy-office-365-proplus-with-system-center-configuration-manager):** Gerencie sua implantação com o Configuration Manager, e baixar e implante o Office de pontos de distribuição em sua rede

- **[Implantar o Office 365 ProPlus com a ODT da nuvem](https://docs.microsoft.com/deployoffice/deploy-office-365-proplus-from-the-cloud):** Gerencie sua implantação com a ODT e instale o Office em dispositivos cliente diretamente do Office CDN
 
- **[Instale o Office 365 ProPlus por conta própria pelo portal do Office](https://support.office.com/article/Download-and-install-or-reinstall-Office-365-or-Office-2016-on-a-PC-or-Mac-4414EAAF-0478-48BE-9C42-23ADC4716658):** Gerencie sua implantação pelo portal do Office e peça que seus usuários instalem o Office nos dispositivos cliente deles diretamente do portal

Muitas organizações usarão uma combinação dessas opções para diferentes usuários. Por exemplo, uma organização pode usar o Configuration Manager para implantar o Office para a maioria de seus usuários, mas permitir que um pequeno grupo de funcionários que não estejam conectados à rede interna com frequência instalem o Office por conta própria. 

Se sua organização usar o Configuration Manager, é recomendável atualizar para o Branch Atual e obter a versão mais recente. Para saber mais, confira [Qual branch do Configuration Manager devo usar?](https://docs.microsoft.com/sccm/core/understand/which-branch-should-i-use)

## <a name="how-microsoft-does-microsoft-365-enterprise"></a>Como a Microsoft desenvolve o Microsoft 365 Enterprise

Saiba como os especialistas da Microsoft estão [implantando e gerenciando as atualizações para o Office 365 ProPlus.](https://www.microsoft.com/itshowcase/deploying-and-managing-microsoft-365#primaryR7)

## <a name="how-contoso-did-microsoft-365-enterprise"></a>Como a Contoso desenvolveu o Microsoft 365 Enterprise

Veja como a Contoso Corporation, uma empresa multinacional fictícia mas representativa, [implantou o Office 365 ProPlus](contoso-o365pp.md).

![A Contoso Corporation](./media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a>Próxima etapa

[Critérios de saída da infraestrutura do Office 365 ProPlus](office365proplus-exit-criteria.md)
