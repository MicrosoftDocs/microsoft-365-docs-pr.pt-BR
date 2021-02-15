---
title: Gerenciador de Conformidade da Microsoft
f1.keywords:
- NOCSH
ms.author: chvukosw
author: chvukosw
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-compliancemanager
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: O Gerenciador de Conformidade da Microsoft ajuda as organizações a simplificar e automatizar as avaliações de risco e sugere ações recomendadas para ajudar a lidar com os riscos.
ms.openlocfilehash: 7bff6a2a7a150a08b98fe7a92cd71d266df9fda7
ms.sourcegitcommit: 20d1158c54a5058093eb8aac23d7e4dc68054688
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2020
ms.locfileid: "49376542"
---
# <a name="microsoft-compliance-manager"></a>Gerenciador de Conformidade da Microsoft

**Neste artigo:** Saiba o que é o Gerenciador de Conformidade, como ele ajuda a simplificar a conformidade e reduzir o risco e seus principais componentes.

## <a name="whats-new-the-ga-release-of-compliance-manager"></a>Novidades: a versão GA do Gerenciador de Conformidade

O Gerenciador de Conformidade agora está geralmente disponível (GA) como uma solução de gerenciamento de conformidade de ponta a ponta dentro do centro de conformidade [do Microsoft 365.](microsoft-365-compliance-center.md) Com esta versão, o Gerenciador de Conformidade conclui a transição de seu local anterior no Portal de Confiança do Serviço da Microsoft. O Gerenciador de Conformidade agora também está disponível para clientes moderados da Comunidade Governamental dos EUA (GCC) e GCC High.

O que começou como a visualização pública da Pontuação de Conformidade evoluiu para uma ferramenta centralizada com recursos de gerenciamento de conformidade aprimorados e maior facilidade de uso.  A versão GA traz uma coleção maior de avaliações pré-criadas para ajudar você a dimensionar suas atividades de conformidade.

**Saiba mais sobre a versão GA:**
- Nossas [perguntas frequentes o](compliance-manager-faq.md) explicam com mais detalhes sobre a evolução.
- Leia sobre aprimoramentos de recursos ga [nesta postagem de blog.](https://aka.ms/compliancemanager/GAblog)

Assista ao vídeo abaixo para saber como o Gerenciador de Conformidade pode ajudar a simplificar como sua organização gerencia a conformidade:
<br>
<br>
>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4FGYZ]

## <a name="what-is-compliance-manager"></a>O que é o Gerenciador de Conformidade

[O Gerenciador de Conformidade](https://compliance.microsoft.com/compliancemanager) da Microsoft é um recurso no centro de conformidade do [Microsoft 365](microsoft-365-compliance-center.md) que ajuda você a gerenciar os requisitos de conformidade da sua organização com mais facilidade e conveniência. O Gerenciador de Conformidade pode ajudá-lo durante toda a jornada de conformidade, desde fazer inventário dos riscos de proteção de dados até gerenciar a complexidade da implementação de controles, manter-se atualizado com regulamentos e certificações e relatar aos auditores.

O Gerenciador de Conformidade ajuda a simplificar a conformidade e reduzir o risco fornecendo:

- Avaliações pré-criadas para normas e regulamentos comuns do setor e regionais, ou avaliações personalizadas para atender às suas necessidades exclusivas de conformidade (as avaliações disponíveis dependem do seu contrato de licenciamento; [saiba mais](https://go.microsoft.com/fwlink/?linkid=2132371)).

- Recursos de fluxo de trabalho para ajudá-lo a concluir com eficiência suas avaliações de risco por meio de uma única ferramenta.

- Orientações passo a passo detalhadas sobre as ações de melhoria sugeridas para ajudá-lo a cumprir os padrões e regulamentos mais relevantes para sua organização. Para ações gerenciadas pela Microsoft, você verá detalhes de implementação e resultados de auditoria.

- Uma pontuação de conformidade baseada em risco para ajudá-lo a entender a postura de conformidade medindo seu progresso na conclusão das ações de melhoria.

O painel do Gerenciador de Conformidade mostra sua pontuação de conformidade atual, ajuda você a ver o que precisa de atenção e orienta você a principais ações de melhoria. Veja a seguir um exemplo da aparência do seu painel do Gerenciador de Conformidade:

![Gerenciador de Conformidade – painel](../media/compliance-manager-dashboard.png "Painel do Gerenciador de Conformidade")

## <a name="understanding-your-compliance-score"></a>Noções básicas sobre a pontuação de conformidade

O Gerenciador de Conformidade concede pontos por concluir ações de melhoria tomadas para atender a uma regulamentação, padrão ou política e combina esses pontos em uma pontuação geral de conformidade. Cada ação tem um impacto diferente na sua pontuação, dependendo dos riscos potenciais envolvidos. Sua pontuação de conformidade pode ajudar a priorizar em qual ação se concentrar para melhorar a postura de conformidade geral.

O Gerenciador de Conformidade fornece uma pontuação inicial com base na linha de base de proteção de dados do Microsoft 365. Esta linha de base é um conjunto de controles que inclui os principais regulamentos e padrões de proteção de dados e governança geral de dados.

##### <a name="learn-more"></a>Saiba mais

[Entenda como sua pontuação de conformidade é calculada.](compliance-score-calculation.md)

[Saiba como trabalhar com ações de melhoria.](compliance-manager-improvement-actions.md)

## <a name="key-elements-controls-assessments-templates-improvement-actions"></a>Principais elementos: controles, avaliações, modelos, ações de melhoria

O Gerenciador de Conformidade usa vários elementos de dados para ajudá-lo a gerenciar suas atividades de conformidade. À medida que você usa o Gerenciador de Conformidade para atribuir, testar e monitorar atividades de conformidade, é útil ter uma compreensão básica dos principais elementos: controles, avaliações, modelos e ações de melhoria.

### <a name="controls"></a>Controles

Um controle é um requisito de uma regulamentação, padrão ou política. Ele define como você avalia e gerencia a configuração do sistema, o processo organizacional e as pessoas responsáveis por atender a um requisito específico de uma regulamentação, padrão ou política.

O Gerenciador de Conformidade acompanha os seguintes tipos de controles:

1. **Controles gerenciados pela Microsoft:** controles para os serviços de nuvem da Microsoft, que a Microsoft é responsável pela implementação
2. **Seus controles:** às vezes chamados de controles gerenciados pelo cliente, esses são controles implementados e gerenciados pela sua organização
3. **Controles compartilhados:** esses são os controles que sua organização e a Microsoft compartilham a responsabilidade pela implementação

##### <a name="learn-more"></a>Saiba mais

[Monitore o progresso dos controles.](compliance-manager-assessments.md#monitor-assessment-progress-and-controls)

[Saiba como o Gerenciador de Conformidade avalia continuamente os controles.](compliance-score-calculation.md#how-compliance-manager-continuously-assesses-controls)

### <a name="assessments"></a>Avaliações

Uma avaliação é o grupo de controles de uma regulamentação, padrão ou política específica. Concluir as ações em uma avaliação ajuda você a atender aos requisitos de um padrão, regulamentação ou lei. Por exemplo, você pode ter uma avaliação que, ao concluir todas as ações dentro dela, ajuda a colocar suas configurações do Microsoft 365 de acordo com os requisitos da ISO 27001.

As avaliações têm vários componentes:

- **Serviços no escopo:** o conjunto específico de serviços Microsoft aplicáveis à avaliação
- **Controles gerenciados pela Microsoft:** controles dos serviços de nuvem da Microsoft, que a Microsoft implementa em seu nome
- **Seus controles:** às vezes chamados de controles gerenciados pelo cliente, são controles implementados e gerenciados pela sua organização
- **Controles compartilhados:** esses são os controles que sua organização e a Microsoft compartilham a responsabilidade pela implementação
- **Pontuação de** avaliação: mostra seu progresso na atingir o total de pontos possíveis de ações dentro da avaliação gerenciadas pela sua organização e pela Microsoft

Ao criar avaliações, você as atribuirá a um grupo. Você pode configurar grupos da maneira que for mais lógica para sua organização. Por exemplo, você pode agrupar avaliações por ano de auditoria, região, solução, equipes em sua organização ou de alguma outra forma. Depois de criar grupos, você pode [filtrar o painel](compliance-manager-setup.md#filtering-your-dashboard-view) do Gerenciador de Conformidade para exibir sua pontuação por um ou mais grupos.

##### <a name="learn-more"></a>Saiba mais

[Crie e gerencie avaliações no Gerenciador de Conformidade.](compliance-manager-assessments.md)

### <a name="templates"></a>Modelos

O Gerenciador de Conformidade fornece modelos para ajudá-lo a criar avaliações rapidamente. Você pode modificar esses modelos para criar uma avaliação otimizada para suas necessidades. Você também pode criar uma avaliação personalizada criando um modelo com seus próprios controles e ações. Por exemplo, você pode querer que um modelo abranger um controle de processo empresarial interno ou um padrão de proteção de dados regional que não seja coberto por um dos nossos mais de 150 modelos de avaliação pré-criado.

##### <a name="learn-more"></a>Saiba mais

[Exibir a lista de modelos de avaliação fornecidos pelo Gerenciador de Conformidade.](compliance-manager-templates-list.md)

[Obter instruções detalhadas para criar e modificar modelos para avaliações.](compliance-manager-templates.md)

### <a name="improvement-actions"></a>Ações de melhoria

As ações de melhoria ajudam a centralizar suas atividades de conformidade. Cada ação de melhoria fornece orientações recomendadas que se destinam a ajudá-lo a se alinhar com os regulamentos e padrões de proteção de dados. Ações de melhoria podem ser atribuídas aos usuários em sua organização para executar o trabalho de implementação e teste. Você também pode armazenar a documentação, as anotações e as atualizações de status do registro dentro da ação de melhoria.

##### <a name="learn-more"></a>Saiba mais

[Use ações de aperfeiçoamento para gerenciar seu fluxo de trabalho de conformidade.](compliance-manager-improvement-actions.md)

[Saiba como as ações impactam sua pontuação de conformidade.](compliance-score-calculation.md#action-types-and-points)

## <a name="supported-languages"></a>Idiomas compatíveis

O Gerenciador de Conformidade está disponível nos seguintes idiomas:

- Inglês
- Bahasa indonésio
- Bahasa malaio
- Chinês (simplificado)
- Chinês (tradicional)
- Tcheco
- Dinamarquês
- Holandês
- Finlandês
- Francês
- Alemão
- Hebraico
- Húngaro
- Italiano
- Japonês
- Coreano
- Norueguês
- Polonês
- Português (Brasil)
- Russo
- Espanhol
- Sueco
- Tailandês
- Turco

## <a name="next-steps-set-up-and-customize"></a>Próximas etapas: configurar e personalizar

Saiba como entrar, atribuir permissões e funções, definir configurações e personalizar o modo de exibição do painel em [Começar com o Gerenciador de Conformidade.](compliance-manager-setup.md)

Em seguida, comece a personalizar o Gerenciador de Conformidade para ajudá-lo a cumprir os padrões do setor mais importantes para sua organização, [configurando avaliações.](compliance-manager-assessments.md)