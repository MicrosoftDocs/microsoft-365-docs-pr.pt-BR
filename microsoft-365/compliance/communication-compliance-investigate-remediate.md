---
title: Investigar e corrigir alertas de conformidade em comunicações
description: Investigar e remediar alertas de conformidade de comunicação no Microsoft 365.
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
ms.openlocfilehash: 7e5dc3ef4a79b1bdbcde9a7a15fec84efe9b92c9
ms.sourcegitcommit: fa5659cb66d84dcfeebc03b47bd9d38017d8934d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2021
ms.locfileid: "50109951"
---
# <a name="investigate-and-remediate-communication-compliance-alerts"></a>Investigar e corrigir alertas de conformidade em comunicações

Depois de configurar suas políticas de conformidade de comunicação, você começará a receber alertas no centro de conformidade do Microsoft 365 para problemas de mensagens que corresponderem às suas condições de política. Siga as instruções de fluxo de trabalho aqui para investigar e resolver problemas de alerta.

## <a name="investigate-alerts"></a>Investigar alertas

A primeira etapa para investigar problemas detectados por suas políticas é analisar os alertas de conformidade de comunicação no centro de conformidade do Microsoft 365. Há várias áreas na área de solução de conformidade de comunicação para ajudá-lo a investigar rapidamente alertas, dependendo de como você prefere exibir o grupo de alertas:

- **Página de política de** conformidade de comunicação: quando você entrar usando credenciais para uma conta de administrador em sua organização do [https://compliance.microsoft.com](https://compliance.microsoft.com) Microsoft 365, selecione Conformidade de comunicação para exibir a página política de conformidade **de** comunicação.  Esta página exibe políticas de conformidade de comunicação configuradas para sua organização do Microsoft 365 e links para modelos de política recomendados. Cada política listada inclui a contagem de alertas que precisam de revisão, o número de itens escalonados e resolvidos, o status da política e a data e hora da última verificação de política. Selecionar uma política exibe todos os alertas pendentes para as combinações com a política, selecionar um alerta específico para iniciar a página de detalhes da política e iniciar ações de correção.
- **Alertas:** navegue até **Alertas** de conformidade de comunicação para exibir os últimos 30 dias de  >   alertas agrupados por diretivas. Essa exibição permite que você veja rapidamente quais políticas de conformidade de comunicação estão gerando a maioria dos alertas ordenados por gravidade. Para iniciar ações de correção, selecione a política associada ao alerta para iniciar a **página detalhes da** política. Na  página Detalhes da Política, você pode revisar um resumo das atividades na  página Visão Geral, revisar e agir em  mensagens de alerta na página Pendente ou revisar o histórico de alertas fechados na página Resolvido. 
- **Relatórios:** navegue até **Relatórios de conformidade de**  >  **comunicação** para exibir widgets de relatório de conformidade de comunicação. Cada widget fornece uma visão geral das atividades e status de conformidade de comunicação, incluindo acesso a informações mais aprofundadas sobre as políticas de resultados e ações de correção.

### <a name="using-filters"></a>Usando filtros

A próxima etapa é classificar as mensagens para que seja mais fácil investigar alertas. Na página **Detalhes da** política, a conformidade de comunicação oferece suporte à filtragem de vários níveis para vários campos de mensagem para ajudá-lo a investigar e analisar rapidamente as mensagens com as políticas de acordo. A filtragem está disponível para itens pendentes e resolvidos para cada política configurada. Você pode configurar consultas de filtro para uma política ou configurar e salvar consultas de filtro padrão e personalizadas para uso em cada política específica. Depois de configurar campos para um filtro, você verá os campos de filtro exibidos na parte superior da fila de mensagens de alerta que você pode configurar para valores de filtro específicos.

Para obter uma lista completa de filtros e detalhes do campo, consulte [Filtros](communication-compliance-feature-reference.md#filters) no artigo de referência do recurso.

#### <a name="to-configure-a-filter"></a>Para configurar um filtro

1. Entre usando [https://compliance.microsoft.com](https://compliance.microsoft.com) credenciais para uma conta de administrador em sua organização do Microsoft 365.

2. No centro de conformidade do Microsoft 365, vá para **Conformidade de comunicação.**

3. Selecione a **guia Políticas** e selecione uma política para investigação, clique duas vezes para abrir a **página** Política.

4. Na página **Política,** selecione a  guia **Pendente** ou Resolvido para exibir os itens para filtragem.

5. Selecione o **controle Filtros** para abrir a **página de detalhes** filtros.

6. Marque uma ou mais caixas de seleção para habilitar filtros para esses alertas. Você pode escolher entre vários filtros, incluindo *Data*, *Remetente*, *Assunto/Título,* *Classificadores* e muito mais.

7. Se você quiser salvar o filtro selecionado como o filtro padrão, selecione **Salvar como padrão.** Se você quiser usar esse filtro como um filtro salvo, selecione **Done**.

8. Se você quiser salvar os filtros selecionados como  uma consulta de filtro, selecione Salvar o controle de consulta depois de configurar pelo menos um valor de filtro. Insira um nome para a consulta de filtro e selecione **Salvar.** Esse filtro está disponível para ser usado apenas para essa política e está listado na seção **Consultas** de filtro salvo da página **de detalhes** Filtros.

    ![Controles detalhados do filtro de conformidade de comunicação](../media/communication-compliance-filter-detail-controls.png)

### <a name="using-near-and-exact-duplicate-analysis"></a>Usando análise duplicada próxima e exata

As políticas de conformidade de comunicação automaticamente digitalizar e agrupar previamente duplicatas de mensagens próximas e exatas sem quaisquer etapas adicionais de configuração. Esse modo de exibição permite que você aja rapidamente em mensagens semelhantes, uma por uma, ou como um grupo, reduzindo a carga de investigação de mensagens para os revisadores. Como duplicatas são detectadas, os **controles Duplicatas Próximas** e/ou Duplicatas Exatas são **exibidos** na barra de ferramentas de ação de correção. Essa exibição não estará disponível se duplicatas próximas ou exatas não foram encontradas.

#### <a name="to-remediate-duplicates"></a>Para remediar duplicatas

1. Entre usando [https://compliance.microsoft.com](https://compliance.microsoft.com) credenciais para uma conta de administrador em sua organização do Microsoft 365.

2. No centro de conformidade do Microsoft 365, vá para **Conformidade de comunicação.**

3. Selecione a **guia Políticas** e selecione uma política para investigação, clique duas vezes para abrir a **página** Política.

4. Na página **Política,** selecione a  guia **Pendente** ou Resolvido para exibir mensagens duplicadas.

5. Selecione os **controles Duplicatas Próximas** **ou Duplicatas Exatas** para abrir a página de detalhes duplicados.

6. Selecione uma ou mais mensagens para remediar os controles de ação dessas mensagens.

7. Selecione **Resolver**, **Notificar**, **Escalonar** ou **Baixar** para aplicar a ação às mensagens duplicadas selecionadas como o filtro padrão.

8. Selecione **Fechar** após concluir as ações de correção nas mensagens.

    ![Controles duplicados exatos de conformidade de comunicação](../media/communication-compliance-duplicates-controls.png)

## <a name="remediate-alerts"></a>Remediar alertas

Não importa onde você comece a revisar alertas ou a filtragem configurada, a próxima etapa é tomar medidas para remediar o alerta. Inicie a correção de alerta usando o seguinte fluxo de trabalho nas páginas **Política** **ou Alertas.**

### <a name="step-1-examine-the-message-basics"></a>Etapa 1: Examinar as noções básicas de mensagem

 Às vezes, é óbvio da origem ou do assunto que uma mensagem pode ser imediatamente remediada. Pode ser que a mensagem seja falsa ou incorretamente a ela corresponder a uma política e deve ser resolvida como um falso positivo. Selecione o **controle Falso Positivo** para resolver imediatamente o alerta e remover da fila de alertas pendente. A partir das informações de origem ou remetente, talvez você já saiba como a mensagem deve ser roteada ou tratada nessas circunstâncias. Considere usar os **controles Tag como** ou **Escalate** para atribuir uma marca às mensagens aplicáveis ou enviar mensagens a um revistor designado.

![Controles de correção de conformidade de comunicação](../media/communication-compliance-remediation-controls.png)

### <a name="step-2-examine-the-message-details"></a>Etapa 2: Examinar os detalhes da mensagem

Depois de analisar as noções básicas da mensagem, é hora de abrir uma mensagem para examinar os detalhes e determinar outras ações de correção. Selecione uma mensagem para exibir as informações completas do corpo e do header da mensagem. Várias exibições diferentes estão disponíveis para ajudá-lo a decidir o curso adequado da ação:

- **Exibição de** origem: esse é o padrão de exibição de mensagens comumente visto na maioria das plataformas de mensagens baseadas na Web. As informações de header são formatadas no estilo normal e o corpo da mensagem dá suporte a arquivos gráficos imbedded e texto em forma de palavras.
- **Exibição de** texto: o texto exibe uma exibição somente de texto numerada em linha da mensagem e inclui a palavra-chave realçada em mensagens e anexos para termos que corresponderem à política de conformidade de comunicação associada. O realçamento de palavras-chave pode ajudá-lo a verificar rapidamente mensagens longas e anexos para a área de interesse. Em alguns casos, o texto realce pode estar apenas em anexos para mensagens que corresponderem às condições da política. Os arquivos incorporados não são exibidos e a numeração de linhas desse ponto de vista é útil para fazer referência a detalhes pertinentes entre vários revisores.
- **Exibição de anotações:** essa exibição permite que os revisadores adicionem anotações diretamente na mensagem que são salvas na exibição da mensagem.
- **Histórico do usuário:** a exibição do histórico do usuário exibe todos os outros alertas gerados por qualquer política de conformidade de comunicação para o usuário que envia a mensagem.
- **Exibição de detalhes da mensagem:** exibição avançada de metadados de mensagem e informações de configuração.
- **Notificação de padrão detectada:** muitas ações incomodar e incomodar ao longo do tempo e envolvem instâncias recorrentes do mesmo comportamento por um usuário. A *notificação de* Padrão detectada é exibida nos detalhes do alerta e chama a atenção para o alerta. A detecção de padrões é feita por política e avalia o comportamento nos últimos 30 dias quando pelo menos duas mensagens são enviadas ao mesmo destinatário por um remetente. Os investigadores e revisadores podem usar essa notificação para identificar comportamento repetido para avaliar o alerta conforme apropriado.
- **Mostrar exibição** traduzir: essa exibição converte automaticamente o  texto da mensagem de alerta para o idioma configurado na configuração de idioma exibido na assinatura do Microsoft 365 para cada revisador. O modo de exibição Traduzir ajuda a ampliar o suporte de investigação para organizações com usuários multilíngues e elimina a necessidade de serviços de tradução adicionais fora do processo de revisão de conformidade de comunicação. Usando os serviços de Tradução da Microsoft, o visualização Traduzir pode ser ligado e desligado conforme necessário e oferece suporte a uma ampla variedade de idiomas. Para uma lista completa de idiomas com suporte, consulte [Idiomas do Microsoft Translator.](https://www.microsoft.com/translator/business/languages/) Os idiomas listados na Lista *de Idiomas* do Tradutor são suportados na exibição Traduzir.

    ![Controles de exibição de mensagem de conformidade de comunicação](../media/communication-compliance-message-views.png)

### <a name="step-3-decide-on-a-remediation-action"></a>Etapa 3: Decidir sobre uma ação de correção

Agora que você analisou os detalhes da mensagem para o alerta, pode escolher várias ações de correção:

- **Resolver:** selecionar **o controle Resolver** remove imediatamente a mensagem da fila de **alertas Pendentes** e nenhuma outra ação pode ser tomada na mensagem. Ao selecionar **Resolver,** você essencialmente fechou o alerta sem classificação e ele não pode ser reaberto para mais ações. Todas as mensagens resolvidas são exibidas na **guia** Resolvido.
- **Falso positivo:** você sempre pode resolver uma mensagem como um falso positivo a qualquer momento durante o fluxo de trabalho de revisão de mensagens. Falso positivo significa que o alerta não foi a actionable ou que foi gerado incorretamente pelo processo de alerta. A mensagem não pode ser reaberta e todas as mensagens de falso positivo são exibidas **na** guia Resolvido.
- **Power Automate (visualização)**: use um fluxo do Power Automate para automatizar tarefas de processo para uma mensagem de alerta. Por padrão, *a* conformidade de comunicação inclui o gerenciador de notificação quando um usuário tem um modelo de fluxo de alerta de conformidade de comunicação que os revisadores podem usar para automatizar o processo de notificação para usuários com alertas de mensagem. Para obter mais informações sobre como criar e gerenciar fluxos do Power Automate em conformidade com a comunicação, consulte o artigo de referência do [recurso de conformidade de](communication-compliance-feature-reference.md#power-automate-flows) comunicação.
- **Tag as**: Tag the message as *compliant*, *non-compliant*, or as *questionable* as it relates to the policies and standards for your organization. Adicionar marcas e comentários de marcação ajuda você a filtrar micro-alertas de política para escalonamentos ou como parte de outros processos de revisão interna. Depois que a marcação for concluída, você também poderá optar por resolver a mensagem para movê-la da fila de revisão pendente.
- **Notificar:** você pode usar o controle **De** notificação para atribuir um modelo de aviso personalizado ao alerta e enviar um aviso de aviso ao usuário. Escolha o modelo de aviso  apropriado configurado na  área de configurações de conformidade de comunicação e selecione Enviar para enviar um lembrete por email para o usuário que enviou a mensagem e para resolver o problema.
- **Escalonar:** usando o **controle Escalonar,** você pode escolher quem mais em sua organização deve analisar a mensagem. Escolha em uma lista de revisadores configurados na política de conformidade de comunicação para enviar uma notificação por email solicitando revisão adicional do alerta de mensagem. O revisador selecionado pode usar um link na notificação por email para ir diretamente aos itens escalonados para eles para revisão.
- **Escalonar para investigação:** usando o **Escalonamento** para [](overview-ediscovery-20.md) controle de investigação, você pode criar um novo caso de Descoberta Avançada para uma ou várias mensagens. Você fornecerá um nome e anotações para a nova ocorrência, e o usuário que enviou a mensagem que corresponde à política será atribuído automaticamente como o custodiante da ocorrência. Você não precisa de permissões adicionais para gerenciar a ocorrência. Criar uma ocorrência não resolve ou cria uma nova marca para a mensagem. Você pode selecionar um total de 100 mensagens ao criar um caso de Descoberta Avançada durante o processo de correção. Há suporte para mensagens em todos os canais de comunicação monitorados pela conformidade de comunicação. Por exemplo, você pode selecionar 50 chats do Microsoft Teams, 25 mensagens de email do Exchange Online e 25 mensagens do Yammer quando abrir um novo caso de Descoberta Eletrônico Avançada para um usuário.
- **Melhorar a classificação (visualização)**: alertas criados a partir de tipos de classificador podem precisar de comentários para ajudar a minimizar falsos positivos em sua organização. Use o **controle melhorar** a classificação para fornecer comentários sobre se a classificação de conformidade de comunicação é válida ou para sugerir outros classificadores de treinamento para esse tipo de combinação. Você pode confirmar se os classificadores são uma match ou *Not a match*, ou sugerir outros classificadores de treinamento para associar a esse tipo de atividade de alerta no futuro. 

    1. Selecione uma mensagem na lista de alertas.
    2. Escolha as reellipses e selecione **Melhorar a classificação.**
    3. No painel **de comentários do classificador** detalhado, se o item for um verdadeiro positivo, escolha **Corresponder**.  Se o item foi incluído incorretamente na categoria como um falso positivo, escolha **Não uma combinação.**
    4. Se houver outro classificador que seria mais apropriado para o item, escolha-o na lista Sugerir **outros classificadores** de treinamento. Esse feedback aciona o outro classificador para avaliar o item.

    > [!TIP]
    > Você pode fornecer comentários sobre vários itens simultaneamente escolhendo todos eles e escolhendo Fornecer comentários detalhados **na** barra de comandos.

    5. Escolha **Enviar comentários** para enviar sua avaliação das classificações **Match** e Not **a match** e sugira outros classificadores de treinamento. Quando você forneceu 30 instâncias de comentários para um classificador, ele automaticamente é restringido. O retraining pode levar de 1 a 4 horas para ser concluído. Os classificadores só podem ser restringidos duas vezes por dia.

    > [!IMPORTANT]
    > Essas informações vão para o classificador em seu locatário, **ela não volta para a Microsoft**.

    Para saber mais sobre como restringir o classificador para conformidade de comunicação, consulte o artigo como restringir um [classificador](classifier-how-to-retrain-comms-compliance.md) no artigo de conformidade de comunicações.

    ![Conformidade de comunicação melhora a classificação](../media/communication-compliance-improve-classifier.png)

- **Remover mensagem no Teams:** usando a mensagem Remover no controle do **Teams,** você pode bloquear mensagens inadequadas e conteúdo identificado em alertas de canais do Microsoft Teams e chats 1:1 e em grupo. As mensagens e o conteúdo removidos são substituídos por uma dica de política que explica que ele está bloqueado e a política que se aplica à remoção da exibição. Os destinatários são fornecidos com um link na dica de política para saber mais sobre a política aplicável e o processo de revisão. O remetente recebe uma dica de política para a mensagem e o conteúdo bloqueados, mas pode analisar os detalhes da mensagem e do conteúdo bloqueados para contexto sobre a remoção.

    ![Remover uma mensagem do Microsoft Teams](../media/communication-compliance-remove-teams-message.png)

### <a name="step-4-determine-if-message-details-should-be-archived-outside-of-communication-compliance"></a>Etapa 4: Determinar se os detalhes da mensagem devem ser arquivados fora da conformidade de comunicação

Detalhes da mensagem podem ser exportados ou baixados se você precisar arquivar as mensagens em uma solução de armazenamento separada. Selecionar o **controle download** adiciona automaticamente mensagens selecionadas a um . Arquivo ZIP que pode ser salvo no armazenamento fora do Microsoft 365.
