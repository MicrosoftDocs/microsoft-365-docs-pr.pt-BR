---
title: Implantar a proteção de informações para regulamentações de privacidade de dados com o Microsoft 365
ms.author: bcarter
author: brendacarter
f1.keywords:
- NOCSH
manager: laurawi
ms.date: 06/09/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- M365solutions
ms.custom: ''
description: Configure a infraestrutura de segurança e serviço para proteger suas informações e aderir às regulamentações de privacidade de dados.
ms.openlocfilehash: 35ccfb21accd969c2a2cbdddde9a4ec1c7eeed64
ms.sourcegitcommit: b03a7ad0a80f8b839f40b8d396ab3a049491a12f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/10/2020
ms.locfileid: "44695098"
---
# <a name="deploy-information-protection-for-data-privacy-regulations-with-microsoft-365"></a>Implantar a proteção de informações para regulamentações de privacidade de dados com o Microsoft 365

Esta solução fornece orientações sobre como planejar e proteger dados pessoais armazenados nos serviços do Microsoft 365 e potencialmente sujeitas a regulamentações de privacidade de dados, como a regulamentação geral de proteção de dados da União Européia (RGPD). Esta solução se concentra nos recursos de conformidade e proteção de informações da Microsoft, a pontuação de conformidade da Microsoft e as ferramentas de avaliação aplicáveis para ajudá-lo a saber seus dados. 
 
Também são fornecidas informações adicionais sobre o uso de controles de proteção de identidade, dispositivo e ameaça da Microsoft para suas necessidades de privacidade de dados, bem como para descoberta de incidentes de dados e ferramentas de resposta. 

## <a name="organization-of-this-guidance-material"></a>Organização deste material de orientação

Para ajudá-lo a entender as ferramentas do Microsoft 365 disponíveis para identificar, gerenciar, controlar e monitorar dados pessoais sujeitos a uma ou mais normas relacionadas à privacidade, esta orientação é organizada em seções.
 
![Implantar a proteção de informações para regulamentações de privacidade de dados](../media/information-protection-deploy/information-protection-deploy-grid.png)

Cada uma dessas seções corresponde a um artigo separado nesta solução.

>[!Note]
>Se você já estiver familiarizado com suas obrigações de privacidade de dados e estiver em execução em um plano existente, convém se concentrar nas diretrizes de prevenção, proteção, retenção e investigação.

>[!Important]
>Seguir estas orientações não o fará necessariamente em conformidade com qualquer regulamentação de privacidade de dados, especialmente considerando o número de etapas necessárias que estão fora do contexto dos recursos. Você é responsável por garantir sua conformidade e consultar suas equipes jurídicas e de conformidade ou para buscar orientações e conselhos de terceiros especializados em conformidade.
>

## <a name="plan-assess-data-privacy-risks-and-identify-sensitive-items"></a>Plano: avaliar os riscos de privacidade de dados e identificar itens confidenciais 

Avaliar as normas e os riscos de privacidade de dados em que sua organização está sujeita é uma primeira etapa a ser executada antes de começar a implementar melhorias, incluindo as obtidas por meio da configuração do Microsoft 365. Isso pode incluir uma avaliação geral da prontidão ou identificação de tipos de informações confidenciais particulares que estão sujeitos aos controles normativos de que sua organização precisa estar em conformidade, bem como a ocorrência deles no seu ambiente Microsoft 365.

Para obter mais informações, consulte [avaliar riscos de privacidade de dados e identificar itens confidenciais](information-protection-deploy-assess.md).

## <a name="track-use-compliance-score-and-compliance-manager"></a>Track: usar a pontuação de conformidade e o gerente de conformidade 

A pontuação de conformidade e o gerente de conformidade oferecem um conjunto integrado de ferramentas disponíveis no portal de confiança do centro de administração de conformidade e serviços do Microsoft 365. Juntas, essas ferramentas oferecem uma capacidade interna de rastrear e gerenciar ações de melhorias gerais, bem como aquelas relacionadas a diversas regulamentações de privacidade de dados às quais você está sujeito.

As ferramentas também permitem que você utilize modelos de avaliação internos específicos para cada regulamentação, onde você pode rastrear itens de ação para cada modelo de avaliação selecionado, bem como exibir controles regulatórios específicos e relacioná-los a ações específicas.

Para saber mais, confira [usar o placar de conformidade e o Gerenciador de conformidade para gerenciar ações de melhoria](information-protection-deploy-compliance.md).

## <a name="prevent-use-identity-device-and-threat-protection-for-data-privacy-regulation"></a>Impedir: usar a proteção de identidade, dispositivo e ameaça para a regulamentação de privacidade de dados

A Microsoft 365 fornece vários recursos de proteção de identidade, dispositivo e ameaça que você pode usar para ajudar a cumprir a conformidade normativa da privacidade dos dados. 

Para obter mais informações, consulte [usar identidade, dispositivo e proteção contra ameaças para regulamentação de privacidade de dados](information-protection-deploy-identity-device-threat.md).

Este artigo descreve brevemente o que os regulamentos de privacidade de dados geralmente chamam nessas áreas e fornece uma lista de soluções do Microsoft 365 relacionadas, com links para mais informações para ajudá-lo a lidar com os requisitos de implementação. 

## <a name="protect-information-subject-to-data-privacy-regulation"></a>Proteger informações sujeitas à regulamentação de privacidade de dados

As regulamentações de privacidade de dados ditam vários controles de proteção de informações pessoais que podem ser empregados em seu ambiente, incluindo mais de 40 proteger os controles de informações entre apenas as quatro regulamentações de privacidade de dados em nosso conjunto de amostra de RGPD, lei de proteção para consumidores da Califórnia (CCPA), HIPAA-alta (lei de privacidade de assistência médica Estados Unidos) e o decreto de proteção

Para obter mais informações, consulte [proteger informações sujeitas à regulamentação de privacidade de dados em sua organização](information-protection-deploy-protect-information.md).

Este artigo apresenta os principais esquemas de controle que podem ser usados para atender às necessidades de proteção de informações para privacidade de dados em sua organização.

## <a name="retain-govern-information-subject-to-data-privacy-regulation"></a>Reter: controlar informações sujeitas à regulamentação de privacidade de dados

Os regulamentos de privacidade de dados chamam os controles de governança de informações pessoais que podem ser empregados no seu ambiente, incluindo mais de vinte e quatro controles nas quatro regulamentações de privacidade de dados em nosso conjunto de exemplos de RGPD, CCPA, HIPAA-alta e LGPD.

Para obter mais informações, consulte [governar informações sujeitas à regulamentação de privacidade de dados em sua organização](information-protection-deploy-govern.md).

Embora as regulamentações de privacidade de dados possam ser vagas em relação à governança de informações, &mdash; como retenção proposital, exclusão e arquivamento &mdash; Este artigo apresenta os esquemas de controle principal que você pode usar para a privacidade de dados da sua organização.

## <a name="investigate-monitor-and-respond-subject-to-data-privacy-regulation"></a>Investigue: monitorar e responder ao assunto para a regulamentação de privacidade de dados

Há recursos do Microsoft 365 disponíveis para ajudá-lo a monitorar, investigar e responder a incidentes de privacidade de dados em sua organização à medida que você opera recursos relacionados. 

Ter processos, procedimentos e outras documentações para cada um deles pode ser importante para demonstrar a conformidade com órgãos regulamentares.

Para obter mais informações, consulte [monitorar e responder a incidentes de privacidade de dados em sua organização](information-protection-deploy-monitor-respond.md).
