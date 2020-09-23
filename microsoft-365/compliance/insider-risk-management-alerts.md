---
title: Alertas de gerenciamento de risco do insider
description: Saiba mais sobre os alertas de gerenciamento de risco do insider no Microsoft 365
keywords: Microsoft 365, risco de insider, gerenciamento de riscos, conformidade
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
ms.openlocfilehash: 602571e5cbd3132209382ca2e2a3d8941ea8ab2e
ms.sourcegitcommit: e5ac81132cc5fd248350627a3cc7b3c640f53b6e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/22/2020
ms.locfileid: "48208817"
---
# <a name="insider-risk-management-alerts"></a>Alertas de gerenciamento de risco do insider

Alertas de gerenciamento de risco do insider são gerados automaticamente pelos indicadores de risco definidos nas políticas de gerenciamento de risco do insider Esses alertas fornecem aos analistas de conformidade e investigadores uma visão de todos os status do risco atual e permitem que sua organização faça a triagem e execute ações para riscos descobertos. Por padrão, as políticas geram uma determinada quantidade de alertas de severidade Baixa, média e alta, mas você pode [aumentar ou diminuir o volume de alerta](insider-risk-management-settings.md#alert-volume) para atender às suas necessidades. Além disso, você pode configurar o [limite de alerta para indicadores de política](insider-risk-management-settings.md#indicator-level-settings-preview) ao criar uma nova política com o assistente de política.

## <a name="alert-dashboard"></a>Painel de alerta

O painel de **alerta** de risco do insider permite que você visualize e atue em alertas gerados por políticas de risco do insider. Cada widget de relatório exibe informações dos últimos 30 dias.

- **Alertas a serem revisados**: o número total de alertas que precisam de revisão e análise estão listados, incluindo uma divisão por severidade de alerta.
- **Abrir alertas nos últimos 30 dias**: o número total de alertas criados por uma política corresponde aos últimos 30 dias, classificados por níveis de severidade de alerta alto, médio e baixo.
- **Tempo médio para resolver alertas**: um resumo das estatísticas úteis de alerta:
    - Tempo médio para resolver alertas de alta gravidade, listados em horas, dias ou meses.
    - Tempo médio para resolver alertas de severidade média, listados em horas, dias ou meses.
    - Tempo médio para resolver alertas de severidade Baixa, listados em horas, dias ou meses.

![Painel de alerta de gerenciamento de risco do insider](../media/insider-risk-alerts-dashboard.png)

>[!NOTE]
>O gerenciamento de riscos Insider usa a limitação de alerta interna para ajudar a proteger e otimizar a investigação de riscos e a experiência de análise. Essa limitação protege contra problemas que podem resultar em uma sobrecarga de alertas de política, como conectores de dados configurados incorretamente ou políticas de DLP. Como resultado, pode haver um atraso na exibição de novos alertas para um usuário.

## <a name="alert-status-and-severity"></a>Status e severidade do alerta

Você pode filtrar alertas em um dos seguintes status:

- **Confirmado**: um alerta confirmado e atribuído a uma ocorrência nova ou existente.
- **Ignorado**: um alerta é Descartado como benigno no processo de triagem.
- **Requer revisão**: um novo alerta em que as ações de triagem ainda não foram realizadas.
- **Resolvido**: um alerta que faz parte de uma ocorrência fechada e resolvida.

As pontuações de risco de alerta são calculados automaticamente de vários indicadores de atividade de risco. Esses indicadores incluem o tipo de atividade de risco, o número e a frequência da ocorrência da atividade, o histórico da atividade de risco do usuário e a adição de riscos de atividade que podem aumentar a gravidade da atividade. A pontuação de risco de alerta orienta a atribuição programática de um nível de severidade de risco para cada alerta e não pode ser personalizada. Se os alertas permanecerem não-triagem e as atividades de risco continuarem a ser acumuladas para o alerta, o nível de severidade pode aumentar. Os analistas e investigadores de risco podem usar a severidade de risco de alerta para ajudar a fazer a triagem de alertas de acordo com as políticas e os padrões de risco da sua organização.

Os níveis de severidade de risco de alerta são:

- **Alta gravidade**: as atividades e os indicadores para o alerta representam um risco significativo. As atividades de risco associadas são sérias, repetitivas e corelacionáveis de alta para outros fatores de risco significativos.
- **Severidade média**: as atividades e os indicadores para o alerta representam um risco moderado. As atividades de risco associadas são moderadas, freqüentes e têm alguma correlação com outros fatores de risco.
- **Severidade Baixa**: as atividades e os indicadores para o alerta representam um risco menor. As atividades de risco associadas são secundárias, mais frequentes e não corelacionadas a outros fatores de risco significativos.

## <a name="filter-alerts-on-the-alert-dashboard"></a>Filtrar alertas no painel de alerta

Dependendo do número e do tipo de políticas de gerenciamento de risco do insider ativos em sua organização, a análise de uma grande fila de alertas pode ser desafiadora. O uso de filtros de alerta pode ajudar os analistas e investigadores a classificarem alertas por vários atributos. Para filtrar alertas no **painel alertas**, selecione o controle **filtro** . Você pode filtrar alertas por um ou mais atributos:

- **Status**: selecione um ou mais valores de status para filtrar a lista de alerta. As opções são *confirmadas*, *ignoradas*, *Revisas*e *resolvidas*.
- **Severidade**: selecione um ou mais níveis de severidade de risco de alerta para filtrar a lista de alerta. As opções são *alta*, *média*e *baixa*.
- **Tempo detectado**: selecione as datas de início e término para quando o alerta foi criado.
- **Política**: selecione uma ou mais políticas para filtrar os alertas gerados pelas políticas selecionadas.

## <a name="search-alerts-on-the-alert-dashboard"></a>Alertas de pesquisa no painel de alerta

Para pesquisar o nome do alerta de uma palavra específica, selecione o controle de **pesquisa** e digite a palavra a ser pesquisada. Os resultados da pesquisa exibem qualquer alerta de política que contenha a palavra definida na pesquisa.

## <a name="triage-alerts"></a>Alertas de triagem

Para fazer a triagem de um alerta de risco do Insider, conclua as seguintes etapas:

1. No [centro de conformidade da Microsoft 365](https://compliance.microsoft.com), vá para gerenciamento de **risco do insider** e selecione a guia **alertas** .
2. No **painel alertas**, selecione o alerta que você deseja fazer a triagem.
3. No **painel detalhes dos alertas**, você pode revisar as guias a seguir e filtrar o alerta:
    - **Resumo**: essa guia contém informações gerais sobre o alerta e permite confirmar o alerta e criar um novo caso ou permite que você ignore o alerta. Ele inclui o status atual do alerta e o nível de severidade do risco de alerta, listados como *alto*, *médio*ou *baixo*. O nível de severidade pode aumentar ou diminuir com o tempo se o alerta não for diminuído.
        - **O que aconteceu**: exibe as três principais atividades de risco e correspondências de política durante o período de avaliação da atividade, incluindo o tipo de violação associado à atividade.
        - **Detalhes do usuário**: exibe informações gerais sobre o usuário atribuído ao alerta. Se a anonimato estiver habilitada, os campos nome de usuário, endereço de email, alias e organização serão anônimos.
        - **Detalhes do alerta**: inclui o período de tempo desde que o alerta foi gerado, as políticas que geraram o alerta estão listadas e o caso gerado a partir do alerta é listado. Para novos alertas, o campo **Case** exibe nenhum.
        - **Conteúdo detectado**: inclui conteúdo associado às atividades de risco para o alerta e resume os eventos de atividade por áreas principais. Selecionar um link de atividade abre o explorador de atividade e exibe detalhes adicionais sobre a atividade.
    - **Atividade do usuário**: essa guia exibe o histórico de atividades do usuário associado ao alerta. Este histórico inclui outros alertas e atividades relacionadas a indicadores de risco definidos no modelo atribuído à política para este alerta. Este histórico permite que analistas de risco e investigadores impeçam o fato de qualquer comportamento arriscado passado para o funcionário como parte do processo de triagem.
    - **Ações**: as ações a seguir estão disponíveis para cada alerta:
        - **Abrir o modo de exibição expandido**: abre o painel do **Explorador de atividades** .
        - **Confirmar e criar caso**: Use esta ação para confirmar e criar um novo caso para todos os alertas associados a um usuário. Essa ação altera automaticamente o status do alerta para *confirmado*.
        - **Ignorar alerta**: Use esta ação para ignorar o alerta. Esta ação altera o status do alerta para *resolvido*.

## <a name="activity-explorer-preview"></a>Explorador de atividade (versão prévia)

>[!NOTE]
>O explorador de atividade está disponível na área gerenciamento de alerta para usuários com eventos de acionamento após este recurso estar disponível na sua organização.

O explorador de atividade fornece investigadores e investigadores de risco com uma ferramenta analítica abrangente que fornece informações detalhadas sobre os alertas. Com o explorador de atividade, os revisores podem rever rapidamente uma linha do tempo de uma atividade arriscada detectada e identificar e filtrar todas as atividades de risco associadas a alertas. Para filtrar alertas no explorador de atividade, selecione o controle de filtro. Você pode filtrar alertas por um ou mais atributos listados no painel de detalhes para o alerta. O Gerenciador de atividades também oferece suporte a colunas personalizáveis para ajudar os investigadores e analistas a concentrarem o painel nas informações mais importantes para eles.

![Visão geral do explorador de atividade de gerenciamento de riscos](../media/insider-risk-management-activity-explorer.png)

Para usar o **Explorador de atividade**, conclua as seguintes etapas:

1. No centro de conformidade da Microsoft 365, vá para **Gerenciamento de risco do insider** e selecione a guia **alertas** .
2. No **painel alertas**, selecione o alerta que você deseja fazer a triagem.
3. No **painel detalhes dos alertas**, selecione **abrir o modo de exibição expandido**.
4. Na página para o alerta selecionado, selecione a guia **Gerenciador de atividade** .

Ao revisar atividades no explorador de atividade, os investigadores e os analistas podem selecionar uma atividade específica e abrir o painel de detalhes de atividade. O painel exibe informações detalhadas sobre a atividade que os investigadores e analistas podem usar durante o processo de triagem de alerta. As informações detalhadas podem fornecer contexto para o alerta e ajudar a identificar o escopo completo da atividade de risco que disparou o alerta.

![Detalhes do explorador de atividades do insider gerenciamento de riscos](../media/insider-risk-management-activity-explorer-details.png)

## <a name="create-a-case-for-an-alert"></a>Criar uma ocorrência para um alerta

Como o alerta é revisado e expirado, você pode criar um novo caso para investigar ainda mais a atividade de risco. Para criar uma ocorrência para um alerta, siga estas etapas:

1. No [centro de conformidade da Microsoft 365](https://compliance.microsoft.com), vá para gerenciamento de **risco do insider** e selecione a guia **alertas** .
2. No **painel alertas**, selecione o alerta que você deseja confirmar e crie um novo caso para o.
3. No **painel de detalhes de alertas**, selecione **ações**  >  **confirmar alertas & criar caso**.
4. Na caixa de diálogo **confirmar alerta e criar caso de risco do insider** , insira um nome para o caso, selecione os usuários a serem adicionados como colaboradores e adicione comentários conforme aplicável. Os comentários são automaticamente adicionados ao caso como uma observação de caso.
5. Selecione **criar caso** para criar um novo caso ou selecione **Cancelar** para fechar a caixa de diálogo sem criar uma ocorrência.

Depois que o caso é criado, os investigadores e analistas podem gerenciar e agir no caso. Consulte o artigo do [caso de gerenciamento de risco do insider](insider-risk-management-cases.md) para obter mais detalhes.
