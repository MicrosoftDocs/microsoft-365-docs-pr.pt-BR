---
title: Implantar a proteção de informações para regulamentações de privacidade de dados com o Microsoft 365
ms.author: bcarter
author: brendacarter
f1.keywords:
- NOCSH
manager: laurawi
ms.date: 06/22/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- m365solution-infoprotection
- m365solution-overview
ms.custom: ''
description: Configure a infraestrutura de segurança e serviço para proteger suas informações e aderir às regulamentações de privacidade de dados.
ms.openlocfilehash: 9af0a113d9b0eb2cbca07fdf457cd8bb7db3e094
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/03/2020
ms.locfileid: "48842291"
---
# <a name="deploy-information-protection-for-data-privacy-regulations-with-microsoft-365"></a>Implantar a proteção de informações para regulamentações de privacidade de dados com o Microsoft 365

Sua organização pode estar sujeita às normas de privacidade de dados regionais que exigem que você proteja, gerencie e forneça direitos e controle sobre as informações pessoais armazenadas na sua infraestrutura de ti, incluindo tanto no local quanto na nuvem. O melhor exemplo de uma regulamentação de privacidade de dados é o RGPD (regulamentação geral de proteção de dados) da União Européia. A falha na conformidade com as regulamentações de privacidade de dados pode resultar em multas substanciais.

Exemplos de tipos de dados no Microsoft 365 incluem sessões de chat no Microsoft Teams, emails no Exchange e arquivos no SharePoint e no OneDrive. Esta solução fornece orientações sobre como avaliar riscos e identificar informações, proteger, controlar e responder a incidentes de privacidade de dados para dados pessoais armazenados nos serviços do Microsoft 365 que estão sujeitos às regulamentações de privacidade de dados.

![O que é proteção de informações para regulamentos de privacidade de dados](../media/information-protection-deploy/information-protection-data-privacy-regulations-overview.png)

Também são fornecidas informações adicionais sobre o uso dos controles de proteção de identidade, dispositivo e ameaça da Microsoft 365 para suas necessidades de privacidade de dados. 

Para atender aos critérios de proteção de informações para conformidade com as regulamentações de privacidade de dados, use estes recursos e recursos do Microsoft 365.

| Capcidade ou recurso | Descrição | Licenças |
|:-------|:-----|:-------|
| Gerenciador de Conformidade | Gerenciar atividades de conformidade normativa, obter uma pontuação geral da configuração atual de conformidade e encontrar recomendações para melhorias nessa ferramenta de avaliação de riscos baseada em fluxo de trabalho no centro de conformidade da Microsoft 365. | Microsoft 365 E3 e E5 |
| Microsoft defender para Office 365 | Proteja seus aplicativos e dados da Microsoft 365— como mensagens de email, documentos do Office e ferramentas de colaboração—de um ataque. | Microsoft 365 E3 e E5 | 
| Rótulos de confidencialidade | Classifique e proteja os dados da organização sem atrapalhar a produtividade e a capacidade de colaboração dos usuários, colocando rótulos com vários níveis de proteção em emails, arquivos ou sites. | Microsoft 365 E3 e E5 |
| Proteção contra Perda de Dados (DLP)  | Detectar, avisar e bloquear compartilhamento arriscado, inadvertido ou impróprio, como o compartilhamento de dados com informações pessoais, interna e externamente. | Microsoft 365 E3 e E5 | 
| Rótulos e políticas de retenção de dados | Implemente controles de governança de informações, como por quanto tempo manter os dados e os requisitos sobre o armazenamento de dados pessoais dos clientes, para estar em conformidade com as políticas da sua organização ou com as regulamentações de dados. | Microsoft 365 E3 e E5 |
| Criptografia de email | Envie e receba mensagens de email criptografadas entre as pessoas dentro e fora da sua organização que contenham dados regulados, como dados pessoais de clientes. | Microsoft 365 E3 e E5 |
||||

## <a name="organization-of-the-guidance-in-this-solution"></a>Organização das orientações desta solução

Para ajudá-lo a entender as ferramentas do Microsoft 365 disponíveis para identificar, gerenciar, controlar e monitorar dados pessoais sujeitos a uma ou mais normas relacionadas à privacidade, esta orientação é organizada em seções.
 
![Etapas para implementar a proteção de informações para regulamentações de privacidade de dados](../media/information-protection-deploy/information-protection-data-privacy-regulations-steps.png)

Cada uma dessas seções corresponde a um artigo separado nesta solução.

>[!Note]
>Se você já estiver familiarizado com suas obrigações de privacidade de dados e estiver em execução em um plano existente, convém se concentrar nas diretrizes de prevenção, proteção, retenção e investigação.

>[!Important]
>Seguir estas orientações não o fará necessariamente em conformidade com qualquer regulamentação de privacidade de dados, especialmente considerando o número de etapas necessárias que estão fora do contexto dos recursos. Você é responsável por garantir sua conformidade e consultar suas equipes jurídicas e de conformidade ou para buscar orientações e conselhos de terceiros especializados em conformidade.
>

## <a name="plan-assess-data-privacy-risks-and-identify-sensitive-items"></a>Plano: avaliar os riscos de privacidade de dados e identificar itens confidenciais

Avaliar as normas e os riscos de privacidade de dados em que sua organização está sujeita é uma primeira etapa a ser executada antes de começar a implementar melhorias, incluindo as obtidas por meio da configuração do Microsoft 365. Isso pode incluir uma avaliação geral da prontidão ou identificação de tipos de informações confidenciais particulares que estão sujeitos aos controles normativos de que sua organização precisa estar em conformidade, bem como a ocorrência deles no seu ambiente Microsoft 365.

Para obter mais informações, consulte [avaliar riscos de privacidade de dados e identificar itens confidenciais](information-protection-deploy-assess.md).

## <a name="track-run-risk-assessments-and-check-your-compliance-score"></a>Track: executar avaliações de risco e verificar sua pontuação de conformidade

O Gerenciador de conformidade, disponível no centro de conformidade da Microsoft 365, fornece uma capacidade interna de rastrear e gerenciar ações de melhorias gerais, bem como aquelas relacionadas a várias leis de privacidade de dados que se aplicam a você.

Aproveite os modelos de avaliação internos específicos para cada regulamentação, onde você pode rastrear itens de ação para cada modelo de avaliação selecionado, bem como para exibir controles regulatórios específicos e relacioná-los a ações específicas.

Para obter mais informações, consulte [usar o Gerenciador de conformidade para gerenciar ações de melhoria](information-protection-deploy-compliance.md).

## <a name="prevent-protect-personal-data"></a>Impedir: proteger dados pessoais

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

## <a name="investigate-monitor-investigate-and-respond-to-data-privacy-incidents"></a>Investigar: monitorar, investigar e responder a incidentes de privacidade de dados

Há recursos do Microsoft 365 disponíveis para ajudá-lo a monitorar, investigar e responder a incidentes de privacidade de dados em sua organização à medida que você opera recursos relacionados. 

Ter processos, procedimentos e outras documentações para cada um deles pode ser importante para demonstrar a conformidade com órgãos regulamentares.

Para obter mais informações, consulte [monitorar e responder a incidentes de privacidade de dados em sua organização](information-protection-deploy-monitor-respond.md).
