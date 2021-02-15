---
title: Casos de gerenciamento de riscos insider
description: Saiba mais sobre casos de gerenciamento de riscos insider no Microsoft 365
keywords: Microsoft 365, gerenciamento de riscos insider, gerenciamento de riscos, conformidade
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
ms.openlocfilehash: c128f9e0c5754305e8b4d785c6a88931bc3ea976
ms.sourcegitcommit: cbe8724bd71d1c002395d98f1451c5f578c824f9
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/26/2021
ms.locfileid: "49988167"
---
# <a name="insider-risk-management-cases"></a>Casos de gerenciamento de riscos insider

Os casos são o centro do gerenciamento de riscos insider e permitem que você investigue profundamente e aja em problemas gerados por indicadores de risco definidos em suas políticas. Os casos são criados manualmente a partir de alertas em situações em que mais ações são necessárias para resolver um problema relacionado à conformidade de um usuário. Cada caso tem como escopo um único usuário e vários alertas para o usuário podem ser adicionados a um caso existente ou a um novo caso. 

Depois de investigar os detalhes de um caso, você pode tomar medidas ao:

- enviar um aviso ao usuário
- resolvendo o caso como benigno
- compartilhando a ocorrência com sua instância do ServiceNow ou com um destinatário de email
- escalating the case for an Advanced eDiscovery investigation

## <a name="cases-dashboard"></a>Painel de casos

O painel de casos de gerenciamento de riscos **insider** permite que você veja e aja em casos. Cada widget de relatório no painel exibe informações dos últimos 30 dias.

- **Casos ativos:** o número total de casos ativos sob investigação.
- **Casos nos últimos 30 dias:** o número total de casos criados, organizados por status *Ativo* *e* Fechado.
- **Estatísticas:** tempo médio de ocorrências ativas, listadas em horas, dias ou meses.

A fila de casos lista todos os casos ativos e fechados para sua organização, além do status atual dos seguintes atributos de caso:

- **Nome da** ocorrência: o nome da ocorrência, definido quando um alerta é confirmado e o caso é criado.  
- **Status**: o status do caso, *Ativo* ou *Fechado.*
- **Usuário**: o usuário da ocorrência. Se o anonimato de nomes de usuário estiver habilitado, as informações anônimas serão exibidas.
- **Caso de tempo aberto:** o tempo que passou desde que o caso foi aberto.
- **Total de alertas de política:** o número de diretivas que são incluídas no caso. Esse número pode aumentar se novos alertas são adicionados ao caso.
- **Last updated**: The time that has passed since there has been an added case note or change in the case state.
- **Last updated by:** The name of the insider risk management analyst or investigator that last updated the case.

![Painel de casos de gerenciamento de riscos insider](../media/insider-risk-cases-dashboard.png)

Use o **controle de** pesquisa para pesquisar nomes de ocorrências para texto específico e use o filtro de ocorrências para classificar casos pelos seguintes atributos:

- Status
- Caso de hora aberto, data de início e data de término
- Última atualização, data de início e data de término

## <a name="filter-cases"></a>Casos de filtro

Dependendo do número e do tipo de políticas de gerenciamento de riscos insider ativos em sua organização, a revisão de uma grande fila de casos pode ser um desafio. O uso de filtros de caso pode ajudar analistas e investigadores a classificar casos por vários atributos. Para filtrar alertas no painel **Casos,** selecione o **controle Filter.** Você pode filtrar casos por um ou mais atributos:

- **Status:** selecione um ou mais valores de status para filtrar a lista de ocorrências. As opções são *Ativa* e *Fechada.*
- **Caso de hora aberto:** selecione as datas de início e término para quando a ocorrência foi aberta.
- **Last updated:** Select the start and end dates for when the case was updated.

## <a name="investigate-a-case"></a>Investigar um caso

Uma investigação mais profunda dos alertas de gerenciamento de riscos interno é fundamental para a tomada de ações corretivas adequadas. Os casos de gerenciamento de riscos insider são a ferramenta de gerenciamento central para se aprofundar no histórico de atividades de risco do usuário e nos detalhes do alerta e explorar o conteúdo e as mensagens expostas a riscos. Analistas e investigadores de risco também usam casos para centralizar comentários e anotações de revisão e processar a resolução de casos.

Selecionar um caso abre as ferramentas de gerenciamento de ocorrências e permite que analistas e investigadores se adcarem nos detalhes dos casos.

### <a name="case-overview"></a>Visão geral do caso

A **guia Visão geral** do caso resume a atividade de alerta e o histórico do nível de risco do caso. 

- O widget **Alertas** mostra as políticas de acordo com o caso, incluindo o status do alerta, a gravidade do risco de alerta e quando o alerta foi detectado. 
- O **gráfico de histórico do** nível de risco exibe o nível de risco do usuário nos últimos 30 dias. O gráfico de linhas permite que analistas e investigadores vejam rapidamente a tendência no risco geral do usuário ao longo do tempo. 
- O **widget de conteúdo atividade** de risco resume os tipos de dados e conteúdo contidos em alertas adicionados ao caso. Esse widget oferece uma exibição completa de todos os dados e conteúdo definidos em risco no caso.

O **painel detalhes** do caso está disponível em todas as guias de gerenciamento de casos e resume os detalhes do caso para analistas e investigadores de risco. Ele inclui as seguintes áreas:

- **Nome da** ocorrência: o nome da ocorrência, prefixado com um número de sequência de caso gerado automaticamente e o nome do risco associado ao modelo de política que o primeiro alerta confirmado corresponde. 
- **Status da** ocorrência: o status atual do caso, *Ativo* ou *Fechado.*
- **Pontuação de risco do usuário:** o nível de risco calculado atual do usuário para o caso. Essa pontuação é calculada a cada 24 horas e usa as pontuações de risco de alerta de todos os alertas ativos associados ao usuário.
- **Alertas confirmados:** lista de alertas para o usuário confirmados para o caso.
- **Conteúdo relacionado:** lista de conteúdo, ordenada por fontes e tipos de conteúdo. Por exemplo, para o conteúdo de alerta de caso no SharePoint Online, você pode ver nomes de pasta ou arquivo listados que estão associados à atividade de risco para alertas no caso.

![Detalhes do caso de gerenciamento de riscos interno](../media/insider-risk-case-details.png)

### <a name="alerts"></a>Alertas

A **guia Alertas** resume os alertas atuais incluídos no caso. Novos alertas podem ser adicionados a um caso existente e eles serão adicionados à fila de **alerta** à medida que são atribuídos. Os seguintes atributos de alerta estão listados na fila:

- Status
- Severity
- Tempo detectado

Selecione um alerta da fila para exibir a **página Detalhes do** alerta.

Use o controle de pesquisa para pesquisar nomes de alerta para texto específico e use o filtro de alerta para classificar casos pelos seguintes atributos:

- Status
- Severity
- Hora detectada, data de início e data de término

Use o controle de filtro para filtrar alertas por vários atributos, incluindo:

- **Status:** selecione um ou mais valores de status para filtrar a lista de alertas. As opções são *Confirmado*, *Descartado,* *Precisa de Revisão* e *Resolvido.*
- **Gravidade:** selecione um ou mais níveis de gravidade de risco de alerta para filtrar a lista de alertas. As opções são *Alta,* *Média* e *Baixa.*
- **Hora detectada:** selecione as datas de início e término para quando o alerta foi criado.
- **Política:** selecione uma ou mais políticas para filtrar os alertas gerados pelas políticas selecionadas.

### <a name="user-activity"></a>Atividades do usuário

A **guia Atividade do** usuário é uma das ferramentas mais poderosas para análise e investigação de riscos internos para casos na solução de gerenciamento de riscos internos. Essa guia é estruturada para permitir a revisão rápida de um caso, incluindo uma linha do tempo histórica de todos os alertas, todos os detalhes de alertas, a pontuação de risco atual do usuário no caso e controles para tomar medidas efetivas para conter os riscos no caso.

![Atividade do usuário de gerenciamento de riscos do Insider](../media/insider-risk-user-activities.png)

1. **Filtros de data e hora** da janela: por padrão, os últimos seis meses de alertas confirmados no caso são exibidos no gráfico de atividades do usuário. Você pode filtrar facilmente a exibição do gráfico com os controles deslizantes em ambas as extremidades da janela do gráfico ou definindo datas específicas de início e término no controle de filtro do gráfico.
2. **Atividade e detalhes do alerta de** risco: as atividades de risco são exibidas visualmente como bolhas coloridas no gráfico de atividades do usuário. Bolhas são criadas para diferentes categorias de risco e o tamanho da bolha é proporcional ao número de atividades de risco para a categoria. Selecione uma bolha para exibir os detalhes de cada atividade de risco. Os detalhes incluem:
    - **Data** da atividade de risco.
    - A **categoria de atividade de risco.** Por exemplo, *email(s) com anexos enviados para fora* da organização ou *Arquivos baixados do SharePoint Online.*
    - **Pontuação de** risco para o alerta. Essa pontuação é a pontuação numérica para o nível de gravidade do risco de alerta.
    - Número de eventos associados ao alerta. Links para cada arquivo ou email associado à atividade de risco também estão disponíveis.
3. **Legenda de atividade de** risco: na parte inferior do gráfico de atividades do usuário, uma legenda codificada por cores ajuda a determinar rapidamente a categoria de risco para cada alerta.
4. **Cronograma de atividades de** risco : a cronologia completa de todos os alertas de risco associados ao caso estão listados, incluindo todos os detalhes disponíveis na bolha de alerta correspondente.
5. **Ações de caso:** As opções para resolver o caso estão na barra de ferramentas de ação de caso. Você pode resolver um caso, enviar um aviso por email para o usuário ou encaminhar o caso para uma investigação de dados ou de usuário.

### <a name="activity-explorer-preview"></a>Explorador de atividades (visualização)

>[!IMPORTANT]
>A guia Explorador de atividades está disponível na área de gerenciamento de caso para usuários com eventos disparados depois que esse recurso está disponível em sua organização.

A **guia Explorador de** atividades permite que analistas e investigadores de risco revisem os detalhes de atividade associados a alertas de risco. Por exemplo, como parte das ações de gerenciamento de casos, os investigadores e analistas talvez precisem revisar todas as atividades de risco associadas ao caso para obter mais detalhes. Com o **Explorador de atividades,** os revisadores podem analisar rapidamente uma linha do tempo de atividade arriscada detectada e identificar e filtrar todas as atividades de risco associadas a alertas.

Para obter mais informações sobre o Explorador de atividades, consulte o artigo de alertas de [gerenciamento de riscos do Insider.](insider-risk-management-alerts.md#activity-explorer-preview)

### <a name="content-explorer"></a>Explorador de Conteúdo

A **guia Explorador de** Conteúdo permite que analistas e investigadores de risco revisem cópias de todos os arquivos individuais e mensagens de email associadas a alertas de risco. Por exemplo, se um alerta for criado quando um usuário baixar centenas de arquivos do SharePoint Online e a atividade disparar um alerta de política, todos os arquivos baixados para o alerta serão capturados e copiados para o caso de gerenciamento de riscos interno das fontes de armazenamento originais.

O Explorador de Conteúdo é uma ferramenta avançada com recursos básicos e avançados de pesquisa e filtragem. Para saber mais sobre como usar o Explorador de Conteúdo, consulte o Explorador de Conteúdo de gerenciamento de riscos [do Insider.](insider-risk-management-content-explorer.md)

![Insider risk management case Content Explorer](../media/insider-risk-content-explorer.png)

### <a name="case-notes"></a>Anotações de caso

A **guia Anotações** de caso é onde analistas e investigadores de risco compartilham comentários, comentários e ideias sobre seu trabalho para o caso. As anotações são adições permanentes a uma ocorrência e não podem ser editadas ou excluídas após a anotação ser salva. Quando um caso é criado a partir  de um alerta, os comentários inseridos na caixa de diálogo Confirmar alerta e criar caso de risco interno são adicionados automaticamente como uma anotação de caso.

O painel de anotações de caso exibe anotações do usuário que criou a nota e o tempo que passou desde que a anotação foi salva. Para pesquisar o campo de texto de  anotação de caso de uma palavra-chave específica, use o botão Pesquisar no painel de ocorrências e insira uma palavra-chave específica.

Para adicionar uma observação a uma ocorrência:

1. No centro [de conformidade do Microsoft 365,](https://compliance.microsoft.com)vá para o gerenciamento de riscos do **Insider** e selecione a **guia** Casos.
2. Selecione uma ocorrência e, em seguida, selecione a **guia Anotações de** caso.
3. Selecione **Add case note**.
4. Na caixa **de diálogo Adicionar anotação de** caso, digite sua nota para a ocorrência. Selecione **Salvar** para adicionar a nota à ocorrência ou selecione **Cancelar** fechar sem salvar a anotação na ocorrência.

### <a name="contributors"></a>Colaboradores

A **guia Colaboradores,** no caso, é onde analistas e investigadores de risco podem adicionar outros revisadores ao caso. Por padrão, todos os usuários atribuídos às funções de Analistas de Gerenciamento de Riscos Do Insider e Investigadores de Gerenciamento de Riscos **Insider** são **listados** como colaboradores para cada caso ativo e fechado. Somente os usuários atribuídos à **função Investigadores** de Gerenciamento de Riscos Insider têm permissão para exibir arquivos e mensagens no Explorador de Conteúdo.

O acesso temporário a uma ocorrência pode ser concedido adicionando um usuário como colaborador. Os colaboradores têm todo o controle de gerenciamento de caso no caso específico, exceto:

- Permissão para confirmar ou descartar alertas
- Permissão para editar os colaboradores para casos
- Permissão para exibir arquivos e mensagens no Explorador de Conteúdo

Para adicionar um colaborador a uma ocorrência:

1. No centro [de conformidade do Microsoft 365,](https://compliance.microsoft.com)vá para o gerenciamento de riscos do **Insider** e selecione a **guia** Casos.
2. Selecione uma ocorrência e selecione a **guia Colaboradores.**
3. Selecione **Adicionar colaborador.**
4. Na caixa **de diálogo** Adicionar colaborador, comece a digitar o nome do usuário que você deseja adicionar e selecione o usuário na lista de usuários sugeridos. Essa lista é gerada a partir do Azure Active Directory da sua assinatura de locatário.
5. Selecione **Adicionar** para adicionar o usuário como colaborador ou selecione **Cancelar** fechar a caixa de diálogo sem adicionar o usuário como colaborador.

## <a name="case-actions"></a>Ações de caso

Analistas e investigadores de risco podem tomar medidas em um caso em um dos vários métodos, dependendo da gravidade do caso, do histórico de risco do usuário e das diretrizes de risco da sua organização. Em algumas situações, talvez seja necessário escalonar um caso para um usuário ou investigação de dados para colaborar com outras áreas da sua organização e para aprofundar-se nas atividades de risco. O gerenciamento de riscos insider está totalmente integrado com outras soluções de conformidade do Microsoft 365 para ajudá-lo com o gerenciamento de resolução de ponta a ponta.

### <a name="send-email-notice"></a>Enviar aviso por email

Na maioria dos casos, as ações do usuário que criam alertas de risco interno são inadvertida ou acidentais. Enviar um aviso de lembrete para o usuário por email é um método eficaz para documentar a revisão e a ação de casos e é um método para lembrar os usuários de políticas corporativas ou apontar para o treinamento de atualização. Os avisos são [gerados a](insider-risk-management-notices.md) partir de modelos de aviso que você cria para sua infraestrutura de gerenciamento de riscos insider.

É importante lembrar que enviar um aviso por email para um usuário **_não_* _ resolve o caso como _Closed*. Em alguns casos, talvez você queira deixar um caso aberto após enviar um aviso para um usuário para procurar mais atividades de risco sem abrir um novo caso. Se você quiser resolver um caso depois de enviar um aviso, selecione o caso **Resolver** como uma etapa seguinte após enviar um aviso.

Para enviar um aviso ao usuário atribuído a uma ocorrência:

1. No centro [de conformidade do Microsoft 365,](https://compliance.microsoft.com)vá para o gerenciamento de riscos do **Insider** e selecione a **guia** Casos.
2. Selecione uma ocorrência e, em seguida, selecione **o botão Enviar aviso de email** na barra de ferramentas de ação de caso.
3. Na caixa **de diálogo Enviar aviso por email,** selecione o **controle** suspenso Escolher um modelo de aviso para selecionar o modelo de aviso para o aviso. Essa seleção pré-preenche os outros campos no aviso.
4. Revise os campos de aviso e atualize conforme apropriado. Os valores inseridos aqui substituirão os valores no modelo.
5. Selecione **Enviar** para enviar o aviso ao usuário ou selecione **Cancelar** fechar a caixa de diálogo sem enviar o aviso ao usuário. Todos os avisos enviados são adicionados à fila de anotações de caso no painel **Anotações de** caso.

### <a name="escalate-for-investigation"></a>Escalonar para investigação

Escalone o caso de investigação do usuário em situações em que uma revisão legal adicional é necessária para a atividade de risco do usuário. Esse escalonamento abre um novo caso de Descoberta eDiscovery Avançada em sua organização do Microsoft 365. A Descoberta Avançada fornece um fluxo de trabalho de ponta a ponta para preservar, coletar, analisar, analisar e exportar conteúdo que responde às investigações legais internas e externas da sua organização. Ele também permite que sua equipe jurídica gerencie todo o fluxo de trabalho de notificação de responsabilidade legal para se comunicar com os responsáveis envolvidos em um caso. Atribuir um revisador como um custodiante em um caso de Descoberta Avançada criado a partir de um caso de gerenciamento de riscos insider ajuda sua equipe jurídica a tomar as medidas apropriadas e gerenciar a preservação do conteúdo. Para saber mais sobre os casos de Descoberta Avançada, confira Visão Geral da Descoberta Avançada no [Microsoft 365.](overview-ediscovery-20.md)

Para escalonar um caso para uma investigação de usuário:

1. No centro [de conformidade do Microsoft 365,](https://compliance.microsoft.com)vá para o gerenciamento de riscos do **Insider** e selecione a **guia** Casos.
2. Selecione uma ocorrência e selecione o **botão Escalonar para investigação** na barra de ferramentas de ação de caso.
3. Na caixa **de diálogo Escalonar para investigação,** insira um nome para a nova investigação de usuário. Se necessário, insira anotações sobre a ocorrência e selecione **Escalonar**.
4. Revise os campos de aviso e atualize conforme apropriado. Os valores inseridos aqui substituirão os valores no modelo.
5. Selecione **Confirmar** para criar o caso de investigação do usuário ou **selecione Cancelar** para fechar a caixa de diálogo sem criar um novo caso de investigação de usuário.

Depois que o caso de gerenciamento de riscos insider tiver sido escalonado para um novo caso de investigação de usuário, você poderá analisar o novo caso na área Avançada de Descoberta e no centro de conformidade do  >   Microsoft 365.

### <a name="run-automated-tasks-with-power-automate-flows-for-the-case"></a>Executar tarefas automatizadas com fluxos do Power Automate para o caso

Usando fluxos recomendados do Power Automate, os investigadores e analistas de risco podem tomar medidas rapidamente para:

- Solicitar informações do RH ou da empresa sobre um usuário em um caso de risco interno
- Notificar o gerente quando um usuário tiver um alerta de risco interno
- Adicionar lembrete de calendário para acompanhar um caso de risco interno
- Criar um registro para um caso de gerenciamento de risco interno no ServiceNow

Para executar, gerenciar ou criar fluxos do Power Automate para um caso de gerenciamento de riscos interno:

1. Selecione **Automatizar na** barra de ferramentas de ação de caso. 
2. Escolha o fluxo do Power Automate a ser executado e selecione **Executar fluxo.** 
3. Após a conclusão do fluxo, selecione **Concluído.**

Para saber mais sobre fluxos do Power Automate para gerenciamento de riscos insider, consulte Getting [started with insider risk management settings](insider-risk-management-settings.md#power-automate-flows-preview).

### <a name="view-or-create-a-microsoft-teams-team-for-the-case"></a>Exibir ou criar uma equipe do Microsoft Teams para o caso

Quando a integração do Microsoft Teams para gerenciamento de riscos insider está habilitada nas configurações, uma equipe do Microsoft Teams é criada automaticamente sempre que um alerta é confirmado e um caso é criado. Os investigadores e analistas de risco podem abrir rapidamente o Microsoft Teams e navegar diretamente para a equipe em busca de um caso selecionando Exibir a equipe **do Microsoft Teams** na barra de ferramentas de ação do caso.

Para casos abertos antes da habilitação da integração com o Microsoft Team, os investigadores e analistas de risco podem criar uma nova equipe do Microsoft Teams para um caso selecionando Criar a equipe do **Microsoft Teams** na barra de ferramentas de ação de caso.

Quando um caso é resolvido, a Equipe da Microsoft associada será automaticamente arquivada (oculta e transformada em somente leitura).

Para saber mais sobre o Microsoft Teams para gerenciamento de riscos insider, confira Como começar a trabalhar com as configurações de gerenciamento de [riscos insider.](insider-risk-management-settings.md#microsoft-teams-preview)

### <a name="share-the-case"></a>Compartilhar a ocorrência

O compartilhamento de um caso de gerenciamento de riscos interno permite que os investigadores e analistas de risco colaborem facilmente com outros participantes da conformidade em sua organização. Você pode compartilhar rapidamente um link para um caso de gerenciamento de riscos internos com participantes externos da área de gerenciamento de casos. Para acessar o caso de gerenciamento de riscos interno a partir do link, as partes interessadas devem ser incluídas em qualquer um dos grupos de função de gerenciamento de risco interno.

>[!NOTE]
>Agradecemos seus comentários e suporte durante a visualização do conector do ServiceNow. Decidimos encerrar a visualização do conector serviceNow e interromper o suporte no gerenciamento de riscos insider em 30 de novembro de 2020. Estamos avaliando ativamente métodos alternativos para fornecer aos clientes a integração do ServiceNow no gerenciamento de riscos insider.

As seguintes opções de compartilhamento estão disponíveis:

- **ServiceNow**: depois de configurar o conector do Microsoft 365 ServiceNow para sua organização do Microsoft 365, você pode compartilhar facilmente um link para o caso, abrir um incidente ou solicitar uma alteração com sua organização do ServiceNow. Para compartilhar a ocorrência com o ServiceNow, selecione **Compartilhar**  >  **ServiceNow** na ação da ocorrência. A integração do ServiceNow com o gerenciamento de riscos interno inclui as seguintes informações e ações de caso:
    - **Nome da** tarefa: o nome da nova tarefa do ServiceNow.
    - **Descrição da** tarefa: a descrição da nova tarefa do ServiceNow. Esse campo de descrição editável inclui automaticamente um link para o caso de gerenciamento de riscos interno.
    - **Tipo de** tarefa: o tipo de tarefa para a nova tarefa serviceNow, *incidente* ou *solicitação de alteração*.
    - **Prioridade**: a prioridade para a nova tarefa serviceNow, *planejamento*, *baixo*, *moderado*, *alto* ou *crítico*.
    - **Data de** conclusão: a data solicitada para concluir a tarefa do ServiceNow.

![Compartilhamento de gerenciamento de riscos interno com o ServiceNow](../media/insider-risk-share-servicenow.png)

- **Email:** compartilha um link para o caso de gerenciamento de riscos interno em um email. Você pode escolher qualquer cliente de email configurado localmente com essa opção de compartilhamento. Para compartilhar o link da ocorrência com o email, selecione **Compartilhar** Email na barra de ferramentas  >   de ação da ocorrência.
- **Link de cópia:** copia um link para o caso de gerenciamento de risco interno para sua área de transferência. Para copiar o link da ocorrência para a área de transferência, **selecione** o link Copiar  >  **Compartilhamento** na barra de ferramentas de ação da ocorrência.

### <a name="resolve-the-case"></a>Resolver o caso

Depois que os analistas e investigadores de risco concluíram sua revisão e investigação, um caso pode ser resolvido para agir em todos os alertas atualmente incluídos no caso. Resolver um caso adiciona uma classificação de resolução, altera o status do caso para *Fechado* e os motivos da ação de resolução são adicionados automaticamente à fila de anotações de caso no painel Anotações **de** caso. Os casos são resolvidos como:

- **Benigno**: a classificação para casos em que a política corresponder alertas é avaliada como baixo risco, não sério ou falso positivo.
- **Violação confirmada de política:** a classificação para casos em que a política corresponder alertas é avaliada como arriscada, séria ou o resultado de intenção mal-intencionada.

Para resolver um caso:

1. No centro [de conformidade do Microsoft 365,](https://compliance.microsoft.com)vá para o gerenciamento de riscos do **Insider** e selecione a **guia** Casos.
2. Selecione uma ocorrência e, em seguida, selecione o **botão Resolver caso** na barra de ferramentas de ação de caso.
3. Na caixa **de diálogo Resolver caso,** selecione **o controle Resolver** como menu suspenso para selecionar a classificação de resolução do caso. As opções são **Violação de política Benigna** **ou Confirmada.**
4. Na caixa **de diálogo Resolver caso,** insira os motivos para a classificação de resolução no **campo de texto** Ação tomada.
5. Selecione **Resolver** para fechar a ocorrência ou **selecione Cancelar** fechar a caixa de diálogo sem resolver o caso.
