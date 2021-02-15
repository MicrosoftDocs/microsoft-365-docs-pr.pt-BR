---
title: Introdução ao gerenciamento de riscos internos
description: Configure o gerenciamento de riscos insider em sua organização.
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
ms.collection:
- m365-security-compliance
- m365solution-insiderrisk
- m365initiative-compliance
ms.openlocfilehash: 13e5d1f160fe957748295749662a7042489887ca
ms.sourcegitcommit: e920e68c8d0eac8b152039b52cfc139d478a67b3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/09/2021
ms.locfileid: "50150579"
---
# <a name="get-started-with-insider-risk-management"></a>Introdução ao gerenciamento de riscos internos

Use políticas de gerenciamento de riscos internas para identificar atividades arriscadas e ferramentas de gerenciamento para agir em alertas de risco em sua organização. Conclua as etapas a seguir para configurar os pré-requisitos e configurar uma política de gerenciamento de riscos interno.

>[!IMPORTANT]
>A solução de gerenciamento de riscos internos do Microsoft 365 fornece uma opção de nível de locatário para ajudar os clientes a facilitar a governança interna no nível do usuário. Os administradores em nível de locatário podem configurar permissões para fornecer acesso a essa solução para os membros da sua organização e configurar conectores de dados no centro de conformidade do Microsoft 365 para importar dados relevantes para oferecer suporte à identificação no nível do usuário de atividades potencialmente arriscadas. Os clientes reconhecem informações relacionadas ao comportamento, ao caractere ou ao desempenho materialmente relacionados ao emprego do usuário individual e podem ser calculadas pelo administrador e disponibilizadas para outras pessoas na organização. Além disso, os clientes reconhecem que devem conduzir sua própria investigação completa relacionada ao comportamento, ao caractere ou ao desempenho do usuário individual materialmente relacionado ao emprego e não apenas depender de informações do serviço de gerenciamento de riscos interno. Os clientes são exclusivamente responsáveis por usar o serviço de gerenciamento de riscos insider do Microsoft 365 e qualquer recurso ou serviço associado em conformidade com todas as leis aplicáveis, incluindo leis relacionadas à identificação de usuário individual e quaisquer ações de correção.

Para obter mais informações sobre como as políticas de risco interno podem ajudá-lo a gerenciar riscos em sua organização, consulte Gerenciamento de riscos do Insider no [Microsoft 365.](insider-risk-management.md)

## <a name="subscriptions-and-licensing"></a>Assinaturas e licenciamento

Antes de começar a trabalhar com o gerenciamento de riscos insider, você deve confirmar sua assinatura do [Microsoft 365](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans) e quaisquer complementos. Para acessar e usar o gerenciamento de riscos insider, sua organização deve ter uma das seguintes assinaturas ou complementos:

- Assinatura do Microsoft 365 E5 (versão paga ou de avaliação)
- Assinatura do Microsoft 365 E3 + o complemento de Conformidade do Microsoft 365 E5
- Assinatura do Microsoft 365 E3 + o complemento Microsoft 365 E5 Insider Risk Management
- Assinatura do Microsoft 365 A5 (versão paga ou de avaliação)
- Assinatura do Microsoft 365 A3 + complemento de Conformidade do Microsoft 365 A5
- Assinatura do Microsoft 365 A3 + o complemento Microsoft 365 A5 Insider Risk Management
- Assinatura do Microsoft 365 G5 (versão paga ou de avaliação)
- Assinatura do Microsoft 365 G3 + o complemento de Conformidade do Microsoft 365 G5
- Assinatura do Microsoft 365 G3 + o complemento Microsoft 365 G5 Insider Risk Management

Os usuários incluídos nas políticas de gerenciamento de riscos insider devem ter uma das licenças atribuídas acima.

Se você não tiver um plano existente do Microsoft 365 Enterprise E5 e quiser experimentar o gerenciamento de riscos [](https://www.microsoft.com/microsoft-365/enterprise) insider, adicione o [Microsoft 365](/office365/admin/try-or-buy-microsoft-365) à sua assinatura existente ou inscreva-se para uma avaliação do Microsoft 365 Enterprise E5.

## <a name="step-1-enable-permissions-for-insider-risk-management"></a>Etapa 1: Habilitar permissões para gerenciamento de riscos insider

>[!Important]
>Depois de configurar seus grupos de função, pode levar até 30 minutos para que as permissões do grupo de função se apliquem a usuários atribuídos em toda a organização.

Há quatro grupos de funções usados para configurar permissões para gerenciar recursos de gerenciamento de riscos insider. Para continuar com essas etapas de configuração, os  administradores de locatários devem primeiro atribuí-lo ao grupo de funções Gerenciamento de Risco Interno ou Administrador de Gerenciamento **de** Risco Interno. Para acessar e gerenciar recursos de gerenciamento de riscos insider após a configuração inicial, os usuários devem ser membros de pelo menos um grupo de funções de gerenciamento de risco interno.

Dependendo da estrutura da sua equipe de gerenciamento de conformidade, você tem opções para atribuir usuários a grupos de função específicos para gerenciar diferentes conjuntos de recursos de gerenciamento de riscos insider. Escolha entre essas opções de grupo de função ao configurar o gerenciamento de riscos interno:

| **Default management role assignments for this role** | **Permissões de função** |
| :---- | :---------------- |
| **Gerenciamento de riscos do Insider** | Use esse grupo de função para gerenciar o gerenciamento de riscos insider para sua organização em um único grupo. Ao adicionar todas as contas de usuário para administradores designados, analistas e investigadores, você pode configurar permissões de gerenciamento de riscos interno em um único grupo. Esse grupo de funções contém todas as funções de permissão de gerenciamento de risco interno. Essa configuração é a maneira mais fácil de começar rapidamente com o gerenciamento de riscos insider e é uma boa opção para organizações que não precisam de permissões separadas definidas para grupos separados de usuários.|
| **Administrador de Gerenciamento de Riscos Do Insider** | Use esse grupo de função para configurar inicialmente o gerenciamento de riscos insider e posteriormente segregar os administradores de risco interno em um grupo definido.  Os usuários desse grupo de função podem criar, ler, atualizar e excluir políticas de gerenciamento de riscos insider, configurações globais e atribuições de grupo de função. |
| **Analistas do Gerenciamento de Risco Interno** | Use esse grupo para atribuir permissões aos usuários que atuarão como analistas de caso de risco interno. Os usuários desse grupo de função podem acessar todos os alertas, ocorrências e modelos de avisos de gerenciamento de riscos insider. Eles não podem acessar o Explorador de Conteúdo de risco interno. |
| **Investigadores do Gerenciamento de Risco Interno** | Use esse grupo para atribuir permissões aos usuários que atuarão como investigadores de dados de risco interno. Os usuários desse grupo de função podem acessar todos os alertas, casos, modelos de avisos e o Explorador de Conteúdo de gerenciamento de riscos. |

> [!NOTE]
> Atualmente, esses grupos de funções não têm suporte no PIM (Privileged Identity Management). Para saber mais sobre PIM, confira Atribuir funções do [Azure AD no Privileged Identity Management.](/azure/active-directory/privileged-identity-management/pim-how-to-add-role-to-user)

### <a name="add-users-to-an-insider-risk-management-role-group"></a>Adicionar usuários a um grupo de função de gerenciamento de risco interno

Conclua as etapas a seguir para adicionar usuários a um grupo de funções de gerenciamento de risco interno:

1. Entre usando [https://protection.office.com/permissions](https://protection.office.com/permissions) credenciais para uma conta de administrador em sua organização do Microsoft 365.

2. No Centro de &amp; Conformidade de Segurança, vá para **Permissões.** Selecione o link para exibir e gerenciar funções no Office 365.

3. Selecione o grupo de função de gerenciamento de risco interno ao que você deseja adicionar usuários e, em seguida, **selecione Editar grupo de funções.**

4. Selecione **Escolher membros** no painel de navegação esquerdo e, em seguida, selecione **Editar.**

5. Selecione **Adicionar** e marque a caixa de seleção de todos os usuários que você deseja adicionar ao grupo de funções.

6. Selecione **Adicionar** e, em seguida, **Terminar.**

7. Selecione **Salvar** para adicionar os usuários ao grupo de funções. Selecione **Fechar** para concluir as etapas.

## <a name="step-2-enable-the-audit-log"></a>Etapa 2: Habilitar o log de auditoria

O gerenciamento de riscos insider usa logs de auditoria para insights do usuário e atividades configuradas em políticas. Os logs de auditoria são um resumo de todas as atividades associadas a uma política de gerenciamento de riscos interno ou sempre que uma política for alterada.

Para obter instruções passo a passo para ativar a auditoria, consulte Ativar ou desativar a pesquisa de [log de auditoria.](turn-audit-log-search-on-or-off.md) Depois de ativar a auditoria, é exibida uma mensagem informando que o log de auditoria está sendo preparado e que você pode executar uma pesquisa em algumas horas após a conclusão da preparação. Você só precisa fazer essa ação uma vez. Para obter mais informações sobre como usar o log de auditoria, consulte [Pesquisar o log de auditoria.](search-the-audit-log-in-security-and-compliance.md)

## <a name="step-3-configure-prerequisites-for-templates"></a>Etapa 3: Configurar pré-requisitos para modelos

A maioria dos modelos de gerenciamento de riscos insider têm pré-requisitos que devem ser configurados para que os indicadores de política gerem alertas de atividade relevantes. Configure os pré-requisitos apropriados dependendo das políticas que você planeja configurar para sua organização.

### <a name="configure-microsoft-365-hr-connector"></a>Configurar o conector do Microsoft 365 HR

O gerenciamento de riscos insider oferece suporte à importação de dados de usuários e de log importados de plataformas de gerenciamento de riscos e recursos humanos de terceiros. O conector de dados de Recursos Humanos (RH) do Microsoft 365 permite que você receber dados de recursos humanos de arquivos CSV, incluindo datas de rescisão do usuário, datas do último emprego, notificações do plano de aperfeiçoamento do desempenho, ações de revisão de desempenho e status de alteração no nível do trabalho. Esses dados ajudam a impulsionar indicadores de alerta em políticas de gerenciamento de riscos interno e são uma parte importante da configuração da cobertura completa do gerenciamento de riscos em sua organização. Se você configurar mais de um conector de RH para sua organização, o gerenciamento de riscos insider obterá automaticamente indicadores de todos os conectores de RH.

O conector do Microsoft 365 HR é necessário ao usar os seguintes modelos de política:

- Roubo de dados do usuário de saída
- Violações da política de segurança por parte dos usuários
- Violações da política de segurança por usuários não coerentes
- Vazamentos de dados por usuários não coerentes

Consulte o artigo Configurar um conector para importar dados de RH para obter orientação passo [a](import-hr-data.md) passo para configurar o conector de RH do Microsoft 365 para sua organização. Depois de configurar o conector de RH, retorne às etapas de configuração.

### <a name="configure-data-loss-prevention-dlp-policies"></a>Configurar políticas de Prevenção contra Perda de Dados (DLP)

O gerenciamento de riscos insider dá suporte ao uso de políticas de DLP para ajudar a identificar a exposição intencional ou acidental de informações confidenciais a partes indesejadas para alertas DLP de alto nível de gravidade. Ao configurar uma política de gerenciamento de riscos interno com qualquer um dos modelos de vazamento **de** dados, você deve atribuir uma política DLP específica à política.

As políticas de DLP ajudam a identificar os usuários para ativar a pontuação de risco no gerenciamento de riscos insider para alertas de DLP de alta gravidade para informações confidenciais e são uma parte importante da configuração da cobertura de gerenciamento de risco total em sua organização. Para obter mais informações sobre gerenciamento de riscos insider e considerações de planejamento e integração de políticas de DLP, consulte Políticas de gerenciamento de riscos [do Insider.](insider-risk-management-policies.md#general-data-leaks)

>[!IMPORTANT]
>Certifique-se de ter concluído o seguinte:
>
>- Você entende e configura corretamente os usuários no escopo nas políticas de gerenciamento de risco interno e DLP para produzir a cobertura de política esperada.
>- Certifique-se **de que** a configuração de relatórios de incidentes na política  de DLP para gerenciamento de risco interno usado com esses modelos está configurada para alertas de alto nível de gravidade. Os alertas de gerenciamento de riscos interno não serão gerados a partir de políticas de DLP com o campo **Relatórios** de incidentes definido como *Baixo* ou *Médio.*

Uma política de DLP é necessária ao usar os seguintes modelos de política:

- Vazamentos gerais de dados
- Vazamentos de dados por usuários prioritários

Consulte o [artigo Criar, testar](create-test-tune-dlp-policy.md) e ajustar um artigo de política de DLP para obter orientação passo a passo sobre como configurar políticas DLP para sua organização. Depois de configurar uma política de DLP, volte para essas etapas de configuração.

### <a name="configure-priority-user-groups"></a>Configurar grupos de usuários prioritários

O gerenciamento de riscos insider inclui suporte para a atribuição de grupos de usuários prioritários a políticas para ajudar a identificar atividades de risco exclusivas para usuários com posições críticas, altos níveis de dados e acesso à rede ou um histórico anterior do comportamento de risco. Criar um grupo de usuários com prioridade e atribuir usuários ao grupo ajuda a criar políticas de escopo para as circunstâncias exclusivas apresentadas por esses usuários.

Um grupo de usuários com prioridade é necessário ao usar os seguintes modelos de política:

- Violações da política de segurança por usuários prioritários
- Vazamentos de dados por usuários prioritários

Consulte o artigo Guia de [configurações](insider-risk-management-settings.md#priority-user-groups-preview) de gerenciamento de riscos interno para obter orientação passo a passo para criar um grupo de usuários com prioridade. Depois de configurar um grupo de usuários com prioridade, volte para estas etapas de configuração.

### <a name="configure-physical-badging-connector-optional"></a>Configurar o conector de badging físico (opcional)

O gerenciamento de riscos insider dá suporte à importação de dados de usuário e log importados de plataformas de controle físico e acesso. O conector de badging físico permite que você acesse dados de arquivos JSON, incluindo IDs de usuário, IDs de ponto de acesso, hora de acesso e datas e status de acesso. Esses dados ajudam a impulsionar indicadores de alerta em políticas de gerenciamento de riscos interno e são uma parte importante da configuração da cobertura completa do gerenciamento de riscos em sua organização. Se você configurar mais de um conector de badging físico para sua organização, o gerenciamento de riscos do insider obterá automaticamente indicadores de todos os conectores de danos físicos. As informações do conector de badging físico complementam outros sinais de risco interno ao usar todos os modelos de política de risco interno.

>[!IMPORTANT]
>Para que as políticas de gerenciamento de riscos insider usem e correlacionem dados de sinal relacionados a usuários de saída e encerrados com dados de eventos de suas plataformas de controle físico e acesso, você também deve configurar o conector de RH do Microsoft 365. Se você habilitar o conector de badging físico sem habilitar o conector de RH do Microsoft 365, as políticas de gerenciamento de riscos insider processarão apenas eventos para acesso físico não autorizado para usuários em sua organização.

Consulte o artigo Configurar um conector para importar dados de danos físicos para obter orientação passo [a](import-physical-badging-data.md) passo sobre como configurar o conector de badging físico para sua organização. Depois de configurar o conector, retorne às etapas de configuração.

## <a name="step-4-configure-insider-risk-settings"></a>Etapa 4: Definir as configurações de risco interno

[As configurações de risco interno se](insider-risk-management-settings.md) aplicam a todas as políticas de gerenciamento de risco interno, independentemente do modelo que você escolheu ao criar uma política. As configurações são configuradas usando o controle de configurações de risco do **Insider** localizado na parte superior de todas as guias de gerenciamento de riscos insider. Essas configurações controlam a privacidade, os indicadores, as janelas de monitoramento e as detecções inteligentes.

Antes de configurar uma política, defina as seguintes configurações de risco interno:

1. No centro [de conformidade do Microsoft 365,](https://compliance.microsoft.com)vá para o gerenciamento de riscos do Insider e selecione as configurações de risco do **Insider** no canto superior direito de qualquer página. 
2. Na página **Privacidade,** selecione uma configuração de privacidade para exibir nomes de usuário para alertas de política.
3. Na página **Indicadores,** selecione os indicadores de alerta que você deseja aplicar a todas as políticas de risco interno.

    >[!IMPORTANT]
    >Para receber alertas de atividades arriscadas definidas em suas políticas, você deve selecionar um ou mais indicadores.

4. Na página **De períodos de política,** selecione os [períodos](insider-risk-management-settings.md#policy-timeframes) de política para entrar em vigor para um usuário quando ele disparar uma combinação para uma política de risco interno.
5. Na página **Detecções inteligentes,** de configure as seguintes configurações para políticas de risco interno:
    - [Detecções de anomalias](insider-risk-management-settings.md#anomaly-detections)
    - [Nível de volume de alerta](insider-risk-management-settings.md#alert-volume)
    - [Status de alerta do Microsoft Defender para Ponto de Extremidade](insider-risk-management-settings.md#microsoft-defender-for-endpoint-preview)
    - [Configurações de domínio](insider-risk-management-settings.md#domains-preview)
6. Na página **Exportar alertas,** habilita a exportação de informações de alerta de risco interno usando as APIs de Gerenciamento do Office 365, se necessário.
7. Na página **Grupos de usuários de** prioridade, crie um grupo de usuários com prioridade e adicione usuários se não tiver criado na Etapa **3.**
8. Na página **fluxos do Power Automate,** configure um fluxo de modelos de fluxo de riscos insider ou crie um novo fluxo. Consulte o [artigo Sobre como começar a trabalhar com configurações](insider-risk-management-settings.md#power-automate-flows-preview) de gerenciamento de riscos insider para obter orientações passo a passo.
9. Na página **Ativos de** prioridade, configure os ativos de prioridade para usar dados do seu controle físico e da plataforma de acesso importados pelo conector de badging físico. Consulte o [artigo Guia de configurações de](insider-risk-management-settings.md#priority-physical-assets-preview) gerenciamento de riscos interno para obter orientações passo a passo.
10. Na página **do Microsoft Teams,** habilita a integração do Microsoft Teams com o gerenciamento de riscos insider para criar automaticamente uma equipe para colaboração de casos ou usuários. Consulte o [artigo Guia de configurações de](insider-risk-management-settings.md#microsoft-teams-preview) gerenciamento de riscos interno para obter orientações passo a passo.
11. Selecione **Salvar** para habilitar essas configurações para suas políticas de risco interno.

## <a name="step-5-create-an-insider-risk-management-policy"></a>Etapa 5: Criar uma política de gerenciamento de riscos interno

As políticas de gerenciamento de riscos internas incluem usuários atribuídos e definem quais tipos de indicadores de risco são configurados para alertas. Antes que as atividades possam disparar alertas, uma política deve ser configurada.

1. No centro [de conformidade do Microsoft 365,](https://compliance.microsoft.com)vá para o gerenciamento de riscos do **Insider** e selecione a **guia** Políticas.
2. Selecione **Criar política para** abrir o assistente de política.
3. Na página **Nova política de risco interno,** preencha os seguintes campos:
    - **Nome (obrigatório)**: insira um nome amigável para a política.
    - **Descrição (opcional)**: insira uma descrição para a política.
    - **Choose policy template (required)**: Select one of the [policy templates](insider-risk-management-policies.md#policy-templates) to define the types of risk indicators are monitored by the policy.

    >[!IMPORTANT]
    >A maioria dos modelos de política tem pré-requisitos que devem ser configurados para que a política gere alertas relevantes. Se você ainda não configurou os pré-requisitos da política aplicável, consulte **a Etapa 3** acima.

4. Selecione **Próximo** para continuar.
5. Na página **Usuários,** selecione Adicionar  usuário ou grupo ou Escolher grupos de usuários de Prioridade para definir quais usuários ou grupos de usuários prioritários serão incluídos na política, dependendo do modelo de política selecionado.  Marque **a caixa de seleção Todos** os usuários e grupos habilitados para email, se aplicável (se você não tiver selecionado um modelo com prioridade baseada no usuário). Selecione **Próximo** para continuar.
6. Na página **Especificar qual conteúdo priorizar (opcional),** você pode atribuir as fontes para priorizar pontuações de risco maiores. No entanto, algumas atividades não gerarão um alerta, a menos que o conteúdo relacionado contenha tipos de informações confidenciais integrados ou personalizados ou tenha sido especificado como prioridade nesta página:
    - **Sites do SharePoint:** selecione **Adicionar site do SharePoint** e selecione as organizações do SharePoint que você deseja priorizar. Por exemplo, *"group1@contoso.sharepoint.com/sites/group1".*
    - **Tipo de informação confidenciais:** selecione **Adicionar tipo de informação sensível** e selecione os tipos de sensibilidade que você deseja priorizar. Por exemplo, *"Número de Conta Bancária dos EUA"* e *"Número de Cartão de Crédito"*.
    - **Rótulos de sensibilidade:** **selecione Adicionar rótulo de** sensibilidade e selecione os rótulos que você deseja priorizar. Por exemplo, *"Confidencial"* e *"Segredo"*.
7. Selecione **Próximo** para continuar.
8. Na página **Selecionar indicadores de** política, você verá os indicadores definidos como disponíveis na página Indicadores de configurações de risco do [](insider-risk-management-settings.md#indicators) **Insider.**  >   Se você selecionou um modelo de vazamento *de* dados no início do assistente, você deve selecionar uma política DLP na lista de lista suspenso de política **de DLP** para habilitar os indicadores de disparo para a política. Selecione os indicadores que você deseja aplicar à política. Se você preferir não usar as configurações de limite de política padrão para esses indicadores, desabilite os limites padrão de uso **recomendados** pela Microsoft e insira os valores de limite para cada indicador selecionado. Se você tiver selecionado pelo menos um indicador *do Office* ou do *Dispositivo,* selecione as pontuações de risco **conforme** apropriado. Os indicadores de pontuação de risco só são aplicáveis aos indicadores selecionados.

    >[!IMPORTANT]
    >Se os indicadores nesta página não puderem ser selecionados, você precisará selecionar os indicadores que deseja habilitar para todas as políticas na página Indicadores de Política de Configurações de gerenciamento de riscos do **Insider.**  >    >  

9. Selecione **Próximo** para continuar.
10. Na página **Policy timeframes,** você [](insider-risk-management-settings.md#policy-timeframes) verá as condições da janela de ativação para a política que, na página De períodos de política de configurações de risco do **Insider.**  >  
11. Selecione **Próximo** para continuar.
12. Na página **Revisão,** revise as configurações escolhidas para a política. Selecione **Editar** para alterar qualquer um dos valores de política ou **selecione Enviar** para criar e ativar a política.

## <a name="next-steps"></a>Próximas etapas

Depois de concluir essas etapas para criar sua primeira política de gerenciamento de riscos insider, você começará a receber alertas de indicadores de atividade após cerca de 24 horas. Configure políticas adicionais conforme necessário usando as orientações na Etapa 4 deste artigo ou as etapas em Criar uma nova política de risco [interno.](insider-risk-management-policies.md#create-a-new-policy)

Para saber mais sobre como investigar alertas de riscos insider e o painel **Alertas,** consulte Alertas de gerenciamento de riscos [do Insider.](insider-risk-management-alerts.md)
