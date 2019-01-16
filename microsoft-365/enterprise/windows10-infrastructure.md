---
title: Infraestrutura do Windows 10 Enterprise para Microsoft 365 Enterprise
description: Fornece uma orientação de alto nível sobre as etapas que necessárias para implantar o Windows 10 Enterprise em PCs como parte do Microsoft 365 Enterprise.
keywords: Implantação do Microsoft 365, Microsoft 365 Enterprise, Microsoft 365 documentação, Windows 10 Enterprise,
author: greg-lindsay
localization_priority: Normal
audience: microsoft-business
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.date: 09/18/2018
ms.author: greglin
ms.openlocfilehash: 80d7c1b56434647387b9c428ca07effdff929abf
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/16/2019
ms.locfileid: "26864683"
---
# <a name="phase-3-windows-10-enterprise"></a>Fase 3: Windows 10 Enterprise

![](./media/deploy-foundation-infrastructure/win10enterprise_icon.png)

Microsoft 365 Enterprise inclui Windows 10 Enterprise, que oferece as ferramentas para fazer mais e permanecer protegido. Windows 10 Enterprise:

- **Está integrado para proporcionar simplicidade** - usufrua do poder da nuvem para ajudar a reduzir a complexidade do gerenciamento de hoje 's moderno ambiente de dispositivo de TI, não importa o tamanho.
- **Tem segurança inteligente** - é a versão mais segura do Windows nunca, com segurança inteligente recursos projetados para que trabalhem juntos para melhor proteger sua organização.
- **Permite que o trabalho em equipe e criatividade** - desbloqueia criatividade e trabalho em equipe para fornecer mais produtivos experiência que os usuários e TI será amor.

Você precisará entender as diferentes maneiras que você pode implantar o sistema operacional Windows 10 e escolha uma apropriada para sua organização. Dependendo de sua assinatura do Microsoft 365 Enterprise, há também Windows 10 serviços e recursos de segurança que você precisará configurá-la para aproveitar ao máximo 10 do Windows.

Windows 10 permite esses cenários de negócios estratégicos para Microsoft 365 Enterprise:

- Aproveitar o conhecimento e a experiência coletiva, capacitando as pessoas a descobrir, compartilhar e dar andamento a arquivos, informações e ideias em toda a sua organização
- Trabalhar com segurança de qualquer lugar, a qualquer momento e em qualquer dispositivo para alcançar mais, mantendo um estilo de trabalho flexível
- Fornecer tranquilidade com controles e visibilidade para conformidade verificada no setor com padrões globais em conformidade
- Proteger informações e reduzir o risco de perda de dados
- Detectar e proteger contra o relatório de ameaças externas – Monitor e analisar atividade para reagir imediatamente para fornecer segurança da organização
- Proteger os usuários e suas contas
- Oferecer suporte à sua organização com privacidade e conformidade aprimoradas para atender ao RGPD (Regulamento Geral sobre a Proteção de Dados)
- Ficar atualizado e manter-se atualizado em seu software e dispositivos de desktop, reduzindo os riscos de segurança e maximizando a eficiência de TI

Para saber mais, confira [Transformação digital usando o Microsoft 365](http://transform.microsoft.com). 

>[!Note]
>Para implantar o Windows 10 Enterprise e o Office 365 ProPlus em conjunto e mudar para um [computador moderno](https://www.microsoft.com/microsoft-365/modern-desktop), confira o [Centro de Implantação de Computador Moderno](http://aka.ms/howtoshift).
>

## <a name="windows-10-deployment"></a>Implantação do Windows 10

Há várias maneiras que você pode implantar o Windows 10 Enterprise para sua organização. Aqui, focaremos em como você pode configurar e implantar uma imagem do Windows 10 Enterprise por meio desses cenários de implantação moderno.

| Cenário da implantação | Quando usá-lo |
|:--- |:--- |
| [Usando o System Center Configuration Manager como uma atualização in-loco](windows10-deploy-inplaceupgrade.md) | Selecione essa opção se você precisa atualizar o Windows 7 ou Windows 8.1 computadores para a <a href="https://aka.ms/windows-10-release-information" target="_blank">versão atual</a> do Windows 10 Enterprise e sua atualmente são gerenciados com o <a href="https://aka.ms/introtosccm" target="_blank">System Center Configuration Manager (ramificação atual)</a>. |
| [Usando o piloto automático do Windows](windows10-deploy-autopilot.md) | Selecione essa opção se você estiver configurando novos computadores Windows com Windows 10 Enterprise, versão 1703 ou pré-instaladas posteriormente. Os usuários finais será iniciar o programa de instalação usando a configuração desejada, inserindo o trabalho ou escola credenciais da conta. |

Se esses cenários de implantação não atender às necessidades da sua organização, poderá aprender sobre outros cenários e entender os recursos e limitações de cada nos [cenários de implantação do Windows 10](https://docs.microsoft.com/windows/deployment/windows-10-deployment-scenarios). Você também pode <a href="https://aka.ms/planforwin10deployment" target="_blank">Planejar a implantação do Windows 10</a> por conta própria.

Você pode aprender mais sobre o Windows 10 com estes artigos:

- [Página do produto do Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise)
- [Windows 10](https://docs.microsoft.com/windows/windows-10)
- [Implantar e atualizar o Windows 10](https://docs.microsoft.com/windows/deployment/)


## <a name="additional-services-and-features"></a>Recursos e serviços adicionais
Como parte da sua implantação do Windows 10 Enterprise, você pode adicionar esses recursos e serviços adicionais.

### <a name="windows-analytics"></a>Windows Analytics

Windows usa dados de diagnóstico para fornecer informações rica e acionáveis para ajudá-lo a obter ideias profundas em eficiência operacional e a integridade do Windows 10 dispositivos em seu ambiente.

* Atualizar preparação - preparação para a atualização ajudarão você a mover para Windows 10 e mantenha-se atualizado com novas atualizações de recurso do Windows 10. 
* Conformidade de atualização - conformidade de atualização está programada para o administrador de TI que deseja obter uma visão abrangente de todos os seus dispositivos do Windows 10, sem quaisquer requisitos de infraestrutura adicional.
* Integridade do dispositivo - você pode usar o dispositivo integridade detectar de maneira proativa e remediar problemas de impacto do usuário final.

Consulte [Visão geral de análise do Windows](https://docs.microsoft.com/windows/deployment/update/windows-analytics-overview) para obter mais informações.

### <a name="windows-security"></a>Segurança do Windows

Windows 10 fornece recursos para ajudar a proteger contra ameaças, ajuda você a proteger seus dispositivos e ajudar com controle de acesso. Com 10 do Windows, você tem recursos de segurança crítico proteger seu direito de dispositivo desde o início. Microsoft 365 E3 adiciona os recursos de segurança, como Windows Olá para negócios, controle de aplicativo do Windows Defender e proteção de informações do Windows. Com o Microsoft E5 de 365, você obtém todas a proteção de segurança do Microsoft 365 E3 além de recursos de segurança baseado em nuvem e a proteção de ameaça avançado do Windows Defender. 

Para saber mais sobre os recursos de segurança que você obtenha com Windows 10 Enterprise e get orientação sobre como você pode implantar, gerenciar, configurar e solucionar problemas de três recursos principais ecurity, consulte [etapa 5: recursos de segurança de implantar o Windows 10 Enterprise](windows10-enable-security-features.md).

## <a name="how-microsoft-does-microsoft-365-enterprise"></a>Como a Microsoft desenvolve o Microsoft 365 Enterprise

Para surgir dentro da Microsoft e saiba como a empresa planejados para, implantado e está gerenciando atualizações do Windows 10, consulte:

- [Preparo da organização para uma implantação perfeita do Windows 10](https://www.microsoft.com/itshowcase/windows10deployment?wt.mc_id=bmkg_itsc)
- [Adoção do Windows como serviço na Microsoft](https://www.microsoft.com/itshowcase/Article/Content/851/Adopting-Windows-as-a-service-at-Microsoft)
- [Implantar o Windows 10 na Microsoft como uma atualização in-loco](https://www.microsoft.com/itshowcase/Article/Content/668/Deploying-Windows-10-at-Microsoft-as-an-inplace-upgrade)
- [Implementação de autenticação segura do usuário com o Windows Hello para Empresas](https://www.microsoft.com/itshowcase/Article/Content/756/Implementing-strong-user-authentication-with-Windows-Hello-for-Business)
- [Implantação do Windows 10: dicas e truques da TI da Microsoft](https://www.microsoft.com/itshowcase/Article/Content/951/Windows-10-deployment-tips-and-tricks-from-Microsoft-IT) (vídeo)
- [A Proteção Avançada contra Ameaças do Windows Defender ajuda a detectar ameaças sofisticadas](https://www.microsoft.com/itshowcase/Article/Content/854/Windows-Defender-ATP-helps-detect-sophisticated-threats)
- [Proteção da empresa moderna com o Windows Defender e a Proteção Avançada contra Ameaças do Windows Defender](https://www.microsoft.com/itshowcase/Article/Content/903/Securing-the-modern-enterprise-with-Windows-Defender-and-Windows-Defender-ATP) (vídeo)

## <a name="how-contoso-did-microsoft-365-enterprise"></a>Como a Contoso desenvolveu o Microsoft 365 Enterprise

Consulte como a Contoso Corporation, uma empresa multinacional empresa fictícia, mas representativa, [implantado Windows 10 Enterprise](contoso-win10.md).

![](./media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a>Próxima etapa

|||
|:-------|:-----|
|![](./media/stepnumbers/Step1.png)| [Preparar sua organização para Windows 10 Enterprise](windows10-prepare-your-org.md) |
