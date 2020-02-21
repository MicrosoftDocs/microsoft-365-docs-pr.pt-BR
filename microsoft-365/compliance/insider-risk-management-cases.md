---
title: Casos de gerenciamento de risco do insider
description: Saiba mais sobre os casos de gerenciamento de risco do insider no Microsoft 365
keywords: Microsoft 365, gerenciamento de risco do Insider, gerenciamento de riscos, conformidade
localization_priority: Normal
ms.prod: Microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: m365-security-compliance
ms.openlocfilehash: 6b5132cad5725e46a49b9010868ede423321f307
ms.sourcegitcommit: 87cc278ea2ddcd536ecfaa3dfae9a5ddaa502cf9
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42179172"
---
# <a name="insider-risk-management-cases"></a>Casos de gerenciamento de risco do insider

Os casos são o coração do gerenciamento de risco do insider e permitem que você investigue profundamente e execute ações geradas pelos indicadores de risco definidos em suas políticas. Os casos são criados manualmente a partir de alertas nas situações em que a ação adicional é necessária para lidar com um problema relacionado à conformidade de um funcionário. Cada caso é delimitado a um único funcionário, e vários alertas para o funcionário podem ser adicionados a um caso existente ou a um novo caso. Após investigar os detalhes de um caso, você pode executar uma ação enviando ao funcionário um aviso, resolvendo o caso como benigno ou encaminhar para uma investigação de dados ou de funcionários.

## <a name="case-dashboard"></a>Painel de casos

O **painel de casos** de gerenciamento de risco do insider permite que você visualize e execute ações em casos. Cada widget de relatório no painel exibe informações dos últimos 30 dias.

- **Casos ativos**: o número total de casos ativos sob investigação.
- **Casos nos últimos 30 dias**: o número total de ocorrências criadas, classificadas por status *ativo* e *fechado* .
- **Estatísticas**: tempo médio de ocorrências ativas, listadas em horas, dias ou meses.

A fila de casos lista todos os casos ativos e fechados para sua organização, além do estado atual dos seguintes atributos de caso:

- **Nome do caso**: o nome do caso, definido quando um alerta é confirmado e o caso é criado.  
- **Status**: o status do caso, *ativo* ou *fechado*.
- **Usuário**: o funcionário do caso.
- **Caso de tempo aberto**: o tempo decorrido desde que o caso foi aberto.
- **Total de alertas de política**: o número de correspondências de política incluído no caso. Esse número pode aumentar se novos alertas forem adicionados ao caso.
- **Última atualização**: o tempo decorrido desde que houve uma observação de caso adicionada ou alteração no estado de caso.
- **Última atualização**: o nome do analista de gerenciamento de risco do insider ou do investigador que atualizou pela última vez o caso.

![Painel de casos de gerenciamento de risco do insider](../media/insider-risk-cases-dashboard.png)

Use o controle de **pesquisa** para pesquisar nomes de caso para texto específico e use o filtro de caso para classificar casos pelos seguintes atributos:

- Status
- Caso de tempo aberto, data de início e data de término
- Última atualização, data de início e data de término

## <a name="investigate-a-case"></a>Investigue uma ocorrência

A investigação mais profunda dos alertas de gerenciamento de risco do Insider é fundamental para a realização de ações corretivas adequadas. Os casos de gerenciamento de risco do insider são a ferramenta de gerenciamento central para se aprofundar nos detalhes de alerta e histórico de atividades de risco do funcionário e explorar o conteúdo e as mensagens expostos aos riscos. Os analistas e investigadores de risco também usam casos para centralizar comentários e notas de revisão e para processar a resolução de casos. 

Selecionar um caso abre as ferramentas de gerenciamento de casos e permite que analistas e investigadores se aprofundarem nos detalhes dos casos.

### <a name="case-overview"></a>Visão geral da ocorrência

A guia **visão geral de casos** resume a atividade de alerta e o histórico de nível de risco da ocorrência. O widget **alertas** mostra as correspondências de política para o caso, incluindo o status do alerta, a severidade do risco de alerta e quando o alerta foi detectado. O gráfico de **histórico de nível de risco** exibe o nível de risco do usuário nos últimos 30 dias. O gráfico de linhas permite que analistas e investigadores vejam rapidamente a tendência no risco geral do usuário ao longo do tempo. O widget **conteúdo da atividade de risco** resume os tipos de dados e conteúdo contidos nos alertas adicionados ao caso. Este widget fornece uma visão completa de todos os dados e conjunto de conteúdo em risco no caso.

O painel de **detalhes de caso** está disponível em todas as guias de gerenciamento de caso e resume os detalhes de caso para analistas e investigadores de risco. Ele inclui as seguintes áreas:

- **Nome do caso**: o nome da ocorrência, prefixado com um número de sequência de ocorrências gerado automaticamente e o nome do risco associado ao modelo de política que o primeiro alerta confirmado corresponde. 
- **Status do caso**: o status atual do caso, *ativo* ou *fechado*.
- **Pontuação de risco do usuário**: o nível de risco calculado atual do usuário para o caso. Essa pontuação é calculada a cada 24 horas e usa as pontuações de risco de alerta de todos os alertas ativos associados ao usuário.
- **Alertas confirmados**: lista de alertas para o usuário confirmado para o caso.
- **Conteúdo em risco**: lista de conteúdo, classificada por fontes e tipos de conteúdo. Por exemplo, para o conteúdo de alerta de caso no SharePoint Online, você pode ver nomes de pastas ou arquivos listados que estão associados à atividade de risco para alertas no caso.

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

### <a name="user-activity"></a>Atividades do usuário

A guia **atividade do usuário** é uma das ferramentas mais poderosas para análise de riscos internos e investigação de casos na solução de gerenciamento de risco do insider. Esta guia é estruturada para habilitar a revisão rápida de um caso, incluindo uma linha do tempo histórica de todos os alertas, todos os detalhes dos alertas, a pontuação de risco atual para o usuário no caso e os controles para executar a ação efetiva para conter os riscos no caso.

![Atividade do usuário de gerenciamento de risco do insider](../media/insider-risk-user-activities.png)

1. **Filtros de data e hora da janela**: por padrão, os últimos seis meses de alertas confirmados no caso são exibidos no gráfico de atividade do usuário. Você pode filtrar facilmente o modo de exibição de gráfico com os controles Slider em ambas as extremidades da janela do gráfico ou definindo datas de início e de término específicas no controle de filtro de gráfico.
2. **Atividade e detalhes de alerta de risco**: as atividades de risco são exibidas visualmente como bolhas coloridas no gráfico de atividades do usuário. As bolhas são criadas para diferentes categorias de risco e o tamanho da bolha é proporcional ao número de atividades de risco para a categoria. Selecione uma bolha para exibir os detalhes de cada atividade de risco. Os detalhes incluem:
    - **Data** da atividade de risco.
    - A **categoria atividade de risco**. Por exemplo, *emails com anexos enviados fora da organização* ou *arquivo (s) baixados do SharePoint Online*.
    - **Pontuação de risco** para o alerta. Esta pontuação é a pontuação numérica do nível de severidade de risco de alerta.
    - Número de eventos associados ao alerta. Os links para cada arquivo ou email associado à atividade de risco também estão disponíveis.
3. **Legenda da atividade do risco**: na parte inferior do gráfico de atividade do usuário, uma legenda codificada por cores ajuda a determinar rapidamente a categoria de risco para cada alerta.
4. **Cronologia da atividade de risco**: o cronograma completo de todos os alertas de risco associados ao caso está listado, incluindo todos os detalhes disponíveis na bolha de alerta correspondente.
5. **Ações de caso**: as opções para resolver o caso estão na barra de ferramentas ação de caso. Você pode resolver uma ocorrência, enviar um aviso por email ao funcionário ou escalonar o caso de uma investigação de dados ou de funcionário.

### <a name="content-explorer"></a>Explorador de conteúdo

A guia **Gerenciador de conteúdo** permite que analistas de risco e investigadores revisem cópias de todos os arquivos e mensagens de email individuais associados a alertas de risco. Por exemplo, se um alerta é criado quando um funcionário baixa centenas de arquivos do SharePoint Online para um dispositivo USB e a atividade dispara um alerta de política, todos os arquivos baixados para o alerta são capturados e copiados para o caso de gerenciamento de risco do insider da fontes de armazenamento originais.

O Gerenciador de conteúdo é uma poderosa ferramenta com recursos básicos e avançados de pesquisa e filtragem. Para saber mais sobre como usar o Gerenciador de conteúdo, confira [Insider Risk Management Content Explorer](insider-risk-management-content-explorer.md).

![Gerenciador de conteúdo de caso de gerenciamento de risco](../media/insider-risk-content-explorer.png)

### <a name="case-notes"></a>Anotações de caso

A guia de **notas de caso** no caso é onde os analistas e investigadores de risco compartilham comentários, comentários e ideias sobre o trabalho da ocorrência. As anotações são adições permanentes a um caso e não podem ser editadas ou excluídas após a anotação ser salva. Quando um caso é criado a partir de um alerta, os comentários inseridos na caixa de diálogo **confirmar alerta e criar caso de caso de insider** são automaticamente adicionados como uma nota de caso.

O painel de anotações de caso exibe anotações pelo usuário que criou a anotação e o tempo decorrido desde que a anotação foi salva. Para pesquisar o campo de texto de nota de caso para uma palavra-chave específica, use o botão de **pesquisa** no painel de casos e insira uma palavra-chave específica.

Para adicionar uma nota a uma ocorrência:

1. No [centro de conformidade da Microsoft 365](https://compliance.microsoft.com), vá para gerenciamento de **risco do insider** e selecione a guia **ocorrências** .
2. Selecione uma ocorrência e, em seguida, selecione a guia **notas de caso** .
3. Selecione **Adicionar observação de caso**.
4. Na caixa de diálogo **Adicionar nota de caso** , digite a anotação para o caso. Selecione **salvar** para adicionar a anotação ao caso ou selecione **Cancelar** fechar sem salvar a anotação no caso.

### <a name="contributors"></a>Colaboradores

A guia **colaboradores** no caso é onde analistas de risco e investigadores podem adicionar outros revisores ao caso. Seja padrão, todos os usuários atribuídos aos **analistas de gerenciamento de risco do insider** e às funções de **investigadores de gerenciamento de risco do insider** são listados como colaboradores para cada caso ativo e fechado.

Todos os casos de gerenciamento de risco do insider devem ser gerenciados com os controles de acesso apropriados no local para manter a confidencialidade e integridade da investigação. Para ajudar a manter o controle de acesso de casos, os usuários recebem um dos dois tipos de acesso a casos:

- **Acesso permanente**: o acesso permanente é concedido automaticamente aos usuários com os **analistas de gerenciamento de risco do insider** e as funções de **investigadores de gerenciamento de risco do insider** quando o caso é criado a partir de um alerta. O acesso permanente concede controle total do caso para o tempo de vida do caso e concede a capacidade de adicionar outros colaboradores de caso.
- **Acesso temporário**: o acesso temporário só é concedido aos usuários por colaboradores que têm acesso permanente à ocorrência. Normalmente, esse nível de acesso é concedido ao usuário que precisa adicionar anotações a um caso. Os colaboradores com acesso temporário têm todo o controle de gerenciamento de casos, exceto:
    - Permissão para confirmar ou ignorar alertas
    - Permissão para editar os colaboradores para casos
    - Permissão para exibir arquivos e mensagens no explorador de conteúdo

Para adicionar um colaborador a uma ocorrência:

1. No [centro de conformidade da Microsoft 365](https://compliance.microsoft.com), vá para gerenciamento de **risco do insider** e selecione a guia **ocorrências** .
2. Selecione uma ocorrência e, em seguida, selecione a guia **colaboradores** .
3. Selecione **Adicionar colaborador**.
4. Na caixa de diálogo **Adicionar colaborador** , comece a digitar o nome do usuário que você deseja adicionar e, em seguida, selecione o usuário na lista de usuários sugeridos. Essa lista é gerada a partir do Azure Active Directory de sua assinatura de locatário.
5. Na caixa de diálogo **Adicionar colaborador** , selecione o nível de acesso para o colaborador. Você pode selecionar **permanente** ou **temporário**.
6. Selecione **Adicionar** para adicionar o usuário como colaborador ou selecione **Cancelar** feche a caixa de diálogo sem adicionar o usuário como colaborador.

## <a name="case-actions"></a>Ações de caso

Os analistas e investigadores de risco podem agir em um caso de vários métodos, dependendo da gravidade do caso, do histórico de riscos do funcionário e das diretrizes de risco da sua organização. Em algumas situações, talvez seja necessário escalonar uma ocorrência para um funcionário ou uma investigação de dados para colaborar com outras áreas da sua organização e para se aprofundar em atividades de risco. O gerenciamento de riscos do insider está totalmente integrado a outros recursos de conformidade da Microsoft 365 para ajudá-lo com o gerenciamento de resolução de ponta a ponta.

### <a name="send-a-notice"></a>Enviar um aviso

Na maioria dos casos, as ações de funcionários que criam alertas de política de correspondência são inadvertidas ou acidentais. Enviar um aviso de lembrete para o funcionário por email é um método eficaz para documentar a revisão e a ação do caso, bem como um método para lembrar os funcionários das políticas corporativas ou a apontar para o treinamento atualizado. Os avisos são gerados de [modelos de aviso que você cria](insider-risk-management-notices.md) para a infraestrutura de gerenciamento de risco do insider.

É importante lembrar que enviar um aviso para ***um funcionário não*** resolve o caso como *fechado*. Em alguns casos, convém deixar um caso aberto após enviar um aviso a um funcionário para procurar atividades de risco adicionais sem abrir um novo caso. Se quiser resolver um caso após enviar um aviso, você deve selecionar o caso de **resolução** como uma etapa de acompanhamento após enviar um aviso.

Para enviar um aviso ao funcionário atribuído a uma ocorrência:

1. No [centro de conformidade da Microsoft 365](https://compliance.microsoft.com), vá para gerenciamento de **risco do insider** e selecione a guia **ocorrências** .
2. Selecione uma ocorrência e, em seguida, selecione o botão **Enviar aviso por email** na barra de ferramentas ação de ocorrência.
3. Na caixa de diálogo **Enviar aviso por email** , selecione o controle de menu suspenso **escolher um modelo de aviso** para selecionar o modelo de aviso para o aviso. Esta seleção preenche previamente os outros campos no aviso.
4. Revise os campos de aviso e atualize conforme apropriado. Os valores inseridos aqui substituirão os valores no modelo.
5. Selecione **Enviar** para enviar o aviso ao funcionário ou selecione **Cancelar** feche a caixa de diálogo sem enviar o aviso ao funcionário. Todos os avisos enviados são adicionados à fila de notas de caso no painel de **notas de caso** .

### <a name="escalate-for-investigation"></a>Escalonar para investigação

Escalonar o caso para investigação de funcionários em situações em que a análise jurídica adicional é necessária para a atividade de risco do funcionário. Esse escalonamento abre uma nova ocorrência de descoberta eletrônica avançada na sua organização do Microsoft 365. A descoberta eletrônica avançada fornece um fluxo de trabalho de ponta a ponta para preservar, coletar, analisar, analisar e exportar o conteúdo que responde às investigações legais internas e externas da sua organização. Também permite que sua equipe jurídica gerencie todo o fluxo de trabalho de notificação de retenção legal para se comunicar com os responsáveis envolvidos em um caso. A atribuição de um revisor como um responsável em uma ocorrência de descoberta eletrônica avançada criada a partir de um caso de gerenciamento de risco do insider ajuda sua equipe jurídica a executar a ação apropriada e a gerenciar a preservação de conteúdo. Para saber mais sobre casos de descoberta eletrônica avançada, confira [visão geral do EDsicovery avançado no Microsoft 365](overview-ediscovery-20.md).

Para escalonar uma ocorrência para uma investigação de funcionário:

1. No [centro de conformidade da Microsoft 365](https://compliance.microsoft.com), vá para gerenciamento de **risco do insider** e selecione a guia **ocorrências** .
2. Selecione uma ocorrência e, em seguida, selecione o botão **escalonar para investigação** na barra de ferramentas ação de ocorrência.
3. Na caixa **de diálogo escalar para investigação** , insira um nome para a nova investigação de funcionário. Se necessário, insira observações sobre o caso e selecione **escalonar**.
5. Selecione **confirmar** para criar o caso de investigação de funcionário ou selecione **Cancelar** para fechar a caixa de diálogo sem criar um novo caso de investigação de funcionário.

Após o caso de gerenciamento de risco do insider ser escalonado para um novo caso de investigação de funcionários, você pode examinar o novo caso**na área de** **descoberta eletrônica** > do centro de conformidade da Microsoft 365.

### <a name="resolve-the-case"></a>Resolver o caso

Após os analistas e investigadores de riscos terem concluído a análise e a investigação, um caso pode ser resolvido para executar ações em todos os alertas incluídos no caso. A resolução de um caso adiciona uma classificação de resolução, altera o status do caso para *fechado*e os motivos da ação de resolução são automaticamente adicionados à fila de notas de caso no painel de **notas de caso** . Os casos são resolvidos como:

- **Benigno**: a classificação de casos em que os alertas de correspondência de política são avaliados como baixo risco, não sério ou falso positivo.
- **Violação de política confirmada**: a classificação de casos em que os alertas de correspondência de política são avaliados como arriscados, sérios ou resultantes de más intenções.

Para resolver uma ocorrência:

1. No [centro de conformidade da Microsoft 365](https://compliance.microsoft.com), vá para gerenciamento de **risco do insider** e selecione a guia **ocorrências** .
2. Selecione uma ocorrência e, em seguida, selecione o botão **resolver ocorrência** na barra de ferramentas ação da ocorrência.
3. Na caixa de diálogo **resolver caso** , selecione o controle **resolver como** menu suspenso para selecionar a classificação de resolução para o caso. As opções são **benignas** ou as **violações de política confirmadas**.
4. Na caixa de diálogo **resolver caso** , insira os motivos para a classificação de resolução no campo de texto **ação realizada** .
5. Selecione **resolver** para fechar o caso ou selecione **Cancelar** fechar a caixa de diálogo sem resolver o caso.
