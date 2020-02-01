---
title: Configurar conformidade de comunicação (versão prévia)
description: Configurar políticas de conformidade de comunicação para configurar comunicações de funcionários para revisão.
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
ms.openlocfilehash: 24c87b8244b2dc53f58a07784c07231fb1588121
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2020
ms.locfileid: "41595838"
---
# <a name="configure-communication-compliance-in-microsoft-365-preview"></a>Configurar a conformidade em comunicações no Microsoft 365 (visualização)

> [!IMPORTANT]
> Este tópico se aplica à configuração da conformidade de comunicação em uma assinatura do Microsoft 365. Se você quiser configurar políticas de supervisão para uma assinatura do Office 365, consulte [Configure supervisão for Office 365](supervision-policies.md).

Use políticas de conformidade de comunicação para capturar comunicações de funcionários para verificação por revisores internos ou externos. Para obter mais informações sobre como as políticas de conformidade de comunicação podem ajudá-lo a monitorar as comunicações em sua organização, consulte [políticas de conformidade de comunicação no Microsoft 365](communication-compliance.md).

> [!NOTE]
> Os usuários monitorados por políticas de conformidade de comunicação devem ter uma licença de conformidade do Microsoft 365 e5, uma licença do Office 365 Enterprise E3 com o complemento de conformidade avançada ou ser incluído em uma assinatura do Office 365 Enterprise e5.
> Se você não tem um plano Enterprise E5 existente e deseja tentar a conformidade de comunicação, pode [se inscrever para uma avaliação do Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).
  
Siga estas etapas para configurar e usar a conformidade de comunicação em sua organização do Microsoft 365:
  
- **Etapa 1 (opcional)**: [configurar grupos para conformidade de comunicação](#step-1-set-up-groups-for-communication-compliance-optional) 

    Antes de começar a usar a conformidade de comunicação, determine quem precisa de comunicações revisadas e quem realiza as revisões. Se você quiser começar com apenas alguns usuários para ver como funciona a conformidade de comunicação, você pode ignorar a configuração de grupos por enquanto.

- **Etapa 2 (obrigatório)**: [tornar a conformidade de comunicação disponível em sua organização](#step-2-make-communication-compliance-available-in-your-organization-required)

    Adicione a si mesmo à função de **administrador de análise de supervisão** para que você possa configurar políticas. Você também precisará criar um novo grupo com o **administrador de análise de supervisão**, o gerenciamento de **casos**e as funções de **revisão** para pessoas ou grupos que terão medidas investigativas e de correção em mensagens com correspondências de política. Qualquer pessoa que tenha essas funções atribuídas pode acessar a página **conformidade de comunicação** no centro de conformidade da Microsoft 365. Se o email reviewable estiver hospedado no Exchange Online, cada revisor deverá ter [acesso ao PowerShell remoto para o Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online/disable-access-to-exchange-online-powershell).

- **Etapa 3 (obrigatório)**: [Configurar uma política de conformidade de comunicação](#step-3-create-a-communication-compliance-policy-required)

    Você cria políticas de conformidade de comunicação no centro de conformidade da Microsoft 365. Essas políticas definem quais comunicações estão sujeitas a análise em sua organização e especifica quem realiza as revisões. As comunicações incluem email, Microsoft Teams, Skype for Business e comunicações de plataforma de terceiros (como Facebook, Twitter, etc.).

- **Etapa 4 (opcional)**: [criar modelos de aviso de funcionário](#step-4-create-employee-notice-templates-optional)

    Criar modelos de aviso personalizados para enviar notificações por email aos funcionários como uma opção de correção para correspondências de política.

- **Etapa 5 (opcional)**: [testar sua política de conformidade de comunicação](#step-5-test-your-communication-compliance-policy-optional)

    Teste sua política de conformidade de comunicação para garantir que ela funcione conforme o desejado. É importante garantir que sua estratégia de conformidade esteja atendendo aos padrões.

- **Etapa 6 (opcional)**: [habilitar a auditoria para suas políticas de conformidade de comunicação](#step-6-enable-auditing-for-your-communication-compliance-policies-optional)

    Habilite a auditoria da sua organização para registrar atividades de gerenciamento para políticas de conformidade de comunicação.

## <a name="step-1-set-up-groups-for-communication-compliance-optional"></a>Etapa 1: configurar grupos para conformidade de comunicação (opcional)

 Ao criar uma política de conformidade de comunicação, você define quem tem suas comunicações revisadas e quem realiza as revisões. Na política, você usará endereços de email para identificar pessoas ou grupos de pessoas. Para simplificar a configuração, você pode criar grupos para pessoas que tenham suas comunicações revisadas e grupos para pessoas que revisam essas comunicações. Se você estiver usando grupos, poderá precisar de vários. Por exemplo, se você quiser monitorar as comunicações entre dois grupos distintos de pessoas ou se quiser especificar um grupo que não será supervisionado.

Use o gráfico a seguir para ajudá-lo a configurar grupos na sua organização para políticas de conformidade de comunicação:

| **Membro de política** | **Grupos com suporte** | **Grupos sem suporte** |
|:-----|:-----|:-----|
|Usuários supervisionados <br> Usuários não supervisionados | Grupos de distribuição <br> Grupos do Office 365 | Grupos dinâmicos de distribuição |
| Revisores | Grupos de segurança habilitados para email  | Grupos de distribuição <br> Grupos dinâmicos de distribuição |
  
Quando você seleciona um grupo do Office 365 para usuários supervisionados, a política monitora o conteúdo da caixa de correio compartilhada do Office 365 e os canais do Microsoft Teams associados ao grupo. Quando você seleciona uma lista de distribuição, a política monitora caixas de correio de usuários individuais.

Para obter mais informações sobre a configuração de grupos, consulte:

- [Criar e gerenciar grupos de distribuição](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-distribution-groups/manage-distribution-groups)
- [Gerenciar grupos de segurança habilitados para email](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-mail-enabled-security-groups)
- [Visão geral dos grupos do Office 365](https://docs.microsoft.com/office365/admin/create-groups/office-365-groups?view=o365-worldwide)

## <a name="step-2-make-communication-compliance-available-in-your-organization-required"></a>Etapa 2: tornar a conformidade de comunicação disponível em sua organização (obrigatório)

> [!Important]
> Por padrão, os administradores globais não têm acesso aos recursos de conformidade de comunicação. As funções atribuídas nesta etapa são necessárias para que qualquer recurso de conformidade de comunicação possa ser acessado.

Para tornar a **conformidade de comunicação** disponível como uma opção de menu no centro de conformidade do Microsoft 365, você deve receber a função de administrador de análise de **supervisão** . Além disso, para investigar e corrigir mensagens com correspondências de política, você deve criar um grupo para revisores com o **administrador de análise de supervisão**, o gerenciamento de **casos**e as funções de **revisão** .

### <a name="create-a-new-role-group"></a>Criar um novo grupo de função

1. Entre [https://protection.office.com/permissions](https://protection.office.com/permissions) usando as credenciais de uma conta de administrador na sua organização do Microsoft 365.

2. No centro de segurança e conformidade do Microsoft Office 365, acesse **permissões**. Selecione o link para exibir e gerenciar funções no Office 365.

3. Selecione **Criar**.

4. No campo **nome** , dê um nome amigável ao novo grupo de funções. Selecione **Avançar**.

5. Selecione **escolher funções** e, em seguida, selecione **Adicionar**. Marque a caixa de seleção para **administrador de análise de supervisão**, gerenciamento de **casos**e **revisão**e, em seguida, selecione **Adicionar** e **concluir**. Selecione **Avançar**.

    ![Grupos de função de conformidade de comunicação necessária](media/communication-compliance-role-groups.png)

6. Selecione **escolher Membros** e selecione **Adicionar**. Marque a caixa de seleção de todos os usuários e grupos que você deseja criar políticas e gerenciar mensagens com correspondências de política e, em seguida, selecione **Adicionar** e **concluir**. Selecione **Avançar**.

7. Selecione **Criar grupo de função** para concluir.

Para obter mais informações sobre grupos de funções e permissões, consulte [permissões no centro de conformidade](../security/office-365-security/protect-against-threats.md).

## <a name="step-3-create-a-communication-compliance-policy-required"></a>Etapa 3: criar uma política de conformidade de comunicação (obrigatório)
  
1. Entre [https://compliance.microsoft.com](https://compliance.microsoft.com) usando as credenciais de uma conta de administrador na sua organização do Microsoft 365.

2. No centro de conformidade da Microsoft 365, selecione **conformidade de comunicação**.
  
3. Selecione a guia **políticas** .

4. Selecione **criar política** para criar e configurar uma nova política de um modelo ou para criar e configurar uma política personalizada.

    Se você escolher um modelo de política para criar uma política, você irá:

    - Confirme ou atualize o nome da política. Os nomes de política não podem ser alterados depois que a política é criada.
    - Escolha os usuários ou grupos para supervisionar, incluindo a escolha de usuários ou grupos que você gostaria de excluir.
    - Escolha os revisores da política. Os revisores podem ser usuários individuais ou [grupos de segurança habilitados para email](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-mail-enabled-security-groups#create-a-mail-enabled-security-group). Todos os revisores devem ter caixas de correio hospedadas no Exchange Online.
    - Escolha um campo condição limitada, geralmente um tipo de informação confidencial ou um dicionário de palavras-chave para aplicar à política.

    Se você optar por usar o assistente de política para criar uma política personalizada, você irá:

    - Forneça um nome e uma descrição para a política. Os nomes de política não podem ser alterados depois que a política é criada.
    - Escolha os usuários ou grupos para supervisionar, incluindo todos os usuários em sua organização, usuários e grupos específicos ou outros usuários e grupos que você gostaria de excluir. -
    - Escolha os revisores da política. Os revisores podem ser usuários individuais ou [grupos de segurança habilitados para email](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-mail-enabled-security-groups#create-a-mail-enabled-security-group). Todos os revisores devem ter caixas de correio hospedadas no Exchange Online.
    - Escolha os canais de comunicação a serem verificados, incluindo o Exchange, o Microsoft Teams ou o Skype for Business. Você também pode optar por verificar fontes de terceiros se tiver configurado um conector no Microsoft 365.
    - Escolha a direção de comunicação para monitorar, incluindo comunicações de entrada, de saída ou internas.
    - Definir as [condições](communication-compliance-feature-reference.md#ConditionalSettings)de política de conformidade de comunicação. Você pode escolher entre as condições endereço da mensagem, palavra-chave, tipos de arquivo e correspondência de tamanho.
    - Escolha se você deseja incluir tipos de informações confidenciais. Esta etapa é onde você pode selecionar os tipos de informações confidenciais padrão e personalizadas. Escolha de tipos de informações confidenciais personalizados existentes ou dicionários de palavras-chave personalizados no assistente de política de conformidade de comunicação. Você pode criar esses itens antes de executar o assistente, se necessário. Você também pode criar novos tipos de informações confidenciais de dentro do assistente de política de conformidade de comunicação.
    - Escolha se você deseja habilitar o classificador de idiomas ofensivo. Esse classificador detecta o idioma inapropriado enviado ou recebido no corpo de mensagens de email.
    - Defina a porcentagem de comunicação a ser revisada.
    - Revise suas seleções de política e crie a política.

5. Selecione **criar política** ao usar os modelos ou **Enviar** ao usar o assistente de política personalizada.

6. A página **sua política foi criada** é exibida com diretrizes sobre quando a política será ativada e quais comunicações serão capturadas.

## <a name="step-4-create-employee-notice-templates-optional"></a>Etapa 4: criar modelos de aviso de funcionário (opcional)

Se você deseja ter a opção de responder a um alerta de política enviando um aviso de lembrete para o funcionário associado, você precisará criar pelo menos um modelo de aviso em sua organização. Os campos de modelo de aviso são editáveis antes de serem enviados como parte do processo de correção de alerta e a criação de um modelo de aviso personalizado para cada política de conformidade de comunicação é recomendada.

1. Entre [https://compliance.microsoft.com](https://compliance.microsoft.com) usando as credenciais de uma conta de administrador na sua organização do Microsoft 365.

2. No centro de conformidade da Microsoft 365, vá para **conformidade de comunicação**.

3. Selecione a guia **modelos de aviso** e, em seguida, selecione **criar modelo de aviso**.

4. Na página **modificar um modelo de aviso** , preencha os seguintes campos:

    - Nome do modelo de aviso (obrigatório)
    - Enviar de (obrigatório)
    - CC e Cco (opcional)
    - Assunto (obrigatório)
    - Corpo da mensagem (obrigatório)

5. Selecione **salvar** para criar e salvar o modelo de aviso.

## <a name="step-5-test-your-communication-compliance-policy-optional"></a>Etapa 5: testar sua política de conformidade de comunicação (opcional)

Depois de criar uma política de conformidade de comunicação, é recomendável testá-la para garantir que as condições definidas estejam sendo aplicadas corretamente pela política. Você também pode querer [testar suas políticas de DLP (prevenção de perda de dados)](create-test-tune-dlp-policy.md) se suas políticas de conformidade de comunicação incluírem tipos de informações confidenciais. Certifique-se de que você dá às suas políticas tempo de ativação para que as comunicações que você deseja testar sejam capturadas.

Siga estas etapas para testar sua política de conformidade de comunicação:

1. Abra um cliente de email ou o Microsoft Teams enquanto estiver conectado como um usuário supervisionado definido na política que você deseja testar.
2. Envie um email ou chat do Microsoft Teams que atendam aos critérios definidos na política de conformidade de comunicação. Este teste pode ser uma palavra-chave, o tamanho do anexo, o domínio, etc. Certifique-se de determinar se as configurações condicionais configuradas na política são muito restritivas ou muito lenients.

    > [!NOTE]
    > As comunicações em todos os canais de origem podem levar até 24 horas para serem processadas completamente em uma política.

3. Entre no Microsoft 365 como um revisor designado na política de conformidade de comunicação. Navegue até **** > **alertas** de conformidade de comunicação para exibir os alertas de suas políticas.

4. Corrija o alerta usando os controles de correção e verifique se o alerta foi resolvido corretamente.

## <a name="step-6-enable-auditing-for-your-communication-compliance-policies-optional"></a>Etapa 6: habilitar a auditoria para suas políticas de conformidade de comunicação (opcional)

Depois de testar as políticas, convém habilitar a auditoria para que as atividades associadas ao gerenciamento de conformidade de comunicação sejam registradas. Isso pode ser um resumo de todas as atividades associadas a uma política organizacional definida ou a qualquer momento em que uma política de conformidade de comunicação é alterada.

Quando a auditoria está habilitada, as políticas de conformidade de comunicação têm trilhas de auditoria internas para a preparação completa para auditorias internas ou externas. Você pode usar o controle **Exportar atividades de revisão** na página principal de qualquer política para gerar um arquivo de auditoria ou exibir atividades de auditoria no log de auditoria unificada se a auditoria estiver habilitada.

Para ativar a auditoria, clique em **iniciar a gravação da atividade de administrador e usuário** na página **pesquisa de log de auditoria** no centro de conformidade & segurança do Office 365. Se você não vir esse link, significa que a auditoria já está ativada na sua organização. Depois que você ativar a auditoria, será exibida uma mensagem dizendo que o log de auditoria está sendo preparado e que você pode executar uma pesquisa em algumas horas após a conclusão da preparação. Isso só precisa ser feito uma vez. Para obter mais informações sobre o log de auditoria, consulte [Search the Audit Log](search-the-audit-log-in-security-and-compliance.md).

