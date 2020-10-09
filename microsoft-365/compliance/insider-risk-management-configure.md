---
title: Introdução ao gerenciamento de riscos internos
description: Configure o gerenciamento de risco do insider em sua organização.
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
ms.collection:
- m365-security-compliance
- m365solution-insiderrisk
- m365initiative-compliance
ms.openlocfilehash: 707f2b260ff9d4a452cdb65d75a1a8fe6a13af3f
ms.sourcegitcommit: cd17328baa58448214487e3e68c37590ab9fd08d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/09/2020
ms.locfileid: "48399166"
---
# <a name="get-started-with-insider-risk-management"></a>Introdução ao gerenciamento de riscos internos

Use políticas de gerenciamento de risco do insider para identificar atividades arriscadas e ferramentas de gerenciamento para atuar nos alertas de risco em sua organização. Conclua as etapas a seguir para configurar os pré-requisitos e configurar uma política de gerenciamento de risco do insider.

>[!IMPORTANT]
>A solução Microsoft 365 Insider Risk Management oferece uma opção de nível de locatário para ajudar os clientes a facilitar a governança interna no nível do usuário. Os administradores de nível de locatário podem configurar permissões para fornecer acesso a essa solução para os membros da sua organização e configurar os conectores de dados no centro de conformidade da Microsoft 365 para importar dados relevantes para dar suporte à identificação de nível de usuário de atividades potencialmente arriscadas. Os clientes reconhecem as ideias relacionadas ao comportamento, ao caractere ou ao desempenho do usuário individual relacionado ao emprego que pode ser calculado pelo administrador e disponibilizado para outras pessoas na organização.

Para obter mais informações sobre como as políticas de risco do insider podem ajudá-lo a gerenciar riscos em sua organização, consulte [Insider Risk Management in Microsoft 365](insider-risk-management.md).

## <a name="before-you-begin"></a>Antes de começar

Antes de começar a usar o gerenciamento de risco do Insider, você deve confirmar sua [assinatura do Microsoft 365](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans) e outros Complementos. Para acessar e usar o gerenciamento de risco do Insider, sua organização deve ter uma das seguintes assinaturas ou Complementos:

- Assinatura do Microsoft 365 E5 (versão paga ou de avaliação)
- Assinatura do Microsoft 365 E3 + o complemento de conformidade do Microsoft 365 e5
- Assinatura do Microsoft 365 E3 + o complemento de gerenciamento de risco do Microsoft 365 E5 Insider
- Assinatura do Microsoft 365 a5 (versão paga ou de avaliação)
- Assinatura do 365 a3 + o complemento de conformidade do Microsoft 365 a5
- Assinatura do 365 a3 + o complemento de gerenciamento de risco Microsoft 365 a5 Insider

Os usuários incluídos nas políticas de gerenciamento de risco do insider devem receber uma das licenças acima.

Se você não tiver um plano existente do Microsoft 365 Enterprise E5 e quiser experimentar o gerenciamento de risco do Insider, você pode [Adicionar o microsoft 365](https://docs.microsoft.com/office365/admin/try-or-buy-microsoft-365) à sua assinatura existente ou [inscrever-se em uma avaliação](https://www.microsoft.com/microsoft-365/enterprise) do Microsoft 365 Enterprise e5.

## <a name="step-1-enable-permissions-for-insider-risk-management"></a>Etapa 1: Habilitar permissões para o gerenciamento de risco do insider

>[!Important]
>Após configurar seus grupos de função, pode levar até 30 minutos para que as permissões de grupo de função sejam aplicadas a usuários atribuídos em toda a organização.

Há quatro grupos de funções usados para configurar permissões para gerenciar recursos de gerenciamento de risco do insider. Para continuar com essas etapas de configuração, os administradores de locatários devem primeiro atribuí-lo ao grupo de função **Gerenciamento de riscos Insider** ou **administrador de gerenciamento de risco do insider** . Para acessar e gerenciar recursos de gerenciamento de risco do insider após a configuração inicial, os usuários devem ser um membro de pelo menos um grupo de funções de gerenciamento de risco do insider.

Dependendo da estrutura da sua equipe de gerenciamento de conformidade, você tem opções para atribuir usuários a grupos de função específicos para gerenciar diferentes conjuntos de recursos de gerenciamento de risco do insider. Escolha uma destas opções de grupo de funções ao configurar o gerenciamento de risco do insider:

| **Default management role assignments for this role** | **Permissões de função** |
| :---- | :---------------- |
| **Gerenciamento de risco do insider** | Use esse grupo de funções para gerenciar o gerenciamento de riscos do insider para sua organização em um único grupo. Ao adicionar todas as contas de usuário para administradores, analistas e investigadores designados, você pode configurar permissões de gerenciamento de risco do insider em um único grupo. Esse grupo de função contém todas as funções de permissão de gerenciamento de risco do insider. Essa configuração é a maneira mais fácil de começar rapidamente com o gerenciamento de risco do insider e é uma boa opção para organizações que não precisam de permissões separadas definidas para grupos de usuários separados.|
| **Administrador de gerenciamento de risco do insider** | Use esse grupo de funções para configurar inicialmente o gerenciamento de riscos de insider e depois para separar os administradores de risco internos em um grupo definido.  Os usuários desse grupo de funções podem criar, ler, atualizar e excluir políticas de gerenciamento de risco do Insider, configurações globais e atribuições de grupos de função. |
| **Analistas de gerenciamento de risco do insider** | Use esse grupo para atribuir permissões a usuários que atuarão como analistas de caso de risco do insider. Os usuários desse grupo de funções podem acessar todos os modelos de alerta, casos e avisos de gerenciamento de risco do insider. Eles não podem acessar o Gerenciador de conteúdo de risco do insider. |
| **Investigadores de gerenciamento de risco do insider** | Use esse grupo para atribuir permissões a usuários que atuarão como investigadores de dados de risco do insider. Os usuários desse grupo de funções podem acessar todos os alertas de gerenciamento de risco do Insider, ocorrências, modelos de avisos e o Gerenciador de conteúdo. |

> [!NOTE]
> Atualmente, esses grupos de função não têm suporte no gerenciamento de identidade privilegiada (PIM). Para saber mais sobre o PIM, confira [atribuir funções do Azure AD no gerenciamento de identidade privilegiado](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-how-to-add-role-to-user).

### <a name="add-users-to-an-insider-risk-management-role-group"></a>Adicionar usuários a um grupo de funções de gerenciamento de risco do insider

Conclua as seguintes etapas para adicionar usuários a um grupo de funções de gerenciamento de risco do insider.

1. Entre [https://protection.office.com/permissions](https://protection.office.com/permissions) usando as credenciais de uma conta de administrador na sua organização do Microsoft 365.

2. No centro de &amp; conformidade de segurança, acesse **permissões**. Selecione o link para exibir e gerenciar funções no Office 365.

3. Selecione o grupo de funções de gerenciamento de risco do insider ao qual você deseja adicionar usuários e, em seguida, selecione **Editar grupo de função**.

4. Selecione **escolher Membros** no painel de navegação esquerdo e, em seguida, selecione **Editar**.

5. Selecione **Adicionar** e marque a caixa de seleção de todos os usuários que você deseja adicionar ao grupo de funções.

6. Selecione **Adicionar**e, em seguida, selecione **concluído**.

7. Selecione **salvar** para adicionar os usuários ao grupo de funções. Selecione **fechar** para concluir as etapas.

## <a name="step-2-enable-the-audit-log"></a>Etapa 2: habilitar o log de auditoria

O gerenciamento de risco do insider usa logs de auditoria para insights e atividades de usuários configurados em políticas. Os logs de auditoria são um resumo de todas as atividades associadas a uma política de gerenciamento de risco do insider ou a qualquer momento em que uma política é alterada.

Para obter instruções passo a passo para ativar a auditoria, consulte [Ativar ou desativar a pesquisa de log de auditoria](turn-audit-log-search-on-or-off.md). Depois que você ativar a auditoria, será exibida uma mensagem dizendo que o log de auditoria está sendo preparado e que você pode executar uma pesquisa em algumas horas após a conclusão da preparação. Você só precisa executar esta ação uma vez. Para obter mais informações sobre o uso do log de auditoria, consulte [Search the Audit Log](search-the-audit-log-in-security-and-compliance.md).

## <a name="step-3-configure-prerequisites-for-templates"></a>Etapa 3: configurar pré-requisitos para modelos

A maioria dos modelos de gerenciamento de risco do insider tem pré-requisitos que devem ser configurados para indicadores de política para gerar alertas de atividade relevantes. Configure os pré-requisitos apropriados dependendo das políticas que você planeja configurar para sua organização.

Se você estiver configurando uma política usando o *idioma ofensivo no modelo de política de email* , você pode ignorar esta etapa e ir diretamente para a **etapa 4**.

### <a name="configure-microsoft-365-hr-connector"></a>Configurar o conector de RH da Microsoft 365

O gerenciamento de risco do insider oferece suporte à importação de dados de log e de usuário importados de plataformas de gerenciamento e recursos humanos de terceiros. O conector de dados Human Resources (RH) da Microsoft 365 permite que você receba dados de recursos humanos de arquivos CSV, incluindo datas de término do usuário, datas do plano de melhoria do desempenho, ações de análise de desempenho e status de alteração no nível do trabalho. Esses dados ajudam a direcionar os indicadores de alerta nas políticas de gerenciamento de risco do insider e é uma parte importante da configuração da cobertura de gerenciamento de risco completo em sua organização. Se você configurar mais de um conector de RH para sua organização, o gerenciamento de riscos do insider receberá os indicadores automaticamente de todos os conectores de RH.

O conector de RH da Microsoft 365 é necessário ao usar os seguintes modelos de política:

- Parte do roubo de dados do usuário
- Violações de política de segurança por parte dos usuários
- Violações de política de segurança por usuários descontentes
- Vazamentos de dados por usuários descontentes

Consulte o artigo [configurar um conector para importar dados de RH](import-hr-data.md) para obter orientações passo a passo para configurar o Microsoft 365 HR Connector para sua organização. Depois de configurar o conector de RH, retorne a estas etapas de configuração.

### <a name="configure-data-loss-prevention-dlp-policies"></a>Configurar políticas de DLP (prevenção contra perda de dados)

O gerenciamento de riscos do insider suporta o uso de políticas de DLP para ajudar a identificar a exposição intencional ou acidental de informações confidenciais a partes indesejadas para alertas DLP de nível de alta severidade. Ao configurar uma política de gerenciamento de risco do insider com qualquer um dos modelos de **vazamento de dados** , você deve atribuir uma política de DLP específica à política.

As políticas de DLP ajudam a identificar os usuários a ativar a pontuação de riscos no gerenciamento de risco do insider para alertas de DLP de alta gravidade para informações confidenciais e são uma parte importante da configuração da cobertura de gerenciamento de risco completo em sua organização. Para obter mais informações sobre o gerenciamento de risco do insider e as considerações de planejamento e integração de políticas de DLP, consulte [Insider Management Policies](insider-risk-management-policies.md#general-data-leaks)

>[!IMPORTANT]
>Verifique se você concluiu o seguinte:
>
>- Você entende e configurou corretamente os usuários no escopo nas políticas de gerenciamento de risco do DLP e do insider para produzir a cobertura de política que você espera.
>- Certifique-se de que a configuração **relatórios de incidentes** na política de DLP para gerenciamento de risco do insider usada com esses modelos esteja configurada para alertas de nível de severidade *alto* . Os alertas de gerenciamento de risco do insider não serão gerados de políticas DLP com o conjunto de campos **relatórios de incidentes** em *baixo* ou *médio*.

Uma política de DLP é necessária ao usar os seguintes modelos de política:

- Vazamentos de dados gerais
- Vazamentos de dados por usuários de prioridade

Consulte o artigo [criar, testar e ajustar uma política de DLP](create-test-tune-dlp-policy.md) para obter orientações passo a passo para configurar as políticas de DLP para sua organização. Após configurar uma política de DLP, retorne a estas etapas de configuração.

### <a name="configure-priority-user-groups"></a>Configurar grupos de usuários de prioridade

O gerenciamento de riscos do insider inclui suporte para a atribuição de grupos de usuários de prioridade a políticas para ajudar a identificar as atividades de risco exclusivas para o usuário com posições críticas, altos níveis de acesso de dados e de rede ou um histórico passado do comportamento de risco. A criação de um grupo de usuários de prioridade e a atribuição de usuários às políticas de escopo de ajuda do grupo para as circunstâncias exclusivas apresentadas por esses usuários.

Um grupo de usuários de prioridade é necessário ao usar os seguintes modelos de política:

- Violações de política de segurança por usuários de prioridade
- Vazamentos de dados por usuários de prioridade

Consulte o artigo [Guia de introdução às configurações de gerenciamento de risco do insider](insider-risk-management-settings.md#priority-user-groups-preview) para obter orientações passo a passo para criar um grupo de usuários de prioridade. Depois de configurar um grupo de usuários de prioridade, retorne a estas etapas de configuração.

### <a name="configure-physical-badging-connector-optional"></a>Configurar o conector de símbolos físico (opcional)

O gerenciamento de risco do insider oferece suporte à importação de dados de log e de usuário importados de plataformas de acesso físico O conector símbolos físico permite que você extraia dados do Access de arquivos JSON, incluindo IDs de usuário, IDs de ponto de acesso, tempo de acesso e datas e status de acesso. Esses dados ajudam a direcionar os indicadores de alerta nas políticas de gerenciamento de risco do insider e é uma parte importante da configuração da cobertura de gerenciamento de risco completo em sua organização. Se você configurar mais de um conector de símbolos físico para sua organização, o gerenciamento de riscos do insider automaticamente extrairá os indicadores de todos os conectores físicos do símbolos. As informações do conector símbolos físico complementam outros sinais de risco internos ao usar todos os modelos de política de riscos Insider.

>[!IMPORTANT]
>Para políticas de gerenciamento de risco do insider para usar e correlacionar dados de sinal relacionados a cancelamento e usuários demitidos com dados de evento de suas plataformas de controle e de acesso físico, você também deve configurar o Microsoft 365 HR Connector. Se você habilitar o conector símbolos físico sem habilitar o conector de RH da Microsoft 365, as políticas de gerenciamento de risco do insider só processarão eventos para acesso físico não autorizado aos usuários em sua organização.

Consulte o artigo [configurar um conector para importar dados do símbolos físico](import-physical-badging-data.md) para obter orientações passo a passo para configurar o conector símbolos físico para sua organização. Depois de configurar o conector, retorne para estas etapas de configuração.

## <a name="step-4-configure-insider-risk-settings"></a>Etapa 4: definir configurações de risco do insider

[As configurações de risco do insider](insider-risk-management-settings.md) são aplicadas a todas as políticas de gerenciamento de risco do Insider, independentemente do modelo que você escolheu ao criar uma política. As configurações são definidas usando o controle de **configurações de risco do insider** localizado na parte superior de todas as guias de gerenciamento de risco do insider Essas configurações controlam a privacidade, indicadores, monitoramento de janelas e detecções inteligentes.

Antes de configurar uma política, defina as seguintes configurações de risco do insider:

1. No [centro de conformidade da Microsoft 365](https://compliance.microsoft.com), vá para gerenciamento de **risco do insider** e selecione **configurações de risco do insider** no canto superior direito de qualquer página.
2. Na página **privacidade** , selecione uma configuração de privacidade para exibir os nomes de um dos alertas de política.
3. Na página **indicadores** , selecione os indicadores de alerta que você deseja aplicar a todas as políticas de risco do insider.

    >[!IMPORTANT]
    >Para receber alertas para atividades arriscadas definidas em suas políticas, você deve selecionar um ou mais indicadores.

4. Na página **políticas de tempo de política** , selecione os [prazos de política](insider-risk-management-settings.md#policy-timeframes) para entrar em vigor para um usuário quando ele disparar uma correspondência para uma política de risco de insider.
5. Na página **detecções inteligentes** , defina as seguintes configurações para políticas de risco do insider:
    - [Detecções de anomalias](insider-risk-management-settings.md#anomaly-detections)
    - [Detecções de idiomas ofensivos](insider-risk-management-settings.md#offensive-language-detections)
    - [Nível do alerta de volume](insider-risk-management-settings.md#alert-volume)
    - [Status de alerta de proteção avançada contra ameaças do Microsoft 365 defender](insider-risk-management-settings.md#microsoft-defender-advanced-threat-protection-preview)
    - [Configurações de domínio](insider-risk-management-settings.md#domains-preview)
6. Na página **Exportar alertas** , habilite a exportação de informações de alerta de risco do insider usando as APIs de gerenciamento do Office 365, se necessário.
7. Na página **grupos de usuários de prioridade** , crie um grupo de usuários de prioridade e adicione usuários se não criados na **etapa 3**.
8. Na página **fluxos** automáticos de energia, configure um fluxo de modelos de fluxo de risco do insider ou crie um novo fluxo. Consulte o artigo [Guia de introdução às configurações de gerenciamento de risco do insider](insider-risk-management-settings.md#power-automate-flows-preview) para obter orientações passo a passo.
9. Na **página de ativos de prioridade**, configure os ativos de prioridade para usar os dados do controle físico e da plataforma de acesso importados pelo conector símbolos físico. Consulte o artigo [Guia de introdução às configurações de gerenciamento de risco do insider](insider-risk-management-settings.md#priority-physical-assets-preview) para obter orientações passo a passo.
10. Na página **Microsoft Teams** , habilite a integração do Microsoft Teams com o gerenciamento de risco do insider para criar automaticamente uma equipe para colaboração de casos ou usuários. Consulte o artigo [Guia de introdução às configurações de gerenciamento de risco do insider](insider-risk-management-settings.md#microsoft-teams-preview) para obter orientações passo a passo.
11. Selecione **salvar** para habilitar essas configurações para suas políticas de risco do insider.

## <a name="step-5-create-an-insider-risk-management-policy"></a>Etapa 5: criar uma política de gerenciamento de risco do insider

As políticas de gerenciamento de risco do insider incluem usuários atribuídos e definem quais tipos de indicadores de risco estão configurados para alertas. Antes que as atividades possam disparar alertas, uma política deve ser configurada.

1. No [centro de conformidade da Microsoft 365](https://compliance.microsoft.com), vá para gerenciamento de **risco do insider** e selecione a guia **políticas** .
2. Selecione **criar política** para abrir o assistente de política.
3. Na página **nova política de riscos de insider** , preencha os seguintes campos:
    - **Nome (obrigatório)**: Insira um nome amigável para a política.
    - **Descrição (opcional)**: Insira uma descrição para a política.
    - **Escolher modelo de política (obrigatório)**: selecione um dos [modelos de política](insider-risk-management-policies.md#policy-templates) para definir os tipos de indicadores de risco são monitorados pela política.

    >[!IMPORTANT]
    >A maioria dos modelos de política tem pré-requisitos que devem ser configurados para que a política Gere alertas relevantes. Se você não tiver configurado os pré-requisitos de política aplicáveis, consulte a **etapa 3** acima.

    >[!CAUTION]
    >A partir de 16 de outubro de 2020, você não poderá mais criar políticas usando o idioma ofensivo no modelo de email. As políticas ativas que usam esse modelo funcionarão até que sejam permanentemente removidas em janeiro de 2021.

4. Selecione **Avançar** para continuar.
5. Na página **usuários** , selecione **Adicionar usuário ou grupo** ou **escolha prioridade grupos de usuários** para definir quais usuários ou grupos de usuários de prioridade estão incluídos na política, dependendo do modelo de política que você selecionou. Marque a caixa **de seleção todos os usuários e grupos habilitados para email,** se aplicável (se você não tiver selecionado um modelo com prioridade de usuário). Selecione **Avançar** para continuar.
6. Na página **especificar qual conteúdo priorizar (opcional)** , você pode atribuir as fontes a serem priorizadas para maiores pontuações de risco. No entanto, algumas atividades não gerarão nenhum alerta, a menos que o conteúdo relacionado contenha tipos de informações confidenciais internas ou personalizadas ou tenha sido especificado como uma prioridade nesta página:
    - **Sites do SharePoint**: selecione **Adicionar site do SharePoint** e selecione as organizações do SharePoint que você deseja priorizar. Por exemplo, *"group1@contoso.sharepoint.com/sites/group1"*.
    - **Tipo de informação confidencial**: selecione **Adicionar tipo de informações confidenciais** e selecione os tipos de sensibilidade que você deseja priorizar. Por exemplo, *"número de conta bancária dos EUA"* e *"número do cartão de crédito"*.
    - **Rótulos de sensibilidade**: selecione **Adicionar rótulo de confidencialidade** e selecione os rótulos que você deseja priorizar. Por exemplo, *"confidencial"* e *"segredo"*.
7. Selecione **Avançar** para continuar.
8. Na página **selecionar indicadores de política** , você verá os [indicadores](insider-risk-management-settings.md#indicators) definidos como disponíveis na página indicadores de configurações de **risco do insider**  >  **Indicators** . Se você selecionou um modelo de *vazamentos de dados* no início do assistente, deverá selecionar uma política de DLP na lista suspensa **política de DLP** para habilitar os indicadores de disparo para a política. Selecione os indicadores que você deseja aplicar à política. Se preferir não usar as configurações de limite de política padrão para esses indicadores, desabilite o **uso de limiares padrão recomendados pela Microsoft** e insira os valores de limite para cada indicador selecionado. Se você tiver selecionado pelo menos um indicador do *Office* ou *dispositivo* , selecione os **aceleradores de Pontuação de risco** conforme apropriado. Os aumentos de Pontuação de risco só se aplicam aos indicadores selecionados.

    >[!IMPORTANT]
    >Se os indicadores nesta página não puderem ser selecionados, você precisará selecionar os indicadores que deseja habilitar para todas as políticas na página de indicadores de política de configurações de **Gerenciamento de risco do insider**  >  **Settings**  >  **Policy indicators** .

9. Selecione **Avançar** para continuar.
10. Na página **políticas de tempo de política** , você verá as [condições da janela de ativação](insider-risk-management-settings.md#policy-timeframes) para a política que na página períodos de tempo da política de configurações de risco do **Insider**  >  **Policy timeframes** .
11. Selecione **Avançar** para continuar.
12. Na página **revisão** , revise as configurações escolhidas para a política. Selecione **Editar** para alterar qualquer um dos valores da política ou selecione **Enviar** para criar e ativar a política.

## <a name="next-steps"></a>Próximas etapas

Após concluir essas etapas para criar sua primeira política de gerenciamento de risco do Insider, você começará a receber alertas de indicadores de atividade após cerca de 24 horas. Configure as políticas adicionais conforme necessário usando as orientações da etapa 4 deste artigo ou as etapas em [criar uma nova política de risco de insider](insider-risk-management-policies.md#create-a-new-policy).

Para saber mais sobre como investigar alertas de risco do insider e o **painel alertas**, confira [alertas de gerenciamento de risco do insider](insider-risk-management-alerts.md).
