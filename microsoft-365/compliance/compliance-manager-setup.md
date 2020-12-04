---
title: Introdução ao Gerenciador de conformidade da Microsoft
f1.keywords:
- NOCSH
ms.author: chvukosw
author: chvukosw
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
description: Defina as permissões e funções de usuário do Microsoft Compliance Manager e configure o teste automatizado de ações. Gerenciar histórico de usuários e filtrar o modo de exibição do painel.
ms.openlocfilehash: 9a09e12457d39e2f4aab99d3bec68b77c1a3a975
ms.sourcegitcommit: d81c7cea85af6ad5fef81d3c930514a51464368c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/04/2020
ms.locfileid: "49572390"
---
# <a name="get-started-with-compliance-manager"></a>Introdução ao Gerenciador de Conformidade

**Neste artigo:** Este artigo ajuda você a configurar o Gerenciador de conformidade. Saiba como **acessar** o Gerenciador de conformidade, **definir funções e permissões** e configurar **testes automáticos de ações de melhoria**. Mostre o **painel do Gerenciador de conformidade** e entenda as páginas principais: a página ações de melhoria, a página soluções, a página avaliações e a página modelos de avaliação.

## <a name="who-can-access-compliance-manager"></a>Quem pode acessar o gerente de conformidade

O Gerenciador de conformidade está disponível para organizações com o Office 365 e as licenças do Microsoft 365, e para os clientes da nuvem da Comunidade do governo dos EUA (GCC) moderado e GCC alto. A disponibilidade de avaliação e os recursos de gerenciamento dependem do contrato de licenciamento.  [Exibir detalhes da descrição do serviço](https://go.microsoft.com/fwlink/?linkid=2132371).

## <a name="before-you-begin"></a>Antes de começar

O administrador global do Microsoft 365 da sua organização provavelmente será o primeiro usuário a acessar o Gerenciador de conformidade. Recomendamos a entrada de administrador global e defina as permissões do usuário, conforme descrito abaixo, ao visitar o gerente de conformidade pela primeira vez.

## <a name="sign-in"></a>Entrar

1. Vá para o [centro de conformidade da microsoft 365](https://compliance.microsoft.com/) e **entre** com sua conta de administrador global do Microsoft 365.
2. Selecione **Gerenciador de conformidade** no painel de navegação à esquerda. Você chegará ao [painel do Gerenciador de conformidade](#understand-the-compliance-manager-dashboard).

O link direto para o Gerenciador de conformidade do Access é [https://compliance.microsoft.com/compliancemanager](https://compliance.microsoft.com/compliancemanager) .

## <a name="set-user-permissions-and-assign-roles"></a>Definir permissões de usuário e atribuir funções

O Gerenciador de conformidade usa um modelo de permissão RBAC (controle de acesso baseado em função). Somente os usuários atribuídos a uma função podem acessar o Gerenciador de conformidade e as ações permitidas por cada usuário são restringidas por [tipo de função](#role-types).

### <a name="where-to-set-permissions"></a>Onde definir permissões

A pessoa que detém a função de administrador global para sua organização pode definir permissões de usuário no centro de conformidade da Microsoft 365, bem como no Azure Active Directory (Azure AD).

> [!NOTE]
> Os clientes na Comunidade governamental americana (GCC) ambientes altos só podem definir permissões e funções de usuário para o Gerenciador de conformidade no Azure AD. Veja abaixo as instruções do Azure AD e as definições de tipo de função.

Para definir permissões e atribuir funções de dentro do centro de conformidade da Microsoft 365, siga as etapas abaixo:

1. Selecione **permissões** na navegação à esquerda de qualquer lugar no [centro de conformidade do Microsoft 365](https://compliance.microsoft.com/).

2. Próximo à parte superior, selecione o link em **"para exibir e gerenciar funções no Office 365, acesse aqui".** Uma nova guia será aberta para o centro de conformidade & segurança do Office 365 ([saiba por que você é redirecionado](microsoft-365-compliance-center.md#frequently-asked-questions)).

3. Localize o grupo de funções ao qual você deseja adicionar um ou mais usuários e marque a caixa à esquerda do nome do grupo. (Confira a [lista de funções e funções relacionadas abaixo](#role-types). Os nomes dos grupos de função imitam o nome da função.)

4. No painel do submenu desse grupo, selecione **Editar** no cabeçalho **Membros** .

5. Selecione **escolher Membros**. Será exibida outra janela de submenu.

6. Selecione **+ Adicionar** para escolher um ou mais usuários para adicionar ao grupo.

7. Marque a caixa de seleção ao lado dos nomes que você deseja adicionar e, em seguida, selecione o botão **Adicionar** na parte inferior.

8. Quando você terminar de atribuir usuários, selecione **concluído**, selecione **salvar** e **Fechar**.

##### <a name="more-about-the-office-365-security--compliance-center"></a>Saiba mais sobre o centro de conformidade & segurança do Office 365

Saiba mais sobre [permissões no centro de conformidade & segurança do Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center).

Se você não tiver acesso ao centro de segurança e conformidade do Office 365, ou se precisar acessar a versão clássica do Gerenciador de conformidade no portal de confiança do serviço Microsoft, as configurações de administrador no portal de confiança do serviço fornecem outra maneira de atribuir funções ([instruções de exibição](meet-data-protection-and-regulatory-reqs-using-microsoft-cloud.md#assigning-compliance-manager-roles-to-users)). Lembre-se de que essas funções são mais limitadas em sua funcionalidade.

##### <a name="more-about-azure-ad"></a>Mais sobre o Azure AD

Para atribuir funções e definir permissões no Azure AD, confira [atribuir funções de administrador e não-administrador aos usuários com o Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal).

Os usuários com identidades do Azure AD que não têm o Office 365 ou assinaturas do Microsoft 365 não poderão acessar o Gerenciador de conformidade no centro de conformidade do Microsoft 365. Para buscar assistência no acesso ao Gerenciador de conformidade, entre em contato com a [cmresearch@microsoft.com](mailto:cmresearch@microsoft.com).

### <a name="role-types"></a>Tipos de função

A tabela abaixo mostra as funções permitidas por cada função no Gerenciador de conformidade. A tabela também mostra como cada [função do Azure ad](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) é mapeada para as funções do Gerenciador de conformidade. Os usuários precisarão pelo menos da função leitor do Gerenciador de conformidade ou da função leitor global do Azure AD para acessar o Gerenciador de conformidade.


| O usuário pode: | Função de gerente de conformidade | Função do Azure AD | 
| :------------- | :-------------: | :------------: |
| **Ler mas não editar dados**| Leitor do Gerenciador de Conformidade  | Leitor global do Azure AD, leitor de segurança | 
| **Editar dados**| Contribuição do gerente de conformidade | Administrador de Conformidade | 
| **Editar resultados de teste**| Avaliação do Gerenciador de conformidade | Administrador de Conformidade | 
| **Gerenciar avaliações e dados de modelo e locatário**| Administração do Gerenciador de conformidade | Administrador de conformidade, administrador de dados de conformidade, administrador de segurança  | 
| **Atribuir usuários**| Administrador Global | Administrador Global | 

## <a name="settings-for-automated-testing-and-user-history"></a>Configurações para teste automatizado e histórico de usuários

As configurações do Gerenciador de conformidade no centro de conformidade da Microsoft 365 permitem habilitar e desabilitar o teste automático das ações de melhoria. As configurações também permitem que você gerencie os dados dos usuários associados às ações de melhoria, incluindo a capacidade de reatribuir ações de aperfeiçoamento a um usuário diferente.  Somente as pessoas com um administrador global ou função de administrador do gerente de conformidade podem acessar as configurações do Gerenciador de conformidade.

> [!NOTE]
> O recurso de teste automatizado não está disponível para clientes em ambientes GCC elevados porque a pontuação segura não está disponível nesses ambientes. Os clientes com GCC altos precisarão implementar e testar manualmente suas ações de melhoria.

### <a name="set-up-automated-testing"></a>Configurar testes automatizados

Algumas ações de melhoria no Gerenciador de conformidade também são monitoradas pela [Pontuação segura da Microsoft](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-secure-score). Você pode configurar o teste automatizado de ações que são monitoradas em conjunto, o que significa que quando uma ação é testada e atualizada na pontuação segura, esses resultados são sincronizados com as mesmas ações no gerente de conformidade e contam em direção à sua pontuação de conformidade.

O teste automático é ativado por padrão para organizações novas no Gerenciador de conformidade. Ao implantar pela primeira vez o Microsoft 365 ou o Office 365, são necessários aproximadamente sete dias para que a pontuação segura colete dados completamente e o fatora em sua pontuação de conformidade.  Quando o teste automatizado estiver ativado, a data de teste da ação não será atualizada, mas seu status de teste será atualizado. Quando novas avaliações são criadas, as pontuações incluem automaticamente as pontuações de controle da Microsoft e a integração de Pontuação segura.

O administrador global da sua organização pode alterar as configurações para testes automatizados a qualquer momento. Você pode desativar o teste automatizado para ações de melhoria comuns ou ativá-la para ações individuais. Siga as instruções abaixo para alterar as configurações de teste automatizado.

#### <a name="to-manage-your-automated-testing-settings"></a>Para gerenciar as configurações de teste automatizado:

1. Selecione **configurações** na navegação à esquerda de qualquer lugar no [centro de conformidade do Microsoft 365](https://compliance.microsoft.com/).

2. Na página configurações, selecione **Gerenciador de conformidade**.

3. Selecione **teste automatizado** na navegação à esquerda.

4. Selecione o botão aplicável para ativar o teste automático para todas as ações de aprimoramento, desative-a para todas as ações ou ative por ação individual.

5. Se você selecionar **Ativar por ação de aprimoramento**, uma lista mostrará todas as ações de aprimoramento disponíveis para escolher.  Marque a caixa ao lado de qualquer ação que você deseja testar automaticamente.

6. Selecione **salvar** para salvar suas configurações. Você receberá uma mensagem de confirmação na parte superior da tela que a seleção foi salva. Se você receber um aviso de falha, tente novamente.

**Observação:** Somente o administrador global pode ativar ou desativar as atualizações automáticas para todas as ações. O administrador do Gerenciador de conformidade pode ativar atualizações automáticas para ações individuais, mas não para todas as ações globalmente.

### <a name="manage-user-history"></a>Gerenciar histórico de usuário

As configurações de **histórico de gerenciamento de usuário** ajudam a identificar rapidamente quais usuários trabalharam com ações de melhoria no Gerenciador de conformidade. Os dados de usuário identificáveis associados às ações de melhoria incluem qualquer trabalho de implementação e teste realizado, documentos que foram carregados e todas as anotações inseridas. A compreensão e a recuperação desse tipo de dados podem ser necessárias para as necessidades de conformidade da sua organização.

As configurações de histórico do usuário também permitem reatribuir todas as ações de aperfeiçoamento de um usuário para outro.

**Para localizar as configurações de histórico do usuário:**

1. Selecione configurações na navegação à esquerda de qualquer lugar no [centro de conformidade do Microsoft 365](https://compliance.microsoft.com/).

2. Na página configurações, selecione **Gerenciador de conformidade**.

3. Selecione **gerenciar histórico de usuários** na navegação à esquerda.

A página **gerenciar histórico de usuários** mostra uma lista de todos os usuários por endereço de email que são atribuídos a uma ação de melhoria. Use o botão **Pesquisar** para localizar rapidamente um usuário específico digitando seu endereço de email.

À direita do endereço de email de cada usuário, o menu suspenso **selecionar** fornece opções para exportar um relatório, reatribuir ações de aperfeiçoamento ou excluir o histórico. Veja cada seção abaixo para obter detalhes sobre cada opção.

#### <a name="export-a-report-of-user-history-data"></a>Exportar um relatório de dados de histórico do usuário

Você pode exportar um arquivo do Excel que contém uma lista de ações de aperfeiçoamento atribuídas a um usuário no momento.  O relatório também lista qualquer arquivo de evidência carregado por esse usuário. Essas informações podem ajudá-lo a reatribuir ações de melhorias abertas.

O relatório reflete o status da ação de melhoria em sua data de criação. Não é um relatório histórico de todas as alterações anteriores ao seu status ou atribuição (saiba como [exportar um relatório da página ações de aprimoramento](compliance-manager-improvement-actions.md#export-a-report)).

**Siga as etapas abaixo para exportar um relatório por usuário:**

1. Selecione **configurações** na navegação à esquerda de qualquer lugar no [centro de conformidade do Microsoft 365](https://compliance.microsoft.com/).

2. Na página configurações, selecione **Gerenciador de conformidade**.

3. Selecione **gerenciar histórico de usuários** na navegação à esquerda.

4. Encontre o usuário pretendido pesquisando os endereços de email da lista ou selecionando **Pesquisar** e inserindo o endereço de email do usuário.

5. No menu suspenso **selecionar** , escolha **Exportar relatório**.

6. Depois que o arquivo do Excel do seu relatório for gerado, você poderá abri-lo e salvá-lo em sua máquina local.

#### <a name="reassign-improvement-actions-to-another-user"></a>Reatribuir ações de aprimoramento a outro usuário

Você pode reatribuir ações de melhoria de um usuário para outro. Quando você reatribui uma ação, o histórico de carregamento do documento não muda, mas o nome do usuário que carregou originalmente a documentação não aparece mais na ação de aprimoramento.

**Siga as etapas abaixo para reatribuir ações de aperfeiçoamento a outro usuário:**

1. Selecione **configurações** na navegação à esquerda de qualquer lugar no [centro de conformidade do Microsoft 365](https://compliance.microsoft.com/).

2. Na página configurações, selecione **Gerenciador de conformidade**.

3. Selecione **gerenciar histórico de usuários** na navegação à esquerda.

4. Encontre um usuário pesquisando os endereços de email da lista ou selecionando **Pesquisar** e inserindo o endereço de email desse usuário.

5. No menu suspenso **selecionar** , escolha **reatribuir ações de aperfeiçoamento**. O painel de submenu **ações de aprimoramento de reatribuição** será exibido.

6. No campo **Pesquisar usuários** , digite o nome ou o endereço de email do usuário *para* o qual você deseja atribuir as ações de aprimoramento.

7. Quando você vir o nome do usuário pretendido em **que as ações de aperfeiçoamento serão atribuídas**, selecione o usuário e, em seguida, selecione **atribuir ações**.

8. Quando a reatribuição estiver concluída, você verá uma mensagem de confirmação no painel de submenus confirmando que todas as ações de aprimoramento do usuário anterior foram reatribuídas ao novo usuário. Se você receber um aviso de falha de reatribuição, feche a janela e tente novamente. Para fechar o painel de submenu, selecione **concluído**.

O novo destinatário recebe um email que foi atribuído a uma ação de melhoria. O email contém um link direto para a página de detalhes da ação de aprimoramento.
 
 > [!NOTE]
> Se você reatribuir uma ação que tenha uma atualização pendente, o link direto para a ação no email de reatribuição será interrompido se a atualização for aceita após a reatribuição. Você pode corrigir isso reatribuindo novamente a ação ao usuário depois que a atualização for aceita. Saiba mais sobre [atualizações para ações de melhoria](compliance-manager-improvement-actions.md#accepting-updates-to-improvement-actions).

#### <a name="delete-user-history"></a>Excluir Histórico de usuário

Excluir o histórico de um usuário os removerá como proprietário de ações de melhoria e removerá o nome deles de todos os outros campos no Gerenciador de conformidade. Quando você exclui o histórico de um usuário, as ações de melhoria que pertencem a ele não exibirão um valor **atribuído a** até que um novo usuário seja atribuído. Qualquer documento carregado na ação de melhoria mostrará o **usuário removido** no lugar do nome do usuário excluído. Excluir o histórico de usuários é permanente.

Para excluir o histórico de um usuário, siga as etapas abaixo:

1. Selecione **configurações** na navegação à esquerda de qualquer lugar no [centro de conformidade do Microsoft 365](https://compliance.microsoft.com/).

2. Na página configurações, selecione **Gerenciador de conformidade**.

3. Selecione **gerenciar histórico de usuários** na navegação à esquerda.

4. Encontre um usuário pesquisando os endereços de email da lista ou selecionando **Pesquisar** e inserindo o endereço de email desse usuário.

5. No menu suspenso **selecionar** , escolha **Excluir Histórico**.

6. Uma janela é exibida solicitando que você confirme a exclusão permanente do histórico do usuário. Para continuar com a exclusão, selecione **Excluir Histórico**. Para sair sem excluir o histórico, selecione **Cancelar**.

7. Você chegará à página **gerenciar histórico de usuários** com uma mensagem de confirmação na parte superior de que o histórico do usuário foi excluído.

## <a name="understand-the-compliance-manager-dashboard"></a>Entender o painel do Gerenciador de conformidade

O painel do Gerenciador de conformidade foi projetado para fornecer uma visão geral da postura de conformidade atual.

![Gerenciador de conformidade-painel](../media/compliance-manager-dashboard.png "Painel do Gerenciador de conformidade")

### <a name="overall-compliance-score"></a>Pontuação de conformidade geral

A pontuação de conformidade é apresentada em destaque na parte superior. Ele mostra uma porcentagem com base nos pontos obtidos para a conclusão de ações de melhoria que tratam das normas e dos padrões principais de proteção de dados. Pontos de [ações da Microsoft](compliance-manager-assessments.md#microsoft-actions-tab), que são gerenciados pela Microsoft, também contam para sua pontuação de conformidade.

Quando você chegar ao gerente de conformidade pela primeira vez, sua pontuação inicial se baseará na [linha de base de proteção de dados 365 da Microsoft](compliance-manager-assessments.md#data-protection-baseline-default-assessment). Essa avaliação da linha de base, que está disponível para todas as organizações, é um conjunto de controles que inclui normas e padrões comuns do setor. O Gerenciador de conformidade verifica suas soluções existentes da Microsoft 365 e oferece uma avaliação inicial com base em suas configurações atuais de privacidade e segurança. À medida que você adiciona avaliações que são relevantes para sua organização, sua pontuação se torna mais significativa para você.

**Saiba mais:** [entenda como a pontuação de conformidade é calculada](compliance-score-calculation.md).

### <a name="key-improvement-actions"></a>Ações de melhoria de chave

Esta seção lista as principais ações de aprimoramento que você pode tomar agora para fazer o maior impacto positivo em sua pontuação geral de conformidade. Selecione **Exibir todas as ações de aperfeiçoamento** para ir para a página ações de aprimoramento.

### <a name="solutions-that-affect-your-score"></a>Soluções que afetam sua pontuação

Esta seção realça soluções com ações de melhoria que podem afetar positivamente sua pontuação e o número de ações de melhorias pendentes nessas soluções. Selecione **Exibir todas as soluções** para visitar a página soluções.

### <a name="compliance-score-breakdown"></a>Divisão de Pontuação de conformidade

Esta seção oferece uma visão mais detalhada da sua pontuação de duas maneiras diferentes:

- **Categories**: mostra a porcentagem de sua pontuação geral nas categorias de proteção de dados, como "proteger informações" ou "gerenciar dispositivos".
- **Avaliações**: mostra a porcentagem do seu progresso no gerenciamento de Avaliações para padrões específicos de conformidade e proteção de dados, normas ou leis, como RGPD ou NIST 800-53.

### <a name="filtering-your-dashboard-view"></a>Filtrando o modo de exibição do painel

Você pode filtrar o modo de exibição do painel para ver apenas os itens relacionados a normas e padrões específicos, soluções, tipo de ação, grupos de avaliação ou categorias de proteção de dados. Filtrar o modo de exibição dessa forma também filtrará a pontuação no painel, mostrando quantos pontos você alcançou do total de pontos possíveis com base nos critérios de filtro.

Para aplicar filtros:

1. Selecione **filtro** no lado superior direito do painel.
2. Selecione seus critérios de filtro no painel de submenu **filtros** e selecione **aplicar**.

Depois de aplicar um filtro, você verá sua pontuação ajustada em tempo real. A porcentagem de Pontuação de conformidade e as informações de divisão, e as ações e soluções de melhoria, agora pertencem apenas aos dados cobertos por seus critérios de filtro. Se você sair do Gerenciador de conformidade, sua exibição filtrada permanecerá quando você entrar novamente.

Para remover filtros:

- No cabeçalho **filtros aplicados** acima da Pontuação de conformidade, selecione o **X** ao lado do filtro individual que você deseja remover; ou
- Selecione **filtro** no lado superior direito do painel e, em seguida, no painel de submenu **filtros** , selecione **limpar filtros**.

## <a name="improvement-actions-page"></a>Página ações de melhoria

[Ações de melhoria](compliance-manager-improvement-actions.md) são ações gerenciadas pela sua organização. Trabalhar com ações de melhoria ajuda a centralizar as atividades de conformidade e a se alinhar às normas e aos padrões de proteção de dados. Cada ação de melhoria fornece orientações detalhadas de implementação e um link para iniciar você na solução apropriada. Ações de melhoria podem ser atribuídas aos usuários em sua organização para executar o trabalho de implementação e teste. Você também pode armazenar documentação, anotações e registrar as atualizações de status na ação de melhoria.

### <a name="view-your-improvement-actions"></a>Exibir suas ações de aperfeiçoamento

O painel do Gerenciador de conformidade mostra as **principais ações de aprimoramento.** Para exibir todas as ações de aperfeiçoamento, selecione a guia ações de aperfeiçoamento no painel, que traz para a página ações de aprimoramento. Você também pode selecionar Exibir todas as ações de aperfeiçoamento abaixo da lista de ações de aprimoramento de chave no painel para acessar a página ações de aprimoramento.

A página ações de melhoria mostra todas as ações de aperfeiçoamento gerenciadas por sua organização. As ações que são gerenciadas pela Microsoft podem ser exibidas em cada avaliação (Saiba mais sobre as [ações da Microsoft](compliance-manager-assessments.md#microsoft-actions-tab)).

Se você tiver uma longa lista de ações na página ações de aprimoramento, talvez seja útil filtrar o modo de exibição. Selecione **filtro** no canto superior direito da lista ações. Quando o painel de submenu **filtros** for exibido, selecione seus critérios com base em regulamentos e padrões, solução e grupo. Você também pode personalizar o modo de exibição selecionando **Agrupar** no canto superior direito. No menu suspenso, selecione para exibir por grupo, solução, categoria, tipo de ação ou status.

O modo de exibição padrão para esta página não mostra ações de aperfeiçoamento com um status de teste de **aprovado**. Para exibir ações que passaram no teste, marque a caixa **aprovado** no painel de submenu filtros. Somente as ações com um status de teste de contagem **passada** em relação à sua pontuação. Algumas ações podem mostrar um **rótulo de atualização pendente.** Saiba mais sobre [atualizações para ações de melhoria](compliance-manager-improvement-actions.md#accepting-updates-to-improvement-actions).

A página ações de melhoria mostra os seguintes pontos de dados para cada ação de melhoria:

- **Pontos obtidos**: o número de pontos alcançados do total disponível por meio da conclusão da ação
- **Regulamentos**: as regulamentações ou padrões referentes à ação
- **Grupo**: o grupo ao qual você atribuiu a ação
- **Soluções**: a solução onde você pode ir para executar a ação
- **Avaliações**: as avaliações que contêm a ação
- **Categorias**: a categoria de proteção de dados relacionada (como proteger informações, gerenciar dispositivos etc.)
- **Status do teste**:
    - **Nenhum** – nenhuma atualização de status registrada
    - **Não avaliado** -o teste não foi iniciado
    - **Aprovado** -implementação testada com êxito
    - Falha nos testes de **baixo risco** , baixo risco
    - Falha no teste de **risco médio** , risco médio
    - **Falha no alto risco** -falha no teste, alto risco
    - **Fora do escopo** – a ação não está no escopo da avaliação e não afeta sua pontuação
    - **Para ser detectado** -para teste manual, indica que uma ação foi implementada, mas não testada; para teste automatizado, indica que uma ação está aguardando o resultado da automação
    - **Não foi possível detectar** -o status automatizado não pode ser determinado
    - **Parcialmente testado** – Pontuação automatizada que premia pontos parciais

**Saiba mais:** [Confira como atribuir e executar trabalho em ações de melhoria](compliance-manager-improvement-actions.md).

## <a name="solutions-page"></a>Página de soluções

A página soluções mostra o compartilhamento de pontos ganhos e potenciais como organizados por solução. Exibir os pontos e as ações de melhoria restantes desse modo de exibição ajuda a entender quais soluções precisam de mais atenção imediata.

Encontre a página soluções selecionando a guia **soluções** no painel do Gerenciador de conformidade. Você também pode selecionar **Exibir todas as soluções** sob **soluções que afetam sua pontuação** na seção superior direita do seu painel.

### <a name="filtering-your-solutions-view"></a>Filtrando o modo de exibição de soluções

Para filtrar a exibição das soluções:

1. Selecione **filtro** no canto superior esquerdo da sua lista de avaliações.
2. No painel de submenu **filtros** , coloque uma marca ao lado dos critérios desejados (padrões e regulamentos, solução, tipo de ação, grupo Gerenciador de conformidade, categoria).
3. Selecione o botão **aplicar** . O painel de filtro será fechado e você verá o modo de exibição filtrado.

Você também pode modificar o modo de exibição para ver avaliações por grupo, produto ou regulamentação selecionando o tipo de agrupamento no menu suspenso de **grupo** acima da sua lista de avaliações.

### <a name="taking-action-from-the-solution-page"></a>Executar a ação da página solução

A página soluções exibe as soluções da sua organização que estão conectadas às ações de melhoria. A tabela lista a contribuição de cada solução para sua pontuação geral, os pontos obtidos e possíveis dentro dessa solução, e o número restante de ações de aprimoramento agrupadas nessa solução que podem aumentar sua pontuação.

Há duas maneiras de executar uma ação nesta tela:

1. Na linha da sua solução pretendida, na coluna **ações restantes** , selecione o número de hiperlink. Você verá um modo de exibição filtrado da tela ações de melhoria mostrando ações de aperfeiçoamento não testadas para essa solução.

2. Na linha da sua solução pretendida, na coluna **Abrir solução** , selecione **abrir**. Você verá a solução ou o local nos centros de segurança e conformidade do Microsoft 365 e do Office 365, onde você pode executar a ação recomendada.

## <a name="assessments-page"></a>Página de avaliações

A página avaliações lista todas as [avaliações](compliance-manager-assessments.md) configuradas para sua organização. O denominador de Pontuação de conformidade é determinado por todas as avaliações rastreadas. Ao adicionar mais avaliações, você verá mais ações de aperfeiçoamento listadas na página de ações de melhoria e o denominador de Pontuação de conformidade aumenta.

A página avaliações resume as principais informações sobre cada avaliação:

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
3. Selecione o botão **aplicar** . O painel de filtro será fechado e você verá o modo de exibição filtrado.

Você também pode modificar o modo de exibição para ver avaliações por grupo, produto ou regulamentação selecionando o tipo de agrupamento no menu suspenso de **grupo** acima da sua lista de avaliações.

### <a name="default-assessment"></a>Avaliação padrão

Por padrão, você verá a avaliação da [linha de base de proteção de dados](compliance-manager-assessments.md#data-protection-baseline-default-assessment) na página avaliações. O Gerenciador de conformidade também fornece vários [modelos](compliance-manager-templates-list.md) pré-criados para a criação de avaliações.

## <a name="assessment-templates-page"></a>Página de modelos de avaliação

Um modelo é uma estrutura para criar uma avaliação no Gerenciador de conformidade. A página modelos de avaliação exibe uma lista de modelos e detalhes principais. A lista inclui modelos fornecidos pelo gerente de conformidade, bem como quaisquer modelos modificados ou criados por sua organização. Você pode aplicar filtros para localizar um modelo com base em certificação, escopo do produto, país, setor e quem o criou.

Selecione um modelo de sua linha para exibir sua página de detalhes, que contém uma descrição do modelo e mais informações sobre a certificação, o escopo e os detalhes dos controles. Nessa página, você pode selecionar os botões apropriados para criar uma avaliação, exportar os dados do modelo para o Excel ou modificar o modelo.

**Saiba mais:** [Leia como trabalhar com modelos de avaliação](compliance-manager-templates.md).

## <a name="next-step"></a>Próxima etapa
Personalizar o Gerenciador de conformidade [Configurando avaliações](compliance-manager-assessments.md).
