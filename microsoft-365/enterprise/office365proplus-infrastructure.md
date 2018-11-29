---
title: 'Fase 4: Office 365 ProPlus'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/18/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Etapas para implantar a infraestrutura do Office 365 ProPlus para o Microsoft 365 Enterprise.
ms.openlocfilehash: 3f6630d4c120609cbb1737ad96644d43eb2fda3c
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/28/2018
ms.locfileid: "26865211"
---
# <a name="phase-4-office-365-proplus"></a>Fase 4: Office 365 ProPlus

![](./media/deploy-foundation-infrastructure/O365proplus_icon.png)

*Estes critérios aplicam-se às versões E3 e E5 do Microsoft 365 Enterprise e Microsoft 365 Education*

O Microsoft 365 Enterprise inclui o Office 365 ProPlus, a versão de assinatura do Office. Como o Office 2016, o Office 365 ProPlus inclui todos os aplicativos do Office e esses aplicativos são instalados diretamente em seus dispositivos cliente. Ao contrário do Office 2016, o Office 365 ProPlus é atualizado com novos recursos regularmente e tem um modelo de licenciamento baseado em usuário que permite instalar o Office em até 5 dispositivos. Para saber mais, confira [Sobre o Office 365 ProPlus na empresa](https://docs.microsoft.com/deployoffice/about-office-365-proplus-in-the-enterprise).

Nesta fase, você implantará o Office 365 ProPlus em dispositivos cliente como parte do Microsoft 365 Enterprise. Além destas instruções, recomendamos usar o [Microsoft Fastrack](https://fasttrack.microsoft.com/office) para ajudar com sua implantação. 

O Office 365 ProPlus habilita esses cenários estratégicos de negócios para o Microsoft 365 Enterprise:

- Colaborar em documentos em tempo real ou em seu próprio tempo para simplificar o processo de cocriação
- Aproveitar o conhecimento e a experiência coletiva, capacitando as pessoas a descobrir, compartilhar e dar andamento a arquivos, informações e ideias em toda a sua organização
- Capacitar os usuários a transformar processos de negócios e aumentar a eficiência
- Gerenciar projetos, tarefas e prazos para atender seus objetivos de negócios
- Usar assistência inteligente para design, escrita, descoberta de conteúdo e muito mais para ajudar seu trabalho a se destacar
- Descobrir ideias, analisar dados e compartilhar descobertas para ajudar todos a tomar decisões informadas
- Comunicar-se com sua equipe para se manter informado, solicitar sugestões e criar coesão e consenso
- Comunicar-se com parceiros, colegas e clientes em todo o mundo para chamadas agendadas e ad hoc e reuniões online com grupos de todos os portes
- Armazenar e compartilhar arquivos dentro e fora de sua organização para trabalhar de forma transparente entre os limites organizacionais
- Trabalhar com segurança de qualquer lugar, a qualquer momento e em qualquer dispositivo para alcançar mais, mantendo um estilo de trabalho flexível
- Fornecer tranquilidade com controles e visibilidade para conformidade verificada no setor com padrões globais em conformidade
- Proteger informações e reduzir o risco de perda de dados
- Ficar atualizado e manter-se atualizado em seu software e dispositivos de desktop, reduzindo os riscos de segurança e maximizando a eficiência de TI

Para saber mais, confira [Transformação digital usando o Microsoft 365](http://transform.microsoft.com). 

Se você já implantou o Office 365 ProPlus, veja os [critérios de saída](office365proplus-exit-criteria.md) para esta fase para garantir que sua rede atenda às condições obrigatórias do Microsoft 365 Enterprise.

>[!Note]
>Para implantar o Windows 10 Enterprise e o Office 365 ProPlus em conjunto e mudar para um [computador moderno](https://www.microsoft.com/microsoft-365/modern-desktop), confira o [Centro de Implantação de Computador Moderno](http://aka.ms/howtoshift).
>

## <a name="step-1-assess-your-environment"></a>Etapa 1: Avaliar seu ambiente

Antes de implantar o Office 365 ProPlus, siga as orientações em [Avaliar seu ambiente e seus requisitos para a implantação do Office 365 ProPlus](https://docs.microsoft.com/DeployOffice/assess-office-365-proplus). Essa avaliação inclui requisitos do sistema, detalhes dos seus dispositivos cliente (como arquiteturas e idiomas necessários), requisitos de licenciamento, capacidade de rede e compatibilidade do aplicativo. Concluir a avaliação ajudará você a tomar decisões importantes como parte do planejamento da sua implantação.

## <a name="step-2-plan-your-deployment"></a>Etapa 2: Planejar sua implantação

Após a avaliação do ambiente, siga as orientações em [Planejar sua implantação do Office 365 ProPlus](https://docs.microsoft.com/DeployOffice/plan-office-365-proplus) para criar um plano de implantação. Esse plano inclui as seguintes decisões: 

- Onde implantar o Office, incluindo qual ferramenta usar (como o System Center Configuration Manager ou a Ferramenta de Implantação do Office [ODT]) e de onde instalar o Office
- Como gerenciar as atualizações do Office
- Quais canais de atualização utilizar (os canais de atualização do Office controlam a frequência com a qual seus usuários recebem atualizações de recursos para os aplicativos do Office)
- Os pacotes de instalação e grupos de implantação do Office que você deseja usar, incluindo quais aplicativos do Office e idiomas devem ser instalados para quais usuários

O [artigo de planejamento](https://docs.microsoft.com/DeployOffice/plan-office-365-proplus) contém as práticas recomendadas para todas essas opções, incluindo como gerenciar sua implantação, gerenciar suas atualizações, definir os pacotes de instalação e criar grupos de implantação. 

## <a name="step-3-deploy"></a>Etapa 3: Implantar

Com base no seu plano de implantação da etapa 2, escolha como deseja implantar:

- **[Implantar o Office 365 ProPlus com o System Center Configuration Manager](https://docs.microsoft.com/deployoffice/deploy-office-365-proplus-with-system-center-configuration-manager):** Gerencie sua implantação com o Configuration Manager, e baixar e implante o Office de pontos de distribuição em sua rede

- **[Implantar o Office 365 ProPlus com a ODT da nuvem](https://docs.microsoft.com/deployoffice/deploy-office-365-proplus-from-the-cloud):** Gerencie sua implantação com a ODT e instale o Office em dispositivos cliente diretamente do Office CDN
 
- **[Implantar o Office 365 ProPlus com a ODT de uma origem local](https://docs.microsoft.com/deployoffice/deploy-office-365-proplus-from-a-local-source):** Gerencie sua implantação com a ODT, e baixe e implante o Office de uma origem local na sua rede 

- **[Instale o Office 365 ProPlus por conta própria pelo portal do Office](https://support.office.com/article/Download-and-install-or-reinstall-Office-365-or-Office-2016-on-a-PC-or-Mac-4414EAAF-0478-48BE-9C42-23ADC4716658):** Gerencie sua implantação pelo portal do Office e peça que seus usuários instalem o Office nos dispositivos cliente deles diretamente do portal

Muitas organizações usarão uma combinação dessas opções para diferentes usuários. Por exemplo, uma organização pode usar o Configuration Manager para implantar o Office para a maioria de seus usuários, mas permitir que um pequeno grupo de funcionários que não estejam conectados à rede interna com frequência instalem o Office por conta própria. 

Se sua organização usar o Configuration Manager, é recomendável atualizar para o Branch Atual e obter a versão mais recente. Para saber mais, confira [Qual branch do Configuration Manager devo usar?](https://docs.microsoft.com/sccm/core/understand/which-branch-should-i-use)

## <a name="how-microsoft-does-microsoft-365-enterprise"></a>Como a Microsoft desenvolve o Microsoft 365 Enterprise

Saiba como os especialistas da Microsoft planejaram e implantaram o Office 365 ProPlus no Microsoft 365 Enterprise com estes recursos:

- [Preparo da organização para uma implantação perfeita do Office 365 ProPlus 2016](https://www.microsoft.com/itshowcase/Office365adoption)
- [Implantar e atualizar o Microsoft Office 365 ProPlus](https://www.microsoft.com/itshowcase/Article/Content/757/Deploying-and-updating-Microsoft-Office-365-ProPlus)
- [Canais de automação e atualização ajudam a implantar o Microsoft Office 365 ProPlus](https://www.microsoft.com/itshowcase/Article/Content/794/Automation-and-update-channels-help-deploy-Microsoft-Office-365-ProPlus) (vídeo)

## <a name="how-contoso-did-microsoft-365-enterprise"></a>Como a Contoso desenvolveu o Microsoft 365 Enterprise

Veja como a Contoso Corporation, uma empresa multinacional fictícia mas representativa, [implantou o Office 365 ProPlus](contoso-o365pp.md).

![](./media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a>Próxima etapa

[Critérios de saída da infraestrutura do Office 365 ProPlus](office365proplus-exit-criteria.md)
