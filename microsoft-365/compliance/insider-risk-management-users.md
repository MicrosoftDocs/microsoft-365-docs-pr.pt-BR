---
title: Painel usuários de gerenciamento de riscos do Insider
description: Saiba mais sobre o gerenciamento de risco interno Painel de usuários no Microsoft 365
keywords: Microsoft 365, gerenciamento de risco interno, gerenciamento de risco, conformidade
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
ms.openlocfilehash: e59fb8a32275a2ef7c4865e93400b97ad5560df5
ms.sourcegitcommit: 8b1bd7ca8cd81e4270f0c1e06d2b6ca81804a6aa
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/15/2021
ms.locfileid: "50819993"
---
# <a name="insider-risk-management-users-dashboard"></a>Painel usuários de gerenciamento de riscos do Insider

O **painel Usuários** é uma ferramenta importante no fluxo de trabalho de gerenciamento de riscos insider e ajuda os investigadores e analistas a ter uma compreensão mais completa das atividades de risco. Este painel oferece exibições e recursos de gerenciamento para atender às necessidades administrativas entre a criação de políticas de gerenciamento de riscos insider e o gerenciamento de casos de gerenciamento de riscos insider.

Depois que os usuários são adicionados às políticas de gerenciamento de riscos internos, os processos em segundo plano avaliam automaticamente as atividades do usuário para [disparar indicadores](insider-risk-management-settings.md#indicators). Depois que os indicadores de disparo estão presentes, as atividades do usuário são atribuídas a pontuações de risco. Algumas dessas atividades podem resultar em um alerta de risco interno, mas algumas atividades podem não atender a um nível mínimo de pontuação de risco e um alerta de risco interno não será criado. O **painel Usuários** permite que você veja os usuários com esses tipos de indicadores e pontuações de risco, bem como usuários que têm alertas de risco insider ativos.

Saiba mais sobre como o painel Usuários exibe usuários nos seguintes cenários:

- Usuários com alertas de política de risco insider ativo
- Usuários com eventos de acionamento
- Usuários adicionados temporariamente a políticas

## <a name="users-with-active-insider-risk-policy-alerts"></a>Usuários com alertas de política de risco insider ativo

O **painel Usuários** exibe automaticamente todos os usuários com alertas de política de risco insider ativo. Esses usuários com alertas têm um indicador de gatilho e uma pontuação de risco de atividade que atende aos requisitos para criar um alerta de risco interno. As atividades para esses usuários são  exibidas selecionando o usuário no painel Usuários e navegando até a **guia Atividade do** usuário.

## <a name="users-with-triggering-events"></a>Usuários com eventos de acionamento

O **painel Usuários** exibe automaticamente todos os usuários com eventos disparados, mas que não têm uma pontuação de risco de atividade que criaria um alerta de risco interno. Por exemplo, um usuário com uma data de demissão relatada é exibido porque essa atividade é um evento disparador, mas não é uma atividade que tem uma pontuação de risco. As atividades para esses usuários são  exibidas selecionando o usuário no painel Usuários e navegando até a **guia Atividade do** usuário.

## <a name="users-added-temporarily-to-policies"></a>Usuários adicionados temporariamente a políticas

O **painel Usuários** inclui usuários adicionados às políticas de gerenciamento de riscos internas após um evento incomum fora do fluxo de trabalho de gerenciamento de riscos insider. Adicionar usuários temporariamente (do painel Políticas) também é uma maneira de começar a pontuar a atividade do usuário para uma política de gerenciamento de riscos internos para testar a política, mesmo que um conector necessário não seja configurado.

Quando um usuário é adicionado manualmente a uma política, as atividades do usuário dos últimos 90 dias são pontuadas e adicionadas à linha do tempo de atividade **do** usuário. Por exemplo, você tem um usuário que não está sendo atribuído pontuações de risco para uma política de risco interno e o usuário tem atividades de vazamento de dados relatadas ao departamento jurídico em sua organização. O departamento jurídico recomenda que você configure novos requisitos de monitoramento de curto prazo para o usuário. Você pode atribuir temporariamente o usuário à sua *política de vazamentos* de dados por um período de tempo designado (janela de ativação). Todos os usuários adicionados temporariamente são exibidos no painel **Usuários porque** os requisitos de evento de gatilho são isendos.

>[!NOTE]
>Pode levar várias horas para que novos usuários adicionados manualmente apareçam no **painel Usuários.** As atividades dos últimos 90 dias para esses usuários podem levar até 24 horas para serem exibidas. Para exibir atividades para usuários adicionados manualmente, selecione o usuário no painel Usuários e abra a guia **Atividade** do usuário no painel de detalhes. 

O usuário é removido automaticamente do painel **Usuários** e as paradas de pontuação quando o tempo definido na **janela** Ativação expira se:

- o usuário não tem nenhum evento de disparo adicional ou alertas de política de risco interna e
- se a duração da janela **Ativação definida** manualmente for maior do que a duração da janela **de ativação de política** global.

A **configuração da janela** Ativação com a duração mais longa sempre substitui a **configuração** da janela de ativação com uma duração mais curta. Por exemplo, você configurou  a janela Ativação na guia **Períodos** de Tempo da Política global nas configurações globais de gerenciamento de riscos do insider por 15 dias, que são aplicadas automaticamente a todas as políticas de risco internas. 

Você adiciona temporariamente um usuário à política de risco insider *Vazamentos* de dados e define 30 dias como a janela Ativação **desse** usuário. A **configuração da** janela de Ativação global de  15 dias é anulada definindo a configuração da janela de ativação de 30 dias para o usuário temporariamente adicionado. O usuário adicionado temporariamente permanecerá no **painel Usuários** e estará no escopo da política por 30 dias.

No cenário oposto em que a configuração  da janela de Ativação **global** é maior do  que a configuração da janela Ativação definida para um usuário adicionado temporariamente, a configuração da janela Ativação **global** substituiria a configuração da janela Ativação do usuário temporariamente adicionado. O usuário adicionado temporariamente  permanecerá no painel Usuários e estará no escopo da política para o número de dias definido nas configurações da janela **de** Ativação global.

## <a name="view-user-information-on-the-users-dashboard"></a>Exibir informações do usuário no painel Usuários

Cada usuário exibido no painel **Usuários** tem as seguintes informações:

- **Usuários**: o nome de usuário de um usuário. Esse campo será anonimizado se a configuração de anonimização global para o gerenciamento de risco interno estiver habilitada.
- **Nível de** risco : o nível de risco calculado atual do usuário. Essa pontuação é calculada a cada 24 horas e usa as pontuações de risco de alerta de todos os alertas ativos associados ao usuário. Para usuários com apenas indicadores de gatilho, o nível de risco é zero.
- **Alertas ativos**: o número de alertas ativos para todas as políticas.
- **Violações confirmadas**: O número de casos resolvidos como *violação de política confirmada* para o usuário.
- **Caso**: o caso ativo atual para o usuário.

![Painel de usuários de gerenciamento de riscos do Insider](../media/insider-risk-users-dashboard.png)

>[!NOTE]
>O número de usuários exibidos no painel **Usuários** pode ser limitado em algumas instâncias, dependendo do volume de alertas ativos e políticas correspondentes. Os usuários com alertas ativos são exibidos no painel Usuários à medida que os alertas são gerados e podem haver casos raros quando o número máximo de usuários exibidos é atingido.  Se esse limite acontecer, os usuários com alertas ativos  que não são exibidos serão adicionados ao painel Usuários à medida que os alertas de usuário existentes são triaged.

## <a name="view-user-details"></a>Exibir detalhes do usuário

Para exibir mais detalhes sobre atividade de risco para um usuário, abra o painel de detalhes do usuário clicando duas vezes em um usuário no painel **Usuários.** No painel de detalhes, você pode exibir as seguintes informações:

- **Guia Perfil de** Usuário
    - **Nome e título**: o nome e o título de posição para o usuário Azure Active Directory. Esses campos de usuário serão anonimizados ou vazios se a configuração de anonimização global para o gerenciamento de risco interno estiver habilitada.
    - **Email do usuário**: O endereço de email do usuário.
    - **Alias**: o alias de rede do usuário.
    - **Organização ou departamento**: a organização ou o departamento do usuário.

- **Guia Atividade do** usuário
    - **Histórico de atividades recentes do usuário**: lista indicadores de gatilho e indicadores de risco insider para atividades do usuário até os últimos 180 dias. Todas as atividades pertinentes aos indicadores de risco insider também são pontuadas, embora as atividades possam ou não ter gerado um alerta de risco interno. Os exemplos de indicador de disparo podem ser uma data de demissão ou a última data de trabalho agendada para o usuário. Os indicadores de risco insider são atividades determinadas por ter um elemento de risco e são definidos em políticas em que o usuário está incluído. As atividades de evento e risco são listadas com o item mais recente listado primeiro.

## <a name="remove-users-from-in-scope-assignment-to-policies"></a>Remover usuários da atribuição no escopo para políticas

Pode haver cenários em que você precisa parar de atribuir pontuações de risco à atividade de um usuário em políticas de gerenciamento de riscos internas. Use **Remover** usuários  na página painel Usuários para parar de atribuir pontuações de risco para um ou mais usuários de todas as políticas de gerenciamento de riscos internas para as qual eles estão no escopo no momento. Essa ação não remove os usuários da atribuição geral de política (quando você adiciona usuários ou grupos a uma configuração de política), mas simplesmente remove os usuários do processamento ativo por políticas após eventos de gatilho atuais. Se os usuários têm outro evento de gatilho no futuro, as pontuações de risco de políticas começarão automaticamente a ser atribuídas aos usuários novamente. Quaisquer alertas ou casos existentes para esse usuário não serão removidos.

>[!NOTE]
>Remover um usuário de uma política pode levar vários minutos para ser concluído. Depois de concluído, o usuário não será mais listado na página Usuários. Se o usuário removido tiver alertas ou casos ativos, o usuário permanecerá na página Usuários e os detalhes do usuário mostrarão que eles não estão mais no escopo de uma política.

Para remover manualmente os usuários do status no escopo em todas as políticas de gerenciamento de riscos internas, conclua as seguintes etapas:

1. No centro [Microsoft 365 de conformidade,](https://compliance.microsoft.com)vá para Gerenciamento de riscos **do Insider** e selecione **a guia** Usuários.
2. No painel **Usuários,** selecione o usuário ou os usuários que você deseja remover de estar no escopo em políticas de gerenciamento de riscos internas.
3. Selecione **Remover usuários**.
4. No painel **Remover usuário,** Selecione **Remover** ou **Cancelar** para descartar as alterações e fechar a caixa de diálogo.
5. Selecione **Remover** no painel de confirmação para remover o usuário.

## <a name="run-automated-tasks-with-power-automate-flows-for-a-user"></a>Executar tarefas automatizadas com Power Automate fluxos para um usuário

Usando fluxos Power Automate recomendados, os investigadores e analistas de risco podem tomar medidas rapidamente para:

- Notificar os usuários quando eles são adicionados a uma política de risco interno

Para executar, gerenciar ou criar fluxos Power Automate para um usuário de gerenciamento de risco interno:

1. Selecione **Automatizar** na barra de ferramentas de ação do usuário.
2. Escolha o Power Automate fluxo a ser executado e selecione **Executar fluxo**.
3. Após a conclusão do fluxo, selecione **Concluído**.

Para saber mais sobre Power Automate fluxos para gerenciamento de riscos insider, consulte [Getting started with insider risk management settings](insider-risk-management-settings.md#power-automate-flows-preview).
