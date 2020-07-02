---
title: Pontuação de conformidade da Microsoft (visualização)
f1.keywords:
- NOCSH
ms.author: chvukosw
author: chvukosw
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: A pontuação de conformidade da Microsoft (visualização) ajuda as organizações a simplificar e automatizar avaliações de riscos e sugere ações recomendadas para ajudar a lidar com os riscos.
ms.openlocfilehash: 0cb8bd0b5aa39be2a9a6e706afa21bb7dc53eadb
ms.sourcegitcommit: 0650da0e54a2b484a3156b3aabe44397fbb38e00
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2020
ms.locfileid: "45016134"
---
# <a name="microsoft-compliance-score-preview"></a>Pontuação de conformidade da Microsoft (visualização)

**Neste artigo:** Saiba o que é a pontuação de conformidade, como ela ajuda a simplificar a forma como você gerencia a conformidade e como configurá-la para sua organização.

**O que há de novo:** O lançamento de junho de 2020 inclui novas funcionalidades para criar e gerenciar avaliações e para exibir os controles dentro da Pontuação de conformidade. Visite as [notas de versão da Pontuação de conformidade](compliance-score-release-notes.md) para ver as novidades na visualização pública da Pontuação de conformidade.

## <a name="what-is-compliance-score"></a>O que é a pontuação de conformidade

A [Pontuação de conformidade da Microsoft](https://compliance.microsoft.com/compliancescore) é um recurso de visualização no centro de conformidade da [Microsoft 365](microsoft-365-compliance-center.md) para ajudá-lo a entender a postura de conformidade da sua organização. Ele calcula uma pontuação baseada em risco medindo seu progresso em ações de conclusão que ajudam a reduzir os riscos relacionados à proteção de dados e aos padrões normativos.

Você pode usar a pontuação de conformidade como uma ferramenta para rastrear todas as avaliações de risco. Ele fornece recursos de fluxo de trabalho para ajudá-lo a concluir com eficiência as avaliações de riscos por meio de uma ferramenta comum.

Os usuários do [Gerenciador de conformidade](compliance-manager-overview.md) notarão que a pontuação de conformidade agora é um recurso autônomo com um design mais simples e fácil de usar para ajudar as organizações a gerenciar com mais facilidade a conformidade.

A página principal de Pontuação de conformidade é seu painel personalizado. Ele mostra sua pontuação atual, ajuda a ver o que precisa de atenção e orienta as ações para melhorar sua pontuação. Seu painel de Pontuação de conformidade terá a seguinte aparência:

![Pontuação de conformidade-painel](../media/compliance-score-dashboard.png "Painel de Pontuação de conformidade")

### <a name="simplified-compliance-management"></a>Gerenciamento de conformidade simplificado

A pontuação de conformidade ajuda a simplificar o gerenciamento de conformidade fornecendo:

- **Avaliações contínuas**: examina automaticamente seus ambientes Microsoft 365 para detectar e monitorar a eficácia dos controles de proteção de dados em seu sistema
- **Ações recomendadas**: oferece recomendações e orientações passo a passo sobre como implementar controles para maximizar sua pontuação
-  **Mapeamento de controle interno**: ajuda você a se manter atualizado com o panorama de conformidade em evolução, fornecendo uma estrutura de controle comum incorporada

> [!IMPORTANT]
> As recomendações da Pontuação de conformidade e do Gerente de conformidade não devem ser interpretadas como garantia de conformidade. Você pode avaliar e validar a eficácia dos controles de clientes por seu ambiente normativo. Esses serviços estão atualmente em versão prévia e sujeitos aos termos e condições nos [termos dos serviços online](https://go.microsoft.com/fwlink/?linkid=2108910). Confira também [orientações de licenciamento da Microsoft 365 para segurança e conformidade](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).

## <a name="relationship-to-compliance-manager"></a>Relação com o Gerenciador de conformidade

Considere a pontuação de conformidade como uma experiência simplificada do gerente de conformidade. Embora os dois existam como ferramentas distintas ainda integradas, a pontuação de conformidade facilita o monitoramento de sua postura geral de conformidade e a tomada de etapas para melhorá-lo.

A pontuação de conformidade compartilha o mesmo backend com o gerente de conformidade. Tudo o que você fizer em uma ferramenta será apresentado na outra ferramenta.

Algumas funcionalidades de avaliação e gerenciamento de modelos permanecem no gerente de conformidade durante a visualização pública. Recomendamos iniciar todas as atividades de gerenciamento de conformidade na pontuação de conformidade. Quando você chegar às funções tratadas pelo gerente de conformidade, vamos orientá-lo.

#### <a name="learn-more"></a>Saiba mais

[Entender a relação entre a pontuação de conformidade e o gerente de conformidade](compliance-score-release-notes.md#compliance-score-relationship-to-compliance-manager).

## <a name="understanding-your-score"></a>Noções básicas sobre sua pontuação

A pontuação de conformidade indica que você aponta para concluir ações executadas para cumprir uma regulamentação, padrão ou política. Cada ação tem um impacto diferente na sua pontuação, dependendo dos possíveis riscos envolvidos. Sua pontuação pode ajudar a priorizar a ação a ser focalizada para melhorar a postura geral de conformidade.

A pontuação de conformidade fornece uma pontuação inicial com base na linha de base de proteção de dados da Microsoft 365.  Essa linha de base é um conjunto de controles que inclui normas e padrões fundamentais para proteção de dados e governança de dados gerais. Essa linha de base desenha elementos primariamente da NIST CSF (National Institute of Standards and Technology cybersecurity Framework) e ISO (International Organization for Standardization), bem como do FedRAMP (programa de gerenciamento de riscos e autorização federal) e RGPD (regulamentação geral de proteção de dados da União Europeia).

A avaliação da linha de base da proteção de dados é usada para calcular sua pontuação inicial antes de configurar qualquer outra avaliação. Na sua primeira visita, a pontuação de conformidade já está coletando sinais de suas soluções 365 da Microsoft. Você verá rapidamente como sua organização está realizando em relação aos principais padrões e regulamentos de proteção de dados e veja as ações sugeridas de melhoria a serem tomadas.

Como cada organização tem necessidades específicas, a pontuação de conformidade depende de você configurar e gerenciar suas próprias avaliações para reduzir melhor os riscos. Por exemplo, se sua organização pertencer ao setor de serviços financeiros, talvez você queira adicionar a avaliação do FFIEC. Se sua organização pertencer ao setor de saúde, você poderá adicionar a avaliação HIPAA/alta tecnologia.

#### <a name="learn-more"></a>Saiba mais

[Entenda como a pontuação de conformidade é calculada e continuamente monitorada](compliance-score-methodology.md).

[Criar e gerenciar avaliações na pontuação de conformidade](compliance-score-assessments.md).

## <a name="key-components-controls-assessments-templates-improvement-actions"></a>Principais componentes: controles, avaliações, modelos e ações de melhoria

A pontuação de conformidade usa vários componentes para ajudá-lo a gerenciar suas atividades de conformidade. À medida que você usa a pontuação de conformidade para atribuir, testar e monitorar atividades de conformidade, é útil ter uma compreensão básica dos principais componentes: controles, avaliações, modelos e ações de melhoria.

### <a name="controls"></a>Controles

Um controle é um requisito de regulamentação, padrão ou política. Ele define como avaliar e gerenciar a configuração do sistema, o processo organizacional e as pessoas responsáveis por atender a um requisito específico de uma regulamentação, padrão ou política.

A pontuação de conformidade controla dois tipos de controles:

1. **Controles gerenciados pela Microsoft**: controles para serviços de nuvem da Microsoft, que a Microsoft é responsável por implementar
2. **Seus controles**: às vezes chamados de controles de cliente, estes são controles implementados e gerenciados pela sua organização

#### <a name="learn-more"></a>Saiba mais

[Monitorar o progresso dos seus controles](compliance-score-assessments.md#monitor-assessment-progress-and-controls).

### <a name="assessments"></a>Avaliações

Uma avaliação é o agrupamento de controles de uma regulamentação, padrão ou política específica. Concluir as ações em uma avaliação ajudá-lo a atender aos requisitos de um padrão, regulamento ou legislação. Por exemplo, você pode ter uma avaliação que, quando concluir todas as ações dentro dela, traz suas configurações do Microsoft 365 em linha com os requisitos ISO 27001.

As avaliações têm vários componentes:

- **Serviços no escopo**: o conjunto específico de serviços Microsoft aplicável à avaliação
- **Controles gerenciados**pela Microsoft: controles que a Microsoft implementa e testa
- **Seus controles**: controles que você gerencia
- **Pontuação de avaliação**: a porcentagem dos pontos obtidos por meio da conclusão de ações de aperfeiçoamento dentro dessa avaliação

Ao criar avaliações, você as atribuirá a um **grupo**. Você pode configurar grupos de qualquer forma que seja mais lógica para sua organização. Por exemplo, você pode agrupar avaliações por ano, padrão de conformidade, serviço, equipes dentro da sua organização ou alguma outra maneira. Depois de criar grupos, você pode [filtrar o painel de Pontuação de conformidade](compliance-score-setup.md#filtering-your-dashboard-view) para exibir sua pontuação por um ou mais grupos.

#### <a name="learn-more"></a>Saiba mais

[Criar e gerenciar avaliações na pontuação de conformidade](compliance-score-assessments.md).

### <a name="templates"></a>Modelos

A pontuação de conformidade fornece modelos que estão prontos para você criar avaliações rapidamente. Você pode modificar esses modelos para criar uma avaliação otimizada para suas necessidades. Você também pode criar uma avaliação personalizada desenvolvendo seu próprio modelo com seus próprios controles e ações. Por exemplo, você pode querer um modelo para cobrir um controle de processo de negócios interno ou um padrão de proteção de dados regionais que não esteja coberto por um de nossos modelos.

A criação de seus próprios modelos permite que você rastreie não apenas avaliações da nuvem da Microsoft, mas também qualquer outra avaliação de risco no escopo da sua organização.

#### <a name="learn-more"></a>Saiba mais

[Exibir os modelos disponíveis na pontuação de conformidade para compilar avaliações](compliance-score-templates.md).

[Obtenha instruções detalhadas para criar e modificar o Gerenciador de conformidade de modelos](working-with-compliance-manager.md#templates).

### <a name="improvement-actions"></a>Ações de melhoria

As ações de melhoria centralizam suas atividades de conformidade. Cada ação de melhoria fornece orientações detalhadas de implementação para ajudá-lo a se alinhar com regulamentos e padrões de proteção de dados. As ações podem ser atribuídas aos usuários em sua organização para executar o trabalho de implementação e teste. Você também pode armazenar documentação, anotações e registrar as atualizações de status na ação de melhoria.

#### <a name="learn-more"></a>Saiba mais

[Use ações de melhoria para gerenciar seu fluxo de trabalho de conformidade](compliance-score-improvement-actions.md).

## <a name="next-steps-set-up-and-customize"></a>Próximas etapas: configurar e personalizar

Saiba como entrar, definir permissões e funções, configurar atualizações de Pontuação seguras e personalizar o modo de exibição de painel na [configuração de Pontuação de conformidade](compliance-score-setup.md).

Em seguida, inicie a personalização da Pontuação de conformidade da sua organização [Configurando avaliações](compliance-score-assessments.md).