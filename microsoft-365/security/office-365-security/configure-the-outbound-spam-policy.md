---
title: Configurar a filtragem de spam de saída
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a44764e9-a5d2-4c67-8888-e7fb871c17c7
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Os administradores podem aprender a exibir, criar, modificar e excluir políticas de spam de saída na proteção do Exchange Online (EOP).
ms.openlocfilehash: 8a023917443f817476986682dac136ad5c735587
ms.sourcegitcommit: 6a1a8aa024fd685d04da97bfcbc8eadacc488534
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2020
ms.locfileid: "46653012"
---
# <a name="configure-outbound-spam-filtering-in-eop"></a>Configurar a filtragem de spam de saída no EOP

Nas organizações do Microsoft 365 com caixas de correio em organizações do Exchange Online ou do Exchange Online Protection (EOP) sem caixas de correio do Exchange Online, mensagens de email de saída enviadas por meio do EOP são verificadas automaticamente quanto ao spam e à atividade de envio incomum.

O spam de saída de um usuário em sua organização normalmente indica uma conta comprometida. Mensagens de saída suspeitas são marcadas como spam (independentemente do nível de confiança de spam ou SCL) e são roteadas através do [pool de entrega de alto risco](high-risk-delivery-pool-for-outbound-messages.md) para ajudar a proteger a reputação do serviço (ou seja, manter os servidores de email de origem do Microsoft 365 fora das listas de bloqueios de IP). Os administradores são notificados automaticamente sobre atividade de email de saída suspeita e usuários bloqueados por meio de [políticas de alerta](../../compliance/alert-policies.md).

O EOP usa políticas de spam de saída como parte da defesa geral da sua organização contra spam. Para obter mais informações, consulte [Proteção antispam](anti-spam-protection.md).

Os administradores podem exibir, editar e configurar (mas não excluir) a política de spam de saída padrão. Para maior granularidade, você também pode criar políticas personalizadas de spam de saída que se aplicam a usuários, grupos ou domínios específicos em sua organização. Políticas personalizadas sempre terão prioridade sobre a política padrão, mas você pode alterar a prioridade (ordem de execução) de suas políticas personalizadas.

Você pode configurar políticas de spam de saída no centro de conformidade e segurança & ou no PowerShell (Exchange Online PowerShell para organizações do Microsoft 365 com caixas de correio no Exchange Online; EOP PowerShell autônomo para organizações sem caixas de correio do Exchange Online).

## <a name="outbound-spam-policies-in-the-security--compliance-center-vs-powershell"></a>Políticas de spam de saída no centro de conformidade e segurança & vs PowerShell

Os elementos básicos de uma política de spam de saída no EOP são:

- **A política de filtro de spam de saída**: especifica as ações para verdicts de filtragem de spam de saída e as opções de notificação.

- **A regra de filtro de spam de saída**: especifica a prioridade e os filtros de destinatário (aos quais a política se aplica) para uma política de filtro de spam de saída.

A diferença entre esses dois elementos não é óbvia quando você gerencia políticas de spam de saída no centro de conformidade de & de segurança:

- Ao criar uma política de spam de saída no centro de conformidade de & de segurança, você está realmente criando uma regra de filtro de spam de saída e a política de filtro de spam de saída associada ao mesmo tempo usando o mesmo nome para ambos.

- Quando você modifica uma política de spam de saída no centro de conformidade de & de segurança, as configurações relacionadas ao nome, prioridade, habilitado ou desabilitado e filtros de destinatário modificam a regra de filtro de spam de saída. Todas as outras configurações modificam a política de filtro de spam de saída associada.

- Quando você remove uma política de spam de saída do centro de conformidade & segurança, a regra de filtro de spam de saída e a política de filtro de spam de saída associada são removidas.

No PowerShell do Exchange Online ou no PowerShell do EOP autônomo, a diferença entre políticas de filtro de spam de saída e regras de filtro de spam de saída é aparente. Você gerencia as políticas de filtro de spam de saída usando os cmdlets ** \* -HostedOutboundSpamFilterPolicy** e gerencia as regras de filtro de spam de saída usando os cmdlets ** \* -HostedOutboundSpamFilterRule** .

- No PowerShell, você cria primeiro a política de filtro de spam de saída e, em seguida, cria a regra de filtro de spam de saída que identifica a política à qual a regra se aplica.

- No PowerShell, você modifica as configurações da política de filtro de spam de saída e a regra de filtro de spam de saída separadamente.

- Quando você remove uma política de filtro de spam de saída do PowerShell, a regra de filtro de spam de saída correspondente não é removida automaticamente e vice-versa.

### <a name="default-outbound-spam-policy"></a>Política de spam de saída padrão

Todas as organizações têm uma política interna de spam de saída chamada Default que tem estas propriedades:

- A política de filtro de spam de saída chamada default é aplicada a todos os destinatários na organização, mesmo que não haja nenhuma regra de filtro de spam de saída (filtros de destinatário) associada à política.

- A política denominada Padrão tem o valor de prioridade personalizado **Menor**, que não pode ser modificado (a política é sempre aplicada por último). As políticas personalizadas que você cria têm sempre uma prioridade mais alta do que a política denominada Padrão.

- A política denominada Padrão é a política padrão (a propriedade **IsDefault** tem o valor `True`), e não é possível excluir a política padrão.

Para aumentar a eficácia da filtragem de spam de saída, você pode criar políticas personalizadas de spam de saída com configurações mais rígidas que são aplicadas a usuários ou grupos de usuários específicos.

## <a name="what-do-you-need-to-know-before-you-begin"></a>O que você precisa saber antes de começar?

- Abra o Centro de Conformidade e Segurança em <https://protection.office.com/>. Para ir diretamente à página de **Configurações antispam**, use <https://protection.office.com/antispam>.

- Para se conectar ao PowerShell do Exchange Online, confira [Conectar ao PowerShell do Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell). Para se conectar ao EOP PowerShell autônomo, consulte [Conectar-se ao PowerShell do Exchange Online Protection.](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).

- Você precisa ter permissões atribuídas antes de poder executar os procedimentos neste tópico:

  - Para adicionar, modificar e excluir políticas de spam de saída, você precisa ser membro de um dos grupos de função a seguir:

    - **Gerenciamento de organizações** ou **Administrador de segurança** no [Centro de segurança e conformidade](permissions-in-the-security-and-compliance-center.md).
    - **Gerenciamento de organizações** ou **Gerenciamento de higiene** no [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).

  - Para acesso somente leitura às políticas de spam de saída, você precisa ser membro de um dos seguintes grupos de função:

    - **Leitor de segurança** no [Centro de segurança e conformidade](permissions-in-the-security-and-compliance-center.md).
    - **Gerenciamento da organização Somente visualização** no [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).

- Para obter as configurações recomendadas para políticas de spam de saída, confira [configurações de política de filtro de spam de saída do EOP](recommended-settings-for-eop-and-office365-atp.md#eop-outbound-spam-policy-settings).

- As [políticas de alerta](../../compliance/alert-policies.md) padrão denominadas limite de envio de **emails excedidos**, os **padrões de envio de emails suspeitos detectados**e o **usuário impedido de enviar emails** já enviar notificações por email aos membros do grupo **TenantAdmins** (**administradores globais**) sobre atividade de email de saída incomum e usuários bloqueados devido ao spam de saída. Para obter mais informações, consulte [verify the Alert Settings for Restricted Users](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users). Recomendamos que você use essas políticas de alerta em vez das opções de notificação em políticas de spam de saída.

## <a name="use-the-security--compliance-center-to-create-outbound-spam-policies"></a>Usar o centro de conformidade de & de segurança para criar políticas de spam de saída

Criar uma política de spam de saída personalizada no centro de conformidade de & de segurança cria a regra de filtro de spam e a política de filtro de spam associada ao mesmo tempo usando o mesmo nome para ambos.

1. No Centro de Conformidade e Segurança, vá para **Gerenciamento de ameaças** \> **Política** \> **Antispam**.

2. Na página **configurações antispam** , clique em **criar uma política de saída**.

3. Na **política de filtro de spam de saída** , retire-o, defina as seguintes configurações:

   - **Nome**: insira um nome exclusivo e descritivo para a política.

   - **Descrição**: digite uma descrição opcional para a política.

4. Opcion Expanda a seção **notificações** para configurar usuários adicionais que devem receber cópias e notificações de mensagens de email de saída suspeitas:

   - **Enviar uma cópia de mensagens de email de saída suspeitas para pessoas específicas**: essa configuração adiciona os usuários especificados como destinatários Cco às mensagens de saída suspeitas.

     > [!NOTE]
     > Essa configuração só funciona na política de spam de saída padrão. Não funciona em políticas personalizadas de spam de saída que você cria.

     Para habilitar essa configuração:

     1. Marque a caixa de seleção para habilitar a configuração.

     1. Clique em **adicionar pessoas**. No submenu **Adicionar ou remover destinatários** que aparece:

     1. Insira o endereço de email do remetente. Você pode especificar vários endereços de email separados por ponto-e-vírgula (;) ou um destinatário por linha.

     1. Click ![Ícone Adicionar](../../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) para adicionar os destinatários.

        Repita essas etapas quantas vezes for necessário.

        Os destinatários adicionados aparecem na seção **lista de destinatários** do submenu. Para excluir um destinatário, clique no ![ botão Remover ](../../media/scc-remove-icon.png) .

     1. Quando concluir, clique em **Salvar**.

        Para desabilitar essa configuração, desmarque a caixa de seleção.

   - **Notificar pessoas específicas se um remetente estiver bloqueado devido ao envio de spam de saída**:

     > [!IMPORTANT]
     >
     > - Essa configuração está no processo de ser preterido das políticas de spam de saída.
     >
     > - A [política de alerta](../../compliance/alert-policies.md) padrão chamada **usuário Restricted do envio de emails** já envia notificações por email para os membros do grupo **TenantAdmins** (**administradores globais**) quando os usuários são bloqueados devido a exceder os limites na seção **limites de destinatários** . É **altamente recomendável que você use a política de alerta em vez da configuração da política de spam de saída para notificar os administradores e outros usuários**. Para obter instruções, consulte [verificar as configurações de alerta para usuários restritos](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users).

5. Opcion Expanda a seção **limites de destinatário** para configurar os limites e as ações para mensagens de email de saída suspeitas:

   > [!NOTE]
   > Essas configurações só são aplicáveis às caixas de correio baseadas em nuvem.

   - **Número máximo de destinatários por usuário**

     Um valor válido é de 0 a 10000. O valor padrão é 0, o que significa que os padrões de serviço são usados. Para obter mais informações, consulte [enviando limites](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-1).

     - **Limite por hora externo**: o número máximo de destinatários externos por hora.

     - **Limite por hora interno**: o número máximo de destinatários internos por hora.

     - **Limite diário**: o número total máximo de destinatários por dia.

   - **Ação quando um usuário exceder os limites acima**: Configure a ação a ser tomada quando qualquer um dos **limites de destinatário** for excedido. Para todas as ações, os destinatários especificados na política de alerta do usuário que está **impedido de enviar emails** (e, na agora, **pessoas de notificar-se um remetente está bloqueado devido ao envio de spam** de saída na política de spam receber notificações por email.

     - **Impedir que o usuário envie email até o dia seguinte**: Este é o valor padrão. As notificações por email são enviadas e o usuário não poderá enviar mais mensagens até o dia seguinte, com base na hora UTC. Não há como o administrador substituir esse bloco.

       - O alerta de atividade chamado **usuário impedido de enviar email** notifica os administradores (por email e na página **exibir alertas** ).

       - Qualquer destinatário especificado em **notificar pessoas específicas se um remetente estiver bloqueado devido ao envio** da configuração de spam de saída na política também é notificado.

       - O usuário não poderá enviar mais mensagens até o dia seguinte, com base na hora UTC. Não há como o administrador substituir esse bloco.

     - **Impedir que o usuário envie emails**: as notificações por email são enviadas, o usuário é adicionado ao portal **[ <https://sip.protection.office.com/restrictedusers> Restricted Users]** no centro de conformidade do & de segurança e o usuário não pode enviar emails até que sejam removidos do portal de **usuários restritos** por um administrador. Depois que um administrador remover o usuário da lista, o usuário não será restringido novamente nesse dia. Para obter instruções, consulte [removendo um usuário do portal de usuários restritos após o envio de email de spam](removing-user-from-restricted-users-portal-after-spam.md).

     - **Nenhuma ação, somente alerta**: as notificações por email são enviadas.
6. Opcion Expanda a seção de **encaminhamento automático** para configurar controles sobre como o encaminhamento automático por usuários é controlado.

   > [!NOTE]
   > Essas configurações se aplicam apenas às caixas de correio baseadas em nuvem.

   - **Encaminhamento automático**
  
      Selecione uma das opções para controlar como o encaminhamento automático é manipulado.

      - **Automática**: configuração padrão que permite que o sistema controle o encaminhamento automático com o encaminhamento automático desabilitado por padrão.
      - **Ativado: o**encaminhamento externo está habilitado dentro da política sem restrição.
      - **Off**: o encaminhamento externo está desabilitado e será bloqueado

7. Precisam Expanda a seção **aplicado a** para identificar os remetentes internos aos quais a política se aplica.

    Só é possível usar uma condição ou exceção uma vez; contudo, você pode especificar vários valores para a condição ou exceção. Vários valores da mesma condição ou exceção usam a lógica OU (por exemplo, _\<sender1\>_ ou _\<sender2\>_). Para diferentes condições ou exceções, use a lógica E (por exemplo, _\<sender1\>_ e _\<member of group 1\>_).

    O mais fácil é clicar em **Adicionar uma condição** três vezes para ver todas as condições disponíveis. Clique em ![botão Remover](../../media/scc-remove-icon.png) para remover condições que você não queira configurar.

    - **O domínio do remetente é**: especifica remetentes em um ou mais dos domínios aceitos configurados na organização. Clique na caixa **Adicionar uma marca** para ver e selecionar um domínio. Clique novamente na caixa **Adicionar uma marca** para selecionar domínios adicionais se mais de um domínio estiver disponível.

    - O **remetente é**: especifica um ou mais usuários em sua organização. Clique em **Adicionar uma marca** e comece a digitar para filtrar a lista. Clique novamente na caixa **Adicionar uma marca** para selecionar outros remetentes.

    - **O remetente é um membro de**: especifica um ou mais grupos na sua organização. Clique em **Adicionar uma marca** e comece a digitar para filtrar a lista. Clique novamente na caixa **Adicionar uma marca** para selecionar outros remetentes.

    - **Exceto se**: para adicionar exceções à regra, clique em **Adicionar uma condição** três vezes para ver todas as exceções disponíveis. As configurações e o comportamento são exatamente como as condições.

8. Quando concluir, clique em **Salvar**.

## <a name="use-the-security--compliance-center-to-view-outbound-spam-policies"></a>Usar o centro de conformidade de & de segurança para exibir políticas de spam de saída

1. No Centro de Conformidade e Segurança, vá para **Gerenciamento de ameaças** \> **Política** \> **Antispam**.

2. Na página **configurações antispam** , clique em ![ expandir ícone ](../../media/scc-expand-icon.png) para expandir uma política de spam de saída:

   - A política padrão denominada **política de filtro de spam de saída**.

   - Uma política personalizada que você criou onde o valor na coluna **tipo** é a **política de spam de saída personalizada**.

3. As configurações de política são exibidas nos detalhes da política expandida que aparecem ou você pode clicar em **Editar política**.

## <a name="use-the-security--compliance-center-to-modify-outbound-spam-policies"></a>Usar o centro de conformidade de & de segurança para modificar políticas de spam de saída

1. No Centro de Conformidade e Segurança, vá para **Gerenciamento de ameaças** \> **Política** \> **Antispam**.

2. Na página **configurações antispam** , clique em ![ expandir ícone ](../../media/scc-expand-icon.png) para expandir uma política de spam de saída:

   - A política padrão denominada **política de filtro de spam de saída**.

   - Uma política personalizada que você criou onde o valor na coluna **tipo** é a **política de spam de saída personalizada**.

3. Clique em **Editar política**.

Para políticas de spam de saída personalizadas, as configurações disponíveis no submenu que aparecem são idênticas àquelas descritas na seção [usar o centro de conformidade de & de segurança para criar políticas de spam de saída](#use-the-security--compliance-center-to-create-outbound-spam-policies) .

Para a política de spam de saída padrão chamada **política de filtro de spam de saída**, a seção **aplicado à** não está disponível (a política se aplica a todos) e não é possível renomear a política.

Para habilitar ou desabilitar uma política, definir a ordem de prioridade da política ou configurar notificações de quarentena de usuário final, confira as seções a seguir.

### <a name="enable-or-disable-outbound-spam-policies"></a>Habilitar ou desabilitar políticas de spam de saída

1. No Centro de Conformidade e Segurança, vá para **Gerenciamento de ameaças** \> **Política** \> **Antispam**.

2. Na página **configurações antispam** , clique em ![ expandir ícone ](../../media/scc-expand-icon.png) para expandir uma política personalizada que você criou (o valor na coluna **tipo** é a política de **spam de saída personalizada**).

3. Nos detalhes exibidos da política expandida, observe o valor na coluna **Ativado**.

   Mova o botão de alternância para a esquerda para desabilitar a política: ![Desativar](../../media/scc-toggle-off.png)

   Mova o botão de alternância para a direita para habilitar a política: ![Ativar](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)

Não é possível desabilitar a política de spam de saída padrão.

### <a name="set-the-priority-of-custom-outbound-spam-policies"></a>Definir a prioridade das políticas personalizadas de spam de saída

Por padrão, as políticas de spam de saída recebem uma prioridade com base na ordem em que foram criadas (as políticas mais recentes são de prioridade mais baixa do que as diretivas mais antigas). Um número de prioridade menor indica uma maior prioridade para a política (0 é a maior), e as políticas são processadas por ordem de prioridade (políticas com maior prioridade são processadas antes das políticas com menor prioridade). Duas políticas não podem ter a mesma prioridade.

As políticas de spam de saída personalizadas são exibidas na ordem em que são processadas (a primeira política tem o valor de **prioridade** 0). A política de spam de saída padrão chamada **política de filtro de spam de saída** tem o valor de prioridade **mais baixo**e não pode ser alterada.

Para alterar a prioridade de uma política, mova a política para cima ou para baixo na lista (não é possível modificar diretamente o número de **Prioridade** no Centro de Conformidade e Segurança).

1. No Centro de Conformidade e Segurança, vá para **Gerenciamento de ameaças** \> **Política** \> **Antispam**.

2. Na página **configurações antispam** , encontre as políticas nas quais o valor na coluna **tipo** é a política de **spam de saída personalizada**. Observe os valores na coluna **Prioridade**:

   - A política de spam de saída personalizada com a prioridade mais alta tem o ![ ícone de seta para baixo ](../../media/ITPro-EAC-DownArrowIcon.png) **0**.

   - A política de spam de saída personalizada com a prioridade mais baixa tem o ![ ícone de seta para cima ](../../media/ITPro-EAC-UpArrowIcon.png) **n** (por exemplo, ![ ícone de seta para cima ](../../media/ITPro-EAC-UpArrowIcon.png) **3**).

   - Se você tiver três ou mais políticas de spam de saída personalizadas, as políticas entre a prioridade mais alta e a mais baixa terão valores para cima ícone de seta para ![ ](../../media/ITPro-EAC-UpArrowIcon.png)![ baixo ícone ](../../media/ITPro-EAC-DownArrowIcon.png) **n** (por exemplo, seta para cima ícone de seta ![ ](../../media/ITPro-EAC-UpArrowIcon.png)![ para baixo ](../../media/ITPro-EAC-DownArrowIcon.png) **2**).

3. Clique em ![ícone Seta para cima](../../media/ITPro-EAC-UpArrowIcon.png) ou ![ícone Seta para baixo](../../media/ITPro-EAC-DownArrowIcon.png) para mover a política de spam de saída personalizada para cima ou para baixo na lista de prioridades.

## <a name="use-the-security--compliance-center-to-remove-outbound-spam-policies"></a>Usar o centro de conformidade de & de segurança para remover políticas de spam de saída

1. No Centro de Conformidade e Segurança, vá para **Gerenciamento de ameaças** \> **Política** \> **Antispam**.

2. Na página **configurações antispam** , clique em ![ expandir ícone ](../../media/scc-expand-icon.png) para expandir a política personalizada que você deseja excluir (a coluna **tipo** é **personalizada spam de saída**).

3. Nas informações da política expandida, clique em **Excluir política**.

4. Clique em **Sim** na caixa de diálogo exibida.

Não é possível remover a política padrão.

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-outbound-spam-policies"></a>Usar o PowerShell do Exchange Online ou o PowerShell do EOP para configurar políticas de spam de saída

### <a name="use-powershell-to-create-outbound-spam-policies"></a>Usar o PowerShell para criar políticas de spam de saída

A criação de uma política de spam de saída no PowerShell é um processo de duas etapas:

1. Criar a política de filtro de spam de saída.

2. Crie a regra de filtro de spam de saída que especifica a política de filtro de spam de saída à qual a regra se aplica.

 **Observações**:

- Você pode criar uma nova regra de filtro de spam de saída e atribuir uma diretiva de filtro de spam de saída não associada existente a ela. Uma regra de filtro de spam de saída não pode ser associada a mais de uma política de filtro de spam de saída.

- Você pode definir as seguintes configurações em novas políticas de filtro de spam de saída no PowerShell que não estão disponíveis no centro de conformidade & de segurança até que a política seja criada:

  - Crie a nova política como desabilitada (_habilitada_ `$false` no cmdlet **New-HostedOutboundSpamFilterRule** ).

  - Definir a prioridade da política durante a criação (_prioridade_ _\<Number\>_ ) no cmdlet **New-HostedOutboundSpamFilterRule** ).

- Uma nova política de filtro de spam de saída que você cria no PowerShell não fica visível no centro de conformidade & segurança até que você atribua a política a uma regra de filtro de spam.

#### <a name="step-1-use-powershell-to-create-an-outbound-spam-filter-policy"></a>Etapa 1: usar o PowerShell para criar uma política de filtro de spam de saída

Para criar uma política de filtro de spam de saída, use esta sintaxe:

```PowerShell
New-HostedOutboundSpamFilterPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

Este exemplo cria uma nova política de filtro de spam de saída chamada contoso executivos com as seguintes configurações:

- Os limites de taxa de destinatários são restritos a valores menores que o padrão. Para obter mais informações, consulte [enviando limites nas opções do Microsoft 365](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options).

- Depois que um dos limites é alcançado, o usuário é impedido de enviar mensagens.

```PowerShell
New-HostedOutboundSpamFilterPolicy -Name "Contoso Executives" -RecipientLimitExternalPerHour 400 -RecipientLimitInternalPerHour 800 -RecipientLimitPerDay 800 -ActionWhenThresholdReached BlockUser
```

Para informações detalhadas de sintaxes e de parâmetros, consulte [New-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/new-hostedoutboundspamfilterpolicy).

#### <a name="step-2-use-powershell-to-create-an-outbound-spam-filter-rule"></a>Etapa 2: usar o PowerShell para criar uma regra de filtro de spam de saída

Para criar uma regra de filtro de spam de saída, use esta sintaxe:

```PowerShell
New-HostedOutboundSpamFilterRule -Name "<RuleName>" -HostedOutboundSpamFilterPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

Este exemplo cria uma nova regra de filtro de spam de saída chamada contoso executivos com estas configurações:

- A política de filtro de spam de saída chamada contoso executivos está associada à regra.

- A regra se aplica aos membros do grupo chamado Contoso Executives Group.

```PowerShell
New-HostedOutboundSpamFilterRule -Name "Contoso Executives" -HostedOutboundSpamFilterPolicy "Contoso Executives" -SentToMemberOf "Contoso Executives Group"
```

Para informações detalhadas de sintaxes e de parâmetros, consulte [New-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/new-hostedoutboundspamfilterrule).

### <a name="use-powershell-to-view-outbound-spam-filter-policies"></a>Usar o PowerShell para exibir políticas de filtro de spam de saída

Para retornar uma lista resumida de todas as políticas de filtro de spam de saída, execute este comando:

```PowerShell
Get-HostedOutboundSpamFilterPolicy
```

Para retornar informações detalhadas sobre uma política de filtro de spam de saída específica, use a seguinte sintaxe:

```PowerShell
Get-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>" | Format-List [<Specific properties to view>]
```

Este exemplo retorna todos os valores de propriedade da política de filtro de spam de saída chamada executivos.

```PowerShell
Get-HostedOutboundSpamFilterPolicy -Identity "Executives" | Format-List
```

Para informações detalhadas de sintaxes e de parâmetros, consulte [Get-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/get-hostedoutboundspamfilterpolicy).

### <a name="use-powershell-to-view-outbound-spam-filter-rules"></a>Usar o PowerShell para exibir regras de filtro de spam de saída

Para exibir as regras de filtro de spam de saída existentes, use a seguinte sintaxe:

```PowerShell
Get-HostedOutboundSpamFilterRule [-Identity "<RuleIdentity>] [-State <Enabled | Disabled]
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

Para retornar informações detalhadas sobre uma regra de filtro de spam de saída específica, use esta sintaxe:

```PowerShell
Get-HostedOutboundSpamFilterRule -Identity "<RuleName>" | Format-List [<Specific properties to view>]
```

Este exemplo retorna todos os valores de propriedade da regra de filtro de spam de saída chamada contoso executivos.

```PowerShell
Get-HostedOutboundSpamFilterRule -Identity "Contoso Executives" | Format-List
```

Para informações detalhadas de sintaxes e de parâmetros, consulte [Get-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/get-hostedoutboundspamfilterrule).

### <a name="use-powershell-to-modify-outbound-spam-filter-policies"></a>Usar o PowerShell para modificar as políticas de filtro de spam de saída

As mesmas configurações estão disponíveis quando você modifica uma política de filtro de malware no PowerShell quando cria a política, conforme descrito na seção [etapa 1: usar o PowerShell para criar uma política de filtro de spam de saída](#step-1-use-powershell-to-create-an-outbound-spam-filter-policy) , anteriormente neste tópico.

> [!NOTE]
> Não é possível renomear uma política de filtro de spam de saída (o cmdlet **set-HostedOutboundSpamFilterPolicy** não tem nenhum parâmetro _Name_ ). Ao renomear uma política de spam de saída no centro de conformidade & segurança, você estará apenas renomeando a _regra_de filtro de spam de saída.

Para modificar uma política de filtro de spam de saída, use esta sintaxe:

```PowerShell
Set-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>" <Settings>
```

Para informações detalhadas de sintaxes e de parâmetros, consulte [set-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/set-hostedoutboundspamfilterpolicy).

### <a name="use-powershell-to-modify-outbound-spam-filter-rules"></a>Usar o PowerShell para modificar as regras de filtro de spam de saída

A única configuração que não está disponível quando você modifica uma regra de filtro de spam de saída no PowerShell é o parâmetro _habilitado_ que permite criar uma regra desabilitada. Para habilitar ou desabilitar regras de filtro de spam de saída existentes, consulte a próxima seção.

Caso contrário, nenhuma configuração adicional estará disponível quando você modificar uma regra de filtro de spam de saída no PowerShell. As mesmas configurações estão disponíveis quando você cria uma regra, conforme descrito na seção [etapa 2: usar o PowerShell para criar uma regra de filtro de spam de saída](#step-2-use-powershell-to-create-an-outbound-spam-filter-rule) , anteriormente neste tópico.

Para modificar uma regra de filtro de spam de saída, use esta sintaxe:

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "<RuleName>" <Settings>
```

Para informações detalhadas de sintaxes e de parâmetros, consulte [set-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/set-hostedoutboundspamfilterrule).

### <a name="use-powershell-to-enable-or-disable-outbound-spam-filter-rules"></a>Usar o PowerShell para habilitar ou desabilitar as regras de filtro de spam de saída

Habilitar ou desabilitar uma regra de filtro de spam de saída no PowerShell habilita ou desabilita toda a política de spam de saída (a regra de filtro de spam de saída e a política de filtro de spam de saída atribuída). Você não pode habilitar ou desabilitar a política de spam de saída padrão (sempre é sempre aplicada a todos os destinatários).

Para habilitar ou desabilitar uma regra de filtro de spam de saída no PowerShell, use esta sintaxe:

```PowerShell
<Enable-HostedOutboundSpamFilterRule | Disable-HostedOutboundSpamFilterRule> -Identity "<RuleName>"
```

Este exemplo desabilita a regra de filtro de spam de saída chamada departamento de marketing.

```PowerShell
Disable-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

Este exemplo habilita a mesma regra.

```PowerShell
Enable-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

Para informações detalhadas de sintaxes e de parâmetros, consulte [Enable-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/enable-hostedoutboundspamfilterrule) e [Disable-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/disable-hostedoutboundspamfilterrule).

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

> [!NOTE]
>
> - Para definir a prioridade de uma nova regra ao criá-la, use o parâmetro _Priority_ no cmdlet **New-HostedOutboundSpamFilterRule** .
>
> - A política de filtro de spam padrão de saída não tem uma regra de filtro de spam correspondente e sempre tem o valor de prioridade não modificável **mais baixo**.

### <a name="use-powershell-to-remove-outbound-spam-filter-policies"></a>Usar o PowerShell para remover as políticas de filtro de spam de saída

Quando você usa o PowerShell para remover uma política de filtro de spam de saída, a regra de filtro de spam de saída correspondente não é removida.

Para remover uma política de filtro de spam de saída no PowerShell, use esta sintaxe:

```PowerShell
Remove-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>"
```

Este exemplo remove a política de filtro de spam de saída chamada departamento de marketing.

```PowerShell
Remove-HostedOutboundSpamFilterPolicy -Identity "Marketing Department"
```

Para informações detalhadas de sintaxes e de parâmetros, consulte [Remove-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/remove-hostedoutboundspamfilterpolicy).

### <a name="use-powershell-to-remove-outbound-spam-filter-rules"></a>Usar o PowerShell para remover as regras de filtro de spam de saída

Quando você usa o PowerShell para remover uma regra de filtro de spam de saída, a política de filtro de spam de saída correspondente não é removida.

Para remover uma regra de filtro de spam de saída no PowerShell, use esta sintaxe:

```PowerShell
Remove-HostedOutboundSpamFilterRule -Identity "<PolicyName>"
```

Este exemplo remove a regra de filtro de spam de saída chamada departamento de marketing.

```PowerShell
Remove-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

Para informações detalhadas de sintaxes e de parâmetros, consulte [Remove-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/remove-hostedoutboundspamfilterrule).

## <a name="for-more-information"></a>Para obter mais informações

[Remover usuários bloqueados do portal Usuários restritos](removing-user-from-restricted-users-portal-after-spam.md)

[Pool de entrega de alto risco para mensagens de saída](high-risk-delivery-pool-for-outbound-messages.md)

[Perguntas frequentes sobre a proteção antispam](anti-spam-protection-faq.md)

[Relatório de encaminhamento automático de mensagens](mfi-auto-forwarded-messages-report.md)
