---
title: Painel usuários de gerenciamento de risco do insider
description: Saiba mais sobre o painel usuários de gerenciamento de risco do insider no Microsoft 365
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
ms.openlocfilehash: 224221950104b5dee6a6e8f179db34ee6fad014e
ms.sourcegitcommit: e5ac81132cc5fd248350627a3cc7b3c640f53b6e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/22/2020
ms.locfileid: "48208767"
---
# <a name="insider-risk-management-users-dashboard"></a>Painel usuários de gerenciamento de risco do insider

O **painel usuários** é uma ferramenta importante no fluxo de trabalho de gerenciamento de risco do insider e ajuda os investigadores e analistas a ter uma compreensão mais completa das atividades de risco. Esse painel oferece modos de exibição e recursos de gerenciamento para atender às necessidades administrativas entre as políticas de gerenciamento de risco do insider e gerenciamento de casos de gerenciamento do insider.

Após os usuários serem adicionados às políticas de gerenciamento de risco do Insider, os processos em segundo plano estão avaliando automaticamente as atividades do usuário para [acionar indicadores](insider-risk-management-settings.md#indicators). Depois que os indicadores de disparo estiverem presentes, as atividades do usuário receberão pontuações de risco. Algumas dessas atividades podem resultar em um alerta de risco Insider, mas algumas atividades podem não atender a um nível mínimo de Pontuação de risco e um alerta de risco de insider não será criado. O **painel usuários** permite exibir os usuários com esses tipos de indicadores e pontuações de risco, bem como os usuários que têm alertas de risco do Active Insider.

Além disso, pode haver situações em que você precisa adicionar usuários temporariamente às políticas de risco do insider após um evento incomum ser relatado fora do fluxo de trabalho de gerenciamento de risco do insider. O **painel usuários** permite que você adicione manualmente um usuário a uma política de risco do insider por um período específico e ignore o requisito para que um usuário tenha um indicador de acionamento. Esses usuários são sempre exibidos no painel usuários quando atribuídos ativamente a uma política.

Saiba mais sobre como o painel de usuários exibe os usuários nos seguintes cenários:

- Usuários do painel com alertas de política de risco do Active Sider
- Usuários do painel com indicadores de disparo
- Usuários do painel adicionados temporariamente às políticas

## <a name="dashboard-users-with-active-insider-risk-policy-alerts"></a>Usuários do painel com alertas de política de risco do Active Sider

O **painel usuários** exibe automaticamente todos os usuários com alertas de política de risco do insider ativos. Esses usuários com alertas têm um indicador de acionamento e uma pontuação de risco de atividade que atende aos requisitos para a criação de um alerta de risco de insider. As atividades desses usuários são exibidas selecionando o usuário no **painel usuários** e navegando até a guia **atividade do usuário** .

## <a name="dashboard-users-with-triggering-indicators"></a>Usuários do painel com indicadores de disparo

O **painel usuários** exibe automaticamente todos os usuários com indicadores de acionamento, mas que não têm uma pontuação de risco de atividade que criaria um alerta de risco de insider. Por exemplo, um usuário com uma data de demissão relatada é exibido porque esse evento é um indicador de acionamento, mas não é uma atividade com uma pontuação de risco. As atividades desses usuários são exibidas selecionando o usuário no **painel usuários** e navegando até a guia **atividade do usuário** .

## <a name="dashboard-users-added-temporarily-to-policies"></a>Usuários do painel adicionados temporariamente às políticas

O **painel usuários** permite que você adicione usuários temporariamente a uma política de gerenciamento de risco do insider existente após um evento incomum fora do fluxo de trabalho de gerenciamento de risco do insider. A adição temporária de usuários também é uma maneira de adicionar usuários a uma política de gerenciamento de risco do insider para testar a política, mesmo que um conector necessário não esteja configurado.

Quando um usuário é adicionado manualmente a uma política, as atividades do usuário dos últimos 90 dias são classificadas e adicionadas à linha do tempo de **atividade do usuário** . Por exemplo, você tem um usuário que não está em escopo no momento em uma política de risco Insider e o usuário tem atividades de perda de dados relatadas para o departamento jurídico em sua organização. O departamento jurídico recomenda que você configure novos requisitos de monitoramento de curto prazo para o usuário. Você pode atribuir temporariamente o usuário à sua política de *vazamentos de dados* por um período de tempo designado (janela de ativação). Todos os usuários adicionados temporariamente são exibidos no **painel usuários** porque os requisitos do indicador de acionamento são RENUNCIADOS.

>[!NOTE]
>Pode levar várias horas para que novos usuários adicionados manualmente apareçam no **painel usuários**. As atividades dos últimos 90 dias para esses usuários podem levar até 24 horas para serem exibidas. Para exibir as atividades de usuários adicionados manualmente, selecione o usuário no **painel usuários** e abra a guia **atividade do usuário** no painel de detalhes.

O usuário é removido automaticamente da política do insider e do **painel usuários** quando o tempo definido na **janela de ativação** expira se:

- o usuário não tem indicadores de acionamento ou alertas de política de risco Insider e
- se a duração da **janela de ativação** definida manualmente for maior do que a duração da **janela de ativação** da política global. 

A configuração da **janela de ativação** com a duração mais longa sempre substitui a configuração da **janela de ativação** por uma duração mais curta. Por exemplo, você configurou a **janela de ativação** na guia **prazos de política** global nas configurações globais de gerenciamento de risco do insider por 15 dias, que é automaticamente aplicada a todas as suas políticas de risco do insider. 

Você adiciona temporariamente um usuário aos seus *dados que vazam* a política de risco do insider e define 30 dias como a **janela de ativação** para esse usuário. A configuração da **janela de ativação** global de 15 dias é substituída pela definição da configuração da janela de **ativação** de 30 dias para o usuário adicionado temporariamente. O usuário temporariamente adicionado permanecerá no **painel usuários** e estará dentro do escopo da política por 30 dias.

No cenário oposto em que a configuração **da janela de ativação** global é maior do que a configuração da janela de **ativação** definida para um usuário adicionado temporariamente, a configuração da janela de **ativação** global substituirá a configuração da **janela de ativação** para o usuário adicionado temporariamente. O usuário temporariamente adicionado permanecerá no **painel usuários** e estará dentro do escopo da política para o número de dias definido nas configurações da janela de **ativação** global.

## <a name="view-user-information-on-the-users-dashboard"></a>Exibir as informações do usuário no painel usuários

Cada usuário exibido no **painel usuários** tem as seguintes informações:

- **Usuários**: o nome de usuário de um usuário. Este campo é anonimato se a configuração global de anonimato para o gerenciamento de risco do insider estiver habilitada.
- **Nível de risco**: o nível de risco calculado atual do usuário. Essa pontuação é calculada a cada 24 horas e usa as pontuações de risco de alerta de todos os alertas ativos associados ao usuário. Para usuários com apenas indicadores de acionamento, o nível de risco é zero.
- **Alertas ativos**: o número de alertas ativos para todas as políticas.
- **Violações confirmadas**: o número de ocorrências resolvidas como *violação de política confirmada* para o usuário.
- **Caso**: o caso ativo atual do usuário.

![Painel usuários de gerenciamento de risco do insider](../media/insider-risk-users-dashboard.png)

>[!NOTE]
>O número de usuários exibidos no **painel usuários** pode ser limitado em alguns casos, dependendo do volume de alertas ativos e políticas de correspondência. Os usuários com alertas ativos são exibidos no **painel usuários** à medida que os alertas são gerados, e pode haver casos raros quando o número máximo de usuários exibidos é alcançado. Se isso acontecer, os usuários com alertas ativos que não são exibidos serão adicionados ao **painel usuários** , já que os alertas de usuário existentes são classificados.

## <a name="view-user-details"></a>Exibir detalhes do usuário

Para exibir mais detalhes sobre a atividade de risco de um usuário, abra o painel de detalhes do usuário clicando duas vezes em um usuário no **painel usuários**. No painel de detalhes, você pode exibir as seguintes informações:

- Guia **perfil de usuário**
    - **Nome e título**: o nome e cargo do usuário do Azure Active Directory. Esses campos de usuário serão anônimos ou vazios se a configuração global de anonimato para o gerenciamento de risco do insider estiver habilitada.
    - **Email do usuário**: o endereço de email do usuário.
    - **Alias**: o alias de rede do usuário.
    - **Organização ou departamento**: a organização ou departamento do usuário.

- Guia **atividade do usuário**
    - **Histórico da atividade recente do usuário**: lista ambos os indicadores de acionamento e os indicadores de risco do insider para atividades de usuário até os últimos 180 dias. Todas as atividades pertinentes aos indicadores de risco do insider também são pontuadas, embora as atividades possam ou não tenham gerado um alerta de risco de insider. Os exemplos de indicadores de acionamento podem ser uma data de demissão ou a última data de trabalho agendada para o usuário. Os indicadores de risco do insider são as atividades determinadas para ter um elemento de risco e são definidas em políticas nas quais o usuário está incluído. As atividades de evento e risco são listadas com o item mais recente listado primeiro.

## <a name="temporarily-add-a-user-to-a-policy"></a>Adicionar temporariamente um usuário a uma política

Para adicionar temporariamente um usuário a uma política de gerenciamento de risco do Insider, você usará a guia **usuários** na solução de **Gerenciamento de risco do insider** no centro de conformidade da Microsoft 365. Os usuários adicionaram manualmente os requisitos de indicador de disparo para a política à qual são adicionados e são exibidos no **painel usuários**. Para adicionar permanentemente um usuário a uma política de gerenciamento de risco do Insider, você usará o assistente de política.

Conclua as seguintes etapas para adicionar um usuário a uma política de risco Insider existente:

1. No [centro de conformidade da Microsoft 365](https://compliance.microsoft.com), vá para gerenciamento de **risco do insider** e selecione a guia **usuários** .
2. Selecione **Adicionar um usuário a uma política** na barra de ferramentas.
3. Na caixa de diálogo **Adicionar um novo usuário** , comece a digitar um nome de usuário no campo **usuário** . Selecione o usuário que você deseja adicionar a uma política.
4. Selecione a seta suspensa do campo **política** para exibir as políticas de gerenciamento de risco do insider configuradas. Selecione a política à qual adicionar o usuário.
5. Use o controle deslizante da **janela de ativação** para definir por quanto tempo o usuário está incluído em uma política e exibido no painel usuários. O horário especificado determina por quanto tempo a política está ativa para este usuário e é iniciada quando o primeiro alerta é gerado ou um indicador de acionamento (como uma correspondência de política de DLP) é detectado. O intervalo para a **janela de ativação** é de 5 a 30 dias.
6. Selecione **Adicionar** e depois em **confirmar** para adicionar o usuário à política.

>[!NOTE]
>Pode levar várias horas para que novos usuários adicionados manualmente apareçam no **painel usuários**. As atividades dos últimos 90 dias para esses usuários podem levar até 24 horas para serem exibidas. Para exibir as atividades de usuários adicionados manualmente, selecione o usuário no **painel usuários** e abra a guia **atividade do usuário** no painel de detalhes.

## <a name="run-automated-tasks-with-power-automate-flows-for-a-user"></a>Executar tarefas automatizadas com fluxos de energia automatizados para um usuário

Usando os fluxos de alimentação automatizados, os investigadores de risco e os analistas podem tomar medidas rapidamente para:

- Notificar os usuários quando eles forem adicionados a uma política de risco Insider

Para executar, gerenciar ou criar fluxos automatizados de energia para um usuário de gerenciamento de risco do insider:

1. Selecione **automatizar** na barra de ferramentas ação do usuário.
2. Escolha o fluxo automatizado de energia a ser executado e, em seguida, selecione **fluxo de execução**.
3. Após a conclusão do fluxo, selecione **concluído**.

Para saber mais sobre os fluxos de automatização de energia do gerenciamento de risco do Insider, confira [introdução às configurações de gerenciamento de risco do insider](insider-risk-management-settings.md#power-automate-flows-preview).
