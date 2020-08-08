---
title: Introdução à conformidade de comunicação
description: Configurar políticas de conformidade de comunicação para configurar comunicações do usuário para revisão.
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.SupervisoryReview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
- MOE150
ms.openlocfilehash: c61529b612079c93e3c175a67fccd32a7c561400
ms.sourcegitcommit: 9550298946f8accb90cd59be7b46b71d4bf4f8cc
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/08/2020
ms.locfileid: "46597561"
---
# <a name="get-started-with-communication-compliance"></a>Introdução à conformidade de comunicação

Use as políticas de conformidade de comunicação para identificar as comunicações do usuário para verificação por revisores internos ou externos. Para obter mais informações sobre como as políticas de conformidade de comunicação podem ajudá-lo a monitorar as comunicações em sua organização, consulte [políticas de conformidade de comunicação no Microsoft 365](communication-compliance.md). Se você quiser rever como a contoso configurou rapidamente uma política de conformidade de comunicação para monitorar a linguagem ofensiva no Microsoft Teams, Exchange Online e comunicações do Yammer, confira este [estudo de caso](communication-compliance-case-study.md).

## <a name="before-you-begin"></a>Antes de começar

Antes de começar a manter a conformidade de comunicação, você deve confirmar sua [assinatura do Microsoft 365](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans) e quaisquer Complementos. Para acessar e usar a conformidade de comunicação, sua organização deve ter uma das seguintes assinaturas ou Complementos:

- Assinatura do Microsoft 365 E5 (versão paga ou de avaliação)
- Assinatura do Microsoft 365 E3 + o complemento de conformidade do Microsoft 365 e5
- Assinatura do Microsoft 365 E3 + o complemento de gerenciamento de risco do Microsoft 365 E5 Insider
- Assinatura do Microsoft 365 a5 (versão paga ou de avaliação)
- Assinatura do 365 a3 + o complemento de conformidade do Microsoft 365 a5
- Assinatura do 365 a3 + o complemento de gerenciamento de risco Microsoft 365 a5 Insider
- Assinatura do Microsoft 365 G5 (versão paga ou de avaliação)
- Assinatura do Microsoft 365 G5 + o suplemento de conformidade do Microsoft 365 G5
- Assinatura do Microsoft 365 G5 + o complemento de gerenciamento de risco do Microsoft 365 G5 Insider
- Assinatura do Office 365 Enterprise E5 (versão paga ou de avaliação)
- Assinatura do Office 365 Enterprise E3 + o complemento avançado de conformidade do Office 365 (não está mais disponível para novas assinaturas, consulte observação)

Os usuários incluídos nas políticas de conformidade de comunicação devem receber uma das licenças acima.

>[!IMPORTANT]
>O Office 365 Advanced Compliance não é mais vendido como uma assinatura autônoma. Quando as assinaturas atuais expiram, os clientes devem fazer a transição para uma das assinaturas acima, que contêm o mesmo ou outros recursos de conformidade.

Se você não tiver um plano existente do Office 365 Enterprise E5 e quiser experimentar o gerenciamento de risco do Insider, você pode [Adicionar o Microsoft 365](https://docs.microsoft.com/office365/admin/try-or-buy-microsoft-365) à sua assinatura existente ou [inscrever-se em uma avaliação](https://www.microsoft.com/microsoft-365/enterprise) do Office 365 Enterprise e5.

## <a name="step-1-required-enable-permissions-for-communication-compliance"></a>Etapa 1 (obrigatório): Habilitar permissões para conformidade de comunicação

>[!Important]
>Por padrão, os administradores globais não têm acesso aos recursos de conformidade de comunicação. As funções atribuídas nesta etapa são necessárias para que qualquer recurso de conformidade de comunicação possa ser acessado.

Há cinco funções usadas para configurar permissões para gerenciar recursos de conformidade de comunicação. Para tornar a **conformidade de comunicação** disponível como uma opção de menu no centro de conformidade do Microsoft 365 e para continuar com essas etapas de configuração, você deve receber a função de administrador de conformidade de *comunicação* .

Dependendo de como você deseja gerenciar políticas e alertas de comunicação, você precisará criar um ou mais novos grupos de função para administradores, revisores e investigadores. Você tem a opção de atribuir usuários a grupos de função específicos para gerenciar diferentes áreas de recursos de conformidade de comunicação. Ou você pode decidir criar um grupo de função e atribuir todas as funções de conformidade de comunicação ao grupo. Crie um único grupo de função ou vários grupos de função para atender melhor aos seus requisitos de gerenciamento de conformidade.

Escolha uma destas opções de função ao configurar seus grupos de função de conformidade de comunicação:

|**Função**|**Permissões de função**|
|:-----|:-----|
| **Administração de conformidade de comunicação** | Os usuários atribuídos a essa função podem criar, ler, atualizar e excluir políticas de conformidade de comunicação, configurações globais e atribuições de grupos de função. Os usuários atribuídos a essa função não podem exibir alertas de mensagem. |
| **Análise de conformidade de comunicação** | Os usuários atribuídos a essa função podem exibir as políticas em que foram atribuídas como revisores, Exibir metadados de mensagem (não o conteúdo da mensagem), escalonar para revisores adicionais ou enviar notificações aos usuários. Os analistas não podem resolver alertas pendentes. |
| **Investigação de conformidade de comunicação** | Os usuários atribuídos a essa função podem exibir metadados e conteúdo de mensagens, escalonar para revisores adicionais, escalonar para uma ocorrência de descoberta eletrônica avançada, enviar notificações aos usuários e resolver o alerta. |
| **Visualizador de conformidade de comunicação** | Os usuários atribuídos a essa função podem acessar todos os widgets de relatório na home page de conformidade de comunicação e podem exibir todos os relatórios de conformidade de comunicação. |
| **Gerenciamento de casos de conformidade de comunicação** | Os usuários atribuídos a essa função podem gerenciar casos e agir em alertas. Essa função é necessária para criar grupos de funções personalizados para administradores, analistas e investigadores. Os grupos personalizados para visualizadores não precisam dessa função atribuída. |

### <a name="option-1-create-a-new-role-group-with-all-communication-compliance-roles"></a>Opção 1: criar um novo grupo de função com todas as funções de conformidade de comunicação

1. Entre [https://protection.office.com/permissions](https://protection.office.com/permissions) usando as credenciais de uma conta de administrador na sua organização do Microsoft 365.

2. No centro de &amp; conformidade de segurança, acesse **permissões**. Selecione o link para exibir e gerenciar funções no Office 365.

3. Selecione **Criar**.

4. No campo **nome** , dê um nome amigável ao novo grupo de funções. Selecione **Avançar**.

5. Selecione **escolher funções** e, em seguida, selecione **Adicionar**. Marque as caixas de seleção das seguintes funções:

    - Administração de conformidade de comunicação
    - Análise de conformidade de comunicação
    - Investigação de conformidade de comunicação
    - Visualizador de conformidade de comunicação
    - Gerenciamento de casos de conformidade de comunicação

    ![Funções de conformidade de comunicação](../media/communication-compliance-case-roles.png)

6. Selecione **Adicionar** e **concluir**e, em seguida, selecione **Avançar** para continuar.

7. Selecione **escolher Membros** e selecione **Adicionar**. Marque a caixa de seleção de todos os usuários e grupos que você deseja criar políticas e gerenciar mensagens com correspondências de política e, em seguida, selecione **Adicionar** e **concluir**. Selecione **Avançar**.

8. Selecione **Criar grupo de função** para concluir.

### <a name="option-2-create-new-role-groups-with-different-communication-compliance-roles"></a>Opção 2: criar novos grupos de função com diferentes funções de conformidade de comunicação

Crie vários grupos de função para segmentar o acesso à conformidade de comunicação e as responsabilidades entre diferentes usuários da organização. Para cada novo grupo de funções, você atribuirá diferentes funções de conformidade de comunicação.

1. Entre [https://protection.office.com/permissions](https://protection.office.com/permissions) usando as credenciais de uma conta de administrador na sua organização do Microsoft 365.

2. No centro de &amp; conformidade de segurança, acesse **permissões**. Selecione o link para exibir e gerenciar funções no Office 365.

3. Selecione **Criar**.

4. No campo **nome** , dê um nome amigável ao novo grupo de funções. Selecione **Avançar**.

5. Selecione **escolher funções** e, em seguida, selecione **Adicionar**. Marque a caixa de seleção para as funções de conformidade de comunicação que você deseja atribuir a este grupo. Por exemplo, se esse grupo de função for analista de conformidade em sua organização, você selecionará as funções de gerenciamento de *casos de conformidade* de comunicação e *análise de conformidade de comunicação* . Se esse grupo de função é para os investigadores de conformidade, você deve selecionar as funções de *Gerenciamento de casos de conformidade* de *conformidade e investigação de conformidade* de comunicação.

    ![Funções de conformidade de comunicação](../media/communication-compliance-analysts-role-group.png)

6. Selecione **Adicionar** e **concluir**e, em seguida, selecione **Avançar** para continuar.

7. Selecione **escolher Membros** e selecione **Adicionar**. Marque a caixa de seleção de todos os usuários e grupos que você deseja criar políticas e gerenciar mensagens com correspondências de política e, em seguida, selecione **Adicionar** e **concluir**. Selecione **Avançar**.

8. Selecione **Criar grupo de função** para concluir.

9. Crie grupos de função de conformidade de comunicação adicionais, conforme necessário.

Para obter mais informações sobre grupos de funções e permissões, consulte [permissões no centro de conformidade](../security/office-365-security/protect-against-threats.md).

## <a name="step-2-required-enable-the-audit-log"></a>Etapa 2 (obrigatório): habilitar o log de auditoria

A conformidade com comunicações requer logs de auditoria para mostrar alertas e rastrear ações de correção realizadas por revisores. Os logs de auditoria são um resumo de todas as atividades associadas a uma política organizacional definida ou a qualquer momento em que uma política de conformidade de comunicação é alterada.

Para obter instruções passo a passo para ativar a auditoria, consulte [Ativar ou desativar a pesquisa de log de auditoria](turn-audit-log-search-on-or-off.md). Depois que você ativar a auditoria, será exibida uma mensagem dizendo que o log de auditoria está sendo preparado e que você pode executar uma pesquisa em algumas horas após a conclusão da preparação. Você só precisa executar esta ação uma vez. Para obter mais informações sobre o uso do log de auditoria, consulte [Search the Audit Log](search-the-audit-log-in-security-and-compliance.md).

## <a name="step-3-optional-set-up-groups-for-communication-compliance"></a>Etapa 3 (opcional): configurar grupos para conformidade de comunicação

 Ao criar uma política de conformidade de comunicação, você define quem tem suas comunicações revisadas e quem realiza as revisões. Na política, você usará endereços de email para identificar pessoas ou grupos de pessoas. Para simplificar a configuração, você pode criar grupos para pessoas que tenham suas comunicações revisadas e grupos para pessoas que revisam essas comunicações. Se você estiver usando grupos, poderá precisar de vários. Por exemplo, se você quiser monitorar as comunicações entre dois grupos distintos de pessoas ou se quiser especificar um grupo que não será supervisionado.

Use o gráfico a seguir para ajudá-lo a configurar grupos na sua organização para políticas de conformidade de comunicação:

| **Membro de política** | **Grupos com suporte** | **Grupos sem suporte** |
|:-----|:-----|:-----|
|Usuários supervisionados <br> Usuários não supervisionados | Grupos de distribuição <br> Grupos do Microsoft 365 | Grupos dinâmicos de distribuição |
| Revisores | Nenhuma | Grupos de distribuição <br> Grupos dinâmicos de distribuição <br> Grupos de segurança habilitados para email |
  
Quando você atribui um grupo de distribuição na política, a política monitora todos os emails de cada usuário no grupo de distribuição. Quando você atribui um grupo do Microsoft 365 na política, a política monitora todos os emails enviados para esse grupo, não os emails individuais recebidos por cada membro do grupo.

Se você é uma organização com uma implantação local do Exchange ou um provedor de email externo e deseja monitorar os bate-papos do Microsoft Teams para seus usuários, você deve criar um grupo de distribuição para os usuários com caixas de correio locais ou externas para monitorar. Posteriormente nestas etapas, você atribuirá esse grupo de distribuição como a seleção de **usuários e grupos supervisionados** no assistente de política.

>[!IMPORTANT]
>Você deve arquivar uma solicitação com o suporte da Microsoft para permitir que sua organização Use a interface gráfica do usuário no centro de conformidade de & de segurança para pesquisar dados de chat do teams para usuários locais. Para obter mais informações, consulte [pesquisando caixas de correio baseadas em nuvem para usuários locais](search-cloud-based-mailboxes-for-on-premises-users.md).

Para obter mais informações sobre a configuração de grupos, consulte:

- [Criar e gerenciar grupos de distribuição](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-distribution-groups/manage-distribution-groups)
- [Visão geral dos grupos do Microsoft 365](https://docs.microsoft.com/office365/admin/create-groups/office-365-groups?view=o365-worldwide)

## <a name="step-4-optional-verify-your-yammer-tenant-is-in-native-mode"></a>Etapa 4 (opcional): Verifique se seu locatário do Yammer está no modo nativo

No modo nativo, todos os usuários do Yammer estão no Azure Active Directory (AAD), todos os grupos são grupos do Office 365 e todos os arquivos são armazenados no SharePoint Online. Seu locatário do Yammer deve estar no modo nativo para políticas de conformidade de comunicação para examinar e identificar conversas arriscadas em mensagens privadas e conversas da Comunidade no Yammer.

Para obter mais informações sobre como configurar o Yammer no modo nativo, consulte:

- [Visão geral do modo nativo do Yammer no Microsoft 365](https://docs.microsoft.com/yammer/configure-your-yammer-network/overview-native-mode)
- [Configurar sua rede do Yammer para o modo Nativo para o Microsoft 365](https://docs.microsoft.com/yammer/configure-your-yammer-network/native-mode)

## <a name="step-5-required-create-a-communication-compliance-policy"></a>Etapa 5 (obrigatório): criar uma política de conformidade de comunicação
  
>[!Important]
>Não há suporte para o uso do PowerShell para criar e gerenciar políticas de conformidade de comunicação. Para criar e gerenciar essas políticas, você deve usar os controles de gerenciamento de políticas na [solução de conformidade de comunicação do Microsoft 365](https://compliance.microsoft.com/supervisoryreview).

1. Entre [https://compliance.microsoft.com](https://compliance.microsoft.com) usando as credenciais de uma conta de administrador na sua organização do Microsoft 365.

2. No centro de conformidade da Microsoft 365, selecione **conformidade de comunicação**.
  
3. Selecione a guia **políticas** .

4. Selecione **criar política** para criar e configurar uma nova política de um modelo ou para criar e configurar uma política personalizada.

    Se você escolher um modelo de política para criar uma política, você irá:

    - Confirme ou atualize o nome da política. Os nomes de política não podem ser alterados depois que a política é criada.
    - Escolha os usuários ou grupos para supervisionar, incluindo a escolha de usuários ou grupos que você gostaria de excluir.
    - Escolha os revisores da política. Os revisores são usuários individuais e todos os revisores devem ter caixas de correio hospedadas no Exchange Online. Os revisores adicionados aqui são os revisores que você pode escolher ao escalonar um alerta no fluxo de trabalho de investigação e correção. Quando os revisores são adicionados a uma política, eles recebem automaticamente uma mensagem de email que os notifica da atribuição à política e fornece links para informações sobre o processo de revisão.
    - Escolha um campo condição limitada, geralmente um tipo de informação confidencial ou um dicionário de palavras-chave para aplicar à política.

    Se você optar por usar o assistente de política para criar uma política personalizada, você irá:

    - Forneça um nome e uma descrição para a política. Os nomes de política não podem ser alterados depois que a política é criada.
    - Escolha os usuários ou grupos para supervisionar, incluindo todos os usuários em sua organização, usuários e grupos específicos ou outros usuários e grupos que você gostaria de excluir.
    - Escolha os revisores da política. Os revisores são usuários individuais e todos os revisores devem ter caixas de correio hospedadas no Exchange Online. Os revisores adicionados aqui são os revisores que você pode escolher ao escalonar um alerta no fluxo de trabalho de investigação e correção. Quando os revisores são adicionados a uma política, eles recebem automaticamente uma mensagem de email que os notifica da atribuição à política e fornece links para informações sobre o processo de revisão.
    - Escolha os canais de comunicação para verificação, incluindo Exchange, Microsoft Teams, Yammer ou Skype for Business. Você também pode optar por verificar fontes de terceiros se tiver configurado um conector no Microsoft 365.
    - Escolha a direção de comunicação para monitorar, incluindo comunicações de entrada, de saída ou internas.
    - Definir as [condições](communication-compliance-feature-reference.md#ConditionalSettings)de política de conformidade de comunicação. Você pode escolher entre as condições endereço da mensagem, palavra-chave, tipos de arquivo e correspondência de tamanho.
    - Escolha se você deseja incluir tipos de informações confidenciais. Esta etapa é onde você pode selecionar os tipos de informações confidenciais padrão e personalizadas. Escolha de tipos de informações confidenciais personalizados existentes ou dicionários de palavras-chave personalizados no assistente de política de conformidade de comunicação. Você pode criar esses itens antes de executar o assistente, se necessário. Você também pode criar novos tipos de informações confidenciais de dentro do assistente de política de conformidade de comunicação.
    - Escolha se você deseja habilitar classificadores. Os classificadores podem detectar linguagem e imagens inadequadas enviadas ou recebidas no corpo de mensagens de email ou outros tipos de texto. Você pode escolher os seguintes classificadores internos: *ameaça*, *profanação*, *assédio dirigido*, *imagens adultas*, *imagens Racy*e *imagens do Gory*.

    >[!CAUTION]
    >Vamos substituir o classificador interno **Idioma Ofensivo** porque ele tem uma grande quantidade de falsos positivos. Não usá-lo e, se estiver usando, você deverá mover seus processos de negócios para fora dele. Recomendamos usar os classificadores internos **contra ameaças**, **obscenas**e de **assédio direcionado** .

    - Defina a porcentagem de comunicação a ser revisada.
    - Revise suas seleções de política e crie a política.

5. Selecione **criar política** ao usar os modelos ou **Enviar** ao usar o assistente de política personalizada.

6. A página **sua política foi criada** é exibida com diretrizes sobre quando a política será ativada e quais comunicações serão capturadas.

## <a name="step-6-optional-create-notice-templates-and-configure-user-anonymization"></a>Etapa 6 (opcional): criar modelos de aviso e configurar anonimato de usuário

Se você deseja ter a opção de responder a um alerta de política enviando um aviso de lembrete para o usuário associado, você precisará criar pelo menos um modelo de aviso em sua organização. Os campos de modelo de aviso são editáveis antes de serem enviados como parte do processo de correção de alerta e a criação de um modelo de aviso personalizado para cada política de conformidade de comunicação é recomendada.

Você também pode optar por habilitar a anonimato para os nomes de userexibição ao investigar as correspondências de política e realizar ações em mensagens.

1. Entre [https://compliance.microsoft.com](https://compliance.microsoft.com) usando as credenciais de uma conta de administrador na sua organização do Microsoft 365.

2. No centro de conformidade da Microsoft 365, vá para **conformidade de comunicação**.

3. Para configurar a anonimato para nomes de usernames, selecione a guia **privacidade** .

4. Para habilitar a anonimato, selecione **Mostrar versões em anonimato de nomes de**User.

5. Selecione **Salvar**.

6. Navegue até a guia **modelos de aviso** e selecione **criar modelo de aviso**.

7. Na página **modificar um modelo de aviso** , preencha os seguintes campos:

    - Nome do modelo (obrigatório)
    - Enviar de (obrigatório)
    - CC e Cco (opcional)
    - Assunto (obrigatório)
    - Corpo da mensagem (obrigatório)

8. Selecione **salvar** para criar e salvar o modelo de aviso.

## <a name="step-7-optional-test-your-communication-compliance-policy"></a>Etapa 7 (opcional): testar sua política de conformidade de comunicação

Depois de criar uma política de conformidade de comunicação, é recomendável testá-la para garantir que as condições definidas estejam sendo aplicadas corretamente pela política. Você também pode querer [testar suas políticas de DLP (prevenção de perda de dados)](create-test-tune-dlp-policy.md) se suas políticas de conformidade de comunicação incluírem tipos de informações confidenciais. Certifique-se de que você dá às suas políticas tempo de ativação para que as comunicações que você deseja testar sejam capturadas.

Siga estas etapas para testar sua política de conformidade de comunicação:

1. Abra um cliente de email, Microsoft Teams ou Yammer enquanto estiver conectado como um usuário supervisionado definido na política que você deseja testar.
2. Envie uma mensagem de email, chat do Microsoft Teams ou Yammer que atenda aos critérios definidos na política de conformidade de comunicação. Este teste pode ser uma palavra-chave, o tamanho do anexo, o domínio, etc. Certifique-se de determinar se as configurações condicionais configuradas na política são muito restritivas ou muito lenients.

    > [!NOTE]
    > As comunicações em todos os canais de origem podem levar até 24 horas para serem processadas completamente em uma política.

3. Entre no Microsoft 365 como um revisor designado na política de conformidade de comunicação. Navegue até alertas de **conformidade de comunicação**  >  **Alerts** para exibir os alertas de suas políticas.

4. Corrija o alerta usando os controles de correção e verifique se o alerta foi resolvido corretamente.

## <a name="next-steps"></a>Próximas etapas

Depois de concluir essas etapas para criar sua primeira política de conformidade de comunicação, você começará a receber alertas de indicadores de atividade após cerca de 24 horas. Configure políticas adicionais conforme necessário usando as orientações da etapa 5 deste artigo.

Para saber mais sobre a investigação de alertas de conformidade de comunicação, consulte [investigar e corrigir alertas de conformidade de comunicação](communication-compliance-investigate-remediate.md).
