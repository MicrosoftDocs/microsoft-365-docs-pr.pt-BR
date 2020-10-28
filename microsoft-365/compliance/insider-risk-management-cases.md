---
title: Casos de gerenciamento de risco do insider
description: Saiba mais sobre os casos de gerenciamento de risco do insider no Microsoft 365
keywords: Microsoft 365, gerenciamento de risco do Insider, gerenciamento de riscos, conformidade
localization_priority: Normal
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: m365-security-compliance
ms.openlocfilehash: f0251f783aebd1264facfcbaa23a9b7afa286833
ms.sourcegitcommit: 45c0afcf958069c5c1b31f9b6c762d8dd806e1e9
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/27/2020
ms.locfileid: "48774014"
---
# <a name="insider-risk-management-cases"></a>Casos de gerenciamento de risco do insider

Os casos são o coração do gerenciamento de risco do insider e permitem que você investigue profundamente e atue em problemas gerados pelos indicadores de risco definidos em suas políticas. Os casos são criados manualmente a partir de alertas em situações em que uma ação adicional é necessária para lidar com um problema relacionado à conformidade para um usuário. Cada caso é delimitado a um único usuário, e vários alertas para o usuário podem ser adicionados a um caso existente ou a um novo caso. 

Após investigar os detalhes de um caso, você pode executar uma ação por:

- enviar um aviso ao usuário
- Resolvendo o caso como benigno
- compartilhando o caso com sua instância do ServiceNow ou com um destinatário de email
- encaminhar o caso de uma investigação de descoberta eletrônica avançada

## <a name="cases-dashboard"></a>Painel de casos

O **painel de casos** de gerenciamento de risco do insider permite que você visualize e atue em casos. Cada widget de relatório no painel exibe informações dos últimos 30 dias.

- **Casos ativos** : o número total de casos ativos sob investigação.
- **Casos nos últimos 30 dias** : o número total de ocorrências criadas, classificadas por status *ativo* e *fechado* .
- **Estatísticas** : tempo médio de ocorrências ativas, listadas em horas, dias ou meses.

A fila de casos lista todos os casos ativos e fechados para sua organização, além do status atual dos seguintes atributos de caso:

- **Nome do caso** : o nome do caso, definido quando um alerta é confirmado e o caso é criado.  
- **Status** : o status do caso, *ativo* ou *fechado* .
- **Usuário** : o usuário do caso. Se a anonimato de nomes de dados estiver habilitada, as informações do anonimato serão exibidas.
- **Caso de tempo aberto** : o tempo decorrido desde que o caso foi aberto.
- **Total de alertas de política** : o número de correspondências de política incluído no caso. Esse número pode aumentar se novos alertas forem adicionados ao caso.
- **Última atualização** : o tempo decorrido desde que houve uma observação de caso adicionada ou alteração no estado de caso.
- **Última atualização** : o nome do analista de gerenciamento de risco do insider ou do investigador que atualizou pela última vez o caso.

![Painel de casos de gerenciamento de risco do insider](../media/insider-risk-cases-dashboard.png)

Use o controle de **pesquisa** para pesquisar nomes de caso para texto específico e use o filtro de caso para classificar casos pelos seguintes atributos:

- Status
- Caso de tempo aberto, data de início e data de término
- Última atualização, data de início e data de término

## <a name="filter-cases"></a>Filtrar casos

Dependendo do número e do tipo de políticas de gerenciamento de risco do insider ativos em sua organização, a análise de uma grande fila de casos pode ser desafiadora. O uso de filtros de caso pode ajudar os analistas e investigadores a classificar ocorrências por vários atributos. Para filtrar alertas no **painel casos** , selecione o controle de **filtro** . Você pode filtrar ocorrências por um ou mais atributos:

- **Status** : selecione um ou mais valores de status para filtrar a lista de casos. As opções são *ativas* e *fechadas* .
- **Caso de tempo aberto** : selecione as datas de início e término para quando a ocorrência foi aberta.
- **Última atualização** : selecione as datas de início e término para quando o caso foi atualizado.

## <a name="investigate-a-case"></a>Investigue uma ocorrência

A investigação mais profunda dos alertas de gerenciamento de risco do Insider é fundamental para a realização de ações corretivas adequadas. Os casos de gerenciamento de risco do insider são a ferramenta de gerenciamento central para se aprofundar no histórico de atividades de risco do usuário e detalhes de alerta e explorar o conteúdo e as mensagens expostos aos riscos. Os analistas e investigadores de risco também usam casos para centralizar comentários e notas de revisão e para processar a resolução de casos.

Selecionar um caso abre as ferramentas de gerenciamento de casos e permite que analistas e investigadores se aprofundarem nos detalhes dos casos.

### <a name="case-overview"></a>Visão geral da ocorrência

A guia **visão geral de casos** resume a atividade de alerta e o histórico de nível de risco da ocorrência. 

- O widget **alertas** mostra as correspondências de política para o caso, incluindo o status do alerta, a severidade do risco de alerta e quando o alerta foi detectado. 
- O gráfico de **histórico de nível de risco** exibe o nível de risco do usuário nos últimos 30 dias. O gráfico de linhas permite que analistas e investigadores vejam rapidamente a tendência no risco geral do usuário ao longo do tempo. 
- O widget **conteúdo da atividade de risco** resume os tipos de dados e conteúdo contidos nos alertas adicionados ao caso. Este widget fornece uma visão completa de todos os dados e conjunto de conteúdo em risco no caso.

O painel de **detalhes de caso** está disponível em todas as guias de gerenciamento de caso e resume os detalhes de caso para analistas e investigadores de risco. Ele inclui as seguintes áreas:

- **Nome do caso** : o nome da ocorrência, prefixado com um número de sequência de ocorrências gerado automaticamente e o nome do risco associado ao modelo de política que o primeiro alerta confirmado corresponde. 
- **Status do caso** : o status atual do caso, *ativo* ou *fechado* .
- **Pontuação de risco do usuário** : o nível de risco calculado atual do usuário para o caso. Essa pontuação é calculada a cada 24 horas e usa as pontuações de risco de alerta de todos os alertas ativos associados ao usuário.
- **Alertas confirmados** : lista de alertas para o usuário confirmado para o caso.
- **Conteúdo relacionado** : lista de conteúdo, classificada por fontes e tipos de conteúdo. Por exemplo, para o conteúdo de alerta de caso no SharePoint Online, você pode ver nomes de pastas ou arquivos listados que estão associados à atividade de risco para alertas no caso.

![Detalhes do caso de gerenciamento de risco do insider](../media/insider-risk-case-details.png)

### <a name="alerts"></a>Alertas

A guia **alertas** resume os alertas atuais incluídos no caso. Novos alertas podem ser adicionados a um caso existente e eles serão adicionados à fila de **alerta** à medida que forem atribuídos. Os seguintes atributos de alerta são listados na fila:

- Status
- Severity
- Tempo detectado

Selecione um alerta na fila para exibir a página **detalhes do alerta** .

Use o controle de pesquisa para pesquisar os nomes de alerta para texto específico e use o filtro de alerta para classificar casos pelos seguintes atributos:

- Status
- Severity
- Hora da detecção, data de início e data de término

Use o controle de filtro para filtrar alertas por vários atributos, incluindo:

- **Status** : selecione um ou mais valores de status para filtrar a lista de alerta. As opções são *confirmadas* , *ignoradas* , *Revisas* e *resolvidas* .
- **Severidade** : selecione um ou mais níveis de severidade de risco de alerta para filtrar a lista de alerta. As opções são *alta* , *média* e *baixa* .
- **Tempo detectado** : selecione as datas de início e término para quando o alerta foi criado.
- **Política** : selecione uma ou mais políticas para filtrar os alertas gerados pelas políticas selecionadas.

### <a name="user-activity"></a>Atividades do usuário

A guia **atividade do usuário** é uma das ferramentas mais poderosas para análise de riscos internos e investigação de casos na solução de gerenciamento de risco do insider. Esta guia é estruturada para habilitar a revisão rápida de um caso, incluindo uma linha do tempo histórica de todos os alertas, todos os detalhes dos alertas, a pontuação de risco atual para o usuário no caso e os controles para executar a ação efetiva para conter os riscos no caso.

![Atividade do usuário de gerenciamento de risco do insider](../media/insider-risk-user-activities.png)

1. **Filtros de data e hora da janela** : por padrão, os últimos seis meses de alertas confirmados no caso são exibidos no gráfico de atividade do usuário. Você pode filtrar facilmente o modo de exibição de gráfico com os controles Slider em ambas as extremidades da janela do gráfico ou definindo datas de início e de término específicas no controle de filtro de gráfico.
2. **Atividade e detalhes de alerta de risco** : as atividades de risco são exibidas visualmente como bolhas coloridas no gráfico de atividades do usuário. As bolhas são criadas para diferentes categorias de risco e o tamanho da bolha é proporcional ao número de atividades de risco para a categoria. Selecione uma bolha para exibir os detalhes de cada atividade de risco. Os detalhes incluem:
    - **Data** da atividade de risco.
    - A **categoria atividade de risco** . Por exemplo, *emails com anexos enviados fora da organização* ou *arquivo (s) baixados do SharePoint Online* .
    - **Pontuação de risco** para o alerta. Esta pontuação é a pontuação numérica do nível de severidade de risco de alerta.
    - Número de eventos associados ao alerta. Os links para cada arquivo ou email associado à atividade de risco também estão disponíveis.
3. **Legenda da atividade do risco** : na parte inferior do gráfico de atividade do usuário, uma legenda codificada por cores ajuda a determinar rapidamente a categoria de risco para cada alerta.
4. **Cronologia da atividade de risco** : o cronograma completo de todos os alertas de risco associados ao caso está listado, incluindo todos os detalhes disponíveis na bolha de alerta correspondente.
5. **Ações de caso** : as opções para resolver o caso estão na barra de ferramentas ação de caso. Você pode resolver um caso, enviar um aviso por email ao usuário ou escalonar o caso de uma investigação de dados ou de usuário.

### <a name="activity-explorer-preview"></a>Explorador de atividade (versão prévia)

>[!IMPORTANT]
>A guia Explorador de atividade está disponível na área gerenciamento de casos para usuários com eventos de acionamento após este recurso estar disponível na sua organização.

A guia **Explorador de atividade** permite que analistas de risco e investigadores analisem os detalhes de atividade associados a alertas de risco. Por exemplo, como parte das ações de gerenciamento de casos, os investigadores e analistas podem precisar revisar todas as atividades de risco associadas ao caso para obter mais detalhes. Com o **Explorador de atividade** , os revisores podem rever rapidamente uma linha do tempo de uma atividade arriscada detectada e identificar e filtrar todas as atividades de risco associadas a alertas.

Para obter mais informações sobre o explorador de atividade, consulte o artigo [alertas de gerenciamento de risco do insider](insider-risk-management-alerts.md#activity-explorer-preview) .

### <a name="content-explorer"></a>Gerenciador de conteúdo

A guia **Gerenciador de conteúdo** permite que analistas de risco e investigadores revisem cópias de todos os arquivos e mensagens de email individuais associados a alertas de risco. Por exemplo, se um alerta é criado quando um usuário baixa centenas de arquivos do SharePoint Online e a atividade dispara um alerta de política, todos os arquivos baixados para o alerta são capturados e copiados para o caso de gerenciamento de risco do insider das fontes de armazenamento originais.

O Gerenciador de conteúdo é uma poderosa ferramenta com recursos básicos e avançados de pesquisa e filtragem. Para saber mais sobre como usar o Gerenciador de conteúdo, confira [Insider Risk Management Content Explorer](insider-risk-management-content-explorer.md).

![Gerenciador de conteúdo de caso de gerenciamento de risco](../media/insider-risk-content-explorer.png)

### <a name="case-notes"></a>Anotações de caso

A guia de **notas de caso** no caso é onde os analistas e investigadores de risco compartilham comentários, comentários e ideias sobre o trabalho da ocorrência. As anotações são adições permanentes a um caso e não podem ser editadas ou excluídas após a anotação ser salva. Quando um caso é criado a partir de um alerta, os comentários inseridos na caixa de diálogo **confirmar alerta e criar caso de caso de insider** são automaticamente adicionados como uma nota de caso.

O painel de anotações de caso exibe anotações pelo usuário que criou a anotação e o tempo decorrido desde que a anotação foi salva. Para pesquisar o campo de texto de nota de caso para uma palavra-chave específica, use o botão de **pesquisa** no painel de casos e insira uma palavra-chave específica.

Para adicionar uma nota a uma ocorrência:

1. No [centro de conformidade da Microsoft 365](https://compliance.microsoft.com), vá para gerenciamento de **risco do insider** e selecione a guia **ocorrências** .
2. Selecione uma ocorrência e, em seguida, selecione a guia **notas de caso** .
3. Selecione **Adicionar observação de caso** .
4. Na caixa de diálogo **Adicionar nota de caso** , digite a anotação para o caso. Selecione **salvar** para adicionar a anotação ao caso ou selecione **Cancelar** fechar sem salvar a anotação no caso.

### <a name="contributors"></a>Colaboradores

A guia **colaboradores** no caso é onde analistas de risco e investigadores podem adicionar outros revisores ao caso. Seja padrão, todos os usuários atribuídos aos **analistas de gerenciamento de risco do insider** e às funções de **investigadores de gerenciamento de risco do insider** são listados como colaboradores para cada caso ativo e fechado.

Todos os casos de gerenciamento de risco do insider devem ser gerenciados com os controles de acesso apropriados no local para manter a confidencialidade e integridade da investigação. Para ajudar a manter o controle de acesso de casos, os usuários recebem um dos dois tipos de acesso a casos:

- **Acesso permanente** : o acesso permanente é concedido automaticamente aos usuários com os **analistas de gerenciamento de risco do insider** e as funções de **investigadores de gerenciamento de risco do insider** quando o caso é criado a partir de um alerta. O acesso permanente concede controle total do caso para o tempo de vida do caso e concede a capacidade de adicionar outros colaboradores de caso.
- **Acesso temporário** : o acesso temporário só é concedido aos usuários por colaboradores que têm acesso permanente à ocorrência. Normalmente, esse nível de acesso é concedido ao usuário que precisa adicionar anotações a um caso. Os colaboradores com acesso temporário têm todo o controle de gerenciamento de casos, exceto:
    - Permissão para confirmar ou ignorar alertas
    - Permissão para editar os colaboradores para casos
    - Permissão para exibir arquivos e mensagens no explorador de conteúdo

Para adicionar um colaborador a uma ocorrência:

1. No [centro de conformidade da Microsoft 365](https://compliance.microsoft.com), vá para gerenciamento de **risco do insider** e selecione a guia **ocorrências** .
2. Selecione uma ocorrência e, em seguida, selecione a guia **colaboradores** .
3. Selecione **Adicionar colaborador** .
4. Na caixa de diálogo **Adicionar colaborador** , comece a digitar o nome do usuário que você deseja adicionar e, em seguida, selecione o usuário na lista de usuários sugeridos. Essa lista é gerada a partir do Azure Active Directory de sua assinatura de locatário.
5. Na caixa de diálogo **Adicionar colaborador** , selecione o nível de acesso para o colaborador. Você pode selecionar **permanente** ou **temporário** .
6. Selecione **Adicionar** para adicionar o usuário como colaborador ou selecione **Cancelar** feche a caixa de diálogo sem adicionar o usuário como colaborador.

## <a name="case-actions"></a>Ações de caso

Os analistas e investigadores de risco podem agir em um caso de vários métodos, dependendo da gravidade do caso, do histórico de riscos do usuário e das diretrizes de risco da sua organização. Em algumas situações, talvez seja necessário escalonar uma ocorrência para uma investigação de usuário ou de dados para colaborar com outras áreas da sua organização e para se aprofundar em atividades de risco. O gerenciamento de riscos do insider está totalmente integrado a outras soluções de conformidade da Microsoft 365 para ajudá-lo com o gerenciamento de resolução de ponta a ponta.

### <a name="send-email-notice"></a>Enviar aviso por email

Na maioria dos casos, as ações do usuário que criam alertas de risco do insider são inadvertidas ou acidentais. Enviar um aviso de lembrete para o usuário via email é um método eficaz para documentar a revisão e a ação de casos, bem como um método para lembrar os usuários de políticas corporativas ou a apontar para o treinamento de atualização. Os avisos são gerados de [modelos de aviso que você cria](insider-risk-management-notices.md) para a infraestrutura de gerenciamento de risco do insider.

É importante lembrar que enviar um aviso por email a um usuário * *_não_* resolve o caso como _Closed *. Em alguns casos, convém deixar um caso aberto após enviar um aviso a um usuário para procurar atividades de risco adicionais sem abrir um novo caso. Se quiser resolver um caso após enviar um aviso, você deve selecionar o caso de **resolução** como uma etapa de acompanhamento após enviar um aviso.

Para enviar um aviso ao usuário atribuído a uma ocorrência:

1. No [centro de conformidade da Microsoft 365](https://compliance.microsoft.com), vá para gerenciamento de **risco do insider** e selecione a guia **ocorrências** .
2. Selecione uma ocorrência e, em seguida, selecione o botão **Enviar aviso por email** na barra de ferramentas ação de ocorrência.
3. Na caixa de diálogo **Enviar aviso por email** , selecione o controle de menu suspenso **escolher um modelo de aviso** para selecionar o modelo de aviso para o aviso. Esta seleção preenche previamente os outros campos no aviso.
4. Revise os campos de aviso e atualize conforme apropriado. Os valores inseridos aqui substituirão os valores no modelo.
5. Selecione **Enviar** para enviar o aviso ao usuário ou selecione **Cancelar** feche a caixa de diálogo sem enviar o aviso para o usuário. Todos os avisos enviados são adicionados à fila de notas de caso no painel de **notas de caso** .

### <a name="escalate-for-investigation"></a>Escalonar para investigação

Escalonar o caso para investigação de usuário em situações em que a análise jurídica adicional é necessária para a atividade de risco do usuário. Esse escalonamento abre uma nova ocorrência de descoberta eletrônica avançada na sua organização do Microsoft 365. A descoberta eletrônica avançada fornece um fluxo de trabalho de ponta a ponta para preservar, coletar, analisar, analisar e exportar o conteúdo que responde às investigações legais internas e externas da sua organização. Também permite que sua equipe jurídica gerencie todo o fluxo de trabalho de notificação de retenção legal para se comunicar com os responsáveis envolvidos em um caso. A atribuição de um revisor como um responsável em uma ocorrência de descoberta eletrônica avançada criada a partir de um caso de gerenciamento de risco do insider ajuda sua equipe jurídica a executar a ação apropriada e a gerenciar a preservação de conteúdo. Para saber mais sobre casos de descoberta eletrônica avançada, confira [visão geral da descoberta eletrônica avançada no Microsoft 365](overview-ediscovery-20.md).

Para escalonar uma ocorrência para uma investigação de usuário:

1. No [centro de conformidade da Microsoft 365](https://compliance.microsoft.com), vá para gerenciamento de **risco do insider** e selecione a guia **ocorrências** .
2. Selecione uma ocorrência e, em seguida, selecione o botão **escalonar para investigação** na barra de ferramentas ação de ocorrência.
3. Na caixa **de diálogo escalar para investigação** , insira um nome para a nova investigação de usuário. Se necessário, insira observações sobre o caso e selecione **escalonar** .
4. Revise os campos de aviso e atualize conforme apropriado. Os valores inseridos aqui substituirão os valores no modelo.
5. Selecione **confirmar** para criar o caso de investigação de usuário ou selecione **Cancelar** para fechar a caixa de diálogo sem criar um novo caso de investigação de usuário.

Após o caso de gerenciamento de risco do insider ser escalonado para um novo caso de investigação de usuário, você pode examinar o novo caso na área de **descoberta eletrônica** do  >  **Advanced** centro de conformidade da Microsoft 365.

### <a name="run-automated-tasks-with-power-automate-flows-for-the-case"></a>Executar tarefas automatizadas com fluxos de energia automatizar o caso

Usando os fluxos de alimentação automatizados, os investigadores de risco e os analistas podem tomar medidas rapidamente para:

- Solicitar informações de RH ou de negócios sobre um usuário em um caso de risco do insider
- Notificar o gerente quando um usuário tiver um alerta de risco do insider
- Adicionar Lembrete de calendário para acompanhar um caso de risco do insider

Para executar, gerenciar ou criar fluxos automatizados de energia para um caso de gerenciamento de risco do insider:

1. Selecione **automatizar** na barra de ferramentas ação de caso. 
2. Escolha o fluxo automatizado de energia a ser executado e, em seguida, selecione **fluxo de execução** . 
3. Após a conclusão do fluxo, selecione **concluído** .

Para saber mais sobre os fluxos de automatização de energia do gerenciamento de risco do Insider, confira [introdução às configurações de gerenciamento de risco do insider](insider-risk-management-settings.md#power-automate-flows-preview).

### <a name="view-or-create-a-microsoft-teams-team-for-the-case"></a>Exibir ou criar uma equipe do Microsoft Teams para o caso

Quando a integração do Microsoft Teams para o gerenciamento de riscos do insider estiver habilitada nas configurações, uma equipe do Microsoft Teams é criada automaticamente sempre que um alerta é confirmado e um caso é criado. Os investigadores e analistas de risco podem abrir rapidamente o Microsoft Teams e navegar diretamente para a equipe para um caso, selecionando **Exibir equipe do Microsoft Teams** na barra de ferramentas ação de caso.

Para casos abertos antes de habilitar a integração com o Microsoft Team, os investigadores de risco e os analistas podem criar uma nova equipe do Microsoft Teams para um caso selecionando **criar equipe do Microsoft** Teams na barra de ferramentas ação de caso.

Quando um caso for resolvido, a equipe da Microsoft associada será automaticamente arquivada (oculta e desativada para somente leitura).

Para saber mais sobre o Microsoft Teams para gerenciamento de risco do Insider, confira [introdução às configurações de gerenciamento de risco do insider](insider-risk-management-settings.md#microsoft-teams-preview).

### <a name="share-the-case"></a>Compartilhar o caso

O compartilhamento de um caso de gerenciamento de risco do insider permite que os investigadores de risco e analistas colaborem facilmente com outros participantes de conformidade em sua organização. Você pode compartilhar rapidamente um link para um caso de gerenciamento de risco do insider com participantes externos da área de gerenciamento de casos. Para acessar o caso de gerenciamento de risco do Insider a partir do link, os participantes devem ser incluídos em qualquer um dos grupos de função de gerenciamento de risco do insider.

>[!NOTE]
>A visualização do ServiceNow terminará em novembro de 30 2020 e não será continuada. Agradecemos seus comentários e suporte enquanto determinamos as próximas etapas.

As seguintes opções de compartilhamento estão disponíveis:

- **ServiceNow** : depois de configurar o conector 365 do Servicenow da Microsoft para sua organização do Microsoft 365, você pode compartilhar facilmente um link para o caso, abrir um incidente ou solicitar uma alteração com sua organização do ServiceNow. Para compartilhar o caso com o servicenow, selecione **compartilhar** o  >  **servicenow** na ação de caso. A integração do ServiceNow com suporte ao gerenciamento de risco do insider inclui as seguintes informações e ações do caso:
    - **Nome da tarefa** : o nome da nova tarefa do ServiceNow.
    - **Descrição da tarefa** : a descrição da nova tarefa do ServiceNow. Este campo de descrição editável inclui automaticamente um link para o caso de gerenciamento de risco do insider.
    - **Tipo de tarefa** : o tipo de tarefa para a nova tarefa do ServiceNow, o *incidente* ou a *solicitação de alteração* .
    - **Prioridade** : a prioridade da nova tarefa do ServiceNow, *planejamento* , *baixo* , *médio* , *alto* ou *crítico* .
    - **Data de conclusão** : a data solicitada para concluir a tarefa do ServiceNow.

![Compartilhamento de gerenciamento de risco do insider com o ServiceNow](../media/insider-risk-share-servicenow.png)

- **Email** : compartilha um link para o caso de gerenciamento de risco do insider em um email. Você pode escolher qualquer cliente de email configurado localmente com essa opção de compartilhamento. Para compartilhar o link de caso com email, selecione **compartilhar**  >  **email** da barra de ferramentas ação de caso.
- **Copiar link** : copia um link para o caso de gerenciamento de risco do insider para a área de transferência. Para copiar o link de caso para a área de transferência, selecione **compartilhar**  >  **Copiar link** da barra de ferramentas ação de caso.

### <a name="resolve-the-case"></a>Resolver o caso

Após os analistas e investigadores de riscos terem concluído a análise e a investigação, um caso pode ser resolvido para agir em todos os alertas incluídos no caso. A resolução de um caso adiciona uma classificação de resolução, altera o status do caso para *fechado* e os motivos da ação de resolução são automaticamente adicionados à fila de notas de caso no painel de **notas de caso** . Os casos são resolvidos como:

- **Benigno** : a classificação de casos em que os alertas de correspondência de política são avaliados como baixo risco, não sério ou falso positivo.
- **Violação de política confirmada** : a classificação de casos em que os alertas de correspondência de política são avaliados como arriscados, sérios ou resultantes de más intenções.

Para resolver uma ocorrência:

1. No [centro de conformidade da Microsoft 365](https://compliance.microsoft.com), vá para gerenciamento de **risco do insider** e selecione a guia **ocorrências** .
2. Selecione uma ocorrência e, em seguida, selecione o botão **resolver ocorrência** na barra de ferramentas ação da ocorrência.
3. Na caixa de diálogo **resolver caso** , selecione o controle **resolver como** menu suspenso para selecionar a classificação de resolução para o caso. As opções são **benignas** ou as **violações de política confirmadas** .
4. Na caixa de diálogo **resolver caso** , insira os motivos para a classificação de resolução no campo de texto **ação realizada** .
5. Selecione **resolver** para fechar o caso ou selecione **Cancelar** fechar a caixa de diálogo sem resolver o caso.
