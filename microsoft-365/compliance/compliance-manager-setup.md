---
title: Começar com o Microsoft Compliance Manager
f1.keywords:
- NOCSH
ms.author: v-jgriffee
author: jmgriffee
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-compliancemanager
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: De definir permissões e funções de usuário do Microsoft Compliance Manager e configurar testes automatizados de ações. Gerencie o histórico do usuário e filtre o seu painel de exibição.
ms.openlocfilehash: 7e29dd0eff7b05cb55a1fb0e071632353dadbdf8
ms.sourcegitcommit: 46b77a41dfcc0ee80e2b89a7aa49e9bbe5deae5a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/26/2021
ms.locfileid: "53148897"
---
# <a name="get-started-with-compliance-manager"></a>Introdução ao Gerenciador de Conformidade

**Neste artigo:** Este artigo ajuda você a configurar o Gerenciador de Conformidade. Saiba como acessar **o Gerenciador** de Conformidade, definir funções e permissões e configurar testes **automáticos** **de ações de melhoria.** Ande pelo **painel do Gerenciador** de Conformidade e entenda as páginas principais: a página ações de melhoria, a página de soluções, a página avaliações e a página modelos de avaliação.

## <a name="who-can-access-compliance-manager"></a>Who acessar o Gerenciador de Conformidade

O Gerenciador de Conformidade está disponível para organizações com licenças Office 365 e Microsoft 365 e para clientes do Departamento de Defesa (DoD) dos EUA Nuvem da Comunidade Governamental (GCC) moderados, GCC Alta e Departamento de Defesa (DoD). Os recursos de disponibilidade e gerenciamento de avaliação dependem do contrato de licenciamento.  [Exibir detalhes de descrição do serviço](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).

## <a name="before-you-begin"></a>Antes de você começar

O Microsoft 365 administrador global da sua organização provavelmente será o primeiro usuário a acessar o Gerenciador de Conformidade. Recomendamos a entrada do administrador global e definir permissões de usuário conforme descrito abaixo ao visitar o Gerenciador de Conformidade pela primeira vez.

## <a name="sign-in"></a>Entrar

1. Vá para o [Centro de conformidade do Microsoft 365](https://compliance.microsoft.com/) **e entre com** sua conta Microsoft 365 administrador global.
2. Selecione **Gerenciador de Conformidade** no painel de navegação esquerdo. Você chegará ao painel do [Gerenciador de Conformidade.](#understand-the-compliance-manager-dashboard)

O link direto para acessar o Gerenciador de Conformidade é [https://compliance.microsoft.com/compliancemanager](https://compliance.microsoft.com/compliancemanager) .

## <a name="set-user-permissions-and-assign-roles"></a>Definir permissões de usuário e atribuir funções

O Gerenciador de Conformidade usa um modelo de permissão de controle de acesso baseado em função (RBAC). Somente usuários atribuídos a uma função podem acessar o Gerenciador de Conformidade e as ações permitidas por cada usuário são restritas por tipo [de função.](#role-types)

### <a name="where-to-set-permissions"></a>Onde definir permissões

A pessoa que tem a função de administrador global da sua organização pode definir permissões de usuário para o Gerenciador de Conformidade. As permissões podem ser definidas no centro Office 365 Segurança & Conformidade, bem como no Azure Active Directory (Azure AD).

> [!NOTE]
> Os clientes nos ambientes Community (GCC) High e Department of Defense (DoD) só podem definir permissões e funções do usuário para o Gerenciador de Conformidade no Azure AD. Confira abaixo instruções do Azure AD e definições de tipo de função.

Para definir permissões e atribuir funções no centro Office 365 Segurança & Conformidade, siga as etapas a seguir:

1. Vá para o Centro [Office 365 Segurança & Conformidade](https://protection.office.com/) e selecione **Permissões** na navegação à esquerda.

2. Encontre o grupo de funções ao qual você deseja adicionar um ou mais usuários e marque a caixa à esquerda do nome do grupo. (Consulte a [lista de funções e funções relacionadas abaixo](#role-types). Os nomes de grupo de função imitam o nome da função.)

3. No painel sublinhado para esse grupo, selecione **Editar** no header **Membros.**

4. Selecione **Escolher membros**. Outra janela de sobrevoo aparecerá.

5. Selecione **+ Adicionar** para escolher um ou mais usuários para adicionar ao grupo.

6. Selecione a caixa de seleção ao lado dos nomes que você deseja adicionar e selecione o botão **Adicionar** na parte inferior.

7. Quando você terminar de atribuir usuários, selecione **Feito**, em seguida, selecione **Salvar**, em **seguida, Fechar**.

##### <a name="more-about-the-office-365-security--compliance-center"></a>Mais sobre o centro de conformidade Office 365 segurança & segurança

Saiba mais sobre permissões no Centro de Conformidade Office 365 [Segurança & Segurança.](../security/office-365-security/permissions-in-the-security-and-compliance-center.md)

Se você não tiver acesso ao Centro de Conformidade e Segurança do Office 365 ou se precisar acessar a versão clássica do Gerenciador de Conformidade no Portal de Confiança do Serviço Microsoft, as configurações de Administrador no Portal de Confiança do Serviço fornece outra maneira de atribuir funções[(instruções](meet-data-protection-and-regulatory-reqs-using-microsoft-cloud.md#assigning-compliance-manager-roles-to-users)de exibição). Esteja ciente de que essas funções são mais limitadas em sua funcionalidade.

##### <a name="more-about-azure-ad"></a>Mais sobre o Azure AD

Para atribuir funções e definir permissões no Azure AD, consulte [Assign administrator and non-administrator roles to users with Azure Active Directory](/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal).

Os usuários com identidades do Azure AD que não têm assinaturas Office 365 ou Microsoft 365 não poderão acessar o Gerenciador de Conformidade no Centro de conformidade do Microsoft 365. Para buscar ajuda para acessar o Gerenciador de Conformidade, entre [em contato cmresearch@microsoft.com](mailto:cmresearch@microsoft.com).

### <a name="role-types"></a>Tipos de função

A tabela a seguir mostra as funções permitidas por cada função no Gerenciador de Conformidade. A tabela também mostra como cada [função do Azure AD](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) é mapeada para funções do Gerenciador de Conformidade. Os usuários precisarão pelo menos da função de leitor do Gerenciador de Conformidade ou da função de leitor global do Azure AD para acessar o Gerenciador de Conformidade.


| O usuário pode: | Função de Gerenciador de Conformidade | Função do Azure AD | 
| :------------- | :-------------: | :------------: |
| **Ler, mas não editar dados**| Leitor do Gerenciador de Conformidade  | Leitor global do Azure AD, Leitor de segurança | 
| **Editar dados**| Contribuição do Gerenciador de Conformidade | Administrador de Conformidade | 
| **Editar resultados de teste**| Avaliador do Gerenciador de Conformidade | Administrador de Conformidade | 
| **Gerenciar avaliações e dados de modelo e locatário**| Administração do Gerenciador de Conformidade | Administrador de Conformidade, Administrador de Dados de Conformidade, Administrador de Segurança  | 
| **Atribuir usuários**| Administrador global | Administrador global | 

## <a name="settings-for-automated-testing-and-user-history"></a>Configurações para testes automatizados e histórico de usuários

As configurações do Gerenciador de Conformidade no Centro de conformidade do Microsoft 365 permitem habilitar e desabilitar o teste automático de ações de melhoria. As configurações também permitem que você gerencie os dados de usuários associados a ações de melhoria, incluindo a capacidade de reatribuir ações de melhoria para um usuário diferente.  Somente pessoas com uma função de administrador global ou Administrador do Gerenciador de Conformidade podem acessar as configurações do Gerenciador de Conformidade.

> [!NOTE]
> O recurso de teste automatizado não está disponível para os clientes nos ambientes GCC High e DoD, pois a Pontuação Segura não está disponível nesses ambientes. GCC Os clientes high e DoD precisarão implementar e testar manualmente suas ações de melhoria.

### <a name="set-up-automated-testing"></a>Configurar testes automatizados

Algumas ações de melhoria no Gerenciador de Conformidade também são monitoradas pela [Pontuação Segura da Microsoft.](../security/defender/microsoft-secure-score.md) Você pode configurar testes automatizados de ações que são monitoradas em conjunto, o que significa que, quando uma ação é testada e atualizada na Pontuação Segura, esses resultados sincronizam com as mesmas ações no Gerenciador de Conformidade e contam para sua pontuação de conformidade.

O teste automático é ligado por padrão para organizações novas para o Gerenciador de Conformidade. Quando você implanta pela primeira vez Microsoft 365 ou Office 365, leva aproximadamente sete dias para a Pontuação Segura coletar totalmente os dados e fatorá-los em sua pontuação de conformidade.  Quando o teste automatizado estiver ligado, a data de teste da ação não será atualizada, mas seu status de teste será atualizado. Quando novas avaliações são criadas, as pontuações incluem automaticamente pontuações de controle da Microsoft e integração com a Pontuação Segura.

O administrador global da sua organização pode alterar as configurações para testes automatizados a qualquer momento. Você pode desativar o teste automatizado para ações comuns de melhoria ou a ativas para ações individuais. Siga as instruções a seguir para alterar suas configurações de teste automatizadas.

#### <a name="to-manage-your-automated-testing-settings"></a>Para gerenciar suas configurações de teste automatizadas:

1. Selecione **Configurações** navegação à esquerda de qualquer lugar no [Centro de conformidade do Microsoft 365](https://compliance.microsoft.com/).

2. Na página configurações, selecione **Gerenciador de Conformidade**.

3. Selecione **Testes automatizados** na navegação à esquerda.

4. Selecione o botão aplicável para ativar o teste automático para todas as ações de melhoria, acioná-lo para todas as ações ou acioná-lo por ação individual.

5. Se você selecionar **Ativar por ação de** melhoria, uma lista mostrará todas as ações de melhoria disponíveis para escolher.  Marque a caixa ao lado de qualquer ação que você deseja testar automaticamente.

6. Selecione **Salvar** para salvar suas configurações. Você receberá uma mensagem de confirmação na parte superior da tela que sua seleção foi salva. Se você receber um aviso de falha, tente novamente.

**Observação:** Somente o administrador global pode ativar ou desativar atualizações automáticas para todas as ações. O Administrador do Gerenciador de Conformidade pode ativar atualizações automáticas para ações individuais, mas não para todas as ações globalmente.

### <a name="manage-user-history"></a>Gerenciar histórico do usuário

As **configurações gerenciar histórico** do usuário ajudam você a identificar rapidamente quais usuários trabalharam com ações de melhoria no Gerenciador de Conformidade. Os dados de usuário identificáveis associados a ações de melhoria incluem qualquer trabalho de implementação e teste feito, documentos carregados e quaisquer anotações inseridas. Entender e recuperar esse tipo de dados pode ser necessário para as necessidades de conformidade da sua própria organização.

As configurações de histórico do usuário também permitem que você reatribua todas as ações de melhoria de um usuário para outro.

**Para encontrar as configurações de histórico do usuário:**

1. Selecione Configurações navegação à esquerda de qualquer lugar no [Centro de conformidade do Microsoft 365](https://compliance.microsoft.com/).

2. Na página configurações, selecione **Gerenciador de Conformidade**.

3. Selecione **Gerenciar histórico do usuário** na navegação à esquerda.

A **página gerenciar histórico do** usuário mostra uma lista de todos os usuários por endereço de email que são atribuídos a uma ação de melhoria. Use o **botão Pesquisar** para encontrar rapidamente um usuário específico digitando em seu endereço de email.

À direita do endereço de email de cada usuário, o menu suspenso **Selecionar** oferece opções para exportar um relatório, reatribuir ações de melhoria ou excluir histórico. Consulte cada seção abaixo para obter detalhes sobre cada opção.

#### <a name="export-a-report-of-user-history-data"></a>Exportar um relatório de dados de histórico do usuário

Você pode exportar um arquivo Excel que contém uma lista de ações de melhoria atribuídas atualmente a um usuário.  O relatório também lista todos os arquivos de evidências carregados por esse usuário. Essas informações podem ajudá-lo a reatribuir ações de melhoria abertas.

O relatório reflete o status da ação de melhoria a partir de sua data de criação. Não é um relatório histórico de todas as alterações anteriores ao seu status ou atribuição (saiba como exportar um relatório da página ações [de melhoria).](compliance-manager-improvement-actions.md#export-a-report)

**Siga as etapas abaixo para exportar um relatório por usuário:**

1. Selecione **Configurações** navegação à esquerda de qualquer lugar no [Centro de conformidade do Microsoft 365](https://compliance.microsoft.com/).

2. Na página configurações, selecione **Gerenciador de Conformidade**.

3. Selecione **Gerenciar histórico do usuário** na navegação à esquerda.

4. Encontre o usuário pretendido pesquisando os endereços de email de lista ou selecionando **Pesquisar** e inserindo o endereço de email do usuário.

5. No menu **suspenso Selecionar,** escolha **Exportar relatório**.

6. Depois que Excel arquivo do relatório for gerado, você poderá abri-lo e salvá-lo no computador local.

#### <a name="reassign-improvement-actions-to-another-user"></a>Reatribuir ações de melhoria para outro usuário

Você pode reatribuir ações de melhoria de um usuário para outro. Ao reatribuir uma ação, o histórico de carregamento do documento não muda, mas o nome do usuário que originalmente carregou a documentação não aparece mais na ação de aperfeiçoamento.

**Siga as etapas a seguir para reatribuir ações de melhoria a outro usuário:**

1. Selecione **Configurações** navegação à esquerda de qualquer lugar no [Centro de conformidade do Microsoft 365](https://compliance.microsoft.com/).

2. Na página configurações, selecione **Gerenciador de Conformidade**.

3. Selecione **Gerenciar histórico do usuário** na navegação à esquerda.

4. Encontre um usuário pesquisando os endereços de email de lista ou selecionando **Pesquisar** e inserindo o endereço de email desse usuário.

5. No menu **suspenso Selecionar,** escolha **Reatribuir ações de melhoria**. O **painel de destaque das ações** de melhoria de reatribuir será exibido.

6. No campo **Pesquisar usuários,** insira o nome ou o endereço de email do usuário a que você deseja atribuir as ações de *melhoria.*

7. Quando você vir o nome do usuário pretendido em Ações de Aperfeiçoamento serão atribuídas **a**, selecione o usuário e selecione **Atribuir ações**.

8. Quando a reatribuição for concluída, você verá uma mensagem de confirmação no painel do sobrevoo confirmando que todas as ações de melhoria do usuário anterior foram reatribuídas ao novo usuário. Se você receber um aviso de falha de reatribuição, feche a janela e tente novamente. Para fechar o painel de sobrevoos, selecione **Feito**.

O novo destinatário recebe um email atribuído a uma ação de melhoria. O email contém um link direto para a página de detalhes da ação de melhoria.
 
 > [!NOTE]
> Se você reatribuir uma ação que tenha uma atualização pendente, o link direto para a ação no email de reatribuição será desatribuido se a atualização for aceita após a reatribuição. Você pode corrigir isso atribuindo a ação ao usuário depois que a atualização for aceita. Saiba mais sobre [atualizações para ações de melhoria.](compliance-manager-improvement-actions.md#accepting-updates-to-improvement-actions)

#### <a name="delete-user-history"></a>Excluir histórico do usuário

Excluir o histórico de um usuário o removerá como proprietário de ações de melhoria e removerá seu nome de todos os outros campos no Gerenciador de Conformidade. Quando você exclui o histórico de um usuário, as  ações de melhoria que eles possuíam não exibirão um valor Atribuído ao valor até que um novo usuário seja atribuído. Todos os documentos carregados na ação de aperfeiçoamento mostrarão **o usuário** removido no lugar do nome do usuário excluído. Excluir o histórico do usuário é permanente.

Para excluir o histórico de um usuário, siga as etapas abaixo:

1. Selecione **Configurações** navegação à esquerda de qualquer lugar no [Centro de conformidade do Microsoft 365](https://compliance.microsoft.com/).

2. Na página configurações, selecione **Gerenciador de Conformidade**.

3. Selecione **Gerenciar histórico do usuário** na navegação à esquerda.

4. Encontre um usuário pesquisando os endereços de email de lista ou selecionando **Pesquisar** e inserindo o endereço de email desse usuário.

5. No menu **suspenso Selecionar,** escolha **Excluir histórico**.

6. Uma janela aparece solicitando que você confirme a exclusão permanente do histórico do usuário. Para continuar com a exclusão, selecione **Excluir histórico**. Para sair sem excluir o histórico, selecione **Cancelar**.

7. Você chegará novamente à  página Gerenciar histórico do usuário com uma mensagem de confirmação na parte superior de que o histórico do usuário foi excluído.

## <a name="understand-the-compliance-manager-dashboard"></a>Compreender o painel do Gerenciador de Conformidade

O painel do Gerenciador de Conformidade foi projetado para fornecer uma visão geral da postura de conformidade atual.

![Gerenciador de Conformidade - painel](../media/compliance-manager-dashboard.png "Painel do Gerenciador de Conformidade")

### <a name="overall-compliance-score"></a>Classificação geral da conformidade

Sua pontuação de conformidade é destaque na parte superior. Ele mostra uma porcentagem com base em pontos que podem ser alcançados para concluir ações de melhoria que abordam os principais padrões e regulamentos de proteção de dados. Pontos das [ações da Microsoft](compliance-manager-assessments.md#microsoft-actions-tab), que são gerenciadas minha Microsoft, também contam para sua pontuação de conformidade.

Quando você chega ao Gerenciador de Conformidade pela primeira vez, sua pontuação inicial é baseada na linha de base Microsoft 365 [proteção de dados.](compliance-manager-assessments.md#data-protection-baseline-default-assessment) Essa avaliação de linha de base, que está disponível para todas as organizações, é um conjunto de controles que inclui normas e padrões comuns do setor. O Gerenciador de Conformidade verifica suas soluções Microsoft 365 existentes e fornece uma avaliação inicial com base em suas configurações atuais de privacidade e segurança. À medida que você adiciona avaliações relevantes à sua organização, sua pontuação se torna mais significativa para você.

**Saiba mais: Entenda** [como sua pontuação de conformidade é calculada](compliance-score-calculation.md).

### <a name="key-improvement-actions"></a>Principais ações de melhoria

Esta seção lista as principais ações de melhoria que você pode tomar agora para fazer o maior impacto positivo na pontuação geral de conformidade. Selecione **Exibir todas as ações de melhoria** para ir para a página ações de melhoria.

### <a name="solutions-that-affect-your-score"></a>Soluções que afetam sua pontuação

Esta seção destaca as soluções que contêm ações de melhoria que podem afetar positivamente sua pontuação e o número de ações de melhoria pendentes nessas soluções. Selecione **Exibir todas as soluções** para visitar sua página de soluções.

### <a name="compliance-score-breakdown"></a>Detalhamento da pontuação de conformidade

Esta seção oferece uma exibição mais detalhada de sua pontuação de duas maneiras diferentes:

- **Categorias**: mostra a porcentagem da sua pontuação geral nas categorias de proteção de dados, como "proteger informações" ou "gerenciar dispositivos".
- **Avaliações**: mostra a porcentagem do seu progresso no gerenciamento de avaliações para padrões, regulamentos ou leis específicos de conformidade e proteção de dados, como rgpd ou NIST 800-53.

### <a name="filtering-your-dashboard-view"></a>Filtrando o seu painel de exibição

Você pode filtrar a exibição do painel para ver apenas os itens relacionados a normas e padrões específicos, soluções, tipo de ação, grupos de avaliação ou categorias de proteção de dados. Filtrar seu modo de exibição dessa forma também filtrará a pontuação em seu painel, mostrando quantos pontos você atingiu do total de pontos possíveis com base em seus critérios de filtro.

Para aplicar filtros:

1. Selecione **Filtrar** no lado superior direito do painel.
2. Selecione seus critérios de filtro no painel de flyout **Filters** e selecione **Aplicar**.

Depois de aplicar um filtro, você verá sua pontuação ajustada em tempo real. A porcentagem de pontuação de conformidade e informações de divisão e as ações e soluções de melhoria agora pertencem apenas aos dados cobertos por seus critérios de filtro. Se você sair do Gerenciador de Conformidade, sua exibição filtrada permanecerá quando você entrar novamente.

Para remover filtros:

- No título **Filtros aplicados** acima da pontuação de conformidade, selecione **o X** ao lado do filtro individual que você deseja remover; ou
- Selecione **Filtrar** no lado superior direito do  painel e, no painel sub-sub-sublto filtros, selecione **Limpar filtros**.

## <a name="improvement-actions-page"></a>Página Ações de melhoria

[Ações de melhoria](compliance-manager-improvement-actions.md) são ações gerenciadas pela sua organização. Trabalhar com ações de melhoria ajuda a centralizar suas atividades de conformidade e alinhar-se aos regulamentos e padrões de proteção de dados. Cada ação de aperfeiçoamento fornece orientações detalhadas de implementação e um link para iniciar você na solução apropriada. Ações de melhoria podem ser atribuídas aos usuários em sua organização para executar o trabalho de implementação e teste. Você também pode armazenar as atualizações de status de documentação, anotações e registro na ação de melhoria.

### <a name="view-your-improvement-actions"></a>Exibir suas ações de melhoria

O painel do Gerenciador de Conformidade mostra suas **principais ações de melhoria.** Para exibir todas as suas ações de melhoria, selecione a guia Ações de melhoria no painel, que o traz para a página ações de melhoria. Você também pode selecionar Exibir todas as ações de melhoria abaixo da lista de principais ações de melhoria em seu painel para chegar à sua página de ações de melhoria.

A página ações de melhoria mostra todas as ações de melhoria gerenciadas pela sua organização. As ações gerenciadas pela Microsoft podem ser exibidas em cada avaliação (saiba mais sobre [as ações da Microsoft](compliance-manager-assessments.md#microsoft-actions-tab)).

Se você tiver uma longa lista de ações em sua página de ações de melhoria, pode ser útil filtrar sua exibição. Selecione **Filtrar** no canto superior direito da lista de ações. Quando o **painel de** flyout Filters for exibido, selecione seus critérios com base em regulamentos e padrões, solução e grupo. Você também pode personalizar sua exibição **selecionando Grupo** no canto superior direito. No menu suspenso, selecione para exibir por grupo, solução, categoria, tipo de ação ou status.

O modo de exibição padrão para esta página não mostra ações de melhoria com um status de teste de **Passado**. Para exibir ações que passaram no teste, marque a caixa **Passada** no painel de flyout Filters. Somente ações com um status de teste de **Contagem Passada** para sua pontuação. Algumas ações podem mostrar um **rótulo de atualização pendente.** Saiba mais sobre [atualizações para ações de melhoria.](compliance-manager-improvement-actions.md#accepting-updates-to-improvement-actions)

A página ações de melhoria mostra os seguintes pontos de dados para cada ação de melhoria:

- **Pontos atingidos**: o número de pontos atingidos do total disponível ao concluir a ação
- **Regulamentos**: os regulamentos ou padrões relacionados à ação
- **Grupo**: o grupo ao qual você atribuiu a ação
- **Soluções**: a solução onde você pode ir para executar a ação
- **Avaliações**: as avaliações que contêm a ação
- **Categorias**: a categoria de proteção de dados relacionada (como, proteger informações, gerenciar dispositivos, etc.)
- **Status do teste**:
    - **Nenhum** – nenhuma atualização de status registrada
    - **Não avaliado** - os testes ainda não foram iniciados
    - **Passado** - implementação testada com êxito
    - **Baixo risco com falha** - falha no teste, baixo risco
    - **Risco médio com falha** - falha no teste, risco médio
    - **Falha de alto risco** - falha no teste, alto risco
    - **Fora do escopo** – a ação não está no escopo da avaliação e não afeta sua pontuação
    - **Para ser detectado** - para teste manual, indica que uma ação foi implementada, mas não testada; para teste automatizado, indica que uma ação está aguardando o resultado da automação
    - **Não foi possível detectar** - o status automatizado não pode ser determinado
    - **Parcialmente testada** – pontuação automatizada que concede pontos parciais

**Saiba mais:** [Confira como atribuir e executar o trabalho em ações de melhoria.](compliance-manager-improvement-actions.md)

## <a name="solutions-page"></a>Página Soluções

A página soluções mostra o compartilhamento de pontos ganhos e potenciais conforme organizado pela solução. Exibir seus pontos restantes e ações de melhoria desse ponto de vista ajuda você a entender quais soluções precisam de mais atenção imediata.

Encontre a página soluções selecionando a guia **Soluções** no painel do Gerenciador de Conformidade. Você também pode selecionar **Exibir todas as soluções** abaixo Soluções que afetam **sua pontuação** na seção superior direita do painel.

### <a name="filtering-your-solutions-view"></a>Filtrando o seu exibição de soluções

Para filtrar sua exibição de soluções:

1. Selecione **Filtrar** no canto superior esquerdo da lista de avaliações.
2. No painel **de sobrevoos Filtros,** coloque uma verificação ao lado dos critérios desejados (padrões e regulamentos, solução, tipo de ação, grupo Gerenciador de Conformidade, categoria).
3. Selecione o **botão Aplicar.** O painel de filtro será fechado e você verá o seu exibição filtrado.

Você também pode modificar sua exibição para ver avaliações por grupo, produto  ou regulamentação selecionando o tipo de grupo no menu suspenso Grupo acima da lista de avaliações.

### <a name="taking-action-from-the-solution-page"></a>Tomar medidas da página de solução

A página soluções exibe as soluções da sua organização conectadas a ações de melhoria. A tabela lista a contribuição de cada solução para sua pontuação geral, os pontos alcançados e possíveis dentro dessa solução e o número restante de ações de melhoria agrupadas nessa solução que podem aumentar sua pontuação.

Há duas maneiras de tomar medidas nesta tela:

1. Na linha da solução pretendida, na coluna **Ações** Restantes, selecione o número hiperlinkado. Você verá uma exibição filtrada da tela ações de melhoria mostrando ações de melhoria não testadas para essa solução.

2. Na linha da solução pretendido, na coluna **Abrir solução,** selecione **Abrir**. Você verá a solução ou o local nos centros de Microsoft 365 e Office 365 segurança e conformidade onde você pode tomar a ação recomendada.

## <a name="assessments-page"></a>Página Avaliações

A página avaliações lista todas as [avaliações](compliance-manager-assessments.md) configuradas para sua organização. Seu denominador de pontuação de conformidade é determinado por todas as avaliações controladas. À medida que você adiciona mais avaliações, você verá mais ações de melhoria listadas na página ações de melhoria e seu denominador de pontuação de conformidade aumenta.

O **contador de modelos ativados** próximo à parte superior da página mostra o número de modelos de avaliação ativos em uso no momento, fora do número total de modelos disponíveis para sua organização usar. Consulte [Disponibilidade e licenciamento do modelo](compliance-manager-templates.md#template-availability-and-licensing) para obter mais informações.

A página avaliações resume as principais informações sobre cada avaliação:

- **Avaliação**: nome da avaliação
- **Status**:
    - **Concluído** - todos os controles têm um status de "passado", ou pelo menos um é passado e o restante está "fora do escopo"
    - **Incompleto** – pelo menos um controle tem um status de "falha"
    - **Nenhum** - todos os controles não foram testados
    - **Em andamento** - as ações de melhoria têm qualquer outro status, incluindo "em andamento", "crédito parcial" ou "não detectado"
- **Progresso da** avaliação : a porcentagem do trabalho realizado para a conclusão, conforme medido pelo número de controles testados com êxito
- **Suas ações de aperfeiçoamento**: o número de ações concluídas para atender à implementação de seus controles
- **Ações da Microsoft**: o número de ações concluídas para atender à implementação de controles da Microsoft
- **Grupo**: nome do grupo ao que a avaliação pertence
- **Produto**: serviço Microsoft 365 associado
- **Regulamentação**: o padrão regulamentar, a política ou a lei que se aplica à avaliação

### <a name="filtering-your-assessments-view"></a>Filtrando o seu exibição de avaliações

Para filtrar a exibição de avaliações:

1. Selecione **Filtrar** no canto superior esquerdo da lista de avaliações.
2. No painel **de sobrevoos Filtros,** verifique os critérios desejados.
3. Selecione o **botão Aplicar.** O painel de filtro será fechado e você verá o seu exibição filtrado.

Você também pode modificar sua exibição para ver avaliações por grupo, produto  ou regulamentação selecionando o tipo de grupo no menu suspenso Grupo acima da lista de avaliações.

### <a name="default-assessment"></a>Avaliação padrão

Por padrão, você verá a avaliação da Linha de Base de [Proteção](compliance-manager-assessments.md#data-protection-baseline-default-assessment) de Dados na página avaliações. O Gerenciador de Conformidade também fornece vários modelos [pré-construídos](compliance-manager-templates-list.md) para avaliações de construção.

## <a name="assessment-templates-page"></a>Página de modelos de avaliação

Um modelo é uma estrutura para criar uma avaliação no Gerenciador de Conformidade. A página de modelos de avaliação exibe uma lista de modelos e detalhes importantes. A lista inclui modelos fornecidos pelo Gerenciador de Conformidade, bem como todos os modelos que sua organização modificou ou criou. Você pode aplicar filtros para encontrar um modelo com base na certificação, escopo do produto, país, setor e quem o criou.

O **contador de modelos ativados** próximo à parte superior da página mostra o número de modelos de avaliação ativos em uso no momento, fora do número total de modelos disponíveis para sua organização usar. Consulte [Disponibilidade e licenciamento do modelo](compliance-manager-templates.md#template-availability-and-licensing) para obter mais informações.

Selecione um modelo em sua linha para trazer sua página de detalhes, que contém uma descrição do modelo e mais informações sobre os detalhes de certificação, escopo e controles. Nesta página, você pode selecionar os botões apropriados para criar uma avaliação, exportar os dados do modelo para Excel ou modificar o modelo.

**Saiba mais: Leia** [como trabalhar com modelos de avaliação.](compliance-manager-templates.md)

## <a name="next-step"></a>Próxima etapa
Personalize o Gerenciador de Conformidade [configurando avaliações](compliance-manager-assessments.md).
