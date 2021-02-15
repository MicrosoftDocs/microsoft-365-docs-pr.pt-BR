---
title: Implantar a proteção de informações para regulamentos de privacidade de dados com o Microsoft 365
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
description: Configure a infraestrutura de segurança e serviços para proteger suas informações e cumprir as regulamentações de privacidade de dados.
ms.openlocfilehash: 9af0a113d9b0eb2cbca07fdf457cd8bb7db3e094
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/03/2020
ms.locfileid: "48842291"
---
# <a name="deploy-information-protection-for-data-privacy-regulations-with-microsoft-365"></a>Implantar a proteção de informações para regulamentos de privacidade de dados com o Microsoft 365

Sua organização pode estar sujeita a regulamentos regionais de privacidade de dados que exigem que você proteja, gerencie e forneça direitos e controle sobre informações pessoais armazenadas em sua infraestrutura de TI, incluindo no local e na nuvem. O melhor exemplo de uma regulamentação de privacidade de dados é o RGPD (Regulamento Geral sobre a Proteção de Dados) da União Europeia. A não conformidade com as regulamentações de privacidade de dados pode resultar em multas substanciais.

Exemplos dos tipos de dados no Microsoft 365 incluem sessões de chat no Microsoft Teams, emails no Exchange e arquivos no SharePoint e no OneDrive. Esta solução fornece orientações sobre como avaliar riscos e identificar informações, proteger, reger e responder a incidentes de privacidade de dados para dados pessoais armazenados nos serviços do Microsoft 365 sujeitos às regulamentações de privacidade de dados.

![O que é a proteção de informações para regulamentos de privacidade de dados](../media/information-protection-deploy/information-protection-data-privacy-regulations-overview.png)

Informações adicionais também são fornecidas sobre o uso de controles de identidade, dispositivo e proteção contra ameaças do Microsoft 365 para suas necessidades de privacidade de dados. 

Para atender aos critérios de proteção de informações para conformidade com as regulamentações de privacidade de dados, use esses recursos e funcionalidades do Microsoft 365.

| Capcidade ou recurso | Descrição | Licenças |
|:-------|:-----|:-------|
| Gerente de Conformidade | Gerencie as atividades de conformidade regulamentar, receba uma pontuação geral da configuração de conformidade atual e encontre recomendações para melhorar essa ferramenta de avaliação de risco baseada em fluxo de trabalho no centro de conformidade do Microsoft 365. | Microsoft 365 E3 e E5 |
| Microsoft Defender para Office 365 | Proteja seus aplicativos e dados da Microsoft 365— como mensagens de email, documentos do Office e ferramentas de colaboração—de um ataque. | Microsoft 365 E3 e E5 | 
| Rótulos de confidencialidade | Classifique e proteja os dados da organização sem atrapalhar a produtividade e a capacidade de colaboração dos usuários, colocando rótulos com vários níveis de proteção em emails, arquivos ou sites. | Microsoft 365 E3 e E5 |
| Proteção contra Perda de Dados (DLP)  | Detectar, avisar e bloquear compartilhamento arriscado, inadvertido ou impróprio, como o compartilhamento de dados com informações pessoais, interna e externamente. | Microsoft 365 E3 e E5 | 
| Rótulos e políticas de retenção de dados | Implemente controles de governança de informações, como por quanto tempo manter os dados e os requisitos sobre o armazenamento de dados pessoais dos clientes, para estar em conformidade com as políticas da sua organização ou com as regulamentações de dados. | Microsoft 365 E3 e E5 |
| Criptografia de email | Envie e receba mensagens de email criptografadas entre as pessoas dentro e fora da sua organização que contenham dados regulados, como dados pessoais de clientes. | Microsoft 365 E3 e E5 |
||||

## <a name="organization-of-the-guidance-in-this-solution"></a>Organização das diretrizes nesta solução

Para ajudá-lo a entender as ferramentas do Microsoft 365 disponíveis para identificar, gerenciar, controlar e monitorar dados pessoais sujeitos a uma ou mais regulamentações relacionadas à privacidade, essas diretrizes são organizadas em seções.
 
![Etapas para implementar a proteção de informações para regulamentos de privacidade de dados](../media/information-protection-deploy/information-protection-data-privacy-regulations-steps.png)

Cada uma dessas seções corresponde a um artigo separado nesta solução.

>[!Note]
>Se você já estiver familiarizado com suas obrigações de privacidade de dados e estiver executando em um plano existente, talvez você queira se concentrar nas orientações de Impedir, Proteger, Reter e Investigar.

>[!Important]
>Seguir essas diretrizes não necessariamente fará com que você fique em conformidade com qualquer regulamentação de privacidade de dados, considerando especialmente o número de etapas necessárias que estão fora do contexto dos recursos. Você é responsável por garantir sua conformidade e consultar suas equipes jurídicas e de conformidade ou buscar orientação e conselhos de terceiros especializados em conformidade.
>

## <a name="plan-assess-data-privacy-risks-and-identify-sensitive-items"></a>Plano: Avaliar os riscos de privacidade de dados e identificar itens confidenciais

Avaliar os regulamentos e os riscos de privacidade de dados aos quais sua organização está sujeita é uma primeira etapa importante antes de começar a implementar melhorias, incluindo os que podem ser alcançados por meio da configuração do Microsoft 365. Isso pode incluir uma avaliação de prontidão geral ou a identificação de determinados tipos de informações confidenciais sujeitos a controles regulatórios que sua organização precisa cumprir, bem como a ocorrência deles em seu ambiente do Microsoft 365.

Para obter mais informações, consulte [Avaliar os riscos de privacidade de dados e identificar itens confidenciais.](information-protection-deploy-assess.md)

## <a name="track-run-risk-assessments-and-check-your-compliance-score"></a>Acompanhar: executar avaliações de risco e verificar sua pontuação de conformidade

O Gerenciador de Conformidade, disponível no centro de conformidade do Microsoft 365, oferece a você uma capacidade integrada de acompanhar e gerenciar ações de melhoria em geral, bem como aquelas relacionadas a várias regulamentações de privacidade de dados que se aplicam a você.

Aproveite os modelos de avaliação internos específicos para cada regulamentação, onde você pode acompanhar itens de ação para cada modelo de avaliação selecionado, bem como exibir controles regulamentar específicos e relacioná-los a ações específicas.

Para obter mais informações, [consulte Usar o Gerenciador de Conformidade para gerenciar ações de melhoria.](information-protection-deploy-compliance.md)

## <a name="prevent-protect-personal-data"></a>Impedir: proteger dados pessoais

O Microsoft 365 fornece vários recursos de proteção contra ameaças, dispositivos e identidades que você pode usar para ajudar a cumprir a conformidade regulamentar de privacidade de dados. 

Para obter mais informações, consulte Usar identidade, dispositivo e [proteção contra ameaças para a regulamentação de privacidade de dados.](information-protection-deploy-identity-device-threat.md)

Este artigo descreve resumidamente o que as regulamentações de privacidade de dados geralmente chamam nessas áreas e fornece uma listagem das soluções relacionadas do Microsoft 365, com links para obter mais informações para ajudá-lo a atender a quaisquer requisitos de implementação. 

## <a name="protect-information-subject-to-data-privacy-regulation"></a>Proteger informações sujeitas à regulamentação de privacidade de dados

Os regulamentos de privacidade de dados ditam uma série de controles de proteção de informações pessoais que podem ser empregados em seu ambiente, incluindo mais de quarenta controles de Proteção de Informações em apenas quatro regulamentos de privacidade de dados em nosso conjunto de amostras de GDPR, Lei de Proteção do Consumidor da Califórnia (CCPA), HIPAA-HITECH (lei de privacidade de saúde dos Estados Unidos) e a Lei de Proteção de Dados do Brasil (LGPD).

Para obter mais informações, [consulte Proteger informações sujeitas à regulamentação de privacidade de dados em sua organização.](information-protection-deploy-protect-information.md)

Este artigo aborda os principais esquemas de controle que podem ser usados para lidar com as necessidades de proteção de informações para privacidade de dados em sua organização.

## <a name="retain-govern-information-subject-to-data-privacy-regulation"></a>Reter: Governe as informações sujeitas à regulamentação de privacidade de dados

As regulamentações de privacidade de dados chamam controles de governança de informações pessoais que podem ser empregados em seu ambiente, incluindo mais de vinte e quatro controles em todos os quatro regulamentos de privacidade de dados em nosso conjunto de amostras de RGPD, CCPA, HIPAA-HITECH e LGPD.

Para obter mais informações, [consulte Govern information subject to data privacy regulation in your organization.](information-protection-deploy-govern.md)

Embora as regulamentações de privacidade de dados possam ser vagas em relação à governança de informações, como retenção, exclusão e arquivamento proposital, este artigo estabelece os principais esquemas de controle que você pode usar para atender às necessidades de governança de informações para privacidade de dados em sua &mdash; &mdash; organização.

## <a name="investigate-monitor-investigate-and-respond-to-data-privacy-incidents"></a>Investigar: monitorar, investigar e responder a incidentes de privacidade de dados

Há recursos do Microsoft 365 disponíveis para ajudá-lo a monitorar, investigar e responder a incidentes de privacidade de dados em sua organização à medida que você operacionaliza os recursos relacionados. 

Ter processos, procedimentos e outras documentações para cada um deles pode ser importante para demonstrar a conformidade com órgãos regulamentadores.

Para obter mais informações, [consulte Monitorar e responder a incidentes de privacidade de dados em sua organização.](information-protection-deploy-monitor-respond.md)
