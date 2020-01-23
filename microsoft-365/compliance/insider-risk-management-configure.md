---
title: Introdução ao gerenciamento de risco do Insider (visualização)
description: Configure o gerenciamento de risco do insider em sua organização.
keywords: Microsoft 365, gerenciamento de risco do Insider, gerenciamento de riscos, conformidade
localization_priority: Normal
ms.prod: Microsoft-365-enterprise
ms.topic: article
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: m365-security-compliance
ms.openlocfilehash: 5d32e28d53fccbb16d935bbd9348ad7c12bac365
ms.sourcegitcommit: 3dca80f268006658a0b721aa4f6df1224c7964dc
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/22/2020
ms.locfileid: "41259839"
---
# <a name="get-started-with-insider-risk-management-preview"></a>Introdução ao gerenciamento de risco do Insider (visualização)

Use políticas de gerenciamento de risco do insider para identificar atividades arriscadas e ferramentas de gerenciamento para executar ações nos alertas de risco em sua organização. Para obter mais informações sobre como as políticas de risco do insider podem ajudá-lo a gerenciar riscos em sua organização, consulte [Insider Risk Management in Microsoft 365](insider-risk-management.md).

>[!IMPORTANT]
>A solução Microsoft 365 Insider Risk Management oferece uma opção de nível de locatário para ajudar os clientes a facilitar a governança interna no nível do usuário. Os administradores de nível de locatário podem configurar permissões para fornecer acesso a essa solução para os membros da sua organização e configurar os conectores de dados no centro de conformidade da Microsoft 365 para importar dados relevantes para dar suporte à identificação de nível de usuário potencialmente atividade arriscada. Os clientes reconhecem as ideias relacionadas ao comportamento, ao caractere ou ao desempenho do usuário individual relacionado ao emprego que pode ser calculado pelo administrador e disponibilizado para outras pessoas na organização.

## <a name="before-you-begin"></a>Antes de começar

Antes de começar a usar o gerenciamento de risco do Insider, você deve confirmar sua assinatura do Microsoft 365. Os usuários incluídos nas políticas de gerenciamento de risco do insider devem ter uma licença de conformidade do Microsoft 365 E5 ou incluídas em uma assinatura do Microsoft 365 e5.

Se você não tiver um plano existente do Microsoft 365 Enterprise E5 e quiser experimentar o gerenciamento de risco do Insider, você pode [Adicionar o microsoft 365](https://docs.microsoft.com/office365/admin/try-or-buy-microsoft-365) à sua assinatura existente do Office 365 ou [inscrever-se para uma avaliação](https://www.microsoft.com/microsoft-365/enterprise) do Microsoft 365 Enterprise e5.

Conclua estas etapas para configurar e usar o gerenciamento de risco do insider na sua organização do Microsoft 365:

## <a name="step-1-required-enable-permissions-for-insider-risk-management"></a>Etapa 1 (obrigatório): Habilitar permissões para o gerenciamento de risco do insider

Há quatro funções de permissão usadas para configurar e gerenciar o gerenciamento de risco do insider. Para continuar com essas etapas de configuração, os administradores de locatários devem primeiro atribuir a função de **administrador de gerenciamento de risco do insider** .

| **Função** | **Permissões de função** |
| ---- | ---------------- |
| **Administrador de gerenciamento de risco do insider** | Criar, ler, atualizar e excluir políticas de gerenciamento de risco do insider <br> Criar, ler, atualizar e excluir permissões e funções de gerenciamento de risco do insider |
| **Analistas de gerenciamento de risco do insider** | Acesso a todos os alertas, casos e avisos de gerenciamento de risco do insider |
| **Investigadores de gerenciamento de risco do insider** | Acesso a todos os alertas de gerenciamento de risco do Insider, casos, avisos e o Gerenciador de conteúdo para todos os casos |
| **Visualizador de gerenciamento de risco do insider** | Acesso somente de exibição a todos os alertas de gerenciamento de risco do Insider, casos, avisos e o Gerenciador de conteúdo para todos os casos |

Dependendo da estrutura da sua equipe de gerenciamento de conformidade, você tem duas opções de permissão para configurar funções para gerenciar recursos de gerenciamento de risco do insider. Escolha uma destas opções de gerenciamento de função ao configurar o gerenciamento de risco do insider:

1. **Use o grupo de função de gerenciamento de risco do insider padrão**: Use esse grupo de funções para gerenciar o gerenciamento de riscos do insider para sua organização adicionando todas as contas de usuário para administradores, analistas e investigadores designados em um único grupo. Esse grupo de função contém todas as funções de permissão de gerenciamento de risco do insider. Essa é a maneira mais fácil de começar rapidamente com o gerenciamento de risco do insider e é uma boa opção para organizações que não precisam de permissões separadas definidas para grupos de usuários separados.
2. **Criar grupos diferentes para funções de gerenciamento diferentes**: para organizações que precisam separar permissões para configurar e gerenciar o gerenciamento de risco do Insider, você precisará criar novos grupos de função e atribuir funções e usuários apropriados aos novos grupos. Por exemplo, se você quiser diferentes permissões para análise e investigação de gerenciamento de risco do Insider, precisará criar um grupo para analistas e um grupo separado para investigadores. Para cada grupo, você atribuirá as funções necessárias para essas responsabilidades e, em seguida, adicionará os usuários que devem ser atribuídos ao grupo.

Se você decidir configurar grupos diferentes para diferentes funções, use a tabela a seguir para atribuir as funções necessárias a cada grupo de função:

| **Exemplo de grupo** | **Funções necessárias** |
| ---- | ---------------- |
| **Administradores** | Função de *administrador de gerenciamento de risco do insider* |
| **Analistas** | Função de *analista de gerenciamento de risco do insider* <br> Função de *Gerenciamento de casos* |
| **Investigadores** | Função de *investigadores de gerenciamento de risco do insider* <br> Função de *Gerenciamento de casos* |

### <a name="option-1-add-users-to-the-insider-risk-management-role-group"></a>Opção 1: adicionar usuários ao grupo de funções de gerenciamento de risco do insider

Se você quiser usar um grupo de função para todos os usuários Configurando e gerenciando o gerenciamento de risco do Insider, conclua as seguintes etapas para adicionar usuários ao grupo de funções padrão de **Gerenciamento de risco do insider** :

1. Entre [https://protection.office.com/permissions](https://protection.office.com/permissions) usando as credenciais de uma conta de administrador na sua organização do Microsoft 365.

2. No centro de segurança e conformidade do Microsoft Office 365, acesse **permissões**. Selecione o link para exibir e gerenciar funções no Office 365.

3. Selecione o grupo de função de *Gerenciamento de risco do insider* e selecione **Editar grupo de função**.

4. Selecione **escolher Membros** no painel de navegação esquerdo e, em seguida, selecione **Editar**.

5. Selecione **Adicionar** e marque a caixa de seleção de todos os usuários que você deseja adicionar ao grupo de funções.

6. Selecione **Adicionar**e, em seguida, selecione **concluído**.

7. Selecione **salvar** para adicionar os usuários ao grupo de funções. Selecione **fechar** para concluir as etapas.

### <a name="option-2-create-a-new-role-group"></a>Opção 2: criar um novo grupo de função

Se você precisar criar grupos de função separados para diferentes funções de gerenciamento, conclua as etapas a seguir para criar cada novo grupo:

1. Entre [https://protection.office.com/permissions](https://protection.office.com/permissions) usando as credenciais de uma conta de administrador na sua organização do Microsoft 365.

2. No centro de segurança e conformidade do Microsoft Office 365, acesse **permissões**. Selecione o link para exibir e gerenciar funções no Office 365.

3. Selecione **Criar**.

4. No campo **nome** , dê um nome amigável ao novo grupo de funções. Selecione **Avançar**.

5. Selecione **escolher funções** e, em seguida, selecione **Adicionar**. Marque a caixa de seleção das funções que você precisa atribuir. Por exemplo, se esse grupo for analistas de riscos de insider, selecione a função de *analista de gerenciamento de risco do insider* e a função de *Gerenciamento de casos* e, em seguida, selecione **Adicionar** e **concluir**. Selecione **Avançar**.

6. Selecione **escolher Membros** e selecione **Adicionar**. Marque a caixa de seleção de todos os usuários e grupos que você deseja criar políticas e gerenciar mensagens com correspondências de política e, em seguida, selecione **Adicionar** e **concluir**. Selecione **Avançar**.

7. Selecione **Criar grupo de função** para concluir.

Para obter mais informações sobre grupos de funções e permissões, consulte [permissões no centro de conformidade](../security/office-365-security/protect-against-threats.md).

## <a name="step-2-optional-configure-the-microsoft-365-human-resources-data-connector"></a>Etapa 2 (opcional): Configure o conector de dados de recursos humanos 365 da Microsoft

O gerenciamento de risco do insider oferece suporte à importação de dados de log e de usuário importados de plataformas de gerenciamento e recursos humanos de terceiros. O conector de dados Human Resources (RH) da Microsoft 365 permite que você receba dados de recursos humanos de arquivos CSV, incluindo encerramento do usuário e datas do último emprego. Esses dados ajudam a direcionar os indicadores de alerta nas políticas de gerenciamento de risco do insider e é uma parte importante da configuração da cobertura de gerenciamento de risco completo em sua organização.

Consulte o tópico [configurar um conector para importar dados de RH](import-hr-data.md) para obter orientações passo a passo para configurar o Microsoft 365 HR Connector para sua organização. Depois de configurar o conector de RH, retorne a estas etapas de configuração.

>[!IMPORTANT]
>Se você planeja configurar uma política usando o modelo de *roubo de dados do funcionário de canpartes* , será necessário configurar o conector de RH para usar os recursos de detecção de sinal completo do modelo de política. Se você configurar mais de um conector de RH para sua organização, o gerenciamento de riscos do insider receberá os indicadores automaticamente de todos os conectores de RH.

## <a name="step-3-optional-configure-data-loss-prevention-dlp-policies"></a>Etapa 3 (opcional): configurar políticas de DLP (prevenção contra perda de dados)

O gerenciamento de riscos do insider suporta o uso de políticas DLP para ajudar a identificar a exposição intencional ou acidental de informações confidenciais a partes indesejadas. Ao configurar uma política de gerenciamento de risco do insider com o modelo de *vazamento de dados* , você precisa atribuir uma política de DLP específica à política. Esta política ajuda a direcionar os indicadores de alerta para informações confidenciais é uma parte importante da configuração da cobertura de gerenciamento de risco completo em sua organização.

Consulte o tópico [criar, testar e ajustar uma política de DLP](create-test-tune-dlp-policy.md) para obter orientações passo a passo para configurar as políticas de DLP para sua organização. Após configurar uma política de DLP, retorne a estas etapas de configuração.

>[!IMPORTANT]
>Se você planeja configurar uma política usando o modelo de *vazamento de dados* , precisará configurar pelo menos uma política de DLP para usar os recursos de detecção de sinal completo do modelo de política. Se você configurar mais de uma política de DLP para sua organização, será necessário atribuir uma política de gerenciamento de risco Insider por política DLP.

## <a name="step-4-required-create-an-insider-risk-management-policy"></a>Etapa 4 (obrigatório): criar uma política de gerenciamento de risco do insider

As políticas de gerenciamento de risco do insider incluem usuários atribuídos e definem quais tipos de indicadores de risco estão configurados para alertas. Antes que as atividades possam disparar alertas, uma política deve ser configurada.

1. No [centro de conformidade da Microsoft 365](https://compliance.microsoft.com), vá para gerenciamento de **risco do insider** e selecione a guia **políticas** .
2. Selecione **criar política** para abrir o assistente de política
3. Na página **nova política de riscos de insider** , preencha os seguintes campos:
    - **Nome (obrigatório)**: Insira um nome amigável para a política
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
8. Na página **escolher indicadores de alerta** , você verá os indicadores incluídos no modelo que você escolheu para essa política. Se você selecionou o modelo *vazamentos de dados* no início do assistente, deverá selecionar uma política de DLP na lista suspensa **política de DLP** .
9. Na página **selecionar janela de monitoramento** , você definirá as [condições da janela de monitoramento](insider-risk-management-policies.md#monitoring-windows) para a política. Configure as janelas de monitoramento conforme apropriado.
10. Selecione **Avançar** para continuar.
11. Na página **revisão** , revise as configurações escolhidas para a política. Selecione **Editar** para alterar qualquer um dos valores da política ou selecione **Enviar** para criar e ativar a política.

Após concluir essas etapas para criar sua primeira política de gerenciamento de risco do Insider, você começará a receber alertas de indicadores de atividade após cerca de 24 horas. Configure as políticas adicionais conforme necessário usando as orientações da etapa 4 deste tópico ou as etapas em [criar uma nova política de risco de insider](insider-risk-management-policies.md#create-a-new-policy).
