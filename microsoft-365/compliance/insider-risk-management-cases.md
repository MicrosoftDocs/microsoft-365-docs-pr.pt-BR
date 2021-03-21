---
title: Casos de gerenciamento de riscos insider
description: Saiba mais sobre casos de gerenciamento de riscos insider no Microsoft 365
keywords: Microsoft 365, gerenciamento de risco interno, gerenciamento de riscos, conformidade
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
ms.openlocfilehash: f6f01a1bed296b6af2e6be973de6605910809fc3
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50926399"
---
# <a name="insider-risk-management-cases"></a>Casos de gerenciamento de riscos insider

Os casos são o centro do gerenciamento de riscos insider e permitem que você investigue profundamente e aja em questões geradas por indicadores de risco definidos em suas políticas. Os casos são criados manualmente a partir de alertas em situações em que mais ações são necessárias para resolver um problema relacionado à conformidade para um usuário. Cada caso tem escopo para um único usuário e vários alertas para o usuário podem ser adicionados a um caso existente ou a um novo caso. 

Depois de investigar os detalhes de um caso, você pode tomar medidas por:

- enviar um aviso ao usuário
- resolvendo o caso como benigno
- compartilhando o caso com sua instância serviceNow ou com um destinatário de email
- escalonando o caso para uma investigação de Descoberta Avançada da Descoberta Interna

## <a name="cases-dashboard"></a>Painel de casos

O painel casos de gerenciamento de riscos **insider** permite que você veja e aja em casos. Cada widget de relatório no painel exibe informações dos últimos 30 dias.

- **Casos ativos**: o número total de casos ativos em investigação.
- **Casos nos últimos 30 dias**: O número total de casos criados, organizados pelo status *Ativo* *e* Fechado.
- **Estatísticas**: Tempo médio de casos ativos, listados em horas, dias ou meses.

A fila de casos lista todos os casos ativos e fechados para sua organização, além do status atual dos seguintes atributos de caso:

- **Nome da** ocorrência : o nome da ocorrência, definido quando um alerta é confirmado e o caso é criado.  
- **Status**: o status do caso, *Ativo* ou *Fechado*.
- **Usuário**: o usuário do caso. Se o anonimato para nomes de usuário estiver habilitado, as informações anônimas serão exibidas.
- **Caso de tempo aberto**: o tempo que passou desde que o caso foi aberto.
- **Total de alertas de política**: o número de combinações de política incluídas no caso. Esse número pode aumentar se novos alertas são adicionados ao caso.
- **Last updated**: The time that has passed since there has been a added case note or change in the case state.
- **Last updated by**: The name of the insider risk management analyst or investigator that last updated the case.

![Painel Casos de gerenciamento de riscos do Insider](../media/insider-risk-cases-dashboard.png)

Use o **controle Search** para pesquisar nomes de caso para texto específico e use o filtro de caso para classificar casos pelos seguintes atributos:

- Status
- Caso de tempo aberto, data de início e data de término
- Última atualização, data de início e data de término

## <a name="filter-cases"></a>Casos de filtro

Dependendo do número e do tipo de políticas de gerenciamento de riscos insider ativos em sua organização, a revisão de uma grande fila de casos pode ser desafiadora. O uso de filtros de caso pode ajudar analistas e investigadores a classificar casos por vários atributos. Para filtrar alertas no painel **Casos,** selecione o **controle Filtro.** Você pode filtrar casos por um ou mais atributos:

- **Status**: selecione um ou mais valores de status para filtrar a lista de casos. As opções são *Active* e *Closed*.
- **Caso de tempo aberto**: Selecione as datas de início e término para quando a ocorrência foi aberta.
- **Last updated**: Select the start and end dates for when the case was updated.

## <a name="investigate-a-case"></a>Investigar um caso

Uma investigação mais profunda sobre alertas de gerenciamento de riscos insider é fundamental para a tomada de ações corretivas adequadas. Os casos de gerenciamento de riscos insider são a ferramenta de gerenciamento central para aprofundar o histórico de atividades de risco do usuário, detalhes de alerta, a sequência de eventos de risco e explorar o conteúdo e as mensagens expostas aos riscos. Os analistas e investigadores de riscos também usam casos para centralizar comentários e anotações de revisão e processar a resolução de casos.

Selecionar um caso abre as ferramentas de gerenciamento de casos e permite que analistas e investigadores a fim de investigar os detalhes dos casos.

### <a name="case-overview"></a>Visão geral do caso

A **guia Visão geral** de caso resume a atividade de alerta e o histórico do nível de risco do caso. 

- O widget **Alertas** mostra as combinações de política para o caso, incluindo o status do alerta, a gravidade do risco de alerta e quando o alerta foi detectado. 
- O **gráfico de histórico de** nível de risco exibe o nível de risco do usuário nos últimos 30 dias. O gráfico de linha permite que analistas e investigadores vejam rapidamente a tendência no risco geral do usuário ao longo do tempo. 
- O **widget de conteúdo de** atividade de risco resume os tipos de dados e conteúdo contidos em alertas adicionados ao caso. Esse widget oferece uma exibição completa de todo o conjunto de dados e conteúdo em risco no caso.

O **painel de** detalhes de caso está disponível em todas as guias de gerenciamento de casos e resume os detalhes do caso para analistas de risco e investigadores. Ele inclui as seguintes áreas:

- **Nome da** ocorrência : o nome da ocorrência, prefixado com um número de sequência de caso gerado automaticamente e o nome do risco associado ao modelo de política que o primeiro alerta confirmado corresponde. 
- **Status da ocorrência**: o status atual do caso, *Ativo* ou *Fechado*.
- **Pontuação de risco do usuário**: O nível de risco calculado atual do usuário para o caso. Essa pontuação é calculada a cada 24 horas e usa as pontuações de risco de alerta de todos os alertas ativos associados ao usuário.
- **Alertas confirmados**: Lista de alertas para o usuário confirmado para o caso.
- **Conteúdo relacionado**: lista de conteúdo, classificação por fontes de conteúdo e tipos. Por exemplo, para o conteúdo do alerta de caso no SharePoint Online, você pode ver nomes de pasta ou arquivo listados associados à atividade de risco para alertas no caso.

![Detalhes de caso de gerenciamento de riscos insider](../media/insider-risk-case-details.png)

### <a name="alerts"></a>Alertas

A **guia Alertas** resume os alertas atuais incluídos no caso. Novos alertas podem ser adicionados a um caso existente e eles serão adicionados à fila **de** alerta à medida que eles são atribuídos. Os seguintes atributos de alerta estão listados na fila:

- Status
- Severity
- Tempo detectado

Selecione um alerta na fila para exibir a **página de detalhes alerta.**

Use o controle de pesquisa para pesquisar nomes de alerta para texto específico e use o filtro de alerta para classificar casos pelos seguintes atributos:

- Status
- Severity
- Hora detectada, data de início e data de término

Use o controle de filtro para filtrar alertas por vários atributos, incluindo:

- **Status**: selecione um ou mais valores de status para filtrar a lista de alertas. As opções são *Confirm*, *Dismissed*, *Needs review* e *Resolved*.
- **Severidade**: selecione um ou mais níveis de gravidade de risco de alerta para filtrar a lista de alertas. As opções são *Alta,* *Média* e *Baixa.*
- **Tempo detectado**: Selecione as datas de início e término para quando o alerta foi criado.
- **Política**: selecione uma ou mais políticas para filtrar os alertas gerados pelas políticas selecionadas.

### <a name="user-activity"></a>Atividades do usuário

A **guia Atividade do** usuário é uma das ferramentas mais poderosas para análise e investigação de riscos internos para casos na solução de gerenciamento de riscos internos. Essa guia é estruturada para habilitar uma revisão rápida de um caso, incluindo uma linha do tempo histórica de todos os alertas, detalhes de alerta, a pontuação de risco atual para o usuário no caso, a sequência de eventos de risco e controles para tomar medidas efetivas para conter os riscos no caso.

![Atividade do usuário de gerenciamento de riscos do Insider](../media/insider-risk-user-activities.png)

1. **Filtros de** tempo : Por padrão, os últimos seis meses de alertas confirmados no caso são exibidos no gráfico de atividades do usuário. Você pode filtrar facilmente a exibição do gráfico selecionando as guias *6 Meses*, *3* Meses ou *1* Mês no gráfico de bolhas.
2. **Atividade e detalhes do alerta de** risco : As atividades de risco são exibidas visualmente como bolhas coloridas no gráfico de atividades do usuário. Bolhas são criadas para diferentes categorias de risco e o tamanho da bolha é proporcional ao número de atividades de risco para a categoria. Selecione uma bolha para exibir os detalhes de cada atividade de risco. Os detalhes incluem:
    - **Data** da atividade de risco.
    - A **categoria atividade de risco**. Por exemplo, *Email(s) com anexos enviados* fora da organização ou *Arquivos baixados do SharePoint Online*.
    - **Pontuação de** risco para o alerta. Essa pontuação é a pontuação numérica para o nível de gravidade do risco de alerta.
    - Número de eventos associados ao alerta. Links para cada arquivo ou email associado à atividade de risco também estão disponíveis.
3. **Sequência de riscos (visualização)**: a ordem cronológica das atividades arriscadas é um aspecto importante da investigação de risco e identificar essas atividades relacionadas é uma parte importante da avaliação do risco geral para sua organização. As atividades de alerta relacionadas são exibidas com linhas de conexão para destacar que essas atividades estão associadas a uma área de risco maior. Essa exibição de atividades pode ajudar os investigadores literalmente a "conectar os pontos" para atividades de risco que poderiam ter sido vistas como eventos isolados ou isolados. Selecione qualquer bolha na sequência para exibir detalhes de todas as atividades de risco associadas. Os detalhes incluem:

    - **Nome** da sequência.
    - **Intervalo** de **data ou data** da sequência.
    - **Pontuação de** risco para a sequência. Essa pontuação é a pontuação numérica para a sequência dos níveis combinados de gravidade de risco de alerta para cada atividade relacionada na sequência.
    - **Número de eventos associados a cada alerta na sequência**. Links para cada arquivo ou email associado a cada atividade de risco também estão disponíveis.
    - **Mostrar atividades em sequência**. Exibe a sequência como uma linha de realçamento no gráfico de bolhas e expande os detalhes do alerta para exibir todos os alertas relacionados na sequência.

4. **Legenda de atividade de** risco : na parte inferior do gráfico de atividades do usuário, uma legenda codificada por cores ajuda você a determinar rapidamente a categoria de risco para cada alerta.
5. **Cronologia da** atividade de risco : a cronologia completa de todos os alertas de risco associados ao caso estão listados, incluindo todos os detalhes disponíveis na bolha de alerta correspondente.
6. **Ações de caso**: As opções para resolver o caso estão na barra de ferramentas de ação de caso. Você pode resolver um caso, enviar um aviso de email para o usuário ou escalonar o caso para uma investigação de dados ou de usuário.

### <a name="activity-explorer-preview"></a>Explorador de atividades (visualização)

>[!IMPORTANT]
>A guia Explorador de atividades está disponível na área de gerenciamento de ocorrências para usuários com eventos disparados depois que esse recurso está disponível em sua organização.

A **guia Explorador de** Atividades permite que analistas de risco e investigadores revisem os detalhes de atividade associados a alertas de risco. Por exemplo, como parte das ações de gerenciamento de casos, os investigadores e analistas podem precisar revisar todas as atividades de risco associadas ao caso para obter mais detalhes. Com o **Explorador de** Atividades, os revisadores podem revisar rapidamente uma linha do tempo de atividade arriscada detectada e identificar e filtrar todas as atividades de risco associadas a alertas.

Para obter mais informações sobre o explorador de atividades, consulte o artigo Alertas de gerenciamento de riscos [do Insider.](insider-risk-management-alerts.md#activity-explorer-preview)

### <a name="content-explorer"></a>Explorador de conteúdo

A **guia Explorador de** conteúdo permite que analistas de risco e investigadores revisem cópias de todos os arquivos individuais e mensagens de email associadas a alertas de risco. Por exemplo, se um alerta for criado quando um usuário baixar centenas de arquivos do SharePoint Online e a atividade disparar um alerta de política, todos os arquivos baixados do alerta serão capturados e copiados para o caso de gerenciamento de risco interno de fontes de armazenamento originais.

O Explorador de Conteúdo é uma ferramenta poderosa com recursos básicos e avançados de pesquisa e filtragem. Para saber mais sobre como usar o explorador de conteúdo, consulte [Insider risk management Content explorer](insider-risk-management-content-explorer.md).

![Caso de gerenciamento de riscos insider Explorador de conteúdo](../media/insider-risk-content-explorer.png)

### <a name="case-notes"></a>Anotações de caso

A **guia Anotações** de Caso, no caso, é onde os analistas de risco e os investigadores compartilham comentários, comentários e percepções sobre seu trabalho para o caso. As anotações são adições permanentes a uma ocorrência e não podem ser editadas ou excluídas depois que a nota é salva. Quando um caso é criado a partir  de um alerta, os comentários inseridos na caixa de diálogo Confirmar alerta e criar caso de risco interno são adicionados automaticamente como uma observação de caso.

O painel de anotações de caso exibe anotações do usuário que criou a nota e o tempo passado desde que a nota foi salva. Para pesquisar o campo de texto da nota de caso em busca de uma palavra-chave específica, use o botão **Pesquisar** no painel de ocorrências e insira uma palavra-chave específica.

Para adicionar uma nota a um caso:

1. No Centro de conformidade do [Microsoft 365,](https://compliance.microsoft.com)vá para Gerenciamento de riscos **do Insider** e selecione a **guia** Casos.
2. Selecione um caso e selecione a guia **Anotações de** caso.
3. Selecione **Adicionar nota de caso**.
4. Na caixa **de diálogo Adicionar nota de caso,** digite sua nota para o caso. Selecione **Salvar** para adicionar a nota à ocorrência ou selecione **Cancelar** fechar sem salvar a nota no caso.

### <a name="contributors"></a>Colaboradores

A **guia Colaboradores,** no caso, é onde os analistas de risco e os investigadores podem adicionar outros revisadores ao caso. Por padrão, todos os usuários atribuídos às funções Analistas de Gerenciamento de Riscos do Insider e Investigadores de Gerenciamento de Riscos do **Insider** são **listados** como colaboradores para cada caso ativo e fechado. Somente os usuários atribuídos à **função Investigadores** de Gerenciamento de Riscos do Insider têm permissão para exibir arquivos e mensagens no explorador de conteúdo.

O acesso temporário a um caso pode ser concedido adicionando um usuário como colaborador. Os colaboradores têm todo o controle de gerenciamento de caso no caso específico, exceto:

- Permissão para confirmar ou descartar alertas
- Permissão para editar os colaboradores para casos
- Permissão para exibir arquivos e mensagens no explorador de conteúdo

Para adicionar um colaborador a um caso:

1. No Centro de conformidade do [Microsoft 365,](https://compliance.microsoft.com)vá para Gerenciamento de riscos **do Insider** e selecione a **guia** Casos.
2. Selecione um caso e selecione a guia **Colaboradores.**
3. Selecione **Adicionar colaborador**.
4. Na caixa **de diálogo** Adicionar colaborador, comece a digitar o nome do usuário que você deseja adicionar e selecione o usuário na lista de usuários sugerida. Essa lista é gerada a partir do Azure Active Directory da sua assinatura de locatário.
5. Selecione **Adicionar** para adicionar o usuário como colaborador ou selecione **Cancelar** fechar a caixa de diálogo sem adicionar o usuário como colaborador.

## <a name="case-actions"></a>Ações de caso

Os analistas de risco e os investigadores podem tomar medidas em um caso em um dos vários métodos, dependendo da gravidade do caso, do histórico de risco do usuário e das diretrizes de risco da sua organização. Em algumas situações, você pode precisar escalar um caso para um usuário ou investigação de dados para colaborar com outras áreas da sua organização e para aprofundar as atividades de risco. O gerenciamento de riscos do insider está fortemente integrado a outras soluções de conformidade do Microsoft 365 para ajudá-lo no gerenciamento de resolução de ponta a ponta.

### <a name="send-email-notice"></a>Enviar aviso de email

Na maioria dos casos, as ações do usuário que criam alertas de risco interno são inadvertentes ou acidentais. Enviar um aviso de lembrete para o usuário por email é um método eficaz para documentar a revisão e a ação de caso e é um método para lembrar os usuários das políticas corporativas ou apontar para o treinamento de atualização. Os avisos são [gerados a](insider-risk-management-notices.md) partir de modelos de aviso que você cria para sua infraestrutura de gerenciamento de riscos insider.

É importante lembrar que enviar um aviso de email para um usuário ***** não _ resolve o caso como _Closed*. Em alguns casos, talvez você queira deixar um caso aberto após enviar um aviso a um usuário para procurar mais atividades de risco sem abrir um novo caso. Se você quiser resolver um caso depois de enviar um aviso, selecione o caso **Resolver** como uma etapa a seguir após o envio de um aviso.

Para enviar um aviso ao usuário atribuído a uma ocorrência:

1. No Centro de conformidade do [Microsoft 365,](https://compliance.microsoft.com)vá para Gerenciamento de riscos **do Insider** e selecione a **guia** Casos.
2. Selecione uma ocorrência e selecione o botão **Enviar aviso de email** na barra de ferramentas de ação de caso.
3. Na caixa de diálogo Enviar aviso **de email,** selecione o controle suspenso **Escolher um** modelo de aviso para selecionar o modelo de aviso para o aviso. Essa seleção pré-preenche os outros campos no aviso.
4. Revise os campos de aviso e atualize conforme apropriado. Os valores inseridos aqui substituirão os valores no modelo.
5. Selecione **Enviar** para enviar o aviso ao usuário ou selecione **Cancelar** fechar a caixa de diálogo sem enviar o aviso ao usuário. Todos os avisos enviados são adicionados à fila de anotações de caso no painel **Anotações de** Caso.

### <a name="escalate-for-investigation"></a>Escalonar para investigação

Agilizar o caso da investigação do usuário em situações em que a revisão jurídica adicional é necessária para a atividade de risco do usuário. Essa escalonamento abre um novo caso de Descoberta Secreta Avançada em sua organização do Microsoft 365. A Descoberta Externa Avançada fornece um fluxo de trabalho de ponta a ponta para preservar, coletar, analisar, analisar e exportar conteúdo que responde às investigações legais internas e externas da sua organização. Ele também permite que sua equipe jurídica gerencie todo o fluxo de trabalho de notificação de responsabilidade legal para se comunicar com os custodiantes envolvidos em um caso. Atribuir um revistor como um custodiante em um caso de Descoberta Avançada criado a partir de um caso de gerenciamento de risco interno ajuda sua equipe jurídica a tomar as medidas apropriadas e gerenciar a preservação de conteúdo. Para saber mais sobre os casos de Descoberta Avançada de Descoberta e, consulte [Overview of Advanced eDiscovery in Microsoft 365](overview-ediscovery-20.md).

Para escalonar um caso para uma investigação de usuário:

1. No Centro de conformidade do [Microsoft 365,](https://compliance.microsoft.com)vá para Gerenciamento de riscos **do Insider** e selecione a **guia** Casos.
2. Selecione um caso e selecione o **botão Escalar para investigação** na barra de ferramentas de ação de caso.
3. Na caixa **de diálogo Escalonar para investigação,** insira um nome para a nova investigação de usuário. Se necessário, insira anotações sobre a ocorrência e selecione **Escalate**.
4. Revise os campos de aviso e atualize conforme apropriado. Os valores inseridos aqui substituirão os valores no modelo.
5. Selecione **Confirmar** para criar o caso de investigação do usuário ou selecione **Cancelar** para fechar a caixa de diálogo sem criar um novo caso de investigação de usuário.

Depois que o caso de gerenciamento de risco interno tiver sido escalonado para um novo caso de investigação de usuário, você poderá revisar o novo caso na área **Descoberta** Digital Avançada no centro de conformidade do  >   Microsoft 365.

### <a name="run-automated-tasks-with-power-automate-flows-for-the-case"></a>Executar tarefas automatizadas com fluxos do Power Automate para o caso

Usando fluxos do Power Automate recomendados, os investigadores e analistas de risco podem tomar medidas rapidamente para:

- Solicitar informações de RH ou negócios sobre um usuário em um caso de risco interno
- Notificar o gerente quando um usuário tiver um alerta de risco interno
- Adicionar lembrete de calendário para acompanhar um caso de risco interno
- Criar um registro para um caso de gerenciamento de risco interno no ServiceNow

Para executar, gerenciar ou criar fluxos do Power Automate para um caso de gerenciamento de risco interno:

1. Selecione **Automatizar** na barra de ferramentas de ação de caso. 
2. Escolha o fluxo do Power Automate a ser executado e selecione **Executar fluxo**. 
3. Após a conclusão do fluxo, selecione **Concluído**.

Para saber mais sobre fluxos do Power Automate para gerenciamento de riscos insider, consulte [Getting started with insider risk management settings](insider-risk-management-settings.md#power-automate-flows-preview).

### <a name="view-or-create-a-microsoft-teams-team-for-the-case"></a>Exibir ou criar uma equipe do Microsoft Teams para o caso

Quando a integração do Microsoft Teams para o gerenciamento de riscos insider está habilitada nas configurações, uma equipe do Microsoft Teams é criada automaticamente sempre que um alerta é confirmado e um caso é criado. Os investigadores e analistas de risco podem abrir rapidamente o Microsoft Teams e navegar diretamente para a equipe para um caso selecionando Exibir a equipe do **Microsoft Teams** na barra de ferramentas de ação de caso.

Para casos abertos antes da habilitação da integração do Microsoft Team, os investigadores e analistas de risco podem criar uma nova equipe do Microsoft Teams para um caso selecionando Criar equipe do **Microsoft Teams** na barra de ferramentas de ação de caso.

Quando um caso é resolvido, a Equipe da Microsoft associada será arquivada automaticamente (oculta e transformada em somente leitura).

Para saber mais sobre o Microsoft Teams para gerenciamento de riscos insider, consulte Como começar com as configurações de gerenciamento de riscos [insider.](insider-risk-management-settings.md#microsoft-teams-preview)

### <a name="resolve-the-case"></a>Resolver o caso

Depois que os analistas de risco e os investigadores concluíram sua revisão e investigação, um caso pode ser resolvido para agir em todos os alertas atualmente incluídos no caso. A resolução de um caso adiciona uma classificação de resolução, altera o status do caso para *Closed* e os motivos da ação de resolução são adicionados automaticamente à fila de anotações de caso no painel **Anotações de** caso. Os casos são resolvidos como:

- **Benigno**: a classificação para os casos em que os alertas de diretiva são avaliados como de baixo risco, não grave ou falso positivo.
- **Violação de política confirmada**: a classificação para os casos em que os alertas de diretiva são avaliados como arriscados, sérios ou o resultado de intenção mal-intencionada.

Para resolver um caso:

1. No Centro de conformidade do [Microsoft 365,](https://compliance.microsoft.com)vá para Gerenciamento de riscos **do Insider** e selecione a **guia** Casos.
2. Selecione um caso e selecione o botão **Resolver caso** na barra de ferramentas de ação de caso.
3. Na caixa **de diálogo Resolver caso,** selecione **o controle Resolver como** menu suspenso para selecionar a classificação de resolução do caso. As opções são **Violação de política benigna** **ou confirmada.**
4. Na caixa **de diálogo Resolver** caso, insira os motivos da classificação de resolução no campo Texto Ação **realizada.**
5. Selecione **Resolver** para fechar o caso ou selecione **Cancelar** fechar a caixa de diálogo sem resolver o caso.
