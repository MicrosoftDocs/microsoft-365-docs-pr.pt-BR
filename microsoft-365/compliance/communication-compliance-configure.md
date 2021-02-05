---
title: Introdução à conformidade de comunicação
description: Configure políticas de conformidade de comunicação para configurar as comunicações do usuário para revisão.
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
- m365-security-compliance
- m365solution-insiderrisk
- m365initiative-compliance
search.appverid:
- MET150
- MOE150
ms.openlocfilehash: 442f0dd13415c4ca435cdf69336d1fb07a9e045d
ms.sourcegitcommit: fa5659cb66d84dcfeebc03b47bd9d38017d8934d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2021
ms.locfileid: "50109920"
---
# <a name="get-started-with-communication-compliance"></a>Introdução à conformidade de comunicação

Use as políticas de conformidade de comunicação para identificar as comunicações do usuário para análise pelos revisores internos ou externos. Para obter mais informações sobre como as políticas de conformidade de comunicação podem ajudá-lo a monitorar as comunicações em sua organização, consulte as políticas de conformidade de [comunicação no Microsoft 365.](communication-compliance.md) Se você quiser revisar como a Contoso configurou rapidamente uma política de conformidade de comunicação para monitorar o idioma ofensivo nas comunicações do Microsoft Teams, do Exchange Online e do Yammer, confira este estudo de [caso.](communication-compliance-case-study.md)

## <a name="subscriptions-and-licensing"></a>Assinaturas e licenciamento

Antes de começar a conformidade de comunicação, você deve confirmar sua assinatura do [Microsoft 365](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans) e quaisquer complementos. Para acessar e usar a conformidade de comunicação, sua organização deve ter uma das seguintes assinaturas ou complementos:

- Assinatura do Microsoft 365 E5 (versão paga ou de avaliação)
- Assinatura do Microsoft 365 E3 + o complemento de Conformidade do Microsoft 365 E5
- Assinatura do Microsoft 365 E3 + o complemento Microsoft 365 E5 Insider Risk Management
- Assinatura do Microsoft 365 A5 (versão paga ou de avaliação)
- Assinatura do Microsoft 365 A3 + complemento de Conformidade do Microsoft 365 A5
- Assinatura do Microsoft 365 A3 + o complemento Microsoft 365 A5 Insider Risk Management
- Assinatura do Microsoft 365 G5 (versão paga ou de avaliação)
- Assinatura do Microsoft 365 G5 + complemento de Conformidade do Microsoft 365 G5
- Assinatura do Microsoft 365 G5 + o complemento Microsoft 365 G5 Insider Risk Management
- Assinatura do Office 365 Enterprise E5 (versão paga ou de avaliação)
- Assinatura do Office 365 A5 (versão paga ou de avaliação)
- Assinatura do Office 365 Enterprise E3 + complemento de Conformidade Avançada do Office 365 (não está mais disponível para novas assinaturas, confira a observação)

Os usuários incluídos nas políticas de conformidade de comunicação devem ter uma das licenças atribuídas acima.

>[!IMPORTANT]
>A Conformidade Avançada do Office 365 não é mais vendida como uma assinatura autônoma. Quando as assinaturas atuais expirarem, os clientes devem fazer a transição para uma das assinaturas acima, que contêm os mesmos recursos de conformidade ou adicionais.

Se você não tiver um plano existente do Office 365 Enterprise E5 e quiser experimentar [a](https://www.microsoft.com/microsoft-365/enterprise) conformidade de comunicação, adicione o [Microsoft 365](/office365/admin/try-or-buy-microsoft-365) à sua assinatura existente ou inscreva-se para uma avaliação do Office 365 Enterprise E5.

## <a name="step-1-required-enable-permissions-for-communication-compliance"></a>Etapa 1 (obrigatório): Habilitar permissões para conformidade de comunicação

>[!Important]
>Por padrão, os Administradores Globais não têm acesso aos recursos de conformidade de comunicação. As funções atribuídas nesta etapa são necessárias para que todos os recursos de conformidade de comunicação sejam acessíveis. Depois de configurar seus grupos de função, pode levar até 30 minutos para que as permissões do grupo de função se apliquem a usuários atribuídos em toda a organização.

Há cinco grupos de função usados para configurar permissões para gerenciar recursos de conformidade de comunicação. Para disponibilizar **a** conformidade de comunicação como uma opção de menu no centro de conformidade do  Microsoft 365 e continuar com essas etapas de configuração, você deve ser atribuído aos grupos de funções de Conformidade de Comunicação ou Administrador de Conformidade *de* Comunicação. Para acessar e gerenciar recursos de conformidade de comunicação após a configuração inicial, os usuários devem ser membros de pelo menos um grupo de função de conformidade de comunicação.

Dependendo de como você deseja gerenciar políticas e alertas de comunicação, você precisará atribuir usuários a grupos de função específicos. Você tem a opção de atribuir usuários com diferentes responsabilidades de conformidade a grupos de função específicos para gerenciar diferentes áreas de recursos de conformidade de comunicação. Ou você pode optar por atribuir todas as contas de usuário para administradores designados, analistas, investigadores e visualizadores ao grupo de função *Conformidade* de Comunicação. Use um único grupo de função ou vários grupos de função para melhor se ajustar aos seus requisitos de gerenciamento de conformidade.

Escolha entre essas opções de grupo de função ao configurar a conformidade de comunicação:

| Role | Permissões de função |
|:-----|:-----|
| **Conformidade de Comunicação** | Use esse grupo de função para gerenciar a conformidade de comunicação para sua organização em um único grupo. Ao adicionar todas as contas de usuário para administradores designados, analistas, investigadores e visualizadores, você pode configurar permissões de conformidade de comunicação em um único grupo. Esse grupo de função contém todas as funções de permissão de conformidade de comunicação. Essa configuração é a maneira mais fácil de começar rapidamente com a conformidade de comunicação e é uma boa opção para organizações que não precisam de permissões separadas definidas para grupos separados de usuários. |
| **Administrador de Conformidade de Comunicação** | Use esse grupo de função para configurar inicialmente a conformidade de comunicação e posteriormente segregar os administradores de conformidade de comunicação em um grupo definido. Os usuários atribuídos a esse grupo de funções podem criar, ler, atualizar e excluir políticas de conformidade de comunicação, configurações globais e atribuições de grupo de função. Os usuários atribuídos a esse grupo de funções não podem exibir alertas de mensagem. |
| **Analista de Conformidade de Comunicação** | Use esse grupo para atribuir permissões aos usuários que atuarão como analistas de conformidade de comunicação. Os usuários atribuídos a esse grupo de funções podem exibir políticas onde são atribuídos como Revisadores, exibir metadados de mensagem (não conteúdo de mensagem), escalonar para revistores adicionais ou enviar notificações aos usuários. Os analistas não podem resolver alertas pendentes. |
| **Investigador de conformidade de comunicação** | Use esse grupo para atribuir permissões aos usuários que atuarão como investigadores de conformidade de comunicação. Os usuários atribuídos a esse grupo de funções podem exibir metadados e conteúdo de mensagens, escalonar para revistores adicionais, escalonar para um caso de Descoberta Avançada, enviar notificações aos usuários e resolver o alerta. |
| **Visualizador de Conformidade de Comunicação** | Use esse grupo para atribuir permissões a usuários que gerenciarão relatórios de comunicação. Os usuários atribuídos a esse grupo de função podem acessar todos os widgets de relatórios na home page de conformidade de comunicação e podem exibir todos os relatórios de conformidade de comunicação. |

### <a name="option-1-assign-all-compliance-users-to-the-communication-compliance-role-group"></a>Opção 1: Atribuir todos os usuários de conformidade ao grupo de função Conformidade de Comunicação

1. Entre usando [https://protection.office.com/permissions](https://protection.office.com/permissions) credenciais para uma conta de administrador em sua organização do Microsoft 365.

2. No Centro de &amp; Conformidade de Segurança, vá para **Permissões.** Selecione o link para exibir e gerenciar funções no Office 365.

3. Selecione o grupo *de função Conformidade* de Comunicação e, em seguida, selecione Editar grupo de **funções.**

4. Selecione **Escolher membros** no painel de navegação esquerdo e selecione **Editar.**

5. Selecione **Adicionar** e marque a caixa de seleção de todos os usuários que você deseja adicionar ao grupo de função *Conformidade* de Comunicação.

6. Selecione **Adicionar** e, em seguida, **Terminar.**

7. Selecione **Salvar** para adicionar os usuários ao grupo de funções. Selecione **Fechar** para concluir as etapas

### <a name="option-2-assign-users-to-specific-communication-compliance-role-groups"></a>Opção 2: Atribuir usuários a grupos de função de conformidade de comunicação específicos

Use essa opção para atribuir usuários a grupos de função específicos para segmentar o acesso e as responsabilidades de conformidade de comunicação entre diferentes usuários em sua organização.

1. Entre usando [https://protection.office.com/permissions](https://protection.office.com/permissions) credenciais para uma conta de administrador em sua organização do Microsoft 365.

2. No Centro de &amp; Conformidade de Segurança, vá para **Permissões.** Selecione o link para exibir e gerenciar funções no Office 365.

3. Selecione um dos grupos de função de conformidade de comunicação e, em seguida, **selecione Editar grupo de função**.

4. Selecione **Escolher membros** no painel de navegação esquerdo e, em seguida, selecione **Editar.**

5. Selecione **Adicionar** e marque a caixa de seleção de todos os usuários que você deseja adicionar ao grupo de funções.

6. Selecione **Adicionar** e, em seguida, **Terminar.**

7. Selecione **Salvar** para adicionar os usuários ao grupo de funções.

8. Selecione o próximo grupo de função de conformidade de comunicação e repita as etapas 4 a 7 para cada grupo de função necessário.

9. Selecione **Fechar** para concluir as etapas.

Para obter mais informações sobre grupos de função e permissões, [consulte Permissões no Centro de Conformidade.](../security/office-365-security/protect-against-threats.md)

## <a name="step-2-required-enable-the-audit-log"></a>Etapa 2 (obrigatório): Habilitar o log de auditoria

A conformidade de comunicação requer logs de auditoria para mostrar alertas e rastrear ações de correção tomadas pelos revisadores. Os logs de auditoria são um resumo de todas as atividades associadas a uma política organizacional definida ou sempre que uma política de conformidade de comunicação muda.

Para obter instruções passo a passo para ativar a auditoria, consulte Ativar ou desativar a pesquisa de [log de auditoria.](turn-audit-log-search-on-or-off.md) Depois de ativar a auditoria, é exibida uma mensagem informando que o log de auditoria está sendo preparado e que você pode executar uma pesquisa em algumas horas após a conclusão da preparação. Você só precisa fazer essa ação uma vez. Para obter mais informações sobre como usar o log de auditoria, consulte [Pesquisar o log de auditoria.](search-the-audit-log-in-security-and-compliance.md)

## <a name="step-3-optional-set-up-groups-for-communication-compliance"></a>Etapa 3 (opcional): Configurar grupos para conformidade de comunicação

 Ao criar uma política de conformidade de comunicação, você define quem tem suas comunicações revisadas e quem realiza avaliações. Na política, você usará endereços de email para identificar indivíduos ou grupos de pessoas. Para simplificar a configuração, você pode criar grupos para pessoas com suas comunicações revisadas e grupos para pessoas que revisam essas comunicações. Se você estiver usando grupos, talvez precise de vários. Por exemplo, se você quiser monitorar as comunicações entre dois grupos distintos de pessoas ou se quiser especificar um grupo que não será supervisionado.

Use o gráfico a seguir para ajudá-lo a configurar grupos em sua organização para políticas de conformidade de comunicação:

| **Membro da Política** | **Grupos com suporte** | **Grupos sem suporte** |
|:-----|:-----|:-----|
|Usuários supervisionados <br> Usuários não supervisionados | Grupos de distribuição <br> Grupos do Microsoft 365 | Grupos dinâmicos de distribuição <br> Grupos de distribuição aninhados <br> Grupos de segurança habilitados para email |
| Revisores | Nenhuma | Grupos de distribuição <br> Grupos dinâmicos de distribuição <br> Grupos de distribuição aninhados <br> Grupos de segurança habilitados para email |
  
Quando você atribui um grupo de distribuição na política, a política monitora todos os emails e chats do Teams de cada usuário no grupo de distribuição. Quando você atribui um grupo do Microsoft 365 na política, a política monitora todos os emails e chats do Teams enviados a esse grupo, não os emails e chats individuais recebidos por cada membro do grupo.

Se você é uma organização com uma implantação local do Exchange ou um provedor de email externo e deseja monitorar os chats do Microsoft Teams para seus usuários, você deve criar um grupo de distribuição para os usuários com caixas de correio locais ou externas para monitorar. Posteriormente, nestas etapas, você atribuirá  esse grupo de distribuição como a seleção de usuários e grupos supervisionados no assistente de política.

>[!IMPORTANT]
>Você deve registrar uma solicitação com o suporte da Microsoft para permitir que a sua organização use a interface gráfica do usuário no Centro de Conformidade e Segurança para pesquisar os dados de chat do Teams para usuários locais. Para obter mais informações, consulte Pesquisar caixas de [correio baseadas em nuvem para usuários locais.](search-cloud-based-mailboxes-for-on-premises-users.md)

Para gerenciar usuários supervisionados em grandes organizações corporativas, talvez seja necessário monitorar todos os usuários em grandes grupos. Você pode usar o PowerShell para configurar um grupo de distribuição para uma política de conformidade de comunicação global para o grupo atribuído. Isso permite monitorar milhares de usuários com uma única política e manter a política de conformidade de comunicação atualizada à medida que novos funcionários ingressarem em sua organização.

1. Crie um [grupo](/powershell/module/exchange/new-distributiongroup) de distribuição dedicado para sua política de conformidade de comunicação global com as seguintes propriedades: certifique-se de que esse grupo de distribuição não seja usado para outros fins ou outros serviços do Office 365.

    - **MemberDepartRestriction = Closed**. Garante que os usuários não podem se remover do grupo de distribuição.
    - **MemberJoinRestriction = Fechado**. Garante que os usuários não podem adicionar a si mesmos ao grupo de distribuição.
    - **ModerationEnabled = True**. Garante que todas as mensagens enviadas a esse grupo estejam sujeitas à aprovação e que o grupo não está sendo usado para se comunicar fora da configuração da política de conformidade de comunicação.

    ```PowerShell
    New-DistributionGroup -Name <your group name> -Alias <your group alias> -MemberDepartRestriction 'Closed' -MemberJoinRestriction 'Closed' -ModerationEnabled $true
    ```

2. Selecione um atributo personalizado do [Exchange nãousado](/Exchange/recipients/mailbox-custom-attributes) para acompanhar os usuários adicionados à política de conformidade de comunicação em sua organização.

3. Execute o seguinte script do PowerShell em uma agenda recorrente para adicionar usuários à política de conformidade de comunicação:

    ```PowerShell
    $Mbx = (Get-Mailbox -RecipientTypeDetails UserMailbox -ResultSize Unlimited -Filter {CustomAttribute9 -eq $Null})
    $i = 0
    ForEach ($M in $Mbx) 
    {
      Write-Host "Adding" $M.DisplayName
      Add-DistributionGroupMember -Identity <your group name> -Member $M.DistinguishedName -ErrorAction SilentlyContinue
      Set-Mailbox -Identity $M.Alias -<your custom attribute name> SRAdded 
      $i++
    }
    Write-Host $i "Mailboxes added to supervisory review distribution group."
    ```

Para obter mais informações sobre como configurar grupos, consulte:

- [Criar e gerenciar grupos de distribuição](/Exchange/recipients-in-exchange-online/manage-distribution-groups/manage-distribution-groups)
- [Visão geral dos Grupos do Microsoft 365](/office365/admin/create-groups/office-365-groups)

## <a name="step-4-optional-verify-your-yammer-tenant-is-in-native-mode"></a>Etapa 4 (opcional): verifique se o locatário do Yammer está no modo Nativo

No Modo Nativo, todos os usuários do Yammer estão no Azure Active Directory (Azure AD), todos os grupos são Grupos do Office 365 e todos os arquivos são armazenados no SharePoint Online. Seu locatário do Yammer deve estar no Modo Nativo para políticas de conformidade de comunicação para verificar e identificar conversas arriscadas em mensagens privadas e conversas da comunidade no Yammer.

Para saber mais sobre como configurar o Yammer no modo nativo, confira:

- [Visão geral do Modo Nativo do Yammer no Microsoft 365](/yammer/configure-your-yammer-network/overview-native-mode)
- [Configurar sua rede do Yammer para o modo Nativo para o Microsoft 365](/yammer/configure-your-yammer-network/native-mode)

## <a name="step-5-required-create-a-communication-compliance-policy"></a>Etapa 5 (obrigatório): criar uma política de conformidade de comunicação
  
>[!Important]
>Não há suporte para o uso do PowerShell para criar e gerenciar políticas de conformidade de comunicação. Para criar e gerenciar essas políticas, você deve usar os controles de gerenciamento de política na solução de conformidade de comunicação [do Microsoft 365.](https://compliance.microsoft.com/supervisoryreview)

1. Entre usando [https://compliance.microsoft.com](https://compliance.microsoft.com) credenciais para uma conta de administrador em sua organização do Microsoft 365.

2. No centro de conformidade do Microsoft 365, selecione **Conformidade de comunicação.**
  
3. Selecione a **guia** Políticas.

4. Selecione **Criar política** para criar e configurar uma nova política a partir de um modelo ou para criar e configurar uma política personalizada.

    Se você escolher um modelo de política para criar uma política, você irá:

    - Confirme ou atualize o nome da política. Os nomes das políticas não podem ser alterados depois que a política é criada.
    
    - Escolha os usuários ou grupos para supervisionar, incluindo a escolha de usuários ou grupos que você gostaria de excluir. Ao usar o modelo de conflito de interesse, você selecionará dois grupos ou dois usuários para monitorar comunicações internas.
    
    - Escolha os revisadores da política. Os revisadores são usuários individuais e todos os revisadores devem ter caixas de correio hospedadas no Exchange Online. Os revisadores adicionados aqui são os revisadores que você pode escolher ao escalonar um alerta no fluxo de trabalho de investigação e correção. Quando os revisadores são adicionados a uma política, eles recebem automaticamente uma mensagem de email que os notifica sobre a atribuição à política e fornece links para informações sobre o processo de revisão.
    
    - Escolha um campo de condição limitado, geralmente um tipo de informação sensível ou um dicionário de palavras-chave a ser aplicado à política.

    Se você optar por usar o assistente de política para criar uma política personalizada, você irá:

    - Dê um nome e uma descrição à política. Os nomes das políticas não podem ser alterados depois que a política é criada.
    
    - Escolha os usuários ou grupos para supervisionar, incluindo todos os usuários em sua organização, usuários e grupos específicos ou outros usuários e grupos que você gostaria de excluir.
    
    - Escolha os revisadores da política. Os revisadores são usuários individuais e todos os revisadores devem ter caixas de correio hospedadas no Exchange Online. Os revisadores adicionados aqui são os revisadores que você pode escolher ao escalonar um alerta no fluxo de trabalho de investigação e correção. Quando os revisadores são adicionados a uma política, eles recebem automaticamente uma mensagem de email que os notifica sobre a atribuição à política e fornece links para informações sobre o processo de revisão.
    
    - Escolha os canais de comunicação para verificar, incluindo o Exchange, o Microsoft Teams, o Yammer ou o Skype for Business. Você também optará por verificar fontes de terceiros se tiver configurado um conector no Microsoft 365.
    
    - Escolha a direção de comunicação a ser monitorada, incluindo comunicações de entrada, de saída ou internas.
    
    - Defina as condições de política de conformidade [de comunicação.](communication-compliance-feature-reference.md#ConditionalSettings) Você pode escolher entre o endereço da mensagem, a palavra-chave, os tipos de arquivo e as condições de tamanho de acordo.
    
    - Escolha se você gostaria de incluir tipos de informações confidenciais. Esta etapa é onde você pode selecionar tipos de informações confidenciais padrão e personalizadas. Escolha entre tipos de informações confidenciais personalizados existentes ou dicionários de palavras-chave personalizados no assistente de política de conformidade de comunicação. Você pode criar esses itens antes de executar o assistente, se necessário. Você também pode criar novos tipos de informações confidenciais no assistente de política de conformidade de comunicação.
    
    - Escolha se você gostaria de habilitar classificadores. Os classificadores podem detectar linguagem inadequada e imagens enviadas ou recebidas no corpo de mensagens de email ou outros tipos de texto. Você pode escolher os seguintes classificadores *integrados:* ameaça , *profanação* *,* abuso direcionado *,* imagens de adulto , imagens *de racy* e imagens *gory*.

      > [!CAUTION]
      > Vamos substituir o classificador interno **Idioma Ofensivo** porque ele tem uma grande quantidade de falsos positivos. Não use-o e, se você estiver usando-o no momento, deverá tirar seus processos de negócios dele. Em vez **disso,** **recomendamos** usar  os classificadores de ameaças , profanação e ataques direcionados.

    - Defina a porcentagem de comunicações a analisar.
    
    - Revise suas seleções de política e crie a política.

5. Selecione **Criar política** ao usar os modelos ou Enviar **ao** usar o assistente de política personalizada.

6. A **página Sua política foi criada** é exibida com diretrizes sobre quando a política será ativada e quais comunicações serão capturadas.

## <a name="step-6-optional-create-notice-templates-and-configure-user-anonymization"></a>Etapa 6 (opcional): criar modelos de aviso e configurar o anonimato do usuário

Se você quiser ter a opção de responder a um alerta de política enviando um aviso de lembrete para o usuário associado, será necessário criar pelo menos um modelo de aviso em sua organização. Os campos de modelo de aviso são editáveis antes de eles são enviados como parte do processo de correção de alerta, e é recomendável criar um modelo de aviso personalizado para cada política de conformidade de comunicação.

Você também pode optar por habilitar o anonimato para nomes de usuário exibidos ao investigar as diretivas e tomar medidas em mensagens.

1. Entre usando [https://compliance.microsoft.com](https://compliance.microsoft.com) credenciais para uma conta de administrador na sua organização do Microsoft 365.

2. No centro de conformidade do Microsoft 365, vá para **Conformidade de comunicação.**

3. Para configurar o anonimato para nomes de usuário, selecione a **guia** Privacidade.

4. Para habilitar o anonimato, selecione **Mostrar versões anônimas de nomes de usuário.**

5. Selecione **Salvar**.

6. Navegue até a **guia Modelos de aviso e** selecione Criar modelo de **aviso.**

7. Na página **Modificar um modelo de aviso,** preencha os seguintes campos:

    - Nome do modelo (obrigatório)
    - Enviar de (obrigatório)
    - Cc e Cc (opcional)
    - Assunto (obrigatório)
    - Corpo da mensagem (obrigatório)

8. Selecione **Salvar** para criar e salvar o modelo de aviso.

## <a name="step-7-optional-test-your-communication-compliance-policy"></a>Etapa 7 (opcional): teste sua política de conformidade de comunicação

Depois de criar uma política de conformidade de comunicação, é uma boa ideia testá-la para garantir que as condições definidas estão sendo impostas corretamente pela política. Você também pode testar suas políticas de prevenção contra perda de dados [(DLP)](create-test-tune-dlp-policy.md) se suas políticas de conformidade de comunicação incluem tipos de informações confidenciais. Certifique-se de dar a suas políticas tempo de ativação para que as comunicações que você deseja testar sejam capturadas.

Siga estas etapas para testar sua política de conformidade de comunicação:

1. Abra um cliente de email, o Microsoft Teams ou o Yammer enquanto estiver lo como um usuário supervisionado definido na política que você deseja testar.

2. Envie um email, um chat do Microsoft Teams ou uma mensagem do Yammer que atenda aos critérios definidos na política de conformidade de comunicação. Esse teste pode ser uma palavra-chave, tamanho do anexo, domínio etc. Certifique-se de determinar se as configurações condicionais configuradas na política são muito restritivas ou muito brandas.

    > [!NOTE]
    > As mensagens de email podem levar até 24 horas para processar totalmente em uma política. As comunicações no Microsoft Teams, yammer e plataformas de terceiros podem levar até 48 horas para processar totalmente em uma política.

3. Entre no Microsoft 365 como um revistor designado na política de conformidade de comunicação. Navegue **até**  >  **Alertas de conformidade de** comunicação para exibir os alertas de suas políticas.

4. Correção do alerta usando os controles de correção e verifique se o alerta foi resolvido corretamente.

## <a name="next-steps"></a>Próximas etapas

Depois de concluir essas etapas para criar sua primeira política de conformidade de comunicação, você começará a receber alertas de indicadores de atividade após 24 a 48 horas. Configure políticas adicionais conforme necessário usando as orientações na Etapa 5 deste artigo.

Para saber mais sobre como investigar alertas de conformidade de comunicação, consulte Investigar e [remediar alertas de conformidade de comunicação.](communication-compliance-investigate-remediate.md)
