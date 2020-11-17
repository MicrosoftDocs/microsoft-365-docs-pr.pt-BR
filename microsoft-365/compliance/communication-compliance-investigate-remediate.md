---
title: Investigar e corrigir alertas de conformidade em comunicações
description: Investigue e corrija os alertas de conformidade de comunicação no Microsoft 365.
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.SupervisoryReview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
- MOE150
ms.openlocfilehash: f214c1fcfa8a68695ca0c32a9807972a71ba7612
ms.sourcegitcommit: e7bf23df4852b78912229d1d38ec475223597f34
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "49087156"
---
# <a name="investigate-and-remediate-communication-compliance-alerts"></a>Investigar e corrigir alertas de conformidade em comunicações

Depois de configurar suas políticas de conformidade de comunicação, você começará a receber alertas no centro de conformidade da Microsoft 365 para problemas de mensagens que correspondam às suas condições de política. Siga as instruções do fluxo de trabalho aqui para investigar e corrigir problemas de alerta.

## <a name="investigate-alerts"></a>Investigar alertas

A primeira etapa para investigar problemas detectados por suas políticas é rever alertas de conformidade de comunicação no centro de conformidade da Microsoft 365. Há várias áreas na área de solução de conformidade de comunicação para ajudá-lo a investigar rapidamente os alertas, dependendo de como você prefere exibir o agrupamento de alertas:

- **Página política de conformidade de Comunicação**: quando você entra no [https://compliance.microsoft.com](https://compliance.microsoft.com) usando credenciais para uma conta de administrador na sua organização do Microsoft 365, selecione **conformidade de comunicação** para exibir a página **política** de conformidade de comunicação. Esta página exibe as políticas de conformidade de comunicação configuradas para sua organização do Microsoft 365 e links para os modelos de política recomendados. Cada política listada inclui a contagem de alertas que precisam de revisão, o número de itens escalonados e resolvidos e o status atual da política. Selecionar uma política exibe todos os alertas pendentes para correspondências com a política, selecione um alerta específico para iniciar a página de detalhes da política e para iniciar ações de correção.
- **Alertas**: Navegue até alertas de **conformidade de comunicação**  >  **Alerts** para exibir os últimos 30 dias de alertas agrupados por correspondências de política. Este modo de exibição permite ver rapidamente quais políticas de conformidade de comunicação estão gerando a maioria dos alertas ordenados por severidade. Para iniciar ações de correção, selecione a política associada ao alerta para iniciar a página de **detalhes da política** . Na página **detalhes da política** , você pode revisar um resumo das atividades na **página Visão geral** , examinar e agir em mensagens de alerta na página **pendente** ou examinar o histórico de alertas fechados na página **resolvida** .
- **Relatórios**: Navegue até relatórios de **conformidade de comunicação**  >  **Reports** para exibir widgets de relatório de conformidade de comunicação. Cada widget fornece uma visão geral das atividades e status de conformidade de comunicação, incluindo o acesso a informações mais profundas sobre correspondências de política e ações de correção.

### <a name="using-filters"></a>Usando filtros

A próxima etapa é classificar as mensagens de modo que seja mais fácil investigar os alertas. Na página **detalhes da política** , a conformidade de comunicação oferece suporte à filtragem de vários níveis para vários campos de mensagem para ajudá-lo a investigar e examinar rapidamente as mensagens com correspondências de política. A filtragem está disponível para itens pendentes e resolvidos para cada política configurada. Você pode configurar consultas de filtro para uma política ou configurar e salvar consultas de filtro padrão e personalizadas para uso em cada política específica. Após configurar campos para um filtro, você verá os campos de filtro exibidos na parte superior da fila de mensagens de alerta que você pode configurar para valores de filtro específicos.

Para obter uma lista completa dos filtros e detalhes do campo, consulte [Filters](communication-compliance-feature-reference.md#filters) no artigo de referência do recurso.

#### <a name="to-configure-a-filter"></a>Para configurar um filtro

1. Entre [https://compliance.microsoft.com](https://compliance.microsoft.com) usando as credenciais de uma conta de administrador na sua organização do Microsoft 365.

2. No centro de conformidade da Microsoft 365, vá para **conformidade de comunicação**.

3. Selecione a guia **políticas** e, em seguida, selecione uma política de investigação, clique duas vezes para abrir a página **política** .

4. Na página **política** , selecione a guia **pendente** ou **resolvida** para exibir os itens para filtragem.

5. Selecione o controle **filtros** para abrir a página **filtros** de detalhes.

6. Selecione uma ou mais caixas de seleção para Habilitar filtros para esses alertas. Você pode escolher entre vários filtros, incluindo *Data*, *remetente*, *assunto/título*, *classificadores* e muito mais.

7. Se quiser salvar o filtro selecionado como o filtro padrão, selecione **salvar como padrão**. Se você quiser usar este filtro como um filtro salvo, selecione **concluído**.

8. Se quiser salvar os filtros selecionados como uma consulta de filtro, selecione **salvar o controle de consulta** após ter configurado pelo menos um valor de filtro. Insira um nome para a consulta de filtro e selecione **salvar**. Este filtro está disponível para ser usado apenas para essa política e está listado na seção **consultas de filtro salvas** da página de detalhes de **filtros** .

    ![Controles de detalhe de filtro de conformidade de comunicação](../media/communication-compliance-filter-detail-controls.png)

### <a name="using-near-and-exact-duplicate-analysis"></a>Usando a análise de duplicatas próxima e exata

As políticas de conformidade de comunicação verificam e agrupam automaticamente duplicatas de mensagens próximas e exatas sem nenhuma etapa de configuração adicional. Este modo de exibição permite que você aja rapidamente em mensagens semelhantes, um por um ou um grupo, reduzindo a carga de investigação de mensagens para revisores. Como duplicatas são detectadas, os controles **próximos duplicatas** e/ou **Exact duplicatas** são exibidos na barra de ferramentas ação de correção. Este modo de exibição não estará disponível se não forem encontradas duplicatas ou não.

#### <a name="to-remediate-duplicates"></a>Para corrigir duplicatas

1. Entre [https://compliance.microsoft.com](https://compliance.microsoft.com) usando as credenciais de uma conta de administrador na sua organização do Microsoft 365.

2. No centro de conformidade da Microsoft 365, vá para **conformidade de comunicação**.

3. Selecione a guia **políticas** e, em seguida, selecione uma política de investigação, clique duas vezes para abrir a página **política** .

4. Na página **política** , selecione a guia **pendente** ou **resolvida** para exibir mensagens duplicadas.

5. Selecione os controles **próximos duplicados** ou de **duplicatas exatas** para abrir a página de detalhes de duplicatas.

6. Selecione uma ou mais mensagens para controles de ação de correção para essas mensagens.

7. Selecione **resolver**, **notificar**, **escalonar** ou **baixar** para aplicar a ação às mensagens duplicadas selecionadas como o filtro padrão.

8. Selecione **fechar** após concluir as ações de correção nas mensagens.

    ![Controles de duplicatas de conformidade exata de comunicação](../media/communication-compliance-duplicates-controls.png)

## <a name="remediate-alerts"></a>Corrigir alertas

Não importa onde você comece a revisar os alertas ou a filtragem que você configurou, a próxima etapa é executar uma ação para corrigir o alerta. Inicie a correção de alerta usando o fluxo de trabalho a seguir nas páginas de **políticas** ou **alertas** .

### <a name="step-1-examine-the-message-basics"></a>Etapa 1: examinar as noções básicas da mensagem

 Às vezes, é óbvio da origem ou do assunto que uma mensagem pode ser imediatamente corrigida. Pode ser que a mensagem seja falsa ou incorretamente correspondente a uma política e deve ser resolvida como um falso positivo. Selecione o controle **falso positivo** para resolver imediatamente o alerta e remover da fila de alerta pendente. Nas informações de origem ou do remetente, talvez você já saiba como a mensagem deve ser encaminhada ou tratada nessas circunstâncias. Considere usar a **marca como** ou **escalonar** controles para atribuir uma marca a mensagens aplicáveis ou para enviar mensagens a um revisor designado.

![Controles de correção de conformidade de comunicação](../media/communication-compliance-remediation-controls.png)

### <a name="step-2-examine-the-message-details"></a>Etapa 2: examinar os detalhes da mensagem

Depois de analisar as noções básicas da mensagem, é hora de abrir uma mensagem para examinar os detalhes e determinar as ações de correção posteriores. Selecione uma mensagem para exibir as informações completas de cabeçalho e corpo da mensagem. Vários modos de exibição diferentes estão disponíveis para ajudá-lo a decidir o curso de ação adequado:

- **Modo** de exibição de origem: este modo de exibição é o modo de exibição de mensagem padrão normalmente visto na maioria das plataformas de mensagens baseadas na Web. As informações de cabeçalho são formatadas no estilo normal e o corpo da mensagem suporta arquivos gráficos incorporados e texto com quebra automática de palavra.
- **Exibição de texto**: o modo de exibição de texto exibe um modo de exibição somente texto numerado de linha da mensagem e inclui o realce de uma palavra-chave em mensagens e anexos para termos correspondentes na política de conformidade de comunicação associada. A palavra-chave realce pode ajudá-lo a examinar rapidamente mensagens longas e anexos para a área de interesse. Em alguns casos, o texto realçado pode ser apenas em anexos para as condições de política de correspondência de mensagens. Os arquivos inseridos não são exibidos e a numeração de linhas desse modo de exibição é útil para fazer referência a detalhes pertinentes entre vários revisores.
- **Modo de anotações**: este modo de exibição permite que os revisores adicionem anotações diretamente na mensagem que são salvas no modo de exibição da mensagem.
- **Histórico do usuário**: o modo de exibição de histórico do usuário exibe todos os outros alertas gerados por qualquer política de conformidade de comunicação para o usuário que está enviando a mensagem.
- **Exibição de detalhes da mensagem**: modo de exibição avançado de metadados de mensagens e informações de configuração.
- **Padrão de notificação detectada (visualização)**: muitas ações de assédio e anti-intimidação ao longo do tempo e envolvem instâncias repetidas do mesmo comportamento por um usuário. A notificação de *padrão detectada* é exibida nos detalhes do alerta e aumenta a atenção para o alerta. A detecção de padrões está em uma base por política e avalia o comportamento nos últimos 30 dias quando pelo menos duas mensagens são enviadas para o mesmo destinatário por um remetente. Investigadores e revisores podem usar essa notificação para identificar o comportamento repetido para avaliar o alerta, conforme apropriado.

    ![Controles de exibição de mensagens de conformidade de comunicação](../media/communication-compliance-message-views.png)

### <a name="step-3-decide-on-a-remediation-action"></a>Etapa 3: decidir sobre uma ação de correção

Agora que você analisou os detalhes da mensagem para o alerta, é possível escolher várias ações de correção:

- **Resolver**: selecionar o controle **resolver** imediatamente remove a mensagem da fila de **alertas pendentes** e nenhuma ação adicional pode ser executada na mensagem. Ao selecionar **resolver**, você já fechou o alerta sem mais classificação e não pode ser reaberto para futuras ações. Todas as mensagens resolvidas são exibidas na guia **resolvido** .
- **Falso positivo**: você sempre pode resolver uma mensagem como falso positivo em qualquer ponto durante o fluxo de trabalho de revisão de mensagens. False positivo significa que o alerta não era acionável ou que o alerta foi gerado incorretamente pelo processo de alerta. A mensagem não pode ser reaberta e todas as mensagens falsas positivas são exibidas na guia **resolvido** .
- **Automatização de energia (visualização)**: usar um fluxo automatizado de energia para automatizar tarefas de processo para uma mensagem de alerta. Por padrão, a conformidade de comunicação inclui o *Gerenciador de notificações quando um usuário tem um* modelo de fluxo de alerta de conformidade de comunicação que os revisores podem usar para automatizar o processo de notificação para usuários com alertas de mensagem. Para obter mais informações sobre como criar e gerenciar fluxos automatizados de energia na conformidade de comunicação, consulte o artigo de [referência do recurso de conformidade de comunicação](communication-compliance-feature-reference.md#power-automate-flows-preview) .
- **Marcar como**: marcar a mensagem como *compatível*, *não compatível* ou como *questionável* , pois ela se relaciona com as políticas e os padrões da sua organização. A adição de marcas e comentários de marcação ajuda você a filtrar alertas de política para escalonamento ou como parte de outros processos de revisão internos. Após a conclusão da marcação, você também pode optar por resolver a mensagem para movê-la para fora da fila de revisão pendente.
- **Notificar**: você pode usar o controle **Notify** para atribuir um modelo de aviso personalizado ao alerta e enviar um aviso de aviso ao usuário. Escolha o modelo de aviso apropriado configurado na área **configurações de conformidade de comunicação** e selecione **Enviar** para enviar por email um lembrete para o usuário que enviou a mensagem e para resolver o problema.
- **Escalonar**: usando o controle **escalonar** , você pode escolher quem mais em sua organização deve revisar a mensagem. Escolha em uma lista de revisores configurados na política de conformidade de comunicação para enviar uma notificação por email solicitando uma revisão adicional do alerta de mensagem. O revisor selecionado pode usar um link na notificação por email para ir diretamente para os itens escalonados a eles para revisão.
- **Escalonar para investigação**: usando o **escalonamento para controle de investigação** , você pode criar um novo [caso de descoberta eletrônica avançada](overview-ediscovery-20.md) para mensagens simples ou múltiplas. Você fornecerá um nome e anotações para o novo caso e o usuário que enviou a mensagem que corresponde à política será automaticamente atribuído como o responsável da ocorrência. Você não precisa de nenhuma permissão adicional para gerenciar o caso. Criar uma ocorrência não resolve ou cria uma nova marca para a mensagem. Você pode selecionar um total de 100 mensagens ao criar um caso de descoberta eletrônica avançada durante o processo de correção. As mensagens em todos os canais de comunicação monitorados pela conformidade com comunicações têm suporte. Por exemplo, você pode selecionar 50 chats do Microsoft Teams, 25 mensagens de email do Exchange Online e 25 mensagens do Yammer ao abrir um novo caso de descoberta eletrônica avançada para um usuário.
- **Melhorar a classificação (visualização)**: os alertas criados a partir de um tipo de classificador as correspondências podem precisar de comentários para ajudar a minimizar positivos falsos em sua organização. Use o controle **aprimorar classificação** para fornecer comentários sobre se a classificação de conformidade de comunicação for válida ou para sugerir outros classificadores de uso para esse tipo de correspondência. Você pode confirmar que os classificadores são uma *coincidência* ou *não uma correspondência* ou sugerem que outros classificadores estagiários para associar a esse tipo de atividade de alerta no futuro.

    1. Selecione uma mensagem na lista de alerta.
    2. Escolha as reticências e selecione **melhorar a classificação**.
    3. No painel de **comentários detalhados do classificador** , se o item for true positivo, escolha **CORRESP**.  Se o item foi incorretamente incluído na categoria como falso positivo, escolha **não uma correspondência**.
    4. Se houver outro classificador que seria mais apropriado para o item, escolha-o na lista **sugerir outros classificadores estagiários** . Este feedback dispara o outro classificador para avaliar o item.

    > [!TIP]
    > Você pode fornecer comentários sobre vários itens simultaneamente escolhendo todos eles e escolhendo **fornecer comentários detalhados** na barra de comandos.

    5. Escolha **enviar comentários** para enviar sua avaliação das classificações de correspondência e **não de correspondência** **e sugerir** outros classificadores estagiários. Quando você fornecer 30 instâncias de comentários para um classificador, ele será automaticamente retreinado. O retreinamento pode levar 1-4 horas para ser concluído. Os classificadores só podem ser retreinados duas vezes por dia.

    > [!IMPORTANT]
    > Essas informações vão para o classificador no locatário, **não volta para a Microsoft**.

    Para saber mais sobre o classificador de retreinamento para conformidade de comunicação, consulte o artigo sobre [como retreinar um classificador no artigo de conformidade de comunicações](classifier-how-to-retrain-comms-compliance.md) .

    ![Conformidade de comunicação melhorar a classificação](../media/communication-compliance-improve-classifier.png)

- **Remover mensagem no Teams**: usando a **mensagem de remoção no controle do teams** , você pode bloquear mensagens inadequadas e conteúdo identificado em alertas de canais do Microsoft Teams e de chats 1:1 e de grupo. As mensagens e o conteúdo removidos são substituídos por uma dica de política que explica que ele é bloqueado e a política que se aplica à sua remoção do modo de exibição. Os destinatários recebem um link na dica de política para saber mais sobre a política aplicável e o processo de revisão. O remetente recebe uma dica de política para a mensagem e o conteúdo bloqueados, mas pode revisar os detalhes da mensagem bloqueada e do conteúdo para contexto em relação à remoção.

    ![Remover uma mensagem do Microsoft Teams](../media/communication-compliance-remove-teams-message.png)

### <a name="step-4-determine-if-message-details-should-be-archived-outside-of-communication-compliance"></a>Etapa 4: determinar se os detalhes da mensagem devem ser arquivados fora da conformidade de comunicação

Os detalhes da mensagem podem ser exportados ou baixados se você precisar arquivar as mensagens em uma solução de armazenamento separada. Selecionar o controle de **Download** automaticamente adiciona mensagens selecionadas a um. ZIP arquivo que pode ser salvo no armazenamento fora do Microsoft 365.
