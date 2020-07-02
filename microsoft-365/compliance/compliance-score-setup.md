---
title: Configuração da Pontuação de conformidade da Microsoft (versão prévia)
f1.keywords:
- NOCSH
ms.author: chvukosw
author: chvukosw
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Saiba como configurar e começar a usar a pontuação de conformidade da Microsoft, que ajuda a simplificar e automatizar as avaliações de risco.
ms.openlocfilehash: f7a501d0ede0d7635e20581774ce51a599dde65b
ms.sourcegitcommit: 0650da0e54a2b484a3156b3aabe44397fbb38e00
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2020
ms.locfileid: "45016186"
---
# <a name="compliance-score-preview-setup"></a>Configuração da Pontuação de conformidade (visualização)

**Neste artigo:** Saiba como **acessar** a pontuação de conformidade, definir **funções e permissões**e configurar **as atualizações automáticas de Pontuação segura**. Este artigo também explica as principais páginas de Pontuação de conformidade: **seu painel**, a página ações de melhoria, a página soluções e a página avaliações.

## <a name="before-you-begin"></a>Antes de começar

O administrador global do Microsoft 365 da sua organização provavelmente será o primeiro usuário a ter acesso à pontuação de conformidade. Recomendamos a entrada de administrador global e defina as permissões do usuário, conforme descrito abaixo, ao visitar a pontuação de conformidade pela primeira vez.

## <a name="sign-in"></a>Entrar

1. Vá para o [centro de conformidade da microsoft 365](https://compliance.microsoft.com/) e **entre** com sua conta de administrador global do Microsoft 365.
2. Selecione a **Pontuação de conformidade** no painel de navegação esquerdo. Em seguida, você deve ver seu [painel de Pontuação de conformidade com sua pontuação](#understand-the-compliance-score-dashboard).

O link direto para a pontuação de conformidade do Access é [https://compliance.microsoft.com/compliancescore](https://compliance.microsoft.com/compliancescore) .

## <a name="set-user-permissions-and-assign-roles"></a>Definir permissões de usuário e atribuir funções

A pontuação de conformidade usa um modelo de permissão RBAC (controle de acesso baseado em função). Somente os usuários atribuídos a uma função podem acessar a pontuação de conformidade, e as ações permitidas por cada usuário são restringidas por tipo de função.

### <a name="where-to-set-permissions"></a>Onde definir permissões

A pessoa que detém a função de administrador global para sua organização pode definir permissões de usuário no [Azure Active Directory (Azure AD)](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal) ou no [Gerenciador de conformidade](compliance-manager-overview.md#permissions). Depois que as funções são definidas em qualquer um desses locais, os usuários podem acessar a pontuação de conformidade, bem como o Gerenciador de conformidade.

### <a name="role-types"></a>Tipos de função

A tabela abaixo mostra como cada [função do Azure ad](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) é mapeada para as funções do Gerenciador de conformidade existentes e as funções permitidas por cada função. Os usuários precisarão, pelo menos, da função leitor global do Azure AD para acessar a pontuação de conformidade.


| O usuário pode: | Função do Azure AD | Função de gerente de conformidade | 
| :------------- | :-------------: | :------------: |
| **Ler mas não editar dados**| Leitor global do Azure AD  | Leitor global do Azure AD | 
| **Ler mas não editar dados**| Leitor de segurança | Leitor do Gerenciador de conformidade  | 
| **Editar dados**| Administrador de conformidade | Colaborador do gerente de conformidade | 
| **Editar resultados de teste**| Administrador de conformidade | Consultor do Gerenciador de conformidade | 
| **Gerenciar avaliações e dados de modelo e locatário**| Administrador de conformidade<br>Administrador de dados de conformidade<br>Administrador de segurança | Administrador do Gerenciador de conformidade | 
| **Atribuir usuários**| Administrador global | Administração do portal | 

> [!NOTE]
> Quando você passar da Pontuação de conformidade para o gerente de conformidade para concluir uma tarefa durante a visualização pública, o navegador abrirá uma nova guia e será exibida uma caixa de diálogo. Na seção superior com o cabeçalho, "já é um cliente dos serviços de nuvem da Microsoft? Entre em sua conta, "selecione **entrar no** Gerenciador de conformidade do Access. Você não precisará inserir novamente suas credenciais.

## <a name="configure-automatic-secure-score-updates"></a>Configurar atualizações automáticas de Pontuação segura

Por padrão, todos os novos locatários têm as atualizações automáticas de [Pontuação segura](../security/mtp/microsoft-secure-score-new.md) ativadas. Todas as ações monitoradas por Pontuação segura atualizarão automaticamente o status da mesma ação na pontuação de conformidade.

O administrador global pode gerenciar essa configuração para desativar as atualizações automáticas de todas as ações ou definir atualizações para ações individualmente.

Durante a visualização pública, você precisará ir para o portal de confiança do serviço Microsoft (onde o Gerenciador de conformidade está localizado) para gerenciar as atualizações de Pontuação segura.

Para gerenciar atualizações automáticas de Pontuação segura, siga estas etapas:

1. Entre no portal de [confiança do serviço](https://servicetrust.microsoft.com) com sua conta de administrador global.

2. Na barra de menus superior do portal de confiança do serviço, em **mais**, selecione **administrador** e, em seguida, escolha **configurações**.

3. Na guia **Pontuação segura** , selecione o botão correspondente para **ativar todas as ações**, **desative todas as ações**ou **defina por ação.**

Se você escolher **definir por ação,** siga estas etapas adicionais para ativar as atualizações de Pontuação segura para ações individuais:

4. Selecione **Gerenciador de conformidade** no menu superior (não selecione "Gerenciador de conformidade (clássico)").

5. Selecione **Gerenciamento de locatário** no canto superior direito da tela.

6. No painel **ações do cliente** , encontre a ação pretendida com reticências (**...**) na coluna **ações afetadas** . Clique nas reticências e selecione **Editar.**

7. Alterne a opção de alternância de **atualização contínua de Pontuação segura** para **ativado.**

8. Selecione **salvar.** A monitoração contínua de Pontuação segura agora está ativada para essa ação.

**Observação:** Somente o administrador global pode ativar ou desativar as atualizações automáticas para todas as ações. O administrador do Gerenciador de conformidade pode ativar atualizações automáticas para ações individuais, mas não para todas as ações globalmente.

#### <a name="learn-more"></a>Saiba mais

[Leia sobre gerenciamento de atualizações de Pontuação segura](compliance-manager-release-notes.md#secure-score).

## <a name="understand-the-compliance-score-dashboard"></a>Entender o painel de Pontuação de conformidade

O painel de Pontuação de conformidade foi projetado para fornecer uma visão geral da postura de conformidade atual.

![Pontuação de conformidade-painel](../media/compliance-score-dashboard.png "Painel de Pontuação de conformidade")

### <a name="overall-compliance-score"></a>Pontuação de conformidade geral

A pontuação de conformidade é apresentada em destaque na parte superior. Ele mostra uma porcentagem com base nos pontos obtidos para a conclusão de ações de melhoria que tratam das normas e dos padrões principais de proteção de dados.

Quando você chegar à pontuação de conformidade pela primeira vez, sua pontuação inicial se baseará na linha de base de proteção de dados interna da [Microsoft 365](compliance-score-methodology.md#initial-score-based-on-microsoft-365-data-protection-baseline)— um conjunto de controles que inclui normas e padrões comuns do setor. A pontuação de conformidade verifica suas soluções existentes da Microsoft 365 e oferece uma avaliação inicial com base em suas configurações atuais de privacidade e segurança. À medida que você adiciona avaliações que são relevantes para sua organização, sua pontuação se torna mais significativa para você.

#### <a name="learn-more"></a>Saiba mais
[Entenda como a pontuação de conformidade é calculada](compliance-score-methodology.md).

### <a name="key-improvement-actions"></a>Ações de melhoria de chave

Esta seção lista as principais ações de aprimoramento que você pode tomar agora para fazer o maior impacto positivo em sua pontuação geral de conformidade.

### <a name="solutions-that-affect-your-score"></a>Soluções que afetam sua pontuação

Esta seção mostra soluções contendo ações com a maior oportunidade de afetar positivamente sua pontuação e o número de ações de melhorias pendentes em cada solução.

### <a name="compliance-score-breakdown"></a>Divisão de Pontuação de conformidade

Esta seção oferece uma visão mais detalhada da sua pontuação de duas maneiras diferentes:

- **Categories**: mostra a porcentagem de sua pontuação geral nas categorias de proteção de dados, como "proteger informações" ou "gerenciar dispositivos".
- **Avaliações**: mostra a porcentagem do seu progresso no gerenciamento de Avaliações para padrões específicos de conformidade e proteção de dados, normas ou leis, como RGPD ou NIST 800-53.

### <a name="filtering-your-dashboard-view"></a>Filtrando o modo de exibição do painel

Você pode filtrar o modo de exibição do painel para ver apenas os itens relacionados a normas e padrões específicos, soluções, tipo de ação, grupos de avaliação ou categorias de proteção de dados. Filtrar o modo de exibição dessa forma também filtrará a pontuação no painel, mostrando quantos pontos você alcançou do total de pontos possíveis com base nos critérios de filtro.

Para aplicar filtros:

1. Selecione **filtro** no lado superior direito do painel.
2. Selecione seus critérios de filtro no painel de submenu **filtros** e selecione **aplicar**.

Depois de aplicar um filtro, você verá sua pontuação ajustada em tempo real. A porcentagem de Pontuação de conformidade e as informações de divisão, e as ações e soluções de melhoria, agora pertencem apenas aos dados cobertos por seus critérios de filtro. Se você sair da Pontuação de conformidade, sua exibição filtrada permanecerá quando você entrar novamente.

Para remover filtros:

- No cabeçalho **filtros aplicados** acima da Pontuação de conformidade, selecione o **X** ao lado do filtro individual que você deseja remover; ou
- Selecione **filtro** no lado superior direito do painel e, em seguida, selecione **limpar filtros**.

## <a name="improvement-actions-page"></a>Página ações de melhoria

As [ações de melhoria](compliance-score-improvement-actions.md) centralizam suas atividades de conformidade e ajudam você a alinhar com regulamentos e padrões de proteção de dados. Cada ação de melhoria fornece orientações detalhadas de implementação e um link para iniciar você na solução apropriada. As ações podem ser atribuídas aos usuários em sua organização para executar o trabalho de implementação e teste. Você também pode armazenar documentação, anotações e registrar as atualizações de status na ação de melhoria.

### <a name="view-your-improvement-actions"></a>Exibir suas ações de aperfeiçoamento

O painel de Pontuação de conformidade mostra as **principais ações de aprimoramento**, que são as que têm os pontos mais disponíveis que atendem aos problemas mais importantes.

Para exibir todas as ações de aperfeiçoamento, selecione a guia **ações de aprimoramento** no painel. Ou selecione **Exibir todas as ações de aprimoramento** abaixo da lista de ações de melhoria de chave no painel.

Se você tiver uma longa lista de ações, talvez seja útil filtrar o modo de exibição. Selecione **filtro** no canto superior direito da lista ações. Quando o painel de submenu **filtros** for exibido, selecione seus critérios com base em regulamentos e padrões, solução e grupo. Você também pode personalizar o modo de exibição selecionando **Agrupar** no canto superior direito. No menu suspenso, selecione para exibir por grupo, solução, categoria, tipo de ação ou status.

O modo de exibição padrão para esta página não mostra ações de aperfeiçoamento com um status de teste de **aprovado**. Para exibir ações que passaram no teste, marque a caixa **aprovado** no painel de submenu filtros. Somente as ações com um status de teste de contagem **passada** em relação à sua pontuação.

A página ações de melhoria mostra os seguintes pontos de dados para cada ação de melhoria:

- **Impacto da Pontuação**: os pontos pelos quais a pontuação geral aumentará ao concluir a ação
- **Regulamentos**: a regulamentação ou o padrão referente à ação
- **Grupo**: o grupo ao qual você atribuiu a ação
- **Soluções**: a solução onde você pode ir para executar a ação
- **Avaliações**: a avaliação (que organiza os controles para atender a um determinado objetivo de conformidade) no qual a ação reside
- **Categorias**: a categoria de proteção de dados relacionada (como proteger informações, gerenciar dispositivos etc.)
- **Status do teste**:
    - **Nenhum** – nenhuma atualização de status registrada
    - **Não avaliado** -o teste não foi iniciado
    - **Aprovado** -implementação testada com êxito
    - Falha nos testes de **baixo risco** , baixo risco
    - Falha no teste de **risco médio** , risco médio
    - **Falha no alto risco** -falha no teste, alto risco
    - **Não está no escopo** – a ação não está no escopo da avaliação e não afeta sua pontuação
    - **Para ser detectado** -para teste manual, indica que uma ação foi implementada, mas não testada; para teste automatizado, indica que uma ação está aguardando o resultado da automação
    - **Não foi possível detectar** -o status automatizado não pode ser determinado
    - **Parcialmente testado** – Pontuação automatizada que premia pontos parciais
- **Pontos alcançados**: número de pontos obtidos do máximo possível

#### <a name="learn-more"></a>Saiba mais
[Confira como atribuir e executar trabalho em ações de aprimoramento](compliance-score-improvement-actions.md).

## <a name="solutions-page"></a>Página de soluções

A página soluções mostra o compartilhamento de pontos ganhos e potenciais como organizados por solução. Exibir os pontos e as ações de melhoria restantes desse modo de exibição ajuda a entender quais soluções precisam de mais atenção imediata.

Encontre a página soluções selecionando a guia **soluções** no painel de Pontuação de conformidade. Você também pode selecionar **Exibir todas as soluções** sob **soluções que afetam sua pontuação** na seção superior direita do seu painel.

### <a name="filtering-your-solutions-view"></a>Filtrando o modo de exibição de soluções

Para filtrar a exibição das soluções:

1. Selecione **filtro** no canto superior esquerdo da sua lista de avaliações.
2. No painel de submenu **filtros** , coloque uma marca ao lado dos critérios desejados (padrões e regulamentos, solução, tipo de ação, grupo Gerenciador de conformidade, categoria).
3. Selecione o botão **aplicar** . O painel de filtro será fechado e você verá o modo de exibição filtrado.

Você também pode modificar o modo de exibição para ver avaliações por grupo, produto ou regulamentação selecionando o tipo de agrupamento no menu suspenso de **grupo** acima da sua lista de avaliações.

### <a name="taking-actions-from-the-solution-page"></a>Executando ações da página solução

A página soluções exibe as soluções da sua organização que estão conectadas às ações de melhoria. A tabela lista a contribuição de cada solução para sua pontuação geral, os pontos de aumento de Pontuação obtidos e possíveis dentro dessa solução, e o número restante de ações de aprimoramento agrupadas nessa solução que podem aumentar sua pontuação.

Há duas maneiras de executar uma ação nesta tela:

1. Na linha da sua solução pretendida, na coluna **ações restantes** , selecione o número de hiperlink. Você verá um modo de exibição filtrado da tela ações de melhoria mostrando ações de aperfeiçoamento não testadas para essa solução.

2. Na linha da sua solução pretendida, na coluna **Abrir solução** , selecione **abrir**. Você verá a solução ou o local nos centros de segurança e conformidade do Microsoft 365 e do Office 365, onde você pode executar a ação recomendada.

## <a name="assessments-page"></a>Página de avaliações

A página avaliações lista todas as [avaliações](compliance-score-assessments.md) configuradas para sua organização. O denominador de Pontuação de conformidade é determinado por todas as avaliações rastreadas. Quanto mais avaliações você adicionar, mais ações de melhoria você verá na página ações de melhoria e maior será o denominador de pontuação.

Esta página resume as principais informações sobre cada avaliação:

- **Avaliação**: nome da avaliação
- **Status**:
    - **Concluído** -todos os controles têm um status de "Passed", ou pelo menos um é passado e o restante estão "fora do escopo"
    - **Incompleto** – pelo menos um controle tem um status de "falha"
    - **Nenhum** -todos os controles não foram testados
    - **Em andamento** – as ações de melhoria têm qualquer outro status, incluindo "em andamento", "crédito parcial" ou "não detectada
- **Progresso da avaliação**: a porcentagem do trabalho realizado em direção à conclusão, conforme medido pelo número de controles testados com êxito
- **Suas ações de melhoria**: o número de ações concluídas para satisfazer a implementação de seus controles
- **Ações da Microsoft**: o número de ações concluídas para satisfazer a implementação de controles da Microsoft
- **Grupo**: nome do grupo ao qual a avaliação pertence
- **Produto**: serviço Microsoft 365 associado
- **Regulamentação**: o padrão normativo, política ou legislação que se aplica à avaliação

### <a name="filtering-your-assessments-view"></a>Filtrando o modo de exibição de avaliações

Para filtrar a exibição de avaliações:

1. Selecione **filtro** no canto superior esquerdo da sua lista de avaliações.
2. No painel de submenu **filtros** , verifique os critérios desejados.
3. Selecione o botão Aplicar. O painel de filtro será fechado e você verá o modo de exibição filtrado.

Você também pode modificar o modo de exibição para ver avaliações por grupo, produto ou regulamentação selecionando o tipo de agrupamento no menu suspenso de **grupo** acima da sua lista de avaliações.

### <a name="default-assessment"></a>Avaliação padrão

Por padrão, você verá a avaliação da [linha de base de proteção de dados do Microsoft 365](compliance-score-methodology.md#initial-score-based-on-microsoft-365-data-protection-baseline) na página avaliações. A pontuação de conformidade também fornece vários [modelos](compliance-score-templates.md) prontos para usar para criar avaliações.

## <a name="next-step"></a>Próxima etapa
Personalizar a pontuação de conformidade [Configurando avaliações](compliance-score-assessments.md).