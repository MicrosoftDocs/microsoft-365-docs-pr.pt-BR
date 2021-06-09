---
title: Configurar a filtragem de spam de saída
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a44764e9-a5d2-4c67-8888-e7fb871c17c7
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Os administradores podem aprender a exibir, criar, modificar e excluir políticas de spam de saída no Proteção do Exchange Online (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 9ebff0a93acd505532773fbf5d714268df220c9a
ms.sourcegitcommit: 50908a93554290ff1157b58d0a868a33e012513c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/08/2021
ms.locfileid: "52822004"
---
# <a name="configure-outbound-spam-filtering-in-eop"></a>Configurar a filtragem de spam de saída no EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
- [Proteção do Exchange Online](exchange-online-protection-overview.md)
- [Plano 1 e plano 2 do Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Em organizações Microsoft 365 com caixas de correio no Exchange Online ou organizações de Proteção do Exchange Online (EOP) autônomas sem caixas de correio Exchange Online, as mensagens de email de saída enviadas por meio do EOP são verificadas automaticamente para spam e atividades de envio incomuns.

Spam de saída de um usuário em sua organização normalmente indica uma conta comprometida. As mensagens de saída suspeitas são marcadas como spam (independentemente do nível de confiança de spam ou SCL) e são roteadas pelo [pool](high-risk-delivery-pool-for-outbound-messages.md) de entrega de alto risco para ajudar a proteger a reputação do serviço (ou seja, Microsoft 365 manter os servidores de email de origem fora das listas de bloqueios de IP). Os administradores são automaticamente notificados sobre atividades suspeitas de email de saída e os usuários bloqueados por meio de políticas [de alerta.](../../compliance/alert-policies.md)

O EOP usa políticas de spam de saída como parte da defesa geral da sua organização contra spam. Para obter mais informações, consulte [Proteção antispam](anti-spam-protection.md).

Os administradores podem exibir, editar e configurar (mas não excluir) a política de spam de saída padrão. Para maior granularidade, você também pode criar políticas de spam de saída personalizadas que se aplicam a usuários, grupos ou domínios específicos em sua organização. Políticas personalizadas sempre terão prioridade sobre a política padrão, mas você pode alterar a prioridade (ordem de execução) de suas políticas personalizadas.

Você pode configurar políticas de spam de saída no centro de segurança do Microsoft 365 ou no PowerShell (Exchange Online PowerShell para organizações de Microsoft 365 com caixas de correio no Exchange Online; EOP PowerShell autônomo para organizações sem Exchange Online caixas de correio).

Os elementos básicos de uma política de spam de saída no EOP são:

- **A política de filtro de spam de** saída : especifica as ações para vereditos de filtragem de spam de saída e as opções de notificação.
- **A regra de filtro de spam** de saída : especifica a prioridade e os filtros de destinatário (a quem a política se aplica) para uma política de filtro de spam de saída.

A diferença entre esses dois elementos não é óbvia quando você gerencia as polícias de spam de saída no centro de segurança:

- Ao criar uma política, você está realmente criando uma regra de filtro de spam de saída e a política de filtro de spam de saída associada ao mesmo tempo usando o mesmo nome para ambos.
- Quando você modifica uma política, as configurações relacionadas ao nome, prioridade, habilitado ou desabilitado e filtros de destinatário modificam a regra de filtro de spam de saída. Todas as outras configurações modificam a política de filtro de spam de saída associada.
- Quando você remove uma política, a regra de filtro de spam de saída e a política de filtro de spam de saída associada são removidas.

No PowerShell do Exchange Online ou no PowerShell do EOP autônomo, a política e a regra são gerenciadas separadamente. Para obter mais informações, consulte a seção Usar Exchange Online PowerShell ou [EOP PowerShell](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-outbound-spam-policies) autônomo para configurar políticas de spam de saída posteriormente neste artigo.

Cada organização tem uma política de spam de saída interna chamada Default que tem essas propriedades:

- A política é aplicada a todos os destinatários na organização, mesmo que não haja nenhuma regra de filtro de spam de saída (filtros de destinatário) associada à política.
- A política tem o valor de prioridade personalizado **Menor**, que não pode ser modificado (a política é sempre aplicada por último). As políticas personalizadas que você cria têm sempre uma prioridade mais alta do que a política denominada Padrão.
- A política é a padrão (a propriedade **IsDefault** tem o valor `True`), e não é possível excluir a política padrão.

Para aumentar a eficácia da filtragem de spam de saída, você pode criar políticas de spam de saída personalizadas com configurações mais estritas que são aplicadas a usuários ou grupos específicos de usuários.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Do que você precisa saber para começar?

- Abra o centro de segurança em <https://security.microsoft.com>. Para ir diretamente à página de **Configurações antispam**, use <https://security.microsoft.com/antispam>.

- Para se conectar ao PowerShell do Exchange Online, confira [Conectar ao PowerShell do Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell). Para se conectar ao EOP PowerShell autônomo, consulte [Conectar-se ao PowerShell do Exchange Online Protection.](/powershell/exchange/connect-to-exchange-online-protection-powershell).

- Você precisa de permissões em **Exchange Online** antes de poder realizar os procedimentos neste artigo:
  - Para adicionar, modificar e excluir políticas de spam de saída, você precisa ser membro dos grupos de função Gerenciamento da Organização ou Administrador **de** Segurança. 
  - Para acesso somente leitura a políticas de spam de saída, você precisa ser membro dos grupos de função Leitor **Global** ou **Leitor de** Segurança.

  Para obter mais informações, confira [Permissões no Exchange Online](/exchange/permissions-exo/permissions-exo).

  **Observações**:

  - Adicionar usuários à função correspondente do Azure Active Directory no Centro de administração do Microsoft 365 fornece aos usuários as permissões necessárias _e_ para outros recursos no Microsoft 365. Para obter mais informações, confira o artigo [Sobre funções de administrador](../../admin/add-users/about-admin-roles.md).
  - O grupo de função **Gerenciamento de Organização Somente para Exibição** no [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) também fornece acesso somente leitura ao recurso.

- Para nossas configurações recomendadas para políticas de spam de saída, consulte Configurações de política de filtro de spam de saída do [EOP](recommended-settings-for-eop-and-office365.md#eop-outbound-spam-policy-settings).

- As [](../../compliance/alert-policies.md) políticas de alerta padrão denominadas Limite de envio  de email excederam **,** padrões suspeitos de envio de email detectados **e** o Usuário impedido de enviar emails já envia notificações de email para membros do grupo **TenantAdmins** ( Administradores globais ) sobre atividade de email de saída incomum e usuários **bloqueados** devido ao spam de saída. Para obter mais informações, [consulte Verify the alert settings for restricted users](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users). Recomendamos que você use essas políticas de alerta em vez das opções de notificação em políticas de spam de saída.

## <a name="use-the-security-center-to-create-outbound-spam-policies"></a>Usar o centro de segurança para criar políticas de spam de saída

A criação de uma política de spam de saída personalizada no centro de segurança cria a regra de filtro de spam e a política de filtro de spam associada ao mesmo tempo usando o mesmo nome para ambos.

1. No centro de segurança, acesse **Email e Colaboração** \> **Políticas e Regras** \> **Políticas de ameaças** \> **seção** Políticas \> **Anti-spam**.

2. Na página **Políticas anti-spam,** clique em Criar ícone Criar política e ![ selecione ](../../media/m365-cc-sc-create-icon.png)  **Saída** na listada.

3. O assistente de política é aberto. Na **página Nomear política**, defina as seguintes configurações:
   - **Nome**: insira um nome exclusivo e descritivo para a política.
   - **Descrição**: insira uma descrição opcional para a política.

   Ao terminar, clique em **Avançar**.

4. Na página **Usuários, grupos e domínios** exibida, identifique os destinatários internos aos quais a política se aplica (condições do destinatário):
   - **Usuários**: as caixas de correio, os usuários de email, ou os contatos de email especificados na organização.
   - **Grupos**: os grupos de distribuição, os grupos de segurança habilitados para email ou os grupos do Microsoft 365 habilitados na organização.
   - **Domínios**: todos os destinatários nos [domínios aceitos](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) especificados na organização.

   Clique na caixa apropriada, comece a digitar um valor e selecione o valor desejado dos resultados. Repita esse processo quantas vezes for necessário. Para remover uma entrada existente, clique em Remover ![Ícone Remover](../../media/m365-cc-sc-remove-selection-icon.png) ao lado do valor.

   Para usuários ou grupos, você pode usar a maioria dos identificadores (nome, nome de exibição, alias, endereço de email, nome da conta etc.), mas o nome de exibição correspondente será mostrado nos resultados. Para os usuários, insira um asterisco (\*) por si só para ver todos os valores disponíveis.

   Vários valores na mesma condição ou exceção usam a lógica OR (por exemplo, _\<recipient1\>_ ou _\<recipient2\>_). Diferentes condições usam a lógica AND (por exemplo, _\<recipient1\>_ e _\<member of group 1\>_).

   - **Excluir estes usuários, grupos e domínios**: para adicionar exceções para os destinatários internos aos quais a política se aplica (exceções de destinatários), selecione essa opção e configure as exceções. As configurações e o comportamento são exatamente como as condições.

   Ao terminar, clique em **Avançar**.

5. Na página **Configurações de Proteção** que é aberta, configure as seguintes configurações:
   - **Limites de mensagem**: As configurações desta seção configuram os limites para mensagens de email de saída **de** Exchange Online caixas de correio:
     - **Definir um limite de mensagem externo:** o número máximo de destinatários externos por hora.
     - **Definir um limite de mensagem interno**: O número máximo de destinatários internos por hora.
     - **Definir um limite diário de mensagem:** O número total máximo de destinatários por dia.

     Um valor válido é de 0 a 10.000. O valor padrão é 0, o que significa que os padrões de serviço são usados. Para obter mais informações, consulte [Enviando limites](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-1).

    Insira um valor na caixa ou use as setas de aumento/diminuição na caixa.

   - **Restrição colocada em usuários que** atingem o limite de mensagens : Selecione uma ação na listada quando qualquer um dos limites na seção Configurações de Proteção for **excedido.**

     Para todas as ações, os  destinatários especificados na política de alerta de email restritos ao usuário (e agora redundantes Notificar esses usuários e grupos se um remetente estiver bloqueado devido ao envio da configuração de **spam** de saída mais adiante nesta página) receberão notificações de email.

     - **Restringir o usuário de enviar emails até o dia seguinte:** esse é o valor padrão. As notificações por email são enviadas e o usuário não poderá enviar mais mensagens até o dia seguinte, com base no horário UTC. Não há como o administrador substituir esse bloco.
       - O alerta de atividade denominado **Usuário impedido de enviar emails** notifica os administradores (por email e na página Exibir **alertas).**
       - Todos os destinatários especificados na notificação de pessoas específicas se um remetente for bloqueado devido ao envio de **configuração** de spam de saída na política também serão notificados.
       - O usuário não poderá enviar mais mensagens até o dia seguinte, com base na hora UTC. Não há como o administrador substituir esse bloco.
     - **Restringir o** usuário de enviar emails : as notificações  de email são enviadas, o usuário é adicionado a usuários restritos no centro de segurança e o usuário não pode enviar emails até que eles sejam removidos de usuários restritos por um <https://security.microsoft.com/restrictedusers> administrador.  Depois que um administrador remover o usuário da lista, o usuário não será restrito novamente para esse dia. Para obter instruções, [consulte Removendo um usuário do portal Usuários Restritos depois de enviar emails de spam](removing-user-from-restricted-users-portal-after-spam.md).
     - **Nenhuma ação, alerta somente**: As notificações de email são enviadas.

   - **Regras de encaminhamento**: Use as configurações desta seção para controlar o encaminhamento automático de email por meio Exchange Online **caixas** de correio para destinatários externos. Para obter mais informações, consulte [Control automatic external email forwarding in Microsoft 365](external-email-forwarding.md).

     > [!NOTE]
     > Quando o encaminhamento automático estiver desabilitado, o destinatário receberá um relatório de não entrega (também conhecido como NDR ou mensagem de rejeição) se os destinatários externos enviarem emails para uma caixa de correio que tenha encaminhamento no local. Se a mensagem for enviada  por um remetente interno e o método de encaminhamento for encaminhamento de caixa de correio [(também](/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding) conhecido como encaminhamento _SMTP),_ o remetente interno receberá a NDR. O remetente interno não obterá uma NOTR se o encaminhamento ocorreu devido a uma regra de caixa de entrada.

     Selecione uma das seguintes ações na lista de listadas de regras **de** encaminhamento automático:

     - **Automático - Controlado pelo sistema**: Permite a filtragem de spam de saída para controlar o encaminhamento automático de email externo. Esse é o valor padrão.
     - **On**: O encaminhamento automático de email externo não está desabilitado pela política.
     - **Desativado**: Todo o encaminhamento automático de email externo está desabilitado pela política.

   - **Notificações**: Use as configurações da seção para configurar destinatários adicionais que devem receber cópias e notificações de mensagens de email de saída suspeitas:

     - **Enviar uma cópia de** saída suspeita que exceda esses limites a esses usuários e grupos : Essa configuração adiciona os destinatários especificados ao campo Cc de mensagens de saída suspeitas.

       > [!NOTE]
       > Essa configuração só funciona na política de spam de saída padrão. Ele não funciona em políticas de spam de saída personalizadas que você cria.

       Para habilitar essa configuração, marque a caixa de seleção. Na caixa exibida, clique na caixa, insira um endereço de email válido e pressione Enter ou selecione o valor completo exibido abaixo da caixa.

       Repita essa etapa quantas vezes forem necessárias. Para remover uma entrada existente, clique em Remover ![Ícone Remover](../../media/m365-cc-sc-remove-selection-icon.png) ao lado do valor.

   - **Notificar esses usuários e grupos se um remetente estiver bloqueado devido ao envio de spam de saída**

     > [!IMPORTANT]
     >
     > - Essa configuração está em processo de preterido das políticas de spam de saída.
     >
     > - A [política](../../compliance/alert-policies.md) de alerta padrão denominada Usuário restrito ao envio de **emails** já envia notificações por email aos membros do grupo  **TenantAdmins** (**Administradores** globais ) quando os usuários são bloqueados devido a exceder os limites na seção Limites do Destinatário. Recomendamos que você use a política de alerta em vez dessa configuração na política de spam de saída para notificar **administradores e outros usuários.** Para obter instruções, [consulte Verify the alert settings for restricted users](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users).

   Ao terminar, clique em **Avançar**.

6. Na página **Revisão** exibida, revise suas configurações. Você pode selecionar **Editar** em cada seção para modificar as configurações da seção. Ou você pode clicar em **Voltar** ou selecionar a página específica no assistente.

   Quando terminar, clique em **Criar**.

7. Na mensagem de confirmação exibida, clique em **Concluído**.

## <a name="use-the-security-center-to-view-outbound-spam-policies"></a>Usar o centro de segurança para exibir políticas de spam de saída

1. No centro de segurança, acesse **Email e Colaboração** \> **Políticas e Regras** \> **Políticas de ameaças** \> **seção** Políticas \> **Anti-spam**.

2. Na página **Políticas anti-spam**, procure um dos seguintes valores:
   - O **valor Type** é Política de spam de saída **personalizada**
   - O **valor Name** é Política de saída **anti-spam (Padrão)**

   As propriedades a seguir são exibidas na lista de políticas antispam:

   - **Nome**
   - **Status**
   - **Prioridade**
   - **Tipo**

3. Quando você seleciona uma política de spam de saída clicando no nome, as configurações de política são exibidas em um flyout.

## <a name="use-the-security-center-to-modify-outbound-spam-policies"></a>Usar o centro de segurança para modificar políticas de spam de saída

1. No centro de segurança, acesse **Email e Colaboração** \> **Políticas e Regras** \> **Políticas de ameaças** \> **seção** Políticas \> **Anti-spam**.

2. Na página **Políticas anti-spam,** selecione uma política de spam de saída na lista clicando no nome:
   - Uma política personalizada criada onde o valor na coluna **Tipo** é Política de spam de **saída personalizada.**
   - A política padrão denominada **Política de saída anti-spam (Padrão)**.

3. No submenu de detalhes da política exibido, selecione **Editar** em cada seção para modificar as configurações da seção. Para obter mais informações sobre as configurações, consulte a seção Anterior Usar o centro de segurança [para criar políticas](#use-the-security-center-to-create-outbound-spam-policies) de spam de saída neste artigo.

   Para a política de spam de saída padrão, a seção **Aplicado** a não está disponível (a política se aplica a todos) e você não pode renomear a política.

Para habilitar ou desabilitar uma política, definir a ordem de prioridade da política ou configurar notificações de quarentena de usuário final, confira as seções a seguir.

### <a name="enable-or-disable-custom-outbound-spam-policies"></a>Habilitar ou desabilitar políticas de spam de saída personalizadas

Não é possível desabilitar a política de spam de saída padrão.

1. No centro de segurança, acesse **Email e Colaboração** \> **Políticas e Regras** \> **Políticas de ameaças** \> **seção** Políticas \> **Anti-spam**.

2. Na página **Políticas anti-spam,** selecione uma política com o valor **Tipo** da política de **spam** de saída personalizada na lista clicando no nome.

3. Na parte superior do submenu de detalhes da política exibido, você verá um dos seguintes valores:
   - **Política desativada**: para ativar a política, clique no ![ícone Ativar](../../media/m365-cc-sc-turn-on-off-icon.png) **Ativar** .
   - **Política ativada**: para desativar a política, clique no ![ícone Desativar](../../media/m365-cc-sc-turn-on-off-icon.png) **Desativar**.

4. Na caixa de diálogo de confirmação exibida, clique em **Ativar** ou **Desativar**.

5. Clique em **Fechar** no submenu de detalhes da política.

De volta à página da política principal, o valor **Status** da política será **Ativado** ou **Desativado**.

### <a name="set-the-priority-of-custom-outbound-spam-policies"></a>Definir a prioridade de políticas de spam de saída personalizadas

Por padrão, as políticas de spam de saída têm uma prioridade baseada na ordem em que foram criadas (as políticas mais novas têm prioridade menor do que as políticas mais antigas). Um número de prioridade menor indica uma maior prioridade para a política (0 é a maior), e as políticas são processadas por ordem de prioridade (políticas com maior prioridade são processadas antes das políticas com menor prioridade). Duas políticas não podem ter a mesma prioridade, e o processamento da política será interrompido após a primeira política ser aplicada.

Para alterar a prioridade de uma política, clique em **Aumentar prioridade** ou **Diminuir prioridade** nas propriedades da política (não é possível modificar diretamente o número da **Prioridade** no centro de segurança). Alterar a prioridade de uma política só faz sentido se você tiver várias políticas.

 **Observações**:

- No centro de segurança, você só pode alterar a prioridade da política de spam de saída após a criação. No PowerShell, é possível substituir a prioridade padrão ao criar a regra de filtro de spam (o que pode afetar a prioridade das regras existentes).
- As políticas de spam de saída são processadas na ordem em que são exibidas (a primeira política tem o **valor priority** 0). A política de spam de saída padrão tem o valor de prioridade **Mais** Baixo e você não pode alterá-la.

1. No centro de segurança, acesse **Email e Colaboração** \> **Políticas e Regras** \> **Políticas de ameaças** \> **seção** Políticas \> **Anti-spam**.

2. Na página **Políticas anti-spam,** selecione uma  política de seleção com o valor Tipo da política de **spam** de saída personalizada na lista clicando no nome.

3. Na parte superior do submenu de detalhes da política exibido, você verá **Aumentar a prioridade** ou **Diminuir a prioridade** com base no valor de prioridade atual e no número de políticas personalizadas:
   - A política de spam de saída com **o valor Prioridade** **0** tem apenas a **opção Diminuir** prioridade disponível.
   - A política de spam de saída com o menor valor **priority** (por exemplo, **3**) tem apenas a **opção Aumentar prioridade** disponível.
   - Se você tiver três ou mais políticas de spam de saída, as políticas entre os valores de prioridade mais alto e mais baixo terão as opções **Aumentar** prioridade e Diminuir **prioridade** disponíveis.

   Clique no ![ícone Aumentar prioridade](../../media/m365-cc-sc-increase-icon.png) **Aumentar prioridade** ou no ![ícone Diminuir prioridade](../../media/m365-cc-sc-decrease-icon.png) **Diminuir prioridade** para alterar o valor da **Prioridade**.

4. Quando terminar, clique em **Fechar** no submenu de detalhes da política.

## <a name="use-the-security-center-to-remove-custom-outbound-spam-policies"></a>Usar o centro de segurança para remover políticas personalizadas de spam de saída

Quando você usa o centro de segurança para remover uma política de spam de saída personalizada, a regra de filtro de spam e a política de filtro de spam correspondente são excluídas. Não é possível remover a política de spam de saída padrão.

1. No centro de segurança, acesse **Email e Colaboração** \> **Políticas e Regras** \> **Políticas de ameaças** \> **seção** Políticas \> **Anti-spam**.

2. Na página **Políticas anti-spam,** selecione uma política com o valor **Tipo** da política de **spam** de saída personalizada na lista clicando no nome. Na parte superior do submenu de detalhes da política exibido, clique no ![ícone Mais ações](../../media/m365-cc-sc-more-actions-icon.png) **Mais ações** \> ![ícone Excluir política](../../media/m365-cc-sc-delete-icon.png) **Excluir política**.

3. Na caixa de diálogo de confirmação exibida, clique em **Sim**.

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-outbound-spam-policies"></a>Use Exchange Online PowerShell ou EOP PowerShell autônomo para configurar políticas de spam de saída

Conforme descrito anteriormente, uma política de spam de saída consiste em uma política de filtro de spam de saída e uma regra de filtro de spam de saída.

No Exchange Online PowerShell ou no EOP PowerShell autônomo, a diferença entre políticas de filtro de spam de saída e regras de filtro de spam de saída é aparente. Você gerencia políticas de filtro de spam de saída usando os cmdlets **\* -HostedOutboundSpamFilterPolicy** e gerencia as regras de filtro de spam de saída usando os cmdlets **\* -HostedOutboundSpamFilterRule.**

- No PowerShell, primeiro você cria a política de filtro de spam de saída e, em seguida, cria a regra de filtro de spam de saída que identifica a política à que a regra se aplica.
- No PowerShell, você modifica as configurações na política de filtro de spam de saída e na regra de filtro de spam de saída separadamente.
- Quando você remove uma política de filtro de spam de saída do PowerShell, a regra de filtro de spam de saída correspondente não é removida automaticamente e vice-versa.

### <a name="use-powershell-to-create-outbound-spam-policies"></a>Usar o PowerShell para criar políticas de spam de saída

Criar uma política de spam de saída no PowerShell é um processo de duas etapas:

1. Crie a política de filtro de spam de saída.
2. Crie a regra de filtro de spam de saída que especifica a política de filtro de spam de saída à que a regra se aplica.

   **Observações**:

   - Você pode criar uma nova regra de filtro de spam de saída e atribuir uma política de filtro de spam de saída existente e nãossociada a ela. Uma regra de filtro de spam de saída não pode ser associada a mais de uma política de filtro de spam de saída.
   - Você pode definir as seguintes configurações em novas políticas de filtro de spam de saída no PowerShell que não estão disponíveis no centro de segurança até depois de criar a política:
     - Crie a nova política como desabilitada (_Habilitado_ no `$false` cmdlet **New-HostedOutboundSpamFilterRule).**
     - Definir a prioridade da política durante a criação (_Prioridade_ _\<Number\>_ ) no cmdlet **New-HostedOutboundSpamFilterRule).**
   - Uma nova política de filtro de spam de saída que você cria no PowerShell não fica visível no centro de segurança até que você atribua a política a uma regra de filtro de spam de saída.

#### <a name="step-1-use-powershell-to-create-an-outbound-spam-filter-policy"></a>Etapa 1: usar o PowerShell para criar uma política de filtro de spam de saída

Para criar uma política de filtro de spam de saída, use esta sintaxe:

```PowerShell
New-HostedOutboundSpamFilterPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

Este exemplo cria uma nova política de filtro de spam de saída chamada Contoso Executives com as seguintes configurações:

- Os limites de taxa de destinatário são restritos a valores menores que os padrões. Para obter mais informações, consulte [Sending limits across Microsoft 365 options](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options).

- Depois que um dos limites é atingido, o usuário é impedido de enviar mensagens.

```PowerShell
New-HostedOutboundSpamFilterPolicy -Name "Contoso Executives" -RecipientLimitExternalPerHour 400 -RecipientLimitInternalPerHour 800 -RecipientLimitPerDay 800 -ActionWhenThresholdReached BlockUser
```

Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [New-HostedOutboundSpamFilterPolicy](/powershell/module/exchange/new-hostedoutboundspamfilterpolicy).

#### <a name="step-2-use-powershell-to-create-an-outbound-spam-filter-rule"></a>Etapa 2: usar o PowerShell para criar uma regra de filtro de spam de saída

Para criar uma regra de filtro de spam de saída, use esta sintaxe:

```PowerShell
New-HostedOutboundSpamFilterRule -Name "<RuleName>" -HostedOutboundSpamFilterPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

Este exemplo cria uma nova regra de filtro de spam de saída chamada Contoso Executives com estas configurações:

- A política de filtro de spam de saída chamada Contoso Executives está associada à regra.
- A regra se aplica aos membros do grupo chamado Contoso Executives Group.

```PowerShell
New-HostedOutboundSpamFilterRule -Name "Contoso Executives" -HostedOutboundSpamFilterPolicy "Contoso Executives" -FromMemberOf "Contoso Executives Group"
```

Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [New-HostedOutboundSpamFilterRule](/powershell/module/exchange/new-hostedoutboundspamfilterrule).

### <a name="use-powershell-to-view-outbound-spam-filter-policies"></a>Usar o PowerShell para exibir políticas de filtro de spam de saída

Para retornar uma lista resumida de todas as políticas de filtro de spam de saída, execute este comando:

```PowerShell
Get-HostedOutboundSpamFilterPolicy
```

Para retornar informações detalhadas sobre uma política de filtro de spam de saída específica, use esta sintaxe:

```PowerShell
Get-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>" | Format-List [<Specific properties to view>]
```

Este exemplo retorna todos os valores de propriedade da política de filtro de spam de saída chamada Executivos.

```PowerShell
Get-HostedOutboundSpamFilterPolicy -Identity "Executives" | Format-List
```

Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Get-HostedOutboundSpamFilterPolicy](/powershell/module/exchange/get-hostedoutboundspamfilterpolicy).

### <a name="use-powershell-to-view-outbound-spam-filter-rules"></a>Usar o PowerShell para exibir regras de filtro de spam de saída

Para exibir as regras de filtro de spam de saída existentes, use a seguinte sintaxe:

```PowerShell
Get-HostedOutboundSpamFilterRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled>]
```

Para retornar uma lista resumida de todas as regras de filtro de spam de saída, execute este comando:

```PowerShell
Get-HostedOutboundSpamFilterRule
```

Para filtrar a lista por regras habilitadas ou desabilitadas, execute os seguintes comandos:

```PowerShell
Get-HostedOutboundSpamFilterRule -State Disabled
```

```PowerShell
Get-HostedOutboundSpamFilterRule -State Enabled
```

Para retornar informações detalhadas sobre uma regra específica de filtro de spam de saída, use esta sintaxe:

```PowerShell
Get-HostedOutboundSpamFilterRule -Identity "<RuleName>" | Format-List [<Specific properties to view>]
```

Este exemplo retorna todos os valores de propriedade da regra de filtro de spam de saída chamada Contoso Executives.

```PowerShell
Get-HostedOutboundSpamFilterRule -Identity "Contoso Executives" | Format-List
```

Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Get-HostedOutboundSpamFilterRule](/powershell/module/exchange/get-hostedoutboundspamfilterrule).

### <a name="use-powershell-to-modify-outbound-spam-filter-policies"></a>Usar o PowerShell para modificar políticas de filtro de spam de saída

As mesmas configurações estão disponíveis quando você modifica uma política de filtro de malware no PowerShell como quando você cria a política conforme descrito na Etapa [1: Use](#step-1-use-powershell-to-create-an-outbound-spam-filter-policy) o PowerShell para criar uma seção de política de filtro de spam de saída anteriormente neste artigo.

> [!NOTE]
> Não é possível renomear uma política de filtro de spam de saída (o cmdlet **Set-HostedOutboundSpamFilterPolicy** não tem _parâmetro Name)._ Ao renomear uma política de spam de saída no centro de segurança, você só está renomeando a regra de filtro de spam de _saída._

Para modificar uma política de filtro de spam de saída, use esta sintaxe:

```PowerShell
Set-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>" <Settings>
```

Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Set-HostedOutboundSpamFilterPolicy](/powershell/module/exchange/set-hostedoutboundspamfilterpolicy).

### <a name="use-powershell-to-modify-outbound-spam-filter-rules"></a>Usar o PowerShell para modificar regras de filtro de spam de saída

A única configuração que não está disponível quando você modifica uma regra de filtro de spam de saída no PowerShell é o parâmetro _Enabled_ que permite criar uma regra desabilitada. Para habilitar ou desabilitar as regras de filtro de spam de saída existentes, consulte a próxima seção.

Caso contrário, nenhuma configuração adicional estará disponível quando você modificar uma regra de filtro de spam de saída no PowerShell. As mesmas configurações estão disponíveis quando você cria uma regra, conforme descrito na Etapa [2: Use](#step-2-use-powershell-to-create-an-outbound-spam-filter-rule) o PowerShell para criar uma seção de regra de filtro de spam de saída anteriormente neste artigo.

Para modificar uma regra de filtro de spam de saída, use esta sintaxe:

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "<RuleName>" <Settings>
```

Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Set-HostedOutboundSpamFilterRule](/powershell/module/exchange/set-hostedoutboundspamfilterrule).

### <a name="use-powershell-to-enable-or-disable-outbound-spam-filter-rules"></a>Usar o PowerShell para habilitar ou desabilitar regras de filtro de spam de saída

Habilitar ou desabilitar uma regra de filtro de spam de saída no PowerShell habilita ou desabilita toda a política de spam de saída (a regra de filtro de spam de saída e a política de filtro de spam de saída atribuída). Não é possível habilitar ou desabilitar a política de spam de saída padrão (ela sempre é aplicada a todos os destinatários).

Para habilitar ou desabilitar uma regra de filtro de spam de saída no PowerShell, use esta sintaxe:

```PowerShell
<Enable-HostedOutboundSpamFilterRule | Disable-HostedOutboundSpamFilterRule> -Identity "<RuleName>"
```

Este exemplo desabilita a regra de filtro de spam de saída chamada Departamento de Marketing.

```PowerShell
Disable-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

Este exemplo habilita a mesma regra.

```PowerShell
Enable-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Enable-HostedOutboundSpamFilterRule](/powershell/module/exchange/enable-hostedoutboundspamfilterrule) e [Disable-HostedOutboundSpamFilterRule](/powershell/module/exchange/disable-hostedoutboundspamfilterrule).

### <a name="use-powershell-to-set-the-priority-of-outbound-spam-filter-rules"></a>Usar o PowerShell para definir a prioridade das regras de filtro de spam de saída

O valor mais alto de prioridade que pode ser definido em uma regra é 0. O valor mais baixo que pode ser definido depende do número de regras. Por exemplo, se você tiver cinco regras, use os valores de prioridade de 0 a 4. Alterar a prioridade de uma regra existente pode ter um efeito cascata em outras regras. Por exemplo, se você tiver cinco regras personalizadas (prioridades de 0 a 4) e alterar a prioridade de uma regra para 2, a regra existente com prioridade 2 será alterada para a prioridade 3, e a regra com prioridade 3 será alterada para prioridade 4.

Para definir a prioridade de uma regra de filtro de spam de saída no PowerShell, use a seguinte sintaxe:

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "<RuleName>" -Priority <Number>
```

Este exemplo define a prioridade da regra chamada Marketing Department como 2. Todas as regras existentes com prioridade inferior ou igual a 2 são reduzidas por 1 (seus números de prioridade são aumentados por 1).

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "Marketing Department" -Priority 2
```

**Observações**:

- Para definir a prioridade de uma nova regra ao cria-la, use o parâmetro _Priority_ no cmdlet **New-HostedOutboundSpamFilterRule.**
- A política de filtro de spam padrão de saída não tem uma regra de filtro de spam correspondente e sempre tem o valor de prioridade nãomodificável **Mais baixo**.

### <a name="use-powershell-to-remove-outbound-spam-filter-policies"></a>Usar o PowerShell para remover políticas de filtro de spam de saída

Quando você usa o PowerShell para remover uma política de filtro de spam de saída, a regra de filtro de spam de saída correspondente não é removida.

Para remover uma política de filtro de spam de saída no PowerShell, use esta sintaxe:

```PowerShell
Remove-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>"
```

Este exemplo remove a política de filtro de spam de saída chamada Departamento de Marketing.

```PowerShell
Remove-HostedOutboundSpamFilterPolicy -Identity "Marketing Department"
```

Para obter informações detalhadas sobre sintaxes e parâmetros, [consulte Remove-HostedOutboundSpamFilterPolicy](/powershell/module/exchange/remove-hostedoutboundspamfilterpolicy).

### <a name="use-powershell-to-remove-outbound-spam-filter-rules"></a>Usar o PowerShell para remover regras de filtro de spam de saída

Quando você usa o PowerShell para remover uma regra de filtro de spam de saída, a política de filtro de spam de saída correspondente não é removida.

Para remover uma regra de filtro de spam de saída no PowerShell, use esta sintaxe:

```PowerShell
Remove-HostedOutboundSpamFilterRule -Identity "<PolicyName>"
```

Este exemplo remove a regra de filtro de spam de saída chamada Departamento de Marketing.

```PowerShell
Remove-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

Para obter informações detalhadas sobre sintaxes e parâmetros, [consulte Remove-HostedOutboundSpamFilterRule](/powershell/module/exchange/remove-hostedoutboundspamfilterrule).

## <a name="for-more-information"></a>Para saber mais

[Remover usuários bloqueados do portal Usuários Restritos](removing-user-from-restricted-users-portal-after-spam.md)

[Pool de entrega de alto risco para mensagens de saída](high-risk-delivery-pool-for-outbound-messages.md)

[Perguntas frequentes sobre a proteção antispam](anti-spam-protection-faq.yml)

[Relatório de encaminhamento automático de mensagens](mfi-auto-forwarded-messages-report.md)
