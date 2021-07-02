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
ms.openlocfilehash: f099d7bd180843530d23d0bbcee89dc8ae35cdbb
ms.sourcegitcommit: a4c93a4c7d7db08fe3b032b58d5c7dbbb9476e90
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2021
ms.locfileid: "53256730"
---
# <a name="get-started-with-communication-compliance"></a>Introdução à conformidade de comunicação

Use políticas de conformidade de comunicação para identificar as comunicações do usuário para exame por revisores internos ou externos. Para obter mais informações sobre como as políticas de conformidade de comunicação podem ajudá-lo a monitorar as comunicações em sua organização, consulte políticas de conformidade de [comunicação em Microsoft 365](communication-compliance.md). Se você quiser revisar como a Contoso configurou rapidamente uma política de conformidade de comunicação para monitorar o idioma ofensivo nas comunicações Microsoft Teams, Exchange Online e Yammer, confira este estudo de [caso.](communication-compliance-case-study.md)

## <a name="subscriptions-and-licensing"></a>Assinaturas e licenciamento

Antes de começar a conformidade com a comunicação, você deve confirmar sua assinatura [Microsoft 365 e](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans) quaisquer complementos. Para acessar e usar a conformidade de comunicação, sua organização deve ter uma das seguintes assinaturas ou complementos:

- Microsoft 365 E5 assinatura (versão paga ou de avaliação)
- Microsoft 365 E3 assinatura + o Microsoft 365 E5 Compliance complemento
- Microsoft 365 E3 assinatura + o complemento Microsoft 365 E5 Gerenciamento de Riscos do Insider
- Microsoft 365 A5 assinatura (versão paga ou de avaliação)
- Microsoft 365 A3 assinatura + o complemento Microsoft 365 A5 Conformidade
- Microsoft 365 A3 assinatura + o complemento Microsoft 365 A5 Gerenciamento de Riscos do Insider
- Microsoft 365 Assinatura G5 (versão paga ou de avaliação)
- Microsoft 365 Assinatura do G5 + o complemento Microsoft 365 conformidade do G5
- Microsoft 365 Assinatura do G5 + o complemento Microsoft 365 G5 Insider Risk Management
- Office 365 Enterprise Assinatura E5 (versão paga ou avaliação)
- Office 365 A5 assinatura (versão paga ou de avaliação)
- Office 365 Enterprise Assinatura E3 + o Conformidade Avançada do Office 365 complemento (não está mais disponível para novas assinaturas, consulte observação)

Os usuários incluídos nas políticas de conformidade de comunicação devem ter uma das licenças acima.

> [!IMPORTANT]
> Conformidade Avançada do Office 365 não é mais vendida como uma assinatura autônoma. Quando as assinaturas atuais expirarem, os clientes devem fazer a transição para uma das assinaturas acima, que contêm os mesmos recursos de conformidade ou adicionais.

Se você não tiver um plano Office 365 Enterprise E5 existente e quiser tentar [](/office365/admin/try-or-buy-microsoft-365) a conformidade com a comunicação, [](https://www.microsoft.com/microsoft-365/enterprise) você poderá adicionar Microsoft 365 à sua assinatura existente ou inscrever-se para uma avaliação do Office 365 Enterprise E5.

## <a name="step-1-required-enable-permissions-for-communication-compliance"></a>Etapa 1 (necessária): Habilitar permissões para conformidade de comunicação

> [!IMPORTANT]
> Por padrão, os Administradores Globais não têm acesso aos recursos de conformidade de comunicação. As funções atribuídas nesta etapa são necessárias para que todos os recursos de conformidade de comunicação sejam acessíveis. Depois de configurar seus grupos de função, pode levar até 30 minutos para que as permissões do grupo de funções se apliquem aos usuários atribuídos em toda a sua organização.

Há cinco grupos de função usados para configurar permissões para gerenciar recursos de conformidade de comunicação. Para **disponibilizar** a conformidade de comunicação como uma opção de menu no Centro de conformidade do Microsoft 365 e  continuar com essas etapas de configuração, você deve ser atribuído aos grupos de função Conformidade de Comunicação ou Administrador de *Conformidade* de Comunicação. Para acessar e gerenciar recursos de conformidade de comunicação após a configuração inicial, os usuários devem ser membros de pelo menos um grupo de função de conformidade de comunicação.

Dependendo de como você deseja gerenciar políticas de comunicação e alertas, você precisará atribuir usuários a grupos de função específicos. Você tem a opção de atribuir usuários com responsabilidades de conformidade diferentes a grupos de função específicos para gerenciar diferentes áreas de recursos de conformidade de comunicação. Ou você pode optar por atribuir todas as contas de usuário para administradores, analistas, investigadores e visualizadores designados ao grupo de função *Conformidade* de Comunicação. Use um único grupo de funções ou vários grupos de função para melhor se ajustar aos seus requisitos de gerenciamento de conformidade.

Escolha entre essas opções de grupo de função ao configurar a conformidade de comunicação:

| Função | Permissões de função |
|:-----|:-----|
| **Conformidade de comunicação** | Use esse grupo de funções para gerenciar a conformidade de comunicação para sua organização em um único grupo. Ao adicionar todas as contas de usuário para administradores designados, analistas, investigadores e visualizadores, você pode configurar permissões de conformidade de comunicação em um único grupo. Esse grupo de função contém todas as funções de permissão de conformidade de comunicação. Essa configuração é a maneira mais fácil de começar rapidamente com a conformidade de comunicação e é um bom ajuste para organizações que não precisam de permissões separadas definidas para grupos separados de usuários. |
| **Administrador de Conformidade de Comunicação** | Use esse grupo de funções para configurar inicialmente a conformidade de comunicação e posteriormente para segregar os administradores de conformidade de comunicação em um grupo definido. Os usuários atribuídos a esse grupo de funções podem criar, ler, atualizar e excluir políticas de conformidade de comunicação, configurações globais e atribuições de grupo de função. Os usuários atribuídos a esse grupo de funções não podem exibir alertas de mensagens. |
| **Analista de Conformidade de Comunicação** | Use esse grupo para atribuir permissões aos usuários que atuarão como analistas de conformidade de comunicação. Os usuários atribuídos a esse grupo de funções podem exibir políticas nas quais são atribuídos como Revistores, exibir metadados de mensagens (não conteúdo de mensagem), escalonar para revisadores adicionais ou enviar notificações aos usuários. Os analistas não podem resolver alertas pendentes. |
| **Pesquisador de Conformidade de Comunicação** | Use esse grupo para atribuir permissões aos usuários que atuarão como investigadores de conformidade de comunicação. Os usuários atribuídos a esse grupo de funções podem exibir metadados de mensagens e conteúdo, escalonar para revisadores adicionais, escalonar para um caso Advanced eDiscovery, enviar notificações aos usuários e resolver o alerta. |
| **Visualizador de Conformidade de Comunicação** | Use esse grupo para atribuir permissões aos usuários que gerenciarão relatórios de comunicação. Os usuários atribuídos a esse grupo de funções podem acessar todos os widgets de relatório na home page de conformidade de comunicação e podem exibir todos os relatórios de conformidade de comunicação. |

### <a name="option-1-assign-all-compliance-users-to-the-communication-compliance-role-group"></a>Opção 1: Atribuir todos os usuários de conformidade ao grupo de função Conformidade de Comunicação

1. Entre [https://compliance.microsoft.com/permissions](https://compliance.microsoft.com/permissions) usando credenciais para uma conta de administrador em sua Microsoft 365 organização.

2. No Centro &amp; de Conformidade de Segurança, acesse **Permissões**. Selecione o link para exibir e gerenciar funções em Office 365.

3. Selecione o *grupo de função Conformidade* de Comunicação e selecione Editar grupo de **funções**.

4. Selecione **Escolher membros** no painel de navegação esquerdo e selecione **Editar**.

5. Selecione **Adicionar** e selecione a caixa de seleção para todos os usuários que você deseja adicionar ao grupo de função *Conformidade* de Comunicação.

6. Selecione **Adicionar** e, em seguida, **a**.

7. Selecione **Salvar** para adicionar os usuários ao grupo de funções. Selecione **Fechar** para concluir as etapas

### <a name="option-2-assign-users-to-specific-communication-compliance-role-groups"></a>Opção 2: Atribuir usuários a grupos de função de conformidade de comunicação específicos

Use essa opção para atribuir usuários a grupos de função específicos para segmentar o acesso e as responsabilidades de conformidade de comunicação entre diferentes usuários em sua organização.

1. Entre [https://compliance.microsoft.com/permissions](https://compliance.microsoft.com/permissions) usando credenciais para uma conta de administrador em sua Microsoft 365 organização.

2. No Centro &amp; de Conformidade de Segurança, acesse **Permissões**. Selecione o link para exibir e gerenciar funções em Office 365.

3. Selecione um dos grupos de função de conformidade de comunicação e selecione **Editar grupo de função**.

4. Selecione **Escolher membros** no painel de navegação esquerdo e selecione **Editar**.

5. Selecione **Adicionar** e selecione a caixa de seleção para todos os usuários que você deseja adicionar ao grupo de funções.

6. Selecione **Adicionar** e, em seguida, **a**.

7. Selecione **Salvar** para adicionar os usuários ao grupo de funções.

8. Selecione o próximo grupo de função de conformidade de comunicação e repita as etapas 4 a 7 para cada grupo de função necessário.

9. Selecione **Fechar** para concluir as etapas.

Para obter mais informações sobre grupos de funções e permissões, consulte [Permissões no Centro de Conformidade](../security/office-365-security/protect-against-threats.md).

## <a name="step-2-required-enable-the-audit-log"></a>Etapa 2 (necessária): Habilitar o log de auditoria

A Conformidade de comunicações requer logs de auditoria para mostrar alertas e controlar as ações de correção realizadas por revistores. Os logs de auditoria são um resumo de todas as atividades associadas a uma política organizacional definida ou a qualquer momento em que uma política de conformidade de comunicação muda.

Para obter instruções passo a passo para ativar a auditoria, consulte Ativar ou desativar a pesquisa de [log de auditoria.](turn-audit-log-search-on-or-off.md) Após a ativação, será exibida uma mensagem informando que o log de auditoria está sendo preparado e que você poderá executar uma pesquisa dentro algumas horas quando a preparação estiver concluída. Você só precisa fazer essa ação uma vez. Para obter mais informações sobre como usar o log de auditoria, consulte [Pesquisar o log de auditoria](search-the-audit-log-in-security-and-compliance.md).

## <a name="step-3-optional-set-up-groups-for-communication-compliance"></a>Etapa 3 (opcional): Configurar grupos para conformidade de comunicação

 Ao criar uma política de conformidade de comunicação, você define quem tem suas comunicações revisadas e quem executa críticas. Na política, você usará endereços de email para identificar indivíduos ou grupos de pessoas. Para simplificar sua configuração, você pode criar grupos para pessoas que tenham suas comunicações revisadas e grupos para pessoas que revisam essas comunicações. Se você estiver usando grupos, poderá precisar de vários. Por exemplo, se você quiser monitorar as comunicações entre dois grupos distintos de pessoas ou se quiser especificar um grupo que não será supervisionado.

Use o gráfico a seguir para ajudá-lo a configurar grupos em sua organização para políticas de conformidade de comunicação:

| **Membro da Política** | **Grupos com suporte** | **Grupos sem suporte** |
|:-----|:-----|:-----|
|Usuários supervisionados <br> Usuários excluídos | Grupos de distribuição <br> Grupos do Microsoft 365 | Grupos dinâmicos de distribuição <br> Grupos de distribuição aninhados <br> Grupos de segurança habilitados para email <br> Microsoft 365 grupos com associação dinâmica |
| Revisores | Nenhuma | Grupos de distribuição <br> Grupos dinâmicos de distribuição <br> Grupos de distribuição aninhados <br> Grupos de segurança habilitados para email |

Quando você atribui um grupo de distribuição à política, a política monitora todos os emails e Teams chats de cada usuário no grupo de distribuição. Quando você atribui um grupo Microsoft 365 na política, a política monitora todos os emails e chats Teams enviados a esse grupo, não os emails e chats individuais recebidos por cada membro do grupo.

Se você é uma organização com uma implantação Exchange local ou um provedor de email externo e deseja monitorar chats de Microsoft Teams para seus usuários, você deve criar um grupo de distribuição para os usuários com caixas de correio locais ou externas para monitorar. Posteriormente, nessas etapas, você atribuirá esse grupo de distribuição como a seleção usuários supervisionados e **grupos** no assistente de política. Para obter mais informações sobre os requisitos e limitações para habilenciar o armazenamento baseado em nuvem e o suporte Teams usuários locais, consulte Search for Teams chat data for [on-premises users](search-cloud-based-mailboxes-for-on-premises-users.md).

Para gerenciar usuários supervisionados em grandes organizações empresariais, talvez seja necessário monitorar todos os usuários em grupos grandes. Você pode usar o PowerShell para configurar um grupo de distribuição para uma política de conformidade de comunicação global para o grupo atribuído. Isso permite monitorar milhares de usuários com uma única política e manter a política de conformidade de comunicação atualizada à medida que novos funcionários ingressarem em sua organização.

1. Crie um grupo de [distribuição](/powershell/module/exchange/new-distributiongroup) dedicado para sua política de conformidade de comunicação global com as seguintes propriedades: certifique-se de que esse grupo de distribuição não seja usado para outros fins ou outros serviços Office 365 de comunicação.

    - **MemberDepartRestriction = Closed**. Garante que os usuários não podem se remover do grupo de distribuição.
    - **MemberJoinRestriction = Closed**. Garante que os usuários não podem se adicionar ao grupo de distribuição.
    - **ModerationEnabled = True**. Garante que todas as mensagens enviadas a esse grupo estejam sujeitas à aprovação e que o grupo não está sendo usado para se comunicar fora da configuração da política de conformidade de comunicação.

    ```PowerShell
    New-DistributionGroup -Name <your group name> -Alias <your group alias> -MemberDepartRestriction 'Closed' -MemberJoinRestriction 'Closed' -ModerationEnabled $true
    ```

2. Selecione um atributo Exchange [personalizado](/Exchange/recipients/mailbox-custom-attributes) não Exchange para rastrear usuários adicionados à política de conformidade de comunicação em sua organização.

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
- [Visão geral Microsoft 365 grupos](/office365/admin/create-groups/office-365-groups)

## <a name="step-4-optional-verify-your-yammer-tenant-is-in-native-mode"></a>Etapa 4 (opcional): Verifique se o locatário Yammer está no Modo Nativo

No Modo Nativo, todos os Yammer usuários estão no Azure Active Directory (Azure AD), todos os grupos são Office 365 Grupos e todos os arquivos são armazenados no SharePoint Online. Seu Yammer locatário deve estar no Modo Nativo para políticas de conformidade de comunicação para verificar e identificar conversas arriscadas em mensagens privadas e conversas da comunidade em Yammer.

Para obter mais informações sobre como configurar Yammer no Modo Nativo, consulte:

- [Visão geral Yammer modo nativo no Microsoft 365](/yammer/configure-your-yammer-network/overview-native-mode)
- [Configurar sua rede do Yammer para o modo Nativo para o Microsoft 365](/yammer/configure-your-yammer-network/native-mode)

## <a name="step-5-required-create-a-communication-compliance-policy"></a>Etapa 5 (necessária): Criar uma política de conformidade de comunicação

> [!IMPORTANT]
> Não há suporte para o uso do PowerShell para criar e gerenciar políticas de conformidade de comunicações. Para criar e gerenciar essas políticas, você deve usar os controles de gerenciamento de política na solução de conformidade Microsoft 365 [comunicação.](https://compliance.microsoft.com/supervisoryreview)

1. Entre <https://compliance.microsoft.com> usando credenciais para uma conta de administrador em sua Microsoft 365 organização.

2. Na Centro de conformidade do Microsoft 365, selecione **Conformidade de comunicação**.

3. Selecione a guia **políticas** dados.

4. Selecione **Criar política para** criar e configurar uma nova política a partir de um modelo ou para criar e configurar uma política personalizada.

    Se você escolher um modelo de política para criar uma política, você irá:

    - Confirme ou atualize o nome da política. Os nomes de política não podem ser alterados depois que a política é criada.

    - Escolha os usuários ou grupos a supervisionar, incluindo a escolha de usuários ou grupos que você gostaria de excluir. Ao usar o modelo de conflito de interesses, você selecionará dois grupos ou dois usuários para monitorar as comunicações internas.

    - Escolha os revisadores da política. Os revisadores são usuários individuais e todos os revisadores devem ter caixas de correio hospedadas Exchange Online. Os revistores adicionados aqui são os revisadores que você pode escolher ao escalar um alerta no fluxo de trabalho de investigação e correção. Quando os revisadores são adicionados a uma política, eles recebem automaticamente uma mensagem de email que os notifica sobre a atribuição à política e fornece links para informações sobre o processo de revisão.

    - Escolha um campo de condição limitado, geralmente um tipo de informação confidenciais ou um dicionário de palavras-chave para aplicar à política.

    > [!NOTE]
    > Se você quiser habilitar o reconhecimento óptico de [caracteres (OCR)](communication-compliance-feature-reference.md#optical-character-recognition-ocr) para examinar imagens incorporadas ou anexadas em mensagens para texto impresso ou manuscrito que corresponder às condições da política, selecione Personalizar condições de política e porcentagem e habilitar Extrair texto impresso ou manuscrito de imagens para avaliação  >   . 

    Se você optar por usar o assistente de política para criar uma política personalizada, você irá:

    - Dê à política um nome e uma descrição. Os nomes das políticas não podem ser alterados depois que a política é criada.

    - Escolha os usuários ou grupos a supervisionar, incluindo todos os usuários em sua organização, usuários e grupos específicos ou outros usuários e grupos que você gostaria de excluir.

    - Escolha os revisadores da política. Os revisadores são usuários individuais e todos os revisadores devem ter caixas de correio hospedadas Exchange Online. Os revistores adicionados aqui são os revisadores que você pode escolher ao escalar um alerta no fluxo de trabalho de investigação e correção. Quando os revisadores são adicionados a uma política, eles recebem automaticamente uma mensagem de email que os notifica sobre a atribuição à política e fornece links para informações sobre o processo de revisão.

    - Escolha os canais de comunicação a Exchange, Microsoft Teams, Yammer ou Skype for Business. Você também optará por examinar fontes de terceiros se tiver configurado um conector no Microsoft 365.

    - Escolha a direção de comunicação a ser monitorada, incluindo comunicações internas, de entrada, de saída ou de saída.

    - Defina as condições da política de conformidade [de comunicação.](communication-compliance-feature-reference.md#ConditionalSettings) Você pode escolher entre endereço da mensagem, palavra-chave, tipos de arquivo e condições de combinação de tamanho.

    - Escolha se você gostaria de incluir tipos de informações confidenciais. Esta etapa é onde você pode selecionar tipos de informações confidenciais padrão e personalizados. Escolha entre tipos de informações confidenciais personalizados existentes ou dicionários de palavras-chave personalizados no assistente de política de conformidade de comunicação. Você pode criar esses itens antes de executar o assistente, se necessário. Você também pode criar novos tipos de informações confidenciais no assistente de política de conformidade de comunicação.

    - Escolha se você gostaria de habilitar classificadores. Os classificadores podem detectar idiomas e imagens inadequadas enviadas ou recebidas no corpo de mensagens de email ou outros tipos de texto. Você pode escolher os seguintes classificadores integrados: *Ameaça,* *Profanidade,* Assédio *direcionado,* Imagens de *adulto,* *imagens de reticência* e imagens *de Gory.*

    - [Habilita o reconhecimento óptico de caracteres (OCR)](communication-compliance-feature-reference.md#optical-character-recognition-ocr) para examinar imagens incorporadas ou anexadas em mensagens para texto impresso ou manuscrito que corresponder às condições da política. Para políticas personalizadas, uma ou mais configurações condicionais associadas a texto, palavras-chave, classificadores ou tipos de informações confidenciais devem ser configuradas na política para habilitar a seleção da verificação de reconhecimento óptico de caracteres.

    - Defina a porcentagem das comunicações a analisar.

    - Revise suas seleções de política e crie a política.

5. Selecione **Criar política** ao usar os modelos ou **Enviar** ao usar o assistente de política personalizada.

6. A **sua política foi criada** página é exibida com diretrizes sobre quando a política será ativada e quais comunicações serão capturadas.

## <a name="step-6-optional-create-notice-templates-and-configure-user-anonymization"></a>Etapa 6 (opcional): Criar modelos de aviso e configurar o anonimato do usuário

Se você quiser ter a opção de responder a um alerta de política enviando um aviso de lembrete para o usuário associado, será necessário criar pelo menos um modelo de aviso em sua organização. Os campos do modelo de aviso são editáveis antes que eles sejam enviados como parte do processo de correção de alertas e é recomendável criar um modelo de aviso personalizado para cada política de conformidade de comunicação.

Você também pode optar por habilitar o anonimato para nomes de usuário exibidos ao investigar as combinações de política e tomar medidas em mensagens.

1. Entre [https://compliance.microsoft.com](https://compliance.microsoft.com) usando credenciais para uma conta de administrador em sua Microsoft 365 organização.

2. No Centro de conformidade do Microsoft 365, vá para **Conformidade de comunicação**.

3. Para configurar o anonimato para nomes de usuário, selecione a **guia** Privacidade.

4. Para habilitar o anonimato, selecione **Mostrar versões anonimizadas de nomes de usuário**.

5. Selecione **Salvar**.

6. Navegue até a **guia Modelos de Aviso e** selecione Criar modelo de **aviso.**

7. Na página **Modificar um modelo de aviso,** conclua os seguintes campos:

    - Nome do modelo (obrigatório)
    - Enviar de (obrigatório)
    - Cc e Cc (opcional)
    - Assunto (obrigatório)
    - Corpo da mensagem (obrigatório)

8. Selecione **Salvar** para criar e salvar o modelo de aviso.

## <a name="step-7-optional-test-your-communication-compliance-policy"></a>Etapa 7 (opcional): Teste sua política de conformidade de comunicação

Depois de criar uma política de conformidade de comunicação, é uma boa ideia testá-la para garantir que as condições definidas estão sendo impostas corretamente pela política. Você também pode querer testar suas políticas de prevenção contra perda de dados [(DLP)](create-test-tune-dlp-policy.md) se suas políticas de conformidade de comunicação incluem tipos de informações confidenciais. Certifique-se de dar tempo para que suas políticas sejam ativadas para que as comunicações que você deseja testar sejam capturadas.

Siga estas etapas para testar sua política de conformidade de comunicação:

1. Abra um cliente de email, Microsoft Teams ou Yammer ao entrar como um usuário supervisionado definido na política que você deseja testar.

2. Envie um email, Microsoft Teams chat ou Yammer mensagem que atenda aos critérios definidos na política de conformidade de comunicação. Esse teste pode ser uma palavra-chave, tamanho do anexo, domínio etc. Certifique-se de determinar se as configurações condicionais configuradas na política são muito restritivas ou muito lenientes.

    > [!NOTE]
    > As mensagens de email podem levar até 24 horas para processar totalmente em uma política. As comunicações Microsoft Teams, Yammer e plataformas de terceiros podem levar até 48 horas para processar totalmente em uma política.

3. Entre no Microsoft 365 como um revistor designado na política de conformidade de comunicação. Navegue **até**  >  **Alertas de** conformidade de comunicação para exibir os alertas de suas políticas.

4. Correção do alerta usando os controles de correção e verifique se o alerta foi resolvido corretamente.

## <a name="next-steps"></a>Próximas etapas

Depois de concluir essas etapas para criar sua primeira política de conformidade de comunicação, você começará a receber alertas de indicadores de atividade após 24 a 48 horas. Configure políticas adicionais conforme necessário usando as diretrizes na Etapa 5 deste artigo.

Para saber mais sobre como investigar alertas de conformidade de comunicação, consulte [Investigat and remediate communication compliance alerts](communication-compliance-investigate-remediate.md).
