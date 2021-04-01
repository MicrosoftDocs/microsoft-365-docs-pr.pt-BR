---
title: Introdução ao gerenciamento de riscos internos
description: Configure o gerenciamento de risco interno em sua organização.
keywords: Microsoft 365, gerenciamento de risco interno, gerenciamento de riscos, conformidade
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
ms.openlocfilehash: 9e1b7a18bea09d10cb133ce9106df45533a72172
ms.sourcegitcommit: 39609c4d8c432c8e7d7a31cb35c8020e5207385b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/30/2021
ms.locfileid: "51445225"
---
# <a name="get-started-with-insider-risk-management"></a>Introdução ao gerenciamento de riscos internos

Use políticas de gerenciamento de riscos internas para identificar atividades arriscadas e ferramentas de gerenciamento para agir em alertas de risco em sua organização. Conclua as etapas a seguir para configurar os pré-requisitos e configurar uma política de gerenciamento de riscos internas.

>[!IMPORTANT]
>A solução de gerenciamento de riscos internos do Microsoft 365 fornece uma opção de nível de locatário para ajudar os clientes a facilitar a governança interna no nível do usuário. Os administradores de nível de locatário podem configurar permissões para fornecer acesso a essa solução para membros da sua organização e configurar conectores de dados no centro de conformidade do Microsoft 365 para importar dados relevantes para dar suporte à identificação no nível do usuário de atividades potencialmente arriscadas. Os clientes reconhecem que as percepções relacionadas ao comportamento, ao caractere ou ao desempenho do usuário individual relacionadas ao emprego podem ser calculadas pelo administrador e disponibilizadas para outras pessoas na organização. Além disso, os clientes reconhecem que devem conduzir suas próprias investigações completas relacionadas ao comportamento, ao caractere ou ao desempenho do usuário individual relacionada materialmente ao trabalho e não apenas depender de informações do serviço de gerenciamento de riscos do usuário interno. Os clientes são os únicos responsáveis por usar o serviço de gerenciamento de riscos do Microsoft 365 insider e qualquer recurso ou serviço associado em conformidade com todas as leis aplicáveis, incluindo leis relacionadas à identificação individual do usuário e quaisquer ações de correção.

Para obter mais informações sobre como as políticas de risco internas podem ajudá-lo a gerenciar riscos em sua organização, consulte [Insider risk management in Microsoft 365](insider-risk-management.md).

## <a name="subscriptions-and-licensing"></a>Assinaturas e licenciamento

Antes de começar com o gerenciamento de riscos insider, você deve confirmar sua assinatura do [Microsoft 365](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans) e quaisquer complementos. Para acessar e usar o gerenciamento de riscos insider, sua organização deve ter uma das seguintes assinaturas ou complementos:

- Assinatura do Microsoft 365 E5 (versão paga ou de avaliação)
- Assinatura do Microsoft 365 E3 + complemento de Conformidade do Microsoft 365 E5
- Assinatura do Microsoft 365 E3 + complemento do Microsoft 365 E5 Insider Risk Management
- Assinatura do Microsoft 365 A5 (versão paga ou de avaliação)
- Assinatura do Microsoft 365 A3 + complemento de Conformidade do Microsoft 365 A5
- Assinatura do Microsoft 365 A3 + complemento do Microsoft 365 A5 Insider Risk Management
- Assinatura do Microsoft 365 G5 (versão paga ou de avaliação)
- Assinatura do Microsoft 365 G3 + complemento de Conformidade do Microsoft 365 G5
- Assinatura do Microsoft 365 G3 + complemento do Microsoft 365 G5 Insider Risk Management
- Assinatura do Office 365 E3 + Enterprise Mobility and Security E3 + o complemento conformidade do Microsoft 365 E5

Os usuários incluídos em políticas de gerenciamento de riscos insider devem ser atribuídos a uma das licenças acima.

Se você não tiver um plano existente do Microsoft 365 Enterprise E5 e quiser tentar o gerenciamento de riscos [](https://www.microsoft.com/microsoft-365/enterprise) insider, adicione o [Microsoft 365](/office365/admin/try-or-buy-microsoft-365) à sua assinatura existente ou inscreva-se para uma avaliação do Microsoft 365 Enterprise E5.

## <a name="step-1-enable-permissions-for-insider-risk-management"></a>Etapa 1: Habilitar permissões para gerenciamento de risco interno

>[!Important]
>Depois de configurar seus grupos de função, pode levar até 30 minutos para que as permissões do grupo de funções se apliquem aos usuários atribuídos em toda a sua organização.

Há quatro grupos de funções usados para configurar permissões para gerenciar recursos de gerenciamento de riscos insider. Para continuar com essas etapas de configuração, os administradores de locatários devem primeiro atribuir você ao grupo de função Gerenciamento de Riscos do **Insider** ou Administrador de Gerenciamento de Riscos do **Insider.** Para acessar e gerenciar recursos de gerenciamento de riscos insider após a configuração inicial, os usuários devem ser membros de pelo menos um grupo de função de gerenciamento de risco interno.

Dependendo da estrutura da sua equipe de gerenciamento de conformidade, você tem opções para atribuir usuários a grupos de funções específicos para gerenciar diferentes conjuntos de recursos de gerenciamento de risco interno. Para exibir  a guia Permissões no Centro de Conformidade e Conformidade do Office 365 Security  & e gerenciar grupos de funções, você precisa ser atribuído ao grupo de função Gerenciamento da Organização ou precisa ter a função gerenciamento de *função.* Escolha entre essas opções de grupo de função ao configurar o gerenciamento de riscos insider:

| **Default management role assignments for this role** | **Permissões de função** |
| :------------- | :------------------- |
| **Gerenciamento de riscos do Insider** | Use este grupo de função para gerenciar o gerenciamento de risco inerno da sua organização em um único grupo. Ao adicionar todas as contas de usuário para administradores designados, analistas, investigadores e auditores, você pode configurar permissões de gerenciamento de riscos internas em um único grupo. Este grupo de funções contém todas as funções de permissão de gerenciamento de risco interno e permissões associadas. Essa configuração é a maneira mais fácil de começar rapidamente com o gerenciamento de riscos insider e é um bom ajuste para organizações que não precisam de permissões separadas definidas para grupos separados de usuários. |
| **Administrador de Gerenciamento de Riscos do Insider** | Use esse grupo de funções para configurar inicialmente o gerenciamento de riscos insider e posteriormente para segregar administradores de riscos insider em um grupo definido. Os usuários neste grupo de funções podem habilitar e exibir insights de análise e criar, ler, atualizar e excluir políticas de gerenciamento de riscos insider, configurações globais e atribuições de grupo de função. |
| **Analistas do Gerenciamento de Risco Interno** | Use este grupo para atribuir permissões aos usuários que atuarão como analistas de casos de risco internos. Os usuários neste grupo de funções podem acessar e exibir todos os alertas de gerenciamento de riscos insider, casos, insights de análise e modelos de avisos. Eles não podem acessar o explorador de conteúdo de risco interno. |
| **Investigadores do Gerenciamento de Risco Interno** | Use este grupo para atribuir permissões aos usuários que atuarão como investigadores de dados do risco interno. Os usuários neste grupo de funções podem acessar todos os alertas, casos, modelos de avisos e o explorador de conteúdo para todos os casos. |
| **Auditores de Gerenciamento de Riscos do Insider** | Use esse grupo para atribuir permissões aos usuários que auditarão atividades de gerenciamento de riscos insider. Os usuários neste grupo de funções podem acessar o log de auditoria de risco interno. |

> [!NOTE]
> Atualmente, esses grupos de funções não têm suporte no PIM (Privileged Identity Management). Para saber mais sobre PIM, consulte [Assign Azure AD roles in Privileged Identity Management](/azure/active-directory/privileged-identity-management/pim-how-to-add-role-to-user).

### <a name="add-users-to-an-insider-risk-management-role-group"></a>Adicionar usuários a um grupo de função de gerenciamento de risco interno

Conclua as etapas a seguir para adicionar usuários a um grupo de função de gerenciamento de risco interno:

1. Entre [https://protection.office.com/permissions](https://protection.office.com/permissions) usando credenciais para uma conta de administrador em sua organização do Microsoft 365.

2. No Centro &amp; de Conformidade de Segurança, acesse **Permissões**. Selecione o link para exibir e gerenciar funções no Office 365.

3. Selecione o grupo de função de gerenciamento de risco interno ao que você deseja adicionar usuários e selecione **Editar grupo de função**.

4. Selecione **Escolher membros** no painel de navegação esquerdo e selecione **Editar**.

5. Selecione **Adicionar** e selecione a caixa de seleção para todos os usuários que você deseja adicionar ao grupo de funções.

6. Selecione **Adicionar**, em seguida, selecione **Feito**.

7. Selecione **Salvar** para adicionar os usuários ao grupo de funções. Selecione **Fechar** para concluir as etapas.

## <a name="step-2-enable-the-microsoft-365-audit-log"></a>Etapa 2: Habilitar o log de auditoria do Microsoft 365

O gerenciamento de riscos insider usa logs de auditoria do Microsoft 365 para informações e atividades do usuário identificadas em políticas e insights de análise. Os logs de auditoria do Microsoft 365 são um resumo de todas as atividades dentro da sua organização e as políticas de gerenciamento de riscos insider podem usar essas atividades para gerar insights de política.

Para obter instruções passo a passo para ativar a auditoria, consulte Ativar ou desativar a pesquisa de [log de auditoria.](turn-audit-log-search-on-or-off.md) Após a ativação, será exibida uma mensagem informando que o log de auditoria está sendo preparado e que você poderá executar uma pesquisa dentro algumas horas quando a preparação estiver concluída. Você só precisa fazer essa ação uma vez. Para obter mais informações sobre como usar o log de auditoria do Microsoft 365, consulte [Pesquisar o log de auditoria.](search-the-audit-log-in-security-and-compliance.md)

## <a name="step-3-enable-and-view-insider-risk-analytics-insights-optional"></a>Etapa 3: Habilitar e exibir informações de análise de risco do insider (opcional)

A análise de gerenciamento de riscos insider permite que você conduza uma avaliação de possíveis riscos insider em sua organização sem configurar nenhuma política de risco interna. Essa avaliação pode ajudar sua organização a identificar áreas potenciais de maior risco de usuário e ajudar a determinar o tipo e o escopo das políticas de gerenciamento de riscos internas que você pode considerar configurar. Essa avaliação também pode ajudá-lo a determinar as necessidades de licenciamento adicional ou otimização futura das políticas existentes. Os resultados da análise podem levar até 48 horas antes que as informações sejam disponibilizadas como relatórios para revisão. Para saber mais sobre insights de análise, consulte Configurações de gerenciamento de riscos do [Insider: Analytics (visualização)](insider-risk-management-settings.md#analytics-preview) e confira o vídeo do [Insider Risk Management Analytics](https://www.youtube.com/watch?v=5c0P5MCXNXk) para ajudar a entender como a análise pode ajudar a acelerar a identificação de possíveis riscos insider e ajudá-lo a tomar medidas rapidamente.

Para habilitar o Insider risk Analytics, você deve ser membro do *Insider Risk Management*, Administrador de Gerenciamento de Riscos do *Insider* ou grupo de função de administrador *global* do Microsoft 365.

Conclua as etapas a seguir para habilitar a análise de risco interno:

1. No Centro de conformidade do [Microsoft 365,](https://compliance.microsoft.com)acesse **Insider risk management**.
2. Selecione **Executar verificação** na guia Verificar riscos de **insider no** cartão da organização na guia Visão geral do gerenciamento de riscos insider.  Essa ação a turns on analytics scanning for your organization. Você também pode ativar a verificação em sua organização navegando para o Insider risk **settings**  >  **Analytics (preview)** e habilitando Examinar a atividade do usuário do locatário para identificar possíveis riscos **insider**.
3. No painel **Detalhes do Analytics,** selecione **Executar verificação para iniciar a verificação da sua organização.** Os resultados da análise podem levar até 24 horas antes que as informações sejam disponibilizadas como relatórios para revisão.

Depois de analisar as informações de análise, escolha as políticas de risco internas e configure os pré-requisitos associados que melhor atendem à estratégia de mitigação de riscos insider da sua organização.

## <a name="step-4-configure-prerequisites-for-policies"></a>Etapa 4: Configurar pré-requisitos para políticas

A maioria das políticas de gerenciamento de riscos internas tem pré-requisitos que devem ser configurados para que os indicadores de política gerem alertas de atividade relevantes. Configure os pré-requisitos apropriados, dependendo das políticas que você planeja configurar para sua organização.

### <a name="configure-microsoft-365-hr-connector"></a>Configurar o conector de RH do Microsoft 365

O gerenciamento de riscos insider dá suporte à importação de dados de usuário e log importados de plataformas de gerenciamento de riscos e recursos humanos de terceiros. O conector de dados recursos humanos (RH) do Microsoft 365 permite que você retire dados de recursos humanos de arquivos CSV, incluindo datas de término do usuário, datas de último emprego, notificações do plano de melhoria de desempenho, ações de revisão de desempenho e status de alteração no nível do trabalho. Esses dados ajudam a impulsionar indicadores de alerta nas políticas de gerenciamento de riscos internas e são uma parte importante da configuração da cobertura completa de gerenciamento de riscos em sua organização. Se você configurar mais de um conector de RH para sua organização, o gerenciamento de risco interno puxará automaticamente indicadores de todos os conectores de RH.

O conector de RH do Microsoft 365 é necessário ao usar os seguintes modelos de política:

- Partida do roubo de dados do usuário
- Violações de política de segurança ao separar usuários
- Violações de política de segurança por usuários insatisfeitos
- Vazamentos de dados por usuários insatisfeitos

Consulte o [artigo Configurar](import-hr-data.md) um conector para importar dados de RH para obter orientações passo a passo para configurar o conector de RH do Microsoft 365 para sua organização. Depois de configurar o conector de RH, retorne a essas etapas de configuração.

### <a name="configure-data-loss-prevention-dlp-policies"></a>Configurar políticas de Prevenção contra Perda de Dados (DLP)

O gerenciamento de riscos insider dá suporte ao uso de políticas DLP para ajudar a identificar a exposição intencional ou acidental de informações confidenciais a terceiros indesejados para alertas de DLP de nível de alta gravidade. Ao configurar uma política de gerenciamento de riscos insider com qualquer um dos modelos de vazamento **de** dados, você deve atribuir uma política DLP específica à política.

As políticas de DLP ajudam a identificar os usuários para ativar a pontuação de risco no gerenciamento de risco interno para alertas de DLP de alta gravidade para informações confidenciais e são uma parte importante da configuração da cobertura de gerenciamento de riscos completos em sua organização. Para obter mais informações sobre o gerenciamento de riscos insider e considerações de integração e planejamento de políticas de DLP, consulte Políticas de gerenciamento de riscos [do Insider.](insider-risk-management-policies.md#general-data-leaks)

>[!IMPORTANT]
>Certifique-se de ter concluído o seguinte:
>
>- Você compreende e configura corretamente os usuários no escopo nas políticas de gerenciamento de riscos de DLP e insider para produzir a cobertura de política esperada.
>- Certifique-se **de que a** configuração de relatórios de incidentes na política DLP para gerenciamento de risco interno usado com esses modelos está configurada para alertas de nível de alta gravidade.  Os alertas de gerenciamento de riscos insider não serão gerados a partir de políticas de DLP com o campo **Relatórios** de incidentes definido em *Baixo* ou *Médio.*

Uma política DLP é necessária ao usar os seguintes modelos de política:

- Vazamentos gerais de dados
- Vazamentos de dados por usuários prioritários

Consulte o [artigo Criar, testar e ajustar uma](create-test-tune-dlp-policy.md) política DLP para obter orientações passo a passo para configurar políticas de DLP para sua organização. Depois de configurar uma política DLP, retorne a essas etapas de configuração.

### <a name="configure-priority-user-groups"></a>Configurar grupos de usuários prioritários

O gerenciamento de riscos insider inclui suporte para atribuir grupos de usuários prioritários a políticas para ajudar a identidade de atividades de risco exclusivas para o usuário com posições críticas, altos níveis de dados e acesso à rede ou um histórico passado de comportamento de risco. Criar um grupo de usuários prioritário e atribuir os usuários às políticas de escopo de ajuda do grupo às circunstâncias exclusivas apresentadas por esses usuários.

Um grupo de usuários de prioridade é necessário ao usar os seguintes modelos de política:

- Violações de política de segurança por usuários prioritários
- Vazamentos de dados por usuários prioritários

Consulte o [artigo Sobre como começar com as configurações](insider-risk-management-settings.md#priority-user-groups-preview) de gerenciamento de riscos insider para obter orientações passo a passo para criar um grupo de usuários prioritário. Depois de configurar um grupo de usuários de prioridade, retorne a essas etapas de configuração.

### <a name="configure-physical-badging-connector-optional"></a>Configurar o conector de badging físico (opcional)

O gerenciamento de riscos insider dá suporte à importação de dados de usuário e log de plataformas de controle físico e de acesso. O conector de badging físico permite que você acesse dados de arquivos JSON, incluindo IDs de usuário, IDs de ponto de acesso, hora de acesso e datas e status de acesso. Esses dados ajudam a impulsionar indicadores de alerta nas políticas de gerenciamento de riscos internas e são uma parte importante da configuração da cobertura completa de gerenciamento de riscos em sua organização. Se você configurar mais de um conector de badging físico para sua organização, o gerenciamento de risco interno puxará automaticamente indicadores de todos os conectores de badging físico. As informações do conector de danos físicos complementam outros sinais de risco insider ao usar todos os modelos de política de risco insider.

>[!IMPORTANT]
>Para que as políticas de gerenciamento de riscos internas usem e correlacionam dados de sinal relacionados à partida e ao fim de usuários com dados de eventos de suas plataformas de controle físico e de acesso, você também deve configurar o conector de RH do Microsoft 365. Se você habilitar o conector de badging físico sem habilitar o conector de RH do Microsoft 365, as políticas de gerenciamento de riscos internas só processarão eventos para acesso físico não autorizado para usuários em sua organização.

Consulte o [artigo Configurar](import-physical-badging-data.md) um conector para importar dados de danos físicos para obter orientações passo a passo para configurar o conector de badging físico para sua organização. Depois de configurar o conector, retorne a essas etapas de configuração.

### <a name="configure-microsoft-defender-for-endpoint-optional"></a>Configurar o Microsoft Defender para Ponto de Extremidade (opcional)

[O Microsoft Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) é uma plataforma de segurança de ponto de extremidade empresarial projetada para ajudar as redes corporativas a evitar, detectar, investigar e responder a ameaças avançadas. Para ter melhor visibilidade das violações de segurança em sua organização, você pode importar e filtrar alertas do Defender para o Ponto de Extremidade para atividades usadas em políticas criadas a partir de modelos de política de violação de segurança de gerenciamento de risco interno.

Se você criar políticas de violação de segurança, precisará ter o Microsoft Defender para Ponto de Extremidade configurado em sua organização e habilitar o Defender for Endpoint para integração de gerenciamento de riscos insider no Defender Security Center para importar alertas de violação de segurança. Para obter mais informações sobre requisitos, consulte o [artigo Requisitos mínimos do Microsoft Defender para Pontos de](/windows/security/threat-protection/microsoft-defender-atp/minimum-requirements) Extremidade.

Consulte o [artigo Configurar recursos avançados](/windows/security/threat-protection/microsoft-defender-atp/advanced-features#share-endpoint-alerts-with-microsoft-compliance-center) no Defender para Ponto de Extremidade para obter orientações passo a passo para configurar o Defender para Endpoint para integração de gerenciamento de riscos insider. Depois de configurar o Microsoft Defender para Ponto de Extremidade, retorne a essas etapas de configuração.

## <a name="step-5-configure-insider-risk-settings"></a>Etapa 5: Configurar configurações de risco interno

[As configurações de risco do insider](insider-risk-management-settings.md) se aplicam a todas as políticas de gerenciamento de riscos internas, independentemente do modelo que você escolheu ao criar uma política. As configurações são definidas usando o controle de **configurações de risco interno** localizado na parte superior de todas as guias de gerenciamento de risco interno. Essas configurações controlam a privacidade, os indicadores, as janelas de monitoramento e as detecções inteligentes.

Antes de configurar uma política, defina as seguintes configurações de risco interno:

1. No Centro de conformidade do [Microsoft 365,](https://compliance.microsoft.com)acesse Gerenciamento de riscos do Insider e selecione **Configurações** de risco do **Insider** no canto superior direito de qualquer página.
2. Na página **Privacidade,** selecione uma configuração de privacidade para exibir nomes de usuário para alertas de política.
3. Na página **Indicadores,** selecione os indicadores de alerta que você deseja aplicar a todas as políticas de risco internas.

    >[!IMPORTANT]
    >Para receber alertas para atividades arriscadas definidas em suas políticas, selecione um ou mais indicadores. Se os indicadores não estão configurados em Configurações, os indicadores não serão selecionáveis em políticas de risco internas.

4. Na página **Períodos de tempo da** Política, selecione os [prazos](insider-risk-management-settings.md#policy-timeframes) de política para entrar em vigor para um usuário quando eles dispararem uma combinação para uma política de risco interna.
5. Na página **Detecções Inteligentes,** configure as seguintes configurações para políticas de risco internas:
    - [Exclusões de tipo de arquivo](insider-risk-management-settings.md#file-type-exclusions)
    - [Limites para atividade de arquivo incomum](insider-risk-management-settings.md#threshold-for-unusual-file-activity)
    - [Nível de volume de alerta](insider-risk-management-settings.md#alert-volume)
    - [Status de alerta do Microsoft Defender para Ponto de Extremidade](insider-risk-management-settings.md#microsoft-defender-for-endpoint-preview)
    - [Configurações de domínio](insider-risk-management-settings.md#domains-preview)
6. Na página **Exportar alertas,** habilita a exportação de informações de alerta de risco interno usando as APIs de Gerenciamento do Office 365, se necessário.
7. Na página **Grupos de usuários prioritários,** crie um grupo de usuários de prioridade e adicione usuários se não for criado na **Etapa 3**.
8. Na página **Fluxos do Power Automate,** configure um fluxo de modelos de fluxo de risco interno ou crie um novo fluxo. Consulte o [artigo Sobre como começar com as configurações](insider-risk-management-settings.md#power-automate-flows-preview) de gerenciamento de riscos insider para obter orientações passo a passo.
9. Na página **Ativos de** prioridade, configure ativos prioritários para usar dados de sua plataforma de controle físico e acesso importados pelo conector de danos físicos. Consulte o [artigo Sobre como começar com as configurações](insider-risk-management-settings.md#priority-physical-assets-preview) de gerenciamento de riscos insider para obter orientações passo a passo.
10. Na página **do Microsoft Teams,** habilita a integração do Microsoft Teams com o gerenciamento de riscos insider para criar automaticamente uma equipe para colaboração de caso ou usuário. Consulte o [artigo Sobre como começar com as configurações](insider-risk-management-settings.md#microsoft-teams-preview) de gerenciamento de riscos insider para obter orientações passo a passo.
11. Selecione **Salvar** para habilitar essas configurações para suas políticas de risco insider.

## <a name="step-6-create-an-insider-risk-management-policy"></a>Etapa 6: criar uma política de gerenciamento de riscos internas

As políticas de gerenciamento de riscos internas incluem usuários atribuídos e definem quais tipos de indicadores de risco são configurados para alertas. Antes que as atividades possam disparar alertas, uma política deve ser configurada. Use o assistente de política para criar novas políticas de gerenciamento de riscos internas.

1. No Centro de conformidade do [Microsoft 365,](https://compliance.microsoft.com)acesse Gerenciamento de riscos **do Insider** e selecione **a guia** Políticas.
2. Selecione **Criar política** para abrir o assistente de política.
3. Na página **Modelo de** Política, escolha uma categoria de política e selecione o modelo da nova política. Esses modelos são feitos de condições e indicadores que definem as atividades de risco que você deseja detectar e investigar. Revise os pré-requisitos do modelo, acionando eventos e atividades detectadas para confirmar que esse modelo de política atende às suas necessidades.

    >[!IMPORTANT]
    >Alguns modelos de política têm pré-requisitos que devem ser configurados para que a política gere alertas relevantes. Se você não configurou os pré-requisitos de política aplicável, consulte **a Etapa 4** acima.

4. Selecione **Próximo** para continuar.
5. Na página **Nome e descrição,** conclua os seguintes campos:
    - **Nome (obrigatório)**: Insira um nome amigável para a política. Esse nome não pode ser alterado após a criação da política.
    - **Descrição (opcional)**: Insira uma descrição para a política.

6. Selecione **Próximo** para continuar.
7. Na página **Usuários** e  grupos, selecione Incluir  todos os usuários e grupos ou Incluir usuários e grupos específicos para definir quais usuários ou grupos estão incluídos na política ou se você escolheu um modelo baseado em usuários prioritários; selecione **Adicionar ou editar grupos de usuários prioritários**. Selecionar **Incluir todos os usuários e grupos** procurará disparar eventos para todos os usuários e grupos em sua organização para começar a atribuir pontuações de risco para a política. Selecionar **Incluir usuários e grupos específicos** permite definir quais usuários e grupos atribuir à política.
8. Selecione **Próximo** para continuar.
9. Na página **Conteúdo para priorizar,** você pode atribuir (se necessário) as fontes a priorizar, o que aumenta a chance de gerar um alerta de alta gravidade para essas fontes. Selecione uma das seguintes opções:

    - **Quero especificar sites do SharePoint, rótulos de sensibilidade e/ou** tipos de informações confidenciais como conteúdo de prioridade. Selecionar essa opção permitirá que páginas de detalhes no assistente configurem esses canais.
    - Não quero especificar o conteúdo de prioridade agora (você poderá fazer isso depois que a **política for criada)**. Selecionar essa opção ignorará as páginas de detalhes do canal no assistente.

10. Selecione **Próximo** para continuar.

11. Se você selecionou Quero especificar sites do SharePoint, rótulos de sensibilidade **e/ou** tipos de informações confidenciais como conteúdo de prioridade na etapa anterior, você verá as páginas de detalhes para sites do *SharePoint,* tipos de informações confidenciais *e* rótulos de *sensibilidade.* Use essas páginas de detalhes para definir o SharePoint, tipos de informações confidenciais e rótulos de sensibilidade para priorizar na política.

    - **Sites do SharePoint**: Selecione **Adicionar site do SharePoint** e selecione os sites do SharePoint aos que você tem acesso e deseja priorizar. Por exemplo, *"group1@contoso.sharepoint.com/sites/group1"*.
    - **Tipo de informação confidenciais**: Selecione **Adicionar tipo de informação confidenciais** e selecione os tipos de sensibilidade que você deseja priorizar. Por exemplo, *"Número da* Conta Bancária dos EUA" e *"Número do Cartão de Crédito"*.
    - **Rótulos de sensibilidade**: **Selecione Adicionar rótulo de** sensibilidade e selecione os rótulos que você deseja priorizar. Por exemplo, *"Confidencial"* e *"Segredo"*.

12. Selecione **Próximo** para continuar.
13. Na página **Indicadores e eventos** de gatilho, você verá os indicadores que você definiu como disponíveis na página Indicadores de configurações de risco do [](insider-risk-management-settings.md#indicators) **Insider.**  >   Se você selecionou um modelo de *vazamentos* de dados no início do assistente, você deve selecionar uma política DLP na lista de menus suspenso de política **DLP** para habilitar indicadores de gatilho para a política ou selecionar o evento de disparo integrado.

    >[!IMPORTANT]
    >Se os indicadores nesta página não puderem ser selecionados, você precisará selecionar os indicadores que deseja habilitar para todas as políticas. Você pode usar o **botão Ativar indicadores** no assistente ou selecionar indicadores na página Indicadores de política de gerenciamento de riscos do **Insider.**  >    >  

    Selecione os indicadores que você deseja aplicar à política. Se você preferir não usar as configurações de limite de política padrão para esses indicadores, desabilite os limites padrão de uso **recomendados** pela Microsoft e insira os valores de limite para cada indicador selecionado.

    - Se você tiver selecionado pelo menos um indicador *do Office* ou *dispositivo,* selecione os impulsionadores de **pontuação** de risco conforme apropriado. Os impulsionadores de pontuação de risco só são aplicáveis para indicadores selecionados.
    - Se você tiver  selecionado um modelo de política de roubo  de dados ou *vazamentos* de dados, selecione um ou mais métodos de detecção de sequência e um método de detecção **cumulativa de exfiltração** a ser aplicado à política.

14. Selecione **Próximo** para continuar.
15. Na página **Limites de indicador,** selecione a opção para usar limites de indicador padrão ou para especificar limites personalizados para indicadores individuais. Para cada indicador, escolha o nível apropriado para gerar o nível desejado de alertas de atividade.
16. Selecione **Próximo** para continuar.
17. Na página **Revisão,** revise as configurações escolhidas para a política e quaisquer sugestões ou avisos para suas seleções. Selecione **Editar** para alterar qualquer um dos valores de política ou selecione **Enviar** para criar e ativar a política.

## <a name="next-steps"></a>Próximas etapas

Depois de concluir essas etapas para criar sua primeira política de gerenciamento de riscos insider, você começará a receber alertas de indicadores de atividade após cerca de 24 horas. Configure políticas adicionais conforme necessário usando as diretrizes na Etapa 4 deste artigo ou as etapas em Criar uma [nova política de risco interno.](insider-risk-management-policies.md#create-a-new-policy)

Para saber mais sobre como investigar alertas de risco interno e o **painel Alertas,** consulte Alertas de gerenciamento de riscos [do Insider.](insider-risk-management-alerts.md)
