---
title: Criar e gerenciar avaliações no Microsoft Compliance Manager
f1.keywords:
- NOCSH
ms.author: v-jgriffee
author: jmgriffee
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Crie avaliações no Microsoft Compliance Manager para ajudá-lo a atender aos requisitos de regulamentos e certificações importantes para sua organização.
ms.openlocfilehash: 4530f8544834c672b3ae1ebb70625ffe8f2ae4ae
ms.sourcegitcommit: 46b77a41dfcc0ee80e2b89a7aa49e9bbe5deae5a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/26/2021
ms.locfileid: "53148933"
---
# <a name="build-and-manage-assessments-in-compliance-manager"></a>Criar e gerenciar avaliações no Gerenciador de Conformidade

**Neste artigo:** Saiba como personalizar o Gerenciador de Conformidade para sua organização criando e gerenciando **avaliações.** Este artigo orienta você sobre como criar avaliações, como organizá-las em **grupos,** trabalhar com **controles,** aceitar atualizações e exportar relatórios de **avaliação.**

## <a name="introduction-to-assessments"></a>Introdução às avaliações

O Gerenciador de Conformidade ajuda você a criar avaliações que avaliem sua conformidade com os regulamentos regionais e do setor que se aplicam à sua organização. As avaliações são criadas com base na estrutura de modelos de avaliação, que contêm os controles necessários, as ações de melhoria e as ações da Microsoft para concluir a avaliação. Configurar as avaliações mais relevantes para sua organização pode ajudá-lo a implementar políticas e procedimentos operacionais para limitar o risco de conformidade.

Todas as avaliações estão listadas na guia avaliações do Gerenciador de Conformidade. Saiba mais sobre [como filtrar sua exibição de avaliações e interpretar estados de status.](compliance-manager-setup.md#assessments-page)

> [!IMPORTANT]
> Os modelos disponíveis para sua organização para a criação de avaliações dependem do contrato de licenciamento. [Revise detalhes de licenciamento](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).

## <a name="data-protection-baseline-default-assessment"></a>Avaliação padrão da Linha de Base de Proteção de Dados

Para começar, **a** Microsoft fornece uma avaliação padrão no Gerenciador de Conformidade para a linha Microsoft 365 de proteção **de dados.** Essa avaliação de linha de base tem um conjunto de controles para os principais regulamentos e padrões para proteção de dados e governança geral de dados. Essa linha de base desenha elementos principalmente do NIST CSF (National Institute of Standards and Technology Cybersecurity Framework) e ISO (International Organization for Standardization), bem como do FedRAMP (Programa Federal de Gerenciamento de Riscos e Autorizações) e do RGPD (Regulamento Geral de Proteção de Dados da União Europeia).

Essa avaliação é usada para calcular sua pontuação inicial de conformidade na primeira vez que você vem ao Gerenciador de Conformidade, antes de configurar quaisquer outras avaliações. O Gerenciador de Conformidade coleta sinais iniciais de suas Microsoft 365 soluções. Você verá rapidamente como sua organização está se portando em relação aos principais padrões e regulamentos de proteção de dados e verá ações de melhoria sugeridas a executar.

O Gerenciador de Conformidade se torna mais útil à medida que você cria e gerencia suas próprias avaliações para atender às necessidades específicas da sua organização.

## <a name="understand-groups-before-creating-assessments"></a>Compreender grupos antes de criar avaliações

Ao criar uma avaliação, você precisará atribuí-la a um grupo. Os grupos são contêineres que permitem que você organize avaliações de uma maneira lógica para você, como por ano ou regulamentação, ou com base nas divisões ou geografias da sua organização. É por isso que recomendamos planejar uma estratégia de grupo antes de criar avaliações.

A seguir estão exemplos de dois grupos e suas avaliações subjacentes:

- **AVALIAÇÃO FFIEC IS 2020**
  - FFIEC IS
- **Avaliações de segurança e privacidade de dados**
  - ISO 27001:2013
  - ISO 27018:2014

Quando duas avaliações diferentes nas mesmas ações de melhoria de compartilhamento de grupo gerenciadas, todas as atualizações que você fizer para os detalhes ou status de implementação de uma ação serão sincronizadas automaticamente em todo o grupo. Essa sincronização permite implementar uma ação de melhoria e atender a vários requisitos simultaneamente.

### <a name="create-a-group"></a>Criar um grupo

Você pode criar um grupo ao criar uma nova avaliação. Os grupos não podem ser criados como entidades autônomas.

### <a name="what-to-know-when-working-with-groups"></a>O que saber ao trabalhar com grupos

- Um grupo deve conter pelo menos uma avaliação.
- Os nomes de grupo devem ser exclusivos em sua organização.
- Os grupos não têm propriedades de segurança. Todas as permissões estão associadas a avaliações.
- Depois de adicionar uma avaliação a um grupo, o grupo não pode ser alterado.
- Se você adicionar uma nova avaliação a um grupo existente, as informações comuns de avaliações nesse grupo serão copiadas para a nova avaliação.
- Controles de avaliação relacionados em avaliações diferentes dentro do mesmo grupo são atualizados automaticamente quando concluídos.
- Quando uma alteração é feita para uma melhoria que aparece em vários grupos, essa alteração é refletida em todas as instâncias dessa ação de melhoria.
- Os grupos podem conter avaliações para a mesma certificação ou regulamentação, mas cada grupo só pode conter uma avaliação para um par específico de certificação de produto. Por exemplo, um grupo não pode conter duas avaliações para Office 365 E NIST CSF. Um grupo pode conter várias avaliações para o mesmo produto somente se a certificação ou a regulamentação correspondente para cada uma delas for diferente.
- Excluir uma avaliação quebra a relação entre essa avaliação e o grupo.
- Os grupos não podem ser excluídos manualmente.

## <a name="create-assessments"></a>Criar avaliações

> [!NOTE]
> Somente os usuários que têm uma função de Administrador Global, Administração do Gerenciador de Conformidade ou Assessor do Gerenciador de Conformidade podem criar e modificar avaliações. Saiba mais sobre [funções e permissões.](compliance-manager-setup.md#set-user-permissions-and-assign-roles)

Para começar a criar avaliações, siga estas etapas.

1. Saiba para qual grupo você atribuirá sua avaliação ou esteja preparado para criar um novo para essa avaliação.

2. Abra o assistente de avaliação. Você pode acessar esse painel de sobrevoos de um dos dois locais:
    - Vá para a página **avaliações** no Gerenciador de Conformidade e selecione **Adicionar avaliação;** ou
    - Encontre o modelo que você deseja usar na guia modelos **de** avaliação, veja seus detalhes e selecione **Criar avaliação**. Isso preencherá o campo de seleção de modelo do assistente para você.

3. **Selecione um modelo**: Se você ainda não escolheu um modelo na etapa 2, escolha um modelo para servir como base para sua avaliação. Você verá a lista de modelos divididos em categorias incluídas e premium (consulte [Tipos de](compliance-manager-templates.md#template-availability-and-licensing) modelo para obter mais informações). Selecione o botão de opção ao lado do modelo escolhido e selecione **Próximo**.

4. **Nome e grupo:** De definir essas propriedades para identificar sua avaliação e atribuí-la a um grupo.
    - **Nome**: Insira um nome para sua avaliação no campo **Nome da** Avaliação. Os nomes de avaliação devem ser exclusivos em grupos. Se o nome da sua avaliação corresponde ao nome de outra avaliação em qualquer grupo, você receberá um erro solicitando que você crie um nome diferente.
    - **Grupo**: Atribua sua avaliação a um grupo. Você pode:
        - Selecione **Usar grupo existente para** atribuí-lo a um grupo que você já criou; ou
        - Selecione **Criar novo grupo** para criar um novo grupo e atribua essa avaliação a ele:
            - Determine um nome para seu grupo e insira-o no campo abaixo do botão de rádio.
            - Você pode **copiar dados de um grupo** existente , como detalhes e documentos de implementação e teste, selecionando as caixas apropriadas.

    Quando terminar, selecione **Next**.

5. **Revisar e concluir:** A última tela do assistente mostra o modelo, o nome e o grupo escolhidos para a avaliação. Você pode editar qualquer uma dessas configurações a partir dos links na tela, que o levam de volta às etapas relevantes no assistente. Quando estiver pronto, selecione **Criar avaliação**.

6. A próxima tela confirma que você criou com êxito sua nova avaliação. Selecione **Feito** para fechar o assistente e a página de detalhes da nova avaliação aparecerá na tela.

Se você vir uma tela **de Avaliação com** falha após selecionar **Criar avaliação,** selecione **Tentar** novamente para re-criar sua avaliação.

Você pode alterar o nome da sua avaliação depois de cria-la selecionando o botão **Editar** nome no canto superior direito da página de [detalhes da avaliação.](#monitor-assessment-progress-and-controls)

## <a name="monitor-assessment-progress-and-controls"></a>Monitorar o progresso da avaliação e os controles

Cada avaliação tem uma página de detalhes que fornece uma visão rápida do seu progresso na conclusão da avaliação. A página mostra seu progresso na conclusão de controles e o status de teste das principais ações de melhoria dentro desses controles.

### <a name="overview-tab"></a>Guia Visão geral

A guia visão geral contém um gráfico mostrando sua porcentagem para conclusão da avaliação. Este gráfico contém uma divisão de pontos de ações que você possui e pontos de ações pertencentes à Microsoft, para que você possa ver quantos pontos mais você precisa para concluir a avaliação.

As principais ações de melhoria para controles na avaliação são listadas na ordem do maior impacto potencial para ganhar pontos. O gráfico associado detalha o status de teste agregado de suas ações de melhoria para que você possa avaliar rapidamente o que foi testado e o que ainda precisa ser feito.

Para acessar ações de melhoria individuais, visite a guia **Controles** ou **a guia Suas ações de** melhoria.

### <a name="controls-tab"></a>Guia Controles

A guia controles exibe informações detalhadas para cada controle mapeado para a avaliação. Um **gráfico de divisão de status** de controle mostra o status dos controles por família, para que você possa ver rapidamente quais grupos de controles precisam de atenção.

Abaixo do gráfico, uma tabela lista informações detalhadas sobre cada controle dentro da avaliação. Os controles são agrupados pela família de controles. Expanda cada nome de família para revelar os controles individuais que ele contém. As informações listadas para cada controle incluem:

- **Título do controle**
- **Status**: reflete o status de teste das ações de melhoria no controle 
    - **Passadas** - todas as ações de melhoria têm um status de teste "passado", ou pelo menos uma é passada e o restante está "fora do escopo"
    -  **Falha** - pelo menos uma ação de melhoria tem um status de teste de "falha"
    - **Nenhum** - todas as ações de melhoria não foram testadas
    - **Fora do escopo** - todas as ações de melhoria estão fora do escopo para essa avaliação
    - **Em andamento** - as ações de melhoria têm um status diferente dos listados acima, que podem incluir "em andamento", "crédito parcial" ou "não detectado"
- **ID do controle**: o número de identificação do controle, atribuído por sua regulamentação, padrão ou política correspondente
- **Pontos atingidos**: o número de pontos ganhos ao concluir ações, do número total de pontos alcançáveis 
- **Suas ações**: o número de suas ações concluídas fora do número total de ações a serem realizadas
- **Ações da Microsoft**: o número de ações concluídas pela Microsoft 

Para exibir os detalhes de um controle, selecione-o em sua linha na tabela. A página de detalhes do controle mostra um gráfico indicando o status do teste das ações dentro desse controle. Uma tabela abaixo do gráfico mostra as principais ações de melhoria para esse controle.

Selecione uma ação de melhoria na lista para detalhar a página de detalhes da ação de melhoria. As páginas de detalhes mostram o status do teste, as notas de implementação e o início na solução recomendada.

### <a name="your-improvement-actions-tab"></a>Guia Ações de melhoria

A guia para suas ações de melhoria lista todos os controles na avaliação que são gerenciados pela sua organização. A barra de status detalha o status de teste agregado de suas ações de melhoria na avaliação para que você possa avaliar rapidamente o que foi testado e o que ainda precisa ser feito. Abaixo da barra está a lista completa de ações de melhoria e detalhes importantes, incluindo: status do teste, o número de pontos potenciais e ganhos, regulamentos e padrões associados, solução aplicável, tipo de ação e família de controle. Saiba mais sobre [como as ações contribuem para sua pontuação de conformidade.](compliance-score-calculation.md#action-types-and-points)

Selecione uma ação de aperfeiçoamento para exibir sua página de detalhes e selecione o link Iniciar **agora** para abrir a solução para tomar medidas.

### <a name="microsoft-actions-tab"></a>Guia Ações da Microsoft

A guia Ações da Microsoft lista todas as ações na avaliação gerenciadas pela Microsoft. A lista mostra os principais detalhes da ação, incluindo: status do teste, pontos que contribuem para sua pontuação geral de conformidade, regulamentos e padrões associados, solução aplicável, tipo de ação e família de controle. Selecione uma ação de melhoria para exibir sua página de detalhes.

Saiba mais sobre [como controles e ações de melhoria são controladas e pontuadas.](compliance-score-calculation.md)

## <a name="accept-updates-to-assessments"></a>Aceitar atualizações para avaliações

Quando uma atualização estiver disponível para uma avaliação, você verá uma notificação e terá a opção de aceitar a atualização ou adiá-la posteriormente.

### <a name="what-causes-an-update"></a>O que causa uma atualização

Uma atualização de avaliação ocorre quando há alterações de modelo subjacentes que impactam a pontuação. As alterações podem envolver o ajuste do mapeamento de controle ou outras diretrizes com base em alterações regulatórias ou alterações do produto. As atualizações de avaliação podem se originar da sua organização (como, quando um modelo personalizado é [modificado)](compliance-manager-templates.md#modify-a-template)e da Microsoft.

Se a Microsoft atualizar um modelo do Gerenciador de Conformidade que você estendeu, sua avaliação herdará essas atualizações depois de aceitá-las. Sua avaliação manterá os atributos adicionais que você aplicou à avaliação quando a estendeu.

Avaliações personalizadas que você cria não recebem atualizações de modelo da Microsoft. Avaliações personalizadas podem receber atualizações de ações de melhoria, mas quaisquer atualizações da Microsoft para controlar o mapeamento entre avaliações e ações de melhoria não se aplicam a modelos personalizados.

> [!NOTE]
> As atualizações para avaliações só se aplicam no nível do grupo. Se você tiver duas avaliações criadas a partir do mesmo modelo que existem em dois grupos diferentes, cada avaliação terá uma notificação de atualização pendente e você precisará aceitar a atualização para cada avaliação em seu respectivo grupo individualmente.

#### <a name="where-youll-see-assessment-update-notifications"></a>Onde você verá notificações de atualização de avaliação

A página de detalhes da avaliação também mostra **um rótulo de** atualização pendente ao lado da avaliação com uma atualização. Selecione essa avaliação para chegar à página de detalhes.

Uma mensagem próxima à parte superior da página de detalhes da avaliação mostra que uma atualização está disponível para essa avaliação. Selecione o **botão Revisar atualização** no banner para revisar as alterações específicas e aceitar ou adiar a atualização.

A página de detalhes da avaliação também pode listar ações de melhoria que tenham um **rótulo de** atualização pendente ao lado delas. Essas atualizações são para alterações específicas nas ações de melhoria em si e precisam ser aceitas separadamente. Visite [Aceitar atualizações para ações de melhoria](compliance-manager-improvement-actions.md#accepting-updates-to-improvement-actions) para saber mais.

#### <a name="review-update-to-accept-or-defer"></a>Revisar a atualização para aceitar ou adiar

Depois de **selecionar Revisar atualização** na página de detalhes da avaliação, um painel de sobremenu aparece no lado direito da tela. O painel de sobrevoos fornece os principais detalhes a seguir sobre a atualização pendente:

- O título do modelo
- Fonte da atualização (Microsoft, sua organização ou um usuário específico)
- A data em que a atualização foi criada
- Uma visão geral explicando a atualização
- Detalhes específicos sobre as alterações, incluindo o impacto na pontuação de conformidade, a quantidade de progresso na conclusão da avaliação e o número específico de alterações nas ações e controles de melhoria.

Selecionar o link **Modelo** Atualizado baixará um arquivo Excel que contém dados de controle para a versão do modelo com as atualizações pendentes. Selecionar o **link Modelo** Atual baixa um arquivo do modelo existente sem as alterações.

Para aceitar a atualização e fazer as alterações na sua avaliação, selecione **Aceitar atualização**. As alterações aceitas são permanentes.

Se você selecionar **Cancelar**, a atualização não será aplicada à avaliação. No entanto, você continuará a ver a notificação **de** atualização pendente até aceitar a atualização.

**Por que recomendamos aceitar atualizações**

Aceitar atualizações ajuda a garantir que você tenha as diretrizes mais atualizadas sobre como usar soluções e tomar as ações de melhoria apropriadas para ajudá-lo a atender aos requisitos da certificação em mãos.

**Por que você pode querer adiar uma atualização**

Se você estiver no meio da conclusão de uma avaliação, talvez queira garantir que tenha concluído o trabalho antes de aceitar uma atualização para a avaliação que poderia interromper o mapeamento de controle. Você pode adiar a atualização posteriormente selecionando **Cancelar** no painel do flyout de atualização de revisão.

## <a name="export-an-assessment-report"></a>Exportar um relatório de avaliação

Você pode exportar uma avaliação para um arquivo Excel para participantes de conformidade em sua organização ou para auditores externos e reguladores. Na página detalhes da avaliação, selecione o botão **Gerar relatório** próximo à parte superior da página, que cria um arquivo Excel que você pode salvar e compartilhar.

O relatório é um instantâneo da avaliação a partir da data e hora da exportação. Ele contém os detalhes dos controles gerenciados por você e pela Microsoft, incluindo o status da implementação, a data do teste e os resultados do teste.

## <a name="delete-an-assessment"></a>Excluir uma avaliação

A exclusão de uma avaliação remove-a da lista na página de avaliações. Observe estes pontos importantes sobre a exclusão de avaliações:

- **Excluir uma avaliação é permanente; você não pode obter de volta.** Se você quiser usar a mesma avaliação novamente, precisará re-crie-la.
- Se as ações de melhoria na avaliação não aparecerem em nenhuma outra avaliação, elas serão excluídas quando a avaliação for excluída.
- Recomendamos [exportar um relatório da](#export-an-assessment-report) avaliação antes de excluí-lo permanentemente.

Para excluir uma avaliação, siga as etapas abaixo:

1. Na página **avaliações,** selecione a avaliação que deseja excluir para abrir a página de detalhes dessa avaliação.

2. Selecione **Excluir avaliação** no canto superior direito da tela.

3. Uma janela aparecerá solicitando que você confirme se deseja excluir permanentemente a avaliação. Selecione **Excluir avaliação** para fechar a janela. Você obterá uma janela de confirmação de que sua avaliação foi excluída do Gerenciador de Conformidade.

Se você excluir a única avaliação em um grupo, esse grupo também será excluído do Gerenciador de Conformidade.

> [!NOTE]
> Não é possível excluir todas as avaliações. As organizações precisam de pelo menos uma avaliação para que o Gerenciador de Conformidade funcione corretamente. Se a avaliação que você deseja excluir for a única, adicione outra avaliação antes de excluir a outra avaliação.
