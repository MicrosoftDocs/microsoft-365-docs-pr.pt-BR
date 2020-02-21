---
title: Introdução ao gerenciamento de riscos do insider
description: Configure o gerenciamento de risco do insider em sua organização.
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
ms.openlocfilehash: 4b8bd0f8d540434410d9ebc2365789a669f455e1
ms.sourcegitcommit: 87cc278ea2ddcd536ecfaa3dfae9a5ddaa502cf9
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42179162"
---
# <a name="get-started-with-insider-risk-management"></a>Introdução ao gerenciamento de riscos do insider

Use políticas de gerenciamento de risco do insider para identificar atividades arriscadas e ferramentas de gerenciamento para executar ações nos alertas de risco em sua organização. Conclua as etapas a seguir para configurar os pré-requisitos e configurar uma política de gerenciamento de risco do insider.

>[!IMPORTANT]
>A solução Microsoft 365 Insider Risk Management oferece uma opção de nível de locatário para ajudar os clientes a facilitar a governança interna no nível do usuário. Os administradores de nível de locatário podem configurar permissões para fornecer acesso a essa solução para os membros da sua organização e configurar os conectores de dados no centro de conformidade da Microsoft 365 para importar dados relevantes para dar suporte à identificação de nível de usuário potencialmente atividade arriscada. Os clientes reconhecem as ideias relacionadas ao comportamento, ao caractere ou ao desempenho do usuário individual relacionado ao emprego que pode ser calculado pelo administrador e disponibilizado para outras pessoas na organização.

Para obter mais informações sobre como as políticas de risco do insider podem ajudá-lo a gerenciar riscos em sua organização, consulte [Insider Risk Management in Microsoft 365](insider-risk-management.md).

## <a name="before-you-begin"></a>Antes de começar

Antes de começar a usar o gerenciamento de risco do Insider, você deve confirmar sua [assinatura do Microsoft 365](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans). Para acessar e usar o gerenciamento de risco do Insider, sua organização deve ter uma das seguintes assinaturas:

- Assinatura do Microsoft 365 E5 (versão paga ou de avaliação)
- Assinatura do Microsoft 365 Enterprise E3 com o [complemento de conformidade da Microsoft E5](https://signup.microsoft.com/signup/?offerid=57806d24-4357-4eff-b0a3-4054ebdf2abe&DL=INFORMATION_PROTECTION_COMPLIANCE&ali=1)

Os usuários incluídos nas políticas de gerenciamento de risco do insider devem ter uma licença de conformidade do Microsoft 365 E5 ou incluídas em uma assinatura do Microsoft 365 e5.

Se você não tiver um plano existente do Microsoft 365 Enterprise E5 e quiser experimentar o gerenciamento de risco do Insider, você pode [Adicionar o microsoft 365](https://docs.microsoft.com/office365/admin/try-or-buy-microsoft-365) à sua assinatura existente do Office 365 ou [inscrever-se para uma avaliação](https://www.microsoft.com/microsoft-365/enterprise) do Microsoft 365 Enterprise e5.

## <a name="step-1-required-enable-permissions-for-insider-risk-management"></a>Etapa 1 (obrigatório): Habilitar permissões para o gerenciamento de risco do insider

Há quatro grupos de funções usados para configurar permissões para gerenciar recursos de gerenciamento de risco do insider. Para continuar com essas etapas de configuração, os administradores de locatários devem primeiro atribuí-lo ao grupo de função **Gerenciamento de riscos Insider** ou **administrador de gerenciamento de risco do insider** . Para acessar e gerenciar recursos de gerenciamento de risco do insider após a configuração inicial, os usuários devem ser um membro de pelo menos um grupo de funções de gerenciamento de risco do insider.

Dependendo da estrutura da sua equipe de gerenciamento de conformidade, você tem opções para atribuir usuários a grupos de função específicos para gerenciar diferentes conjuntos de recursos de gerenciamento de risco do insider. Escolha uma destas opções de grupo de funções ao configurar o gerenciamento de risco do insider:

| **Default management role assignments for this role** | **Permissões de função** |
| :---- | :---------------- |
| **Gerenciamento de risco do insider** | Use esse grupo de funções para gerenciar o gerenciamento de riscos do insider para sua organização em um único grupo. Ao adicionar todas as contas de usuário para administradores, analistas e investigadores designados, você pode configurar permissões de gerenciamento de risco do insider em um único grupo. Esse grupo de função contém todas as funções de permissão de gerenciamento de risco do insider. Essa é a maneira mais fácil de começar rapidamente com o gerenciamento de risco do insider e é uma boa opção para organizações que não precisam de permissões separadas definidas para grupos de usuários separados.|
| **Administrador de gerenciamento de risco do insider** | Use esse grupo de funções para configurar inicialmente o gerenciamento de riscos de insider e depois para separar os administradores de risco internos em um grupo definido.  Os usuários desse grupo de funções podem criar, ler, atualizar e excluir políticas de gerenciamento de risco do Insider, configurações globais e atribuições de grupos de função. |
| **Analistas de gerenciamento de risco do insider** | Use esse grupo para atribuir permissões a usuários que atuarão como analistas de caso de risco do insider. Os usuários desse grupo de funções podem acessar todos os modelos de alerta, casos e avisos de gerenciamento de risco do insider. Eles não podem acessar o Gerenciador de conteúdo de risco do insider. |
| **Investigadores de gerenciamento de risco do insider** | Use esse grupo para atribuir permissões a usuários que atuarão como investigadores de dados de risco do insider. Os usuários desse grupo de funções podem acessar todos os alertas de gerenciamento de risco do Insider, casos, modelos de avisos e o Gerenciador de conteúdo para todos os casos. |

### <a name="add-users-to-an-insider-risk-management-role-group"></a>Adicionar usuários a um grupo de funções de gerenciamento de risco do insider

Conclua as seguintes etapas para adicionar usuários a um grupo de funções de gerenciamento de risco do insider.

1. Entre [https://protection.office.com/permissions](https://protection.office.com/permissions) usando as credenciais de uma conta de administrador na sua organização do Microsoft 365.

2. No centro de segurança e conformidade do Microsoft Office 365, acesse **permissões**. Selecione o link para exibir e gerenciar funções no Office 365.

3. Selecione o grupo de funções de gerenciamento de risco do insider ao qual você deseja adicionar usuários e, em seguida, selecione **Editar grupo de função**.

4. Selecione **escolher Membros** no painel de navegação esquerdo e, em seguida, selecione **Editar**.

5. Selecione **Adicionar** e marque a caixa de seleção de todos os usuários que você deseja adicionar ao grupo de funções.

6. Selecione **Adicionar**e, em seguida, selecione **concluído**.

7. Selecione **salvar** para adicionar os usuários ao grupo de funções. Selecione **fechar** para concluir as etapas.

## <a name="step-2-required-enable-the-office-365-audit-log"></a>Etapa 2 (obrigatório): habilitar o log de auditoria do Office 365

O gerenciamento de risco do insider usa logs de auditoria para insights e atividades de usuários configurados em políticas. Os logs de auditoria são um resumo de todas as atividades associadas a uma política de gerenciamento de risco do insider ou a qualquer momento em que uma política é alterada.

Para obter instruções passo a passo para ativar a auditoria, consulte [Ativar ou desativar a pesquisa de log de auditoria do Office 365](turn-audit-log-search-on-or-off.md). Depois que você ativar a auditoria, será exibida uma mensagem dizendo que o log de auditoria está sendo preparado e que você pode executar uma pesquisa em algumas horas após a conclusão da preparação. Você só precisa executar esta ação uma vez. Para obter mais informações sobre o uso do log de auditoria, consulte [Search the Audit Log](search-the-audit-log-in-security-and-compliance.md).

## <a name="step-3-optional-configure-prerequisites-for-templates"></a>Etapa 3 (opcional): configurar pré-requisitos para modelos

Alguns modelos de gerenciamento de risco do insider têm pré-requisitos que devem ser configurados para indicadores de política para gerar alertas de atividade relevantes. Configure os pré-requisitos apropriados dependendo das políticas que você planeja configurar para sua organização.

### <a name="configure-microsoft-365-hr-connector"></a>Configurar o conector de RH da Microsoft 365

O gerenciamento de risco do insider oferece suporte à importação de dados de log e de usuário importados de plataformas de gerenciamento e recursos humanos de terceiros. O conector de dados Human Resources (RH) da Microsoft 365 permite que você receba dados de recursos humanos de arquivos CSV, incluindo encerramento do usuário e datas do último emprego. Esses dados ajudam a direcionar os indicadores de alerta nas políticas de gerenciamento de risco do insider e é uma parte importante da configuração da cobertura de gerenciamento de risco completo em sua organização.

Consulte o tópico [configurar um conector para importar dados de RH](import-hr-data.md) para obter orientações passo a passo para configurar o Microsoft 365 HR Connector para sua organização. Depois de configurar o conector de RH, retorne a estas etapas de configuração.

>[!IMPORTANT]
>Se você configurar uma política usando o modelo de *roubo de dados do funcionário de canpartes* , será necessário configurar o conector de RH para usar os recursos de detecção de sinal completo do modelo de política. Se você configurar mais de um conector de RH para sua organização, o gerenciamento de riscos do insider receberá os indicadores automaticamente de todos os conectores de RH.

### <a name="configure-data-loss-prevention-dlp-policies"></a>Configurar políticas de DLP (prevenção contra perda de dados)

O gerenciamento de riscos do insider suporta o uso de políticas DLP para ajudar a identificar a exposição intencional ou acidental de informações confidenciais a partes indesejadas. Ao configurar uma política de gerenciamento de risco do insider com o modelo de *vazamento de dados* , você precisa atribuir uma política de DLP específica à política. Esta política ajuda a direcionar os indicadores de alerta para informações confidenciais é uma parte importante da configuração da cobertura de gerenciamento de risco completo em sua organização.

Consulte o tópico [criar, testar e ajustar uma política de DLP](create-test-tune-dlp-policy.md) para obter orientações passo a passo para configurar as políticas de DLP para sua organização. Após configurar uma política de DLP, retorne a estas etapas de configuração.

>[!IMPORTANT]
>Se você configurar uma política usando o modelo de *vazamento de dados* , será necessário configurar pelo menos uma política de DLP para usar os recursos de detecção de sinal completo do modelo de política. Se você configurar mais de uma política de DLP para sua organização, será necessário atribuir uma política de gerenciamento de risco Insider por política DLP.

## <a name="step-4-required-configure-insider-risk-settings"></a>Etapa 4 (obrigatório): definir configurações de risco do insider

[As configurações de risco do insider](insider-risk-management-policies.md#policy-settings) são aplicadas a todas as políticas de gerenciamento de risco do Insider, independentemente do modelo que você escolheu ao criar uma política. As configurações são definidas usando o controle de **configurações de risco do insider** localizado na parte superior de todas as guias de gerenciamento de risco do insider Essas configurações controlam a privacidade, indicadores, monitoramento de janelas e detecções inteligentes.

Antes de configurar uma política, defina as seguintes configurações de risco do insider:

1. No [centro de conformidade da Microsoft 365](https://compliance.microsoft.com), vá para gerenciamento de **risco do insider** e selecione **configurações de risco do insider** no canto superior direito de qualquer página.
2. Na página **privacidade** , selecione uma configuração de privacidade para exibir os nomes de um dos alertas de política.
3. Na página **indicadores** , selecione os indicadores de alerta que você deseja aplicar a todas as políticas de risco do insider.

    >[!IMPORTANT]
    >Para receber alertas para atividades arriscadas definidas em suas políticas, você deve selecionar um ou mais indicadores.

4. Na página **políticas de tempo de política** , selecione os [prazos de política](insider-risk-management-policies.md#policy-timeframes) para entrar em vigor para um usuário quando ele disparar uma correspondência para uma política de risco de insider.
5. Na página **detecções inteligentes** , configure as detecções de [idiomas de anomalias e ofensivas](insider-risk-management-policies.md#intelligent-detections) para políticas de risco do insider.
6. Selecione **salvar** para habilitar essas configurações para suas políticas de risco do insider.

## <a name="step-5-required-create-an-insider-risk-management-policy"></a>Etapa 5 (obrigatório): criar uma política de gerenciamento de risco do insider

As políticas de gerenciamento de risco do insider incluem usuários atribuídos e definem quais tipos de indicadores de risco estão configurados para alertas. Antes que as atividades possam disparar alertas, uma política deve ser configurada.

1. No [centro de conformidade da Microsoft 365](https://compliance.microsoft.com), vá para gerenciamento de **risco do insider** e selecione a guia **políticas** .
2. Selecione **criar política** para abrir o assistente de política
3. Na página **nova política de riscos de insider** , preencha os seguintes campos:
    - **Nome (obrigatório)**: Insira um nome amigável para a política.
    - **Descrição (opcional)**: Insira uma descrição para a política.
    - **Escolher modelo de política (obrigatório)**: selecione um dos [modelos de política](insider-risk-management-policies.md#policy-templates) para definir os tipos de indicadores de risco são monitorados pela política.

    >[!IMPORTANT]
    >Se você selecionar o modelo *vazamentos de dados* , precisará configurar pelo menos uma política DLP que será atribuída posteriormente no assistente. Se você selecionar o modelo de *roubo de dados do funcionário de parte* , precisará configurar o conector de RH para usar os recursos de detecção de sinal completo do modelo de política.

4. Selecione **Avançar** para continuar.
5. Na página **usuários** , selecione **Adicionar usuário ou grupo** para definir quais usuários estão incluídos nas caixas de seleção política ou **todos os usuários e grupos habilitados para email** . Selecione **Avançar** para continuar.
6. Na página **especificar qual conteúdo priorizar (opcional)** , você pode atribuir as fontes para priorizar as atividades de usuário arriscadas:
    - **Sites do SharePoint**: selecione **Adicionar site do SharePoint** e selecione as organizações do SharePoint que você deseja priorizar. Por exemplo, *"group1@contoso.sharepoint.com/sites/group1"*.
    - **Tipo de informação confidencial**: selecione **Adicionar tipo de informações confidenciais** e selecione os tipos de sensibilidade que você deseja priorizar. Por exemplo, *"número de conta bancária dos EUA"* e *"número do cartão de crédito"*.
    - **Rótulos de sensibilidade**: selecione **Adicionar rótulo de confidencialidade** e selecione os rótulos que você deseja priorizar. Por exemplo, *"confidencial"* e *"segredo"*.
7. Selecione **Avançar** para continuar.
8. Na página **indicadores de alerta** , você verá os indicadores definidos na página de > **indicadores** de **configurações de risco do insider**. Se você selecionou o modelo *vazamentos de dados* no início do assistente, deverá selecionar uma política de DLP na lista suspensa **política de DLP** .
9. Na página **selecionar janela de monitoramento** , você verá as [condições da janela de monitoramento](insider-risk-management-policies.md#policy-timeframes) da política que na página períodos de tempo da**política** de configurações > de **risco do insider**. Se você tiver selecionado o modelo de política de *roubo de dados do funcionário* de cancelamento de parte, poderá marcar a caixa de seleção *verificar término da postagem de atividade* para detectar a atividade após a data de término importada do conector de RH da Microsoft 365.
10. Selecione **Avançar** para continuar.
11. Na página **revisão** , revise as configurações escolhidas para a política. Selecione **Editar** para alterar qualquer um dos valores da política ou selecione **Enviar** para criar e ativar a política.

Após concluir essas etapas para criar sua primeira política de gerenciamento de risco do Insider, você começará a receber alertas de indicadores de atividade após cerca de 24 horas. Configure as políticas adicionais conforme necessário usando as orientações da etapa 4 deste tópico ou as etapas em [criar uma nova política de risco de insider](insider-risk-management-policies.md#create-a-new-policy).
