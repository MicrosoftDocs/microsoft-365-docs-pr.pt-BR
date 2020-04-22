---
title: Infraestrutura do Windows 10 Enterprise para o Microsoft 365 Enterprise
description: Fornece uma orientação de alto nível sobre as etapas de que você precisa para implantar o Windows 10 Enterprise em PCs como parte do Microsoft 365 Enterprise.
keywords: Microsoft 365, Microsoft 365 Enterprise, documentação do Microsoft 365, Windows 10 Enterprise, implantação
author: greg-lindsay
localization_priority: Normal
ms.collection: M365-modern-desktop
audience: microsoft-business
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.date: 08/28/2019
f1.keywords:
- NOCSH
ms.author: greglin
ms.openlocfilehash: 53c38ba2e915cd439c8d7629bc7f9cd56ebc8647
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2020
ms.locfileid: "43636670"
---
# <a name="phase-3-windows-10-enterprise"></a>Fase 3: Windows 10 Enterprise

![Fase 3: Windows 10 Enterprise](../media/deploy-foundation-infrastructure/win10enterprise_icon.png)

O Microsoft 365 Enterprise inclui o Windows 10 Enterprise, que oferece as ferramentas para fazer mais e permanecer protegido. Windows 10 Enterprise:

- O **é integrado para simplificar** a sua capacidade de aproveitar a nuvem para ajudar a reduzir a complexidade do gerenciamento do atual ambiente de dispositivos de ti modernos, não importa o tamanho.
- A **segurança inteligente** é a versão mais segura do Windows, com recursos de segurança inteligente projetados para trabalhar juntos para proteger melhor sua organização.
- **Permite a criatividade e o trabalho em equipe** – desbloqueia a criatividade e o trabalho em equipe para fornecer a experiência mais produtiva que os usuários e vão adorar.

Você precisará entender as diferentes maneiras de implantar o sistema operacional Windows 10 e escolher o correto para sua organização. Dependendo da sua assinatura do Microsoft 365 Enterprise, há também os serviços do Windows 10 e os recursos de segurança que você precisará configurar para aproveitar ao máximo o Windows 10.

>[!Note]
>Para implantar os aplicativos do Windows 10 Enterprise e do Microsoft 365 para empresas juntos e mudar para uma [área de trabalho moderna](https://www.microsoft.com/microsoft-365/modern-desktop), consulte o [centro de implantação de área de trabalho moderna](https://aka.ms/howtoshift).
>

## <a name="windows-10-deployment"></a>Implantação do Windows 10

Há várias maneiras de implantar o Windows 10 Enterprise para sua organização. Aqui, vamos nos concentrar em como você pode configurar e implantar uma imagem do Windows 10 Enterprise por meio desses cenários de implantação modernos.

| Cenário da implantação | Quando usá-la |
|:--- |:--- |
| [Usando o Microsoft Endpoint Configuration Manager como uma atualização in-loco](windows10-deploy-inplaceupgrade.md) | Selecione esta opção se você precisar atualizar computadores com Windows 7 ou Windows 8,1 para a <a href="https://aka.ms/windows-10-release-information" target="_blank">versão atual</a> do Windows 10 Enterprise e seus computadores estiverem atualmente gerenciados com o <a href="https://docs.microsoft.com/configmgr/core/understand/introduction" target="_blank">Gerenciador de configurações (ramificação atual)</a>. |
| [Usando o Windows AutoPilot](windows10-deploy-autopilot.md) | Selecione essa opção se estiver configurando novos computadores Windows que tenham o Windows 10 Enterprise, versão 1703 ou posterior pré-instalado. Os usuários finais iniciarão a instalação usando a configuração desejada inserindo suas credenciais de conta corporativa ou de estudante. |

Se esses cenários de implantação não atenderem às necessidades da sua organização, você poderá aprender sobre outros cenários e entender os recursos e as limitações de cada um nos [cenários de implantação do Windows 10](https://docs.microsoft.com/windows/deployment/windows-10-deployment-scenarios). Você também pode <a href="https://aka.ms/planforwin10deployment" target="_blank">planejar a implantação do Windows 10</a> por conta própria.

Você pode saber mais sobre o Windows 10 com estes artigos:

- [Página do produto do Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise)
- [Windows 10](https://docs.microsoft.com/windows/windows-10)
- [Implantar e atualizar o Windows 10](https://docs.microsoft.com/windows/deployment/)


## <a name="additional-services-and-features"></a>Serviços e recursos adicionais
Como parte de sua implantação do Windows 10 Enterprise, você pode adicionar esses serviços e recursos adicionais.

### <a name="windows-analytics"></a>Windows Analytics

O Windows usa dados de diagnóstico para fornecer informações ricas e acionáveis para ajudá-lo a obter ideias profundas sobre a eficiência operacional e a integridade de dispositivos Windows 10 em seu ambiente.

* Preparação para atualização-preparação para atualização ajudará você a migrar para o Windows 10 e ficar atualizado com as novas atualizações de recursos do Windows 10. 
* Update Compliance-Update conformidade é direcionado para o administrador de ti que deseja obter uma visão holística de todos os seus dispositivos Windows 10, sem requisitos de infraestrutura adicionais.
* Integridade do dispositivo-você pode usar a integridade do dispositivo para detectar e corrigir problemas de impacto do usuário final de forma proativa.

Consulte [visão geral do Windows Analytics](https://docs.microsoft.com/windows/deployment/update/windows-analytics-overview) para obter mais informações.

### <a name="windows-security"></a>Segurança do Windows

O Windows 10 fornece recursos para ajudar a proteger contra ameaças, ajudá-lo a proteger seus dispositivos e a ajudar no controle de acesso. Com o Windows 10, você obtém recursos de segurança críticos que protegem o seu dispositivo diretamente do início. O Microsoft 365 E3 adiciona recursos de segurança como o Windows Hello para empresas, controle de aplicativos do Windows Defender e proteção de informações do Windows. Com o Microsoft 365 e5, você obtém toda a proteção do Microsoft 365 E3 Security Plus e dos recursos de segurança baseados em nuvem e proteção avançada contra ameaças do Microsoft defender. 

Para saber mais sobre os recursos de segurança obtidos com o Windows 10 Enterprise e obter orientação sobre como implantar, gerenciar, configurar e solucionar problemas de três recursos de segurança principais, consulte [etapa 5: implantar recursos de segurança do Windows 10 Enterprise](windows10-enable-security-features.md).

## <a name="how-microsoft-does-microsoft-365-enterprise"></a>Como a Microsoft desenvolve o Microsoft 365 Enterprise

Inspecione dentro da Microsoft e saiba como a empresa [implantou o Windows 10 Enterprise e está usando autenticação forte, Intune e Microsoft defender ATP](https://www.microsoft.com/itshowcase/deploying-and-managing-microsoft-365#primaryR6).

## <a name="how-contoso-did-microsoft-365-enterprise"></a>Como a Contoso desenvolveu o Microsoft 365 Enterprise

Veja como a Contoso Corporation, uma empresa multinacional fictícia, mas representativa, [implantou o Windows 10 Enterprise](contoso-win10.md).

![A Contoso Corporation](../media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a>Próxima etapa

|||
|:-------|:-----|
|![Etapa 1](../media/stepnumbers/Step1.png)| [Preparar sua organização para o Windows 10 Enterprise](windows10-prepare-your-org.md) |
