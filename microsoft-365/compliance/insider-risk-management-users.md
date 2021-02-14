---
title: Insider risk management Users dashboard
description: Saiba mais sobre o painel De usuários do gerenciamento de riscos interno no Microsoft 365
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
ms.openlocfilehash: 224221950104b5dee6a6e8f179db34ee6fad014e
ms.sourcegitcommit: e5ac81132cc5fd248350627a3cc7b3c640f53b6e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/22/2020
ms.locfileid: "48208767"
---
# <a name="insider-risk-management-users-dashboard"></a>Insider risk management Users dashboard

O **painel Usuários é** uma ferramenta importante no fluxo de trabalho de gerenciamento de riscos interno e ajuda investigadores e analistas a ter uma compreensão mais completa das atividades de risco. Este painel oferece exibições e recursos de gerenciamento para atender às necessidades administrativas entre a criação de políticas de gerenciamento de riscos interno e o gerenciamento de casos de gerenciamento de riscos insider.

Depois que os usuários são adicionados às políticas de gerenciamento de riscos internos, os processos em segundo plano estão avaliando automaticamente as atividades do usuário para [indicadores de disparo.](insider-risk-management-settings.md#indicators) Depois que os indicadores de disparo estão presentes, as atividades do usuário são atribuídas a pontuações de risco. Algumas dessas atividades podem resultar em um alerta de risco interno, mas algumas atividades podem não atender a um nível mínimo de pontuação de risco e um alerta de risco interno não será criado. O **painel Usuários** permite que você veja usuários com esses tipos de indicadores e pontuações de risco, bem como os usuários que têm alertas de risco interno ativos.

Além disso, pode haver cenários em que você precisa adicionar temporariamente usuários a políticas de risco interno após um evento incomum ser relatado fora do fluxo de trabalho de gerenciamento de riscos interno. O **painel Usuários** permite que você adicione manualmente um usuário a uma política de risco interno por um período específico de tempo e ignore o requisito de um usuário para ter um indicador de disparo. Esses usuários são sempre exibidos no painel Usuários quando atribuídos ativamente a uma política.

Saiba mais sobre como o painel Usuários exibe os usuários nos seguintes cenários:

- Dashboard users with active insider risk policy alerts
- Dashboard users with triggering indicators
- Usuários do painel adicionados temporariamente às políticas

## <a name="dashboard-users-with-active-insider-risk-policy-alerts"></a>Dashboard users with active insider risk policy alerts

O **painel Usuários** exibe automaticamente todos os usuários com alertas ativos de política de risco interno. Esses usuários com alertas têm um indicador de acionamento e uma pontuação de risco de atividade que atende aos requisitos para a criação de um alerta de risco interno. As atividades desses usuários são exibidas  selecionando o usuário no painel Usuários e navegando até a **guia Atividade do** usuário.

## <a name="dashboard-users-with-triggering-indicators"></a>Dashboard users with triggering indicators

O **painel Usuários** exibe automaticamente todos os usuários com indicadores de acionamento, mas que não têm uma pontuação de risco de atividade que criaria um alerta de risco interno. Por exemplo, um usuário com uma data de remissão relatada é exibido porque esse evento é um indicador de disparo, mas não é uma atividade que tem uma pontuação de risco. As atividades desses usuários são exibidas  selecionando o usuário no painel Usuários e navegando até a **guia Atividade do** usuário.

## <a name="dashboard-users-added-temporarily-to-policies"></a>Usuários do painel adicionados temporariamente às políticas

O **painel Usuários** permite que você adicione temporariamente usuários a uma política existente de gerenciamento de riscos insider após um evento incomum fora do fluxo de trabalho de gerenciamento de riscos interno. A adição temporária de usuários também é uma maneira de adicionar usuários a uma política de gerenciamento de riscos internos para testar a política, mesmo que um conector necessário não seja configurado.

Quando um usuário é adicionado manualmente a uma política, as atividades do usuário dos 90 dias anteriores são pontuadas e adicionadas à linha do tempo **da atividade do** usuário. Por exemplo, você tem um usuário que não está no escopo no momento em uma política de risco interno e o usuário tem atividades de vazamento de dados relatadas ao departamento jurídico da sua organização. O departamento jurídico recomenda que você configure novos requisitos de monitoramento de curto prazo para o usuário. Você pode atribuir temporariamente o usuário à sua *política de vazamento de* dados por um período designado (janela de ativação). Todos os usuários adicionados temporariamente são exibidos no painel **Usuários porque** os requisitos do indicador de disparo são anulados.

>[!NOTE]
>Pode levar várias horas para que novos usuários adicionados manualmente apareçam no **painel Usuários.** As atividades dos 90 dias anteriores para esses usuários podem levar até 24 horas para exibição. Para exibir as atividades de usuários adicionados  manualmente,  selecione o usuário no painel Usuários e abra a guia Atividade do usuário no painel de detalhes.

O usuário é removido automaticamente da  política interna e do painel Usuários quando a hora definida na **janela** Ativação expira se:

- o usuário não tem nenhum indicador de disparo ou alertas de política de risco interno e
- se a duração da janela **Ativação definida** manualmente for maior que a duração da janela **de Ativação da política** global. 

A **configuração da janela** Ativação com a duração mais longa sempre substitui a configuração **da** janela Ativação por uma duração mais curta. Por exemplo, você configurou  a janela Ativação na guia de **períodos** de política global nas configurações globais de gerenciamento de riscos insider por 15 dias, que é aplicada automaticamente a todas as suas políticas de risco interno. 

Você adiciona temporariamente um usuário à sua política de risco interno de vazamento *de* dados e define 30 dias como a janela **de** ativação para esse usuário. A **configuração de** janela de Ativação global de  15 dias é substituído pela definição da configuração da janela Ativação de 30 dias para o usuário temporariamente adicionado. O usuário temporariamente adicionado permanecerá no painel **Usuários** e estará no escopo da política por 30 dias.

No cenário oposto em que a configuração  da janela Ativação **global** é maior do que  a configuração da janela Ativação definida para um usuário temporariamente adicionado, a configuração da janela Ativação **global** substituiria a configuração da janela Ativação do usuário temporariamente adicionado. O usuário temporariamente adicionado  permanecerá no painel Usuários e estará no escopo da política pelo número de dias definido nas configurações da janela de **Ativação** global.

## <a name="view-user-information-on-the-users-dashboard"></a>Exibir informações do usuário no painel Usuários

Cada usuário exibido no painel **Usuários tem** as seguintes informações:

- **Usuários**: o nome de usuário de um usuário. Esse campo será anônimo se a configuração de anonimato global para o gerenciamento de riscos interno estiver habilitada.
- **Nível de** risco : o nível de risco calculado atual do usuário. Essa pontuação é calculada a cada 24 horas e usa as pontuações de risco de alerta de todos os alertas ativos associados ao usuário. Para usuários com apenas indicadores de disparo, o nível de risco é zero.
- **Alertas ativos:** o número de alertas ativos para todas as políticas.
- **Violações confirmadas:** o número de casos resolvidos *como violação de política* confirmada para o usuário.
- **Caso**: o caso ativo atual do usuário.

![Painel de usuários de gerenciamento de riscos insider](../media/insider-risk-users-dashboard.png)

>[!NOTE]
>O número de usuários  exibidos no painel Usuários pode ser limitado em algumas instâncias, dependendo do volume de alertas ativos e das políticas correspondentes. Os usuários com alertas ativos são exibidos no painel Usuários à medida que os alertas são gerados, e pode haver casos raros quando o número máximo de usuários exibidos é atingido.  Se isso acontecer, os usuários com alertas ativos que  não são exibidos serão adicionados ao painel Usuários à medida que os alertas de usuário existentes são triaged.

## <a name="view-user-details"></a>Exibir detalhes do usuário

Para exibir mais detalhes sobre a atividade de risco para um usuário, abra o painel de detalhes do usuário clicando duas vezes em um usuário no **painel Usuários.** No painel de detalhes, você pode exibir as seguintes informações:

- **Guia Perfil de** Usuário
    - **Nome e título:** o nome e o cargo do usuário do Azure Active Directory. Esses campos de usuário serão anonimizados ou vazios se a configuração de anonimato global para gerenciamento de riscos insider estiver habilitada.
    - **Email do** usuário : o endereço de email do usuário.
    - **Alias:** o alias de rede do usuário.
    - **Organização ou departamento:** a organização ou o departamento do usuário.

- **Guia Atividade do** usuário
    - **Histórico de atividades recentes do usuário:** lista os indicadores de disparo e os indicadores de risco interno para atividades do usuário até os últimos 180 dias. Todas as atividades pertinentes aos indicadores de risco interno também são pontuadas, embora as atividades possam ou não ter gerado um alerta de risco interno. Os exemplos de indicadores de disparo podem ser uma data de vencimento ou a última data agendada do trabalho para o usuário. Os indicadores de risco interno são atividades determinadas como um elemento de risco e são definidas em políticas em que o usuário está incluído. As atividades de evento e risco são listadas com o item mais recente listado primeiro.

## <a name="temporarily-add-a-user-to-a-policy"></a>Adicionar temporariamente um usuário a uma política

Para adicionar temporariamente um usuário a uma política de  gerenciamento de riscos interno, você usará a guia Usuários na solução de gerenciamento de riscos do **Insider** no centro de conformidade do Microsoft 365. Os usuários adicionados manualmente ignoram os requisitos do indicador de acionamento para a política à que são adicionados e são exibidos no **painel Usuários.** Para adicionar permanentemente um usuário a uma política de gerenciamento de riscos interno, você usará o assistente de política.

Conclua as seguintes etapas para adicionar um usuário a uma política de risco interno existente:

1. No centro [de conformidade do Microsoft 365,](https://compliance.microsoft.com)vá para o gerenciamento de riscos do **Insider** e selecione a **guia** Usuários.
2. Selecione **Adicionar um usuário a uma política** na barra de ferramentas.
3. Na caixa **de diálogo Adicionar um novo** usuário, comece a digitar um nome de usuário no **campo** Usuário. Selecione o usuário que você deseja adicionar a uma política.
4. Selecione a seta da lista suspenso para o **campo Política** exibir as políticas de gerenciamento de riscos internas configuradas. Selecione a política à que adicionar o usuário.
5. Use o **controle deslizante** da janela Ativação para definir por quanto tempo o usuário é incluído em uma política e exibido no painel Usuários. O tempo especificado determina por quanto tempo a política está ativa para esse usuário e começa quando o primeiro alerta é gerado ou um indicador de disparo (como uma política de DLP) é detectado. O intervalo para a **janela Ativação** é de 5 a 30 dias.
6. Selecione **Adicionar** e **confirme** para adicionar o usuário à política.

>[!NOTE]
>Pode levar várias horas para que novos usuários adicionados manualmente apareçam no **painel Usuários.** As atividades dos 90 dias anteriores para esses usuários podem levar até 24 horas para exibição. Para exibir as atividades de usuários adicionados  manualmente,  selecione o usuário no painel Usuários e abra a guia Atividade do usuário no painel de detalhes.

## <a name="run-automated-tasks-with-power-automate-flows-for-a-user"></a>Executar tarefas automatizadas com fluxos do Power Automate para um usuário

Usando fluxos recomendados do Power Automate, os investigadores e analistas de risco podem tomar medidas rapidamente para:

- Notificar os usuários quando eles são adicionados a uma política de risco interno

Para executar, gerenciar ou criar fluxos do Power Automate para um usuário de gerenciamento de riscos interno:

1. Selecione **Automatizar na** barra de ferramentas de ação do usuário.
2. Escolha o fluxo do Power Automate a ser executado e selecione **Executar fluxo.**
3. Após a conclusão do fluxo, selecione **Concluído.**

Para saber mais sobre fluxos do Power Automate para gerenciamento de riscos insider, consulte Getting [started with insider risk management settings](insider-risk-management-settings.md#power-automate-flows-preview).
