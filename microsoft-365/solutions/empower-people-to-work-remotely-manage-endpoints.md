---
title: Etapa 3. Implantar o gerenciamento de pontos de extremidade em seus dispositivos, PCs e outros pontos de extremidade
f1.keywords:
- NOCSH
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 06/03/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- remotework
- M365solutions
ms.custom: ''
description: Use o Microsoft Endpoint Manager para gerenciar seus dispositivos, PCs e outros pontos de extremidade.
ms.openlocfilehash: c7149295c24e5339e87db55998ec48fe9f0e9a93
ms.sourcegitcommit: 9195c83c725a7e6ed395ce0253304da54e2195f0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/04/2020
ms.locfileid: "44560488"
---
# <a name="step-3-deploy-endpoint-management-for-your-devices-pcs-and-other-endpoints"></a>Etapa 3. Implantar o gerenciamento de pontos de extremidade em seus dispositivos, PCs e outros pontos de extremidade

Com funcionários remotos, é necessário oferecer suporte a um número crescente de dispositivos pessoais. O gerenciamento de pontos de extremidade é uma abordagem de segurança baseada em políticas que exige que os dispositivos obedeçam a critérios específicos antes de receberem acesso aos recursos. O Microsoft Endpoint Manager oferece um ambiente de trabalho e recursos de gerenciamento modernos para manter seus dados seguros na nuvem e no local. 

O Endpoint Manager fornece serviços e ferramentas para gerenciar dispositivos móveis, computadores desktop, máquinas virtuais, dispositivos incorporados e servidores combinando os seguintes serviços que você já deve conhecer e estar usando.

![Os componentes para o gerenciamento de pontos de extremidade](../media/empower-people-to-work-remotely/endpoint-managment-step-grid.png)

## <a name="microsoft-intune"></a>Microsoft Intune

O Intune foi projetado para ajudá-lo a proteger os dados quando você não gerencia os dispositivos usados ​​para acessar os dados da organização. As políticas de proteção de aplicativos do Intune combinadas com o Acesso Condicional do Azure AD fornecem controle granular sobre dados em dispositivos móveis. O Intune também permite definir políticas abrangentes que permitem que apenas as pessoas certas, em condições certas, acessem os dados da sua empresa e garantam que os dados permaneçam protegidos, controlando como eles os usam no Office, no Outlook e em outros aplicativos móveis.

Para obter mais informações, confira a [visão geral do Microsoft Intune](https://docs.microsoft.com/intune/fundamentals/what-is-intune).

## <a name="configuration-manager"></a>Gerenciador de Configurações

O Gerenciador de Configurações é uma solução de gerenciamento local para gerenciar desktops, servidores e laptops que estão na sua rede ou baseada na Internet. Você pode habilitá-lo na nuvem para integrar-se ao Intune, Azure AD, Microsoft Defender ATP e outros serviços de nuvem. Use o Gerenciador de Configurações para implantar aplicativos, atualizações de software e sistemas operacionais. Você também pode monitorar a conformidade, consultar e agir sobre os clientes em tempo real e muito mais.

Para obter mais informações, confira a [visão geral do Gerenciador de Configurações](https://docs.microsoft.com/mem/configmgr/core/understand/introduction).

## <a name="co-management"></a>Co-gerenciamento

O co-gerenciamento combina seu investimento existente no Gerenciador de Configurações no local com a nuvem, usando o Intune e outros serviços de nuvem do Microsoft 365. Você escolhe se o Gerenciador de Configurações ou o Intune é a autoridade de gerenciamento dos sete grupos de cargas de trabalho diferentes.

Como parte do Endpoint Manager, o co-gerenciamento usa recursos de nuvem, incluindo Acesso Condicional. Você mantém algumas tarefas no local enquanto executa outras na nuvem com o Intune.

Para mais informações, confira esta [visão geral do co-gerenciamento](https://docs.microsoft.com/mem/configmgr/comanage/overview).

## <a name="desktop-analytics"></a>Análise de Área de Trabalho

A Análise de Área de Trabalho é um serviço baseado em nuvem que se integra ao Gerenciador de Configurações e fornece informações e inteligência para que você possa tomar decisões informadas sobre seus clientes Windows. Ela combina dados da sua organização com dados agregados de milhões de dispositivos conectados aos serviços de nuvem da Microsoft. Com a Análise de Área de Trabalho, você pode criar um inventário de aplicativos em execução em sua organização, avaliar a compatibilidade de aplicativos com as atualizações de recursos mais recentes do Windows 10, identificar problemas de compatibilidade e receber sugestões de mitigação com base em informações de dados ativadas em nuvem, criar grupos piloto que representam todo aplicativo e o estado do driver em um conjunto mínimo de dispositivos e implantar o Windows 10 ao piloto e em dispositivos gerenciados por produção.

Para obter mais informações, confira a [visão geral da Análise de Área de Trabalho](https://docs.microsoft.com/mem/configmgr/desktop-analytics/overview).

## <a name="windows-autopilot"></a>Windows Autopilot

O Windows Autopilot é uma plataforma de implantação do Windows de autoatendimento e sem intervenções. Inclui um conjunto de tecnologias usadas para instalar e pré-configurar novos dispositivos, preparando-os para uso produtivo. Você também pode usar o Windows Autopilot para redefinir, redirecionar e recuperar dispositivos. Esta solução permite que um departamento de TI alcance o que foi exposto acima com pouca ou nenhuma infraestrutura a ser gerenciada, com um processo fácil e simples. Da perspectiva do usuário, são necessárias apenas algumas operações simples para deixar seu dispositivo pronto para uso. Da perspectiva do profissional de TI, a única interação necessária do usuário final é conectar-se a uma rede e verificar suas credenciais.

Para obter mais informações, confira a [visão geral do Windows Autopilot](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot).

## <a name="admin-technical-resources-for-endpoint-management"></a>Recursos técnicos de administração para o gerenciamento de pontos de extremidade

- [Vídeo da parte 3 sobre o gerenciamento de dispositivos Windows 10 para funcionários remotos](https://resources.techcommunity.microsoft.com/enabling-remote-work/#security)
- [Vídeo da parte 5 sobre o gerenciamento de áreas de trabalho e navegadores do usuário para funcionários remotos](https://resources.techcommunity.microsoft.com/enabling-remote-work/#security)
- [Implantar uma infraestrutura de mobilidade para o Microsoft 365](https://docs.microsoft.com/microsoft-365/enterprise/mobility-infrastructure)
- [Como registrar diferentes tipos de dispositivos para gerenciamento de dispositivos móveis (MDM)](https://docs.microsoft.com/mem/intune/enrollment/device-enrollment)
- [Como educar seus usuários finais sobre o Microsoft Intune](https://docs.microsoft.com/mem/intune/fundamentals/end-user-educate)
 
## <a name="results-of-step-3"></a>Resultados da Etapa 3

Você está usando o conjunto de recursos e funcionalidades do Endpoint Manager para gerenciar dispositivos móveis, computadores desktop, máquinas virtuais, dispositivos incorporados e servidores.

## <a name="next-step"></a>Próxima etapa

Continue com a [Etapa 4](empower-people-to-work-remotely-teams-productivity-apps.md) para fornecer acesso remoto a aplicativos e serviços locais.
