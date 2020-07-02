---
title: Personalizar a pontuação de conformidade da Microsoft com avaliações
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
description: Projetar a pontuação de conformidade da Microsoft criando Avaliações para ajudá-lo a gerenciar a conformidade da sua organização.
ms.openlocfilehash: 45a5e76aa4f6581146ded510f75d772c202751ee
ms.sourcegitcommit: 3ddcf08e8deec087df1fe524147313f1cb12a26d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2020
ms.locfileid: "45023304"
---
# <a name="customize-compliance-score-preview-with-assessments"></a>Personalizar a pontuação de conformidade (visualização) com avaliações

**Neste artigo:** Saiba como personalizar a pontuação de conformidade configurando as **avaliações**prontas para usar. Leia como modificar o **modelo** para uma avaliação e criar suas próprias avaliações personalizadas para atender às necessidades da sua organização. Este artigo também explica como organizar as avaliações em **grupos**, trabalhar com **controles**e exportar **relatórios**de avaliação.

## <a name="introduction-to-assessments"></a>Introdução às avaliações

A pontuação de conformidade ajuda você a gerenciar a conformidade com as avaliações das normas e certificações que se aplicam à sua organização. As avaliações são agrupamentos de controles de uma regulamentação, padrão ou política específica. A pontuação de conformidade facilita o acompanhamento do controle da conformidade, fornecendo avaliações prontas para uso que abrangem uma variedade de normas e certificações regionais e de setores.

Cada avaliação é criada a partir de um modelo, que serve como uma estrutura contendo os controles e ações de melhoria necessárias para concluir a avaliação. Configurar as avaliações mais relevantes para a sua organização ajuda a garantir que você está implementando políticas e procedimentos operacionais que podem limitar seu risco de conformidade.

Todas as avaliações estão listadas na página avaliações. [Saiba mais](compliance-score-setup.md#assessments-page) sobre como filtrar a exibição de suas avaliações e interpretar os Estados de status.

## <a name="data-protection-baseline-default-assessment"></a>Avaliação padrão da linha de base da proteção de dados

Para começar, a Microsoft fornece uma avaliação **padrão** em Pontuação de conformidade para você que contém a linha de base de proteção de dados do Microsoft 365. Essa linha de base é um conjunto de controles que inclui normas e padrões fundamentais para proteção de dados e governança de dados gerais. Essa linha de base desenha elementos primariamente da NIST CSF (National Institute of Standards and Technology cybersecurity Framework) e ISO (International Organization for Standardization), bem como do FedRAMP (programa de gerenciamento de riscos e autorização federal) e RGPD (regulamentação geral de proteção de dados da União Europeia).

Essa avaliação é usada para calcular sua pontuação inicial na primeira vez que você chegar à pontuação de conformidade, antes de configurar qualquer outra avaliação. A pontuação de conformidade coleta os sinais iniciais de suas soluções da Microsoft 365. Você verá rapidamente como sua organização está realizando em relação aos principais padrões e regulamentos de proteção de dados e veja as ações sugeridas de melhoria a serem tomadas.

Como cada organização tem necessidades específicas, a pontuação de conformidade depende de você configurar e gerenciar suas próprias avaliações para ajudar a minimizar e reduzir o risco da maneira mais abrangente possível.

## <a name="assessment-creation-overview"></a>Visão geral da criação da avaliação

Há três maneiras de configurar avaliações:

1. Escolha uma avaliação pronto para usar.
2. Modificar o modelo de uma avaliação para atender às suas necessidades.
3. Crie sua própria avaliação personalizada.

Os usuários devem conter uma função de administrador global, administrador de conformidade, administrador de dados de conformidade ou administrador de segurança para criar ou modificar avaliações. Saiba mais sobre [funções e permissões](compliance-score-setup.md#set-user-permissions-and-assign-roles).

> [!NOTE]
> Todas as avaliações criadas ou modificadas na pontuação de conformidade também serão refletidas no Gerenciador de conformidade. Saiba mais sobre a [relação entre a pontuação de conformidade e o gerente de conformidade](compliance-score.md#relationship-to-compliance-manager).

### <a name="ready-to-use-assessments"></a>Avaliações prontas para uso

Iniciar sua jornada de conformidade, escolhendo entre a seleção da Pontuação de conformidade de [modelos](compliance-score-templates.md) para a criação de avaliações. Os modelos contêm os controles e as ações de melhoria necessárias para cada avaliação específica. Os modelos da Pontuação de conformidade cobrem regulamentações e certificações que se alinham a indústrias, regiões e padrões comuns de proteção de dados, como RGPD e ISO 27001.

**Para configurar uma avaliação**, escolha um dos modelos quando começar [a criar a avaliação no assistente](#create-an-assessment).

### <a name="modify-the-template-of-an-assessment"></a>Modificar o modelo de uma avaliação

Você pode modificar modelos de Pontuação de conformidade para avaliações a fim de atender melhor às necessidades da sua organização. Por exemplo, se você geralmente precisa estar em conformidade com o HIPAA, mas exigir proteção adicional de dados ou controles de segurança, você pode fazer o nosso modelo HIPAA e adicionar seus próprios campos personalizados para criar uma nova avaliação que monitore seu progresso das formas de que você precisa. Durante a visualização pública, você precisará ir para o Gerenciador de conformidade para modificar modelos.

**Para modificar o modelo de uma avaliação**, siga estas instruções:

1. Exiba a lista de [modelos](compliance-score-templates.md) disponíveis na pontuação de conformidade para determinar qual deles você deseja modificar.
2. Consulte as [instruções do gerente de conformidade para personalizar um modelo usando o processo de extensão](working-with-compliance-manager.md#customize-a-template-through-the-extension-process).
3. Depois de criar o modelo e importá-lo para o Gerenciador de conformidade, você poderá criar sua nova avaliação na pontuação de conformidade. Siga o processo de criação de sua avaliação usando o [Assistente de criação de avaliação](#create-an-assessment).

> [!NOTE]
> Saiba mais sobre a [relação entre a pontuação de conformidade e o gerente de conformidade](compliance-score.md#relationship-to-compliance-manager) durante a visualização pública.

### <a name="create-your-own-custom-assessment"></a>Criar sua própria avaliação personalizada

Você pode criar sua própria avaliação totalmente a partir do zero para acompanhar precisamente o que sua organização precisa. Assim como o processo de modificação descrito acima, criar sua própria avaliação exige que você primeiro crie seu próprio modelo para a avaliação no Gerenciador de conformidade.

**Para criar sua própria avaliação personalizada**, siga estas instruções:

1. Leia como [criar seu próprio modelo no Gerenciador de conformidade](working-with-compliance-manager.md#create-your-own-template-and-import-it-into-compliance-manager).
2. Depois de criar o modelo e importá-lo para o Gerenciador de conformidade, você poderá criar sua nova avaliação na pontuação de conformidade. Siga o processo de criação de sua avaliação usando o [Assistente de criação de avaliação](#create-an-assessment).

## <a name="understand-groups-before-creating-assessments"></a>Entender grupos antes de criar avaliações

Antes de criar ou modificar avaliações, é importante entender como os grupos funcionam. Ao criar uma avaliação, você precisará atribuí-la a um grupo durante esse processo. Portanto, recomendamos planejar uma estratégia de agrupamento para suas avaliações antes de criar avaliações.

### <a name="what-are-groups"></a>O que são grupos

Os grupos são contêineres que permitem organizar avaliações. Você pode agrupar avaliações de uma forma que seja lógica para você, como por ano ou regulamento, ou com base nas divisões ou geografias da sua organização. Veja a seguir exemplos de dois grupos e suas avaliações subjacentes:

- **O FFIEC é avaliações de 2020**
  - Office 365 + FFIEC é
  - Intune + FFIEC é
- **Avaliações de privacidade e segurança de dados**
  - Office 365 + ISO 27001:2013
  - Office 365 + ISO 27018:2014

Quando duas avaliações diferentes no mesmo grupo ações de melhorias de compartilhamento são gerenciadas por você, todas as atualizações feitas nos detalhes ou no status da implementação da ação serão automaticamente sincronizadas com a mesma ação em qualquer outra avaliação do grupo. Essa sincronização permite implementar uma ação de melhoria e atender a vários requisitos em várias regulamentações.

### <a name="how-to-create-a-group"></a>Como criar um grupo

Você cria um grupo durante o processo de [criação de uma nova avaliação](#create-an-assessment).

Os grupos não podem ser criados como entidades autônomas; um grupo deve conter pelo menos uma avaliação. Para criar um grupo, você deve primeiro criar uma avaliação para colocar no grupo.

### <a name="what-to-know-when-working-with-groups"></a>O que saber ao trabalhar com grupos

- Os nomes de grupos devem ser exclusivos dentro da sua organização.
- Grupos não têm propriedades de segurança. Todas as permissões são associadas a avaliações.
- Após adicionar uma avaliação a um grupo, o agrupamento não pode ser alterado.
- Controles de avaliação relacionados em avaliações diferentes no mesmo grupo são atualizados automaticamente quando concluído.
- Se você adicionar uma nova avaliação a um grupo existente, as informações comuns de avaliações nesse grupo serão copiadas para a nova avaliação.
- Os grupos podem conter Avaliações para a mesma certificação ou regulamentação, mas cada grupo só pode conter uma avaliação para um par específico de certificação de produto. Por exemplo, um grupo não pode conter duas avaliações para o Office 365 e o NIST CSF. Um grupo pode conter várias avaliações para o mesmo produto apenas se a certificação ou regulamentação correspondente de cada um for diferente.
- A exclusão de uma apuração interrompe a relação entre essa avaliação e o grupo.
- Não é possível excluir grupos.
- Quando uma alteração é feita em uma melhoria que aparece em vários grupos, essa alteração é refletida em todas as instâncias dessa ação de aprimoramento.

## <a name="create-an-assessment"></a>Criar uma avaliação

Para criar uma avaliação na pontuação de conformidade, siga as etapas abaixo:

1. Na página avaliações, selecione **Adicionar avaliação**. Um assistente de avaliação será exibido em um painel de submenu grande.

2. **Selecione um modelo:** Escolha um modelo para servir como base para a avaliação. Você pode escolher um modelo pronto para usar ou um modelo que tenha modificado ou criado. Selecione o botão de opção ao lado do modelo escolhido e, em seguida, selecione **Avançar**.

> [!NOTE]
> Confira [instruções para criar e modificar modelos](working-with-compliance-manager.md#templates), um processo tratado no gerente de conformidade.

3. **Nome e Grupo:** Insira um nome para a avaliação no campo **nome da avaliação** . Os nomes de avaliação devem ser exclusivos nos grupos. Se o nome de sua avaliação corresponder ao nome de outra avaliação em um determinado grupo, você receberá um erro solicitando que você crie um nome diferente.

4. Atribua sua avaliação a um grupo. Você pode:
    - Selecione **usar grupo existente** para atribuí-lo a um grupo que você já criou; ou
    - Selecione **criar novo grupo** para criar um novo grupo e atribuir essa avaliação a ele. Determine um nome para o seu grupo e insira-o no campo abaixo do botão de opção.

5. **Revisar e concluir:** A última tela do assistente mostra o modelo, nome e grupo escolhido para a avaliação. Você pode editar qualquer uma dessas configurações dos links na tela, que o levará de volta às etapas relevantes no assistente. Quando estiver satisfeito com as configurações, selecione **criar avaliação**.

6. A próxima tela confirma que você criou com êxito sua nova avaliação. Selecione **concluído** para fechar o assistente e a página de detalhes da nova avaliação aparecerá na tela.

Se você vir uma **falha na** tela de avaliação após selecionar **criar avaliação**, selecione **tentar novamente** recriar sua avaliação.

## <a name="delete-an-assessment"></a>Excluir uma avaliação

A exclusão de uma avaliação a remove da lista na página avaliações. **A exclusão de uma avaliação é permanente; Não é possível obtê-lo novamente.** Se você quiser a mesma avaliação novamente, ele deve ser recriado do zero. Se as ações de melhoria na avaliação não aparecerem em qualquer outra avaliação, elas serão excluídas quando a avaliação for excluída. É recomendável exportar um relatório da avaliação antes de excluí-lo permanentemente.

Para excluir uma avaliação, siga as etapas abaixo:

1. Na página avaliações, selecione a avaliação que você deseja excluir para abrir a página detalhes da avaliação.
2. Selecione **excluir avaliação** no canto superior direito da tela.
3. Uma janela será exibida solicitando que você confirme se deseja excluir permanentemente a avaliação. Selecione **excluir avaliação** para fechar a janela. Você receberá uma janela de confirmação de que sua avaliação foi excluída da Pontuação de conformidade.

Se você excluir a única avaliação em um grupo, esse grupo também será excluído da Pontuação de conformidade.

## <a name="monitor-assessment-progress-and-controls"></a>Monitorar o progresso e os controles da avaliação

Cada avaliação tem uma página de detalhes que oferece uma visão geral de seu progresso ao concluir a avaliação. A página mostra o andamento da conclusão dos controles e o status do teste das ações de aprimoramento de chave nesses controles.

### <a name="overview-tab"></a>Guia Visão geral

A guia Visão geral contém um gráfico mostrando sua porcentagem em direção à conclusão da avaliação. Este gráfico contém uma divisão de pontos de ações que você possui e aponta de ações de propriedade da Microsoft, para que você possa ver quantos pontos você precisa para concluir a avaliação.

As principais ações de aprimoramento para controles na avaliação são listadas em ordem de maior impacto potencial para ganhar pontos. O gráfico associado detalha o status de teste agregado de suas ações de aprimoramento, para que você possa avaliar rapidamente o que foi testado e o que ainda precisa ser feito.

Para acessar ações de melhorias individuais, vá para a guia controles.

### <a name="controls-tab"></a>Guia Controles

A guia controles exibe informações detalhadas para cada controle mapeado para a avaliação. Um gráfico de **detalhamento de status de controle** mostra o status dos controles por família, para que você possa ver rapidamente quais agrupamentos de controles precisam de atenção.

Sob o gráfico, uma tabela lista informações detalhadas sobre cada controle na avaliação. Os controles são agrupados pela família de controle. Expanda cada nome de família para revelar os controles individuais que ele contém. As informações listadas para cada controle incluem:

- **Título do controle**
- **Status**: reflete o status do teste das ações de melhoria dentro do controle 
    - **Passed** -todas as ações de aperfeiçoamento têm um status de teste de "Passed", ou pelo menos um é passado e o restante estão "fora do escopo"
    -  **Falha** -pelo menos uma ação de melhoria tem um status de teste de "falha"
    - **None** -todas as ações de aperfeiçoamento não foram testadas
    - **Fora do escopo** -todas as ações de melhoria estão fora do escopo desta avaliação
    - **Em andamento** – as ações de melhoria têm um status diferente daqueles listados acima, que podem incluir "em andamento", "crédito parcial" ou "não detectado"
- **ID de controle**: o número de identificação do controle, atribuído por sua regulamentação, padrão ou política correspondente
- **Pontos alcançados**: o número de pontos obtidos por meio da conclusão de ações, do número total de pontos atingíveis 
- **Suas ações**: o número de ações concluídas do número total de ações a serem realizadas
- **Ações da Microsoft**: o número de ações concluídas pela Microsoft 

Para exibir os detalhes de um controle, selecione-o na sua linha na tabela. A página detalhes do controle mostra um gráfico que indica o status do teste das ações dentro desse controle. Uma tabela abaixo do gráfico mostra as principais ações de aperfeiçoamento para esse controle.

Selecione uma ação de aprimoramento na lista para analisar a página de detalhes da ação de aprimoramento. As páginas de detalhes mostram o status do teste, as notas de implementação e o lançamento na solução recomendada.

#### <a name="learn-more"></a>Saiba mais
[Entenda como as ações de controles e melhorias são rastreadas e pontuadas por Pontuação de conformidade.](compliance-score-methodology.md)

## <a name="export-an-assessment-report"></a>Exportar um relatório de avaliação

Você pode exportar uma avaliação para um arquivo do Excel para stakeholders de conformidade em sua organização ou para auditores externos e reguladores [seguindo estas instruções](working-with-compliance-manager.md#reports). Você precisará visitar o gerente de conformidade para exportar o relatório.

O relatório é um instantâneo da avaliação a partir da data e hora da exportação. Ele contém os detalhes de controles gerenciados por você e pela Microsoft, incluindo o status da implementação, data de teste, resultados de teste e links para documentos de evidência carregados.