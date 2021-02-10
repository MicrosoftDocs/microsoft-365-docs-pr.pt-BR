---
title: Configurar políticas anti-phishing em EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.date: ''
localization_priority: Normal
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Os administradores podem aprender a criar, modificar e excluir as políticas anti-phishing disponíveis em organizações do Exchange Online Protection (EOP) com ou sem caixas de correio do Exchange Online.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 052e19d811f56fe633ff0fbde79f51860a04a669
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/09/2021
ms.locfileid: "50165842"
---
# <a name="configure-anti-phishing-policies-in-eop"></a>Configurar políticas anti-phishing em EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
- [Proteção do Exchange Online](https://go.microsoft.com/fwlink/?linkid=2148611)

Nas organizações do Microsoft 365 com caixas de correio no Exchange Online ou organizações autônomas do Exchange Online Protection (EOP) sem caixas de correio do Exchange Online, há uma política anti-phishing padrão que contém um número limitado de recursos antifalsagem habilitados por padrão. Para obter mais informações, consulte [Configurações de Spoof em políticas anti-phishing.](set-up-anti-phishing-policies.md#spoof-settings)

Os administradores podem exibir, editar e configurar (mas não excluir) a política anti-phishing padrão. Para maior granularidade, você também pode criar políticas anti-phishing personalizadas que se aplicam a usuários, grupos ou domínios específicos em sua organização. Políticas personalizadas sempre terão prioridade sobre a política padrão, mas você pode alterar a prioridade (ordem de execução) de suas políticas personalizadas.

As organizações com caixas de correio do Exchange Online podem configurar políticas anti-phishing no Centro de Conformidade e Segurança & ou no PowerShell do Exchange Online. As organizações autônomas do EOP só podem usar o Centro de Conformidade & segurança.

Para obter informações sobre como criar e modificar as políticas anti-phishing mais avançadas no Microsoft Defender para Office 365 que estão disponíveis no Defender para Office 365, consulte Configurar políticas [anti-phishing no Microsoft Defender para Office 365.](configure-atp-anti-phishing-policies.md)

Os elementos básicos de uma política anti-phishing são:

- **A política anti-phishing:** especifica as proteções de phishing para habilitar ou desabilitar e as ações para aplicar opções.
- **A regra anti-phishing:** especifica a prioridade e os filtros de destinatário (a quem a política se aplica) para uma política anti-phishing.

A diferença entre esses dois elementos não é óbvia quando você gerencia políticas anti-phishing no Centro de Conformidade & e Segurança:

- Ao criar uma política anti-phishing, você está realmente criando uma regra anti-phishing e a política anti-phishing associada ao mesmo tempo usando o mesmo nome para ambos.
- Quando você modifica uma política anti-phishing, as configurações relacionadas ao nome, prioridade, habilitada ou desabilitada e filtros de destinatário modificam a regra anti-phishing. Todas as outras configurações modificam a política anti-phishing associada.
- Quando você remove uma política anti-phishing, a regra anti-phishing e a política anti-phishing associada são removidas.

No PowerShell do Exchange Online, você gerencia a política e a regra separadamente. Para obter mais informações, consulte a seção Usar o PowerShell do Exchange Online para configurar políticas [anti-phishing](#use-exchange-online-powershell-to-configure-anti-phishing-policies) posteriormente neste artigo.

Cada organização tem uma política antiphishing interna chamada Office365 AntiPhish Default que tem estas propriedades:

- A política é aplicada a todos os destinatários na organização, mesmo que não haja nenhuma regra anti-phishing (filtros de destinatário) associada à política.
- A política tem o valor de prioridade personalizado **Menor**, que não pode ser modificado (a política é sempre aplicada por último). As políticas personalizadas que você cria, sempre têm uma prioridade mais alta.
- A política é a padrão (a propriedade **IsDefault** tem o valor `True`), e não é possível excluir a política padrão.

Para aumentar a eficácia da proteção anti-phishing, você pode criar políticas anti-phishing personalizadas com configurações mais estritas aplicadas a usuários ou grupos de usuários específicos.

## <a name="what-do-you-need-to-know-before-you-begin"></a>O que você precisa saber antes de começar?

- Você abrir o Centro de conformidade e segurança em <https://protection.office.com/>. Para ir diretamente para a **página anti-phishing,** use <https://protection.office.com/antiphishing> .

- Para se conectar ao Windows PowerShell do Exchange Online, confira [Conectar ao Windows PowerShell do Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).

  Você não pode gerenciar políticas anti-phishing no EOP PowerShell autônomo.

- Você precisa de permissões no Centro de Conformidade e Segurança antes de poder realizar os procedimentos neste artigo:
  - Para adicionar, modificar e excluir políticas anti-phishing, você  precisa ser membro dos grupos de função Gerenciamento da Organização ou **Administrador de** Segurança.
  - Para acesso somente leitura a políticas anti-phishing, você precisa ser membro dos grupos de funções Leitor **Global** ou **Leitor de** <sup>\*</sup> Segurança.

  Para saber mais, confira [Permissões no Centro de Conformidade de Segurança](permissions-in-the-security-and-compliance-center.md).

  **Observações**:

  - Adicionar usuários à função correspondente do Azure Active Directory no Centro de administração do Microsoft 365 fornece aos usuários as permissões necessárias no Centro de Segurança e Conformidade _e_ permissões para outros recursos no Microsoft 365. Para obter mais informações, confira o artigo [Sobre funções de administrador](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).
  - O **grupo de função Gerenciamento da Organização Somente** Exibição no Exchange [Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) também oferece acesso somente leitura ao <sup>\*</sup> recurso.
  - <sup>\*</sup> No Centro de Conformidade & segurança, o acesso somente leitura permite que os usuários vejam as configurações de políticas anti-phishing personalizadas. Os usuários somente leitura não podem ver as configurações na política anti-phishing padrão.

- Para criar e modificar políticas anti-phishing no EOP autônomo, você precisa fazer algo que exija _moderação_ para seu locatário. Por exemplo, no Centro de administração do Exchange  (EAC), você pode ir para  a guia Permissões, selecionar um grupo de função existente, clicar em Editar ícone e remover uma função (que, por fim, você adicionará ![ ](../../media/ITPro-EAC-EditIcon.png) novamente). Se o seu locatário nunca tiver sido dratado, você obterá uma caixa de diálogo chamada Atualizar configurações da organização **com** uma barra de progresso que deve ser concluída com êxito. Para obter mais informações sobre a moderação, consulte o cmdlet [Enable-OrganizationCustomization](https://docs.microsoft.com/powershell/module/exchange/enable-organizationcustomization) (que não está disponível no EOP PowerShell autônomo ou no Centro de Conformidade e & Segurança).

- Para nossas configurações recomendadas para políticas anti-phishing, consulte as configurações de política [anti-phishing](recommended-settings-for-eop-and-office365-atp.md#eop-default-anti-phishing-policy-settings)padrão do EOP.

- Permita até 30 minutos para que a política atualizada seja aplicada.

- Para obter informações sobre onde as políticas anti-phishing são aplicadas no pipeline de filtragem, consulte Ordem e [precedência da proteção de email.](how-policies-and-protections-are-combined.md)

## <a name="use-the-security--compliance-center-to-create-anti-phishing-policies"></a>Usar o Centro de Conformidade & segurança para criar políticas anti-phishing

Criar uma política anti-phishing personalizada no Centro de Conformidade e Segurança cria a regra anti-phishing e a política anti-phish & ing associada ao mesmo tempo usando o mesmo nome para ambos.

Ao criar uma política anti-phishing, você só pode especificar o nome, a descrição e o filtro de destinatário que identifica a quem a política se aplica. Depois de criar a política, você pode modificar a política para alterar ou revisar as configurações anti-phishing padrão.

1. No Centro de Conformidade & Segurança, vá para **Política** de Gerenciamento \> **de Ameaças** \> **Anti-phishing**.

2. Na página **Anti-phishing,** clique em **Criar**.

3. O **assistente Criar uma nova política anti-phishing** é aberto. Na página **Nomear sua política,** de configure as seguintes configurações:

   - **Nome**: insira um nome exclusivo e descritivo para a política.

   - **Descrição**: digite uma descrição opcional para a política.

   Quando terminar, clique em **Avançar**.

4. Na página **Aplicado a** que aparece, identifique os destinatários internos aos quais a política se aplica.

   Só é possível usar uma condição ou exceção uma vez; contudo, você pode especificar vários valores para a condição ou exceção. Vários valores da mesma condição ou exceção usam a lógica OU (por exemplo, _\<recipient1\>_ ou _\<recipient2\>_). Para diferentes condições ou exceções, use a lógica E (por exemplo, _\<recipient1\>_ e _\<member of group 1\>_).

   Clique **em Adicionar uma condição.** No menu suspenso exibido, selecione uma condição em **Aplicado se:**

   - **O destinatário é:** Especifica uma ou mais caixas de correio, usuários de email ou contatos de email em sua organização.
   - **O destinatário é membro de:** Especifica um ou mais grupos em sua organização.
   - **O domínio do destinatário é**: Especifica os destinatários em um ou mais domínios aceitos configurados na sua organização. 

   Depois de selecionar a condição, um menu suspenso correspondente será exibido com **uma caixa Qualquer uma dessas.**

   - Clique na caixa e role pela lista de valores a selecionar.
   - Clique na caixa e comece a digitar para filtrar a lista e selecionar um valor.
   - Para adicionar valores adicionais, clique em uma área vazia na caixa.
   - Para remover entradas individuais, clique **no** ícone ![ Remover no ](../../media/scc-remove-icon.png) valor.
   - Para remover toda a condição, clique **no** ícone ![ Remover na ](../../media/scc-remove-icon.png) condição.

   Para adicionar uma condição adicional, clique **em Adicionar uma condição** e selecione um valor restante em Aplicado **se**.

   Para adicionar exceções, clique em **Adicionar uma condição** e selecione uma exceção em Exceto **se**. As configurações e o comportamento são exatamente como as condições.

   Quando terminar, clique em **Avançar**.

5. Na página **Revisar as configurações** exibida, revise as configurações. Você pode clicar **em Editar** em cada configuração para modificá-la.

   Quando terminar, clique em **Criar esta política.**

6. Clique **em OK** na caixa de diálogo de confirmação exibida.

Depois de criar a política anti-phishing com essas configurações gerais de política, use as instruções na próxima seção para definir as configurações de proteção na política.

## <a name="use-the-security--compliance-center-to-modify-anti-phishing-policies"></a>Usar o Centro de Conformidade & segurança para modificar políticas anti-phishing

Use os procedimentos a seguir para modificar políticas anti-phishing: uma nova política que você criou ou políticas existentes que você já personalificou.

1. Se você ainda não estiver lá, abra o Centro de  Conformidade e Segurança & e vá para \>  \> **Anti-phishing** da Política de Gerenciamento de Ameaças.

2. Selecione a política anti-phishing personalizada que você deseja modificar. Se ele já estiver selecionado, desmarque-o e selecione-o novamente.

3. O **flyout \<name\> Editar sua** política é exibido. Clicar em **Editar** em qualquer seção lhe dá acesso às configurações dessa seção.

   - As etapas a seguir são apresentadas na ordem em que as seções aparecem, mas não são sequenciais (você pode selecionar e modificar as seções em qualquer ordem).

   - Depois de  clicar em Editar em uma seção, as configurações disponíveis são apresentadas em um formato  de assistente, mas  você  pode pular dentro das páginas em qualquer ordem e pode clicar em Salvar em qualquer página (ou ![ ](../../media/scc-remove-icon.png) **\<name\>** cancelar ou fechar ícone para retornar à página Editar sua política (você não precisa visitar a última página do assistente para salvar ou sair).

4. **Configuração de** política: **clique** em Editar para modificar as mesmas configurações que estavam disponíveis quando você [criou](#use-the-security--compliance-center-to-create-anti-phishing-policies) a política na seção anterior:

   - **Nome**
   - **Descrição**
   - **Aplicado a**
   - **Revise suas configurações**

   Quando terminar, clique em **Salvar** em qualquer página.

5. **Spoof**:  Clique em Editar para ativar ou desativar a inteligência contra spoof, ativar ou desativar a identificação de remetente não autenticado no Outlook e configurar a ação para aplicar às mensagens de remetentes bloqueados. Para obter mais informações, consulte [Configurações de Spoof em políticas anti-phishing.](set-up-anti-phishing-policies.md#spoof-settings)

   Observe que essas mesmas configurações também estão disponíveis em políticas anti-phishing no Defender para Office 365.

   - **Configurações de filtro de spoofing:** o valor padrão é **On,** e recomendamos que você o deixe em. Para desativar, deslize a alternância para **Desligado.** Para obter mais informações, [consulte Configurar a inteligência contra spoof no EOP.](learn-about-spoof-intelligence.md)

     > [!NOTE]
     > Você não precisará desabilitar a proteção anti-spoofing se seu registro MX não apontar para o Microsoft 365; em vez disso, você habilita a Filtragem Aprimorada para Conectores. Para obter instruções, consulte [Filtragem aprimorada para conectores no Exchange Online.](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)

   - **Habilitar o recurso Remetente Não Autenticado:** o valor padrão é **Ativado.** Para desativar, deslize a alternância para **Desligado.**

   - **Ações:** especifique a ação a ser tomada em mensagens que não têm inteligência contra spoof:

     **Se o email for enviado por alguém que não tem permissão para fazer a spoof do seu domínio:**

     - **Mover mensagem para as pastas de Lixo Eletrônico dos destinatários**
     - **Colocar a mensagem em quarentena**

   - **Revise suas configurações:** em vez de clicar em cada etapa individual, as configurações são exibidas em um resumo.

     - Você pode clicar **em Editar** em cada seção para voltar à página relevante.
     - Você pode alternar as seguintes  configurações **diretamente** nesta página:

       - **Habilitar a proteção antispoofing**
       - **Habilitar o recurso Remetente Não Autenticado**

   Quando terminar, clique em **Salvar** em qualquer página.

6. De volta à **página Editar sua política, \<Name\>** revise suas configurações e clique em **Fechar.**

### <a name="use-the-security--compliance-center-to-modify-the-default-anti-phishing-policy"></a>Usar o Centro de Conformidade & segurança para modificar a política anti-phishing padrão

A política antiphishing padrão é denominada Office365 AntiPhish Default e não aparece na lista de políticas. Para modificar a política anti-phishing padrão, faça o seguinte:

1. No Centro de Conformidade & Segurança, vá para **Política** de Gerenciamento \> **de Ameaças** \> **Anti-phishing**.

2. Na página **Anti-phishing,** clique em **Política padrão.**

3. A **página Editar sua política Padrão AntiPhish do Office365 é** exibida. As seções a seguir estão disponíveis, que contêm configurações idênticas para quando você [modifica uma política personalizada.](#use-the-security--compliance-center-to-modify-anti-phishing-policies)

   - **Representação**
   - **Spoof**
   - **Configurações avançadas**

   As configurações a seguir não estão disponíveis quando você modifica a política padrão:

   - Você pode  ver a seção de configuração de política e os valores, mas não há **nenhum** link de edição, portanto, você não pode modificar as configurações (nome da política, descrição e a quem a política se aplica (aplica-se a todos os destinatários)).
   - Não é possível excluir a política padrão.
   - Não é possível alterar a prioridade da política padrão (ela é sempre aplicada por último).

4. Na página **Editar sua política Padrão AntiPhish do Office365,** revise suas configurações e clique em **Fechar.**

### <a name="enable-or-disable-custom-anti-phishing-policies"></a>Habilitar ou desabilitar políticas anti-phishing personalizadas

1. No Centro de Conformidade & Segurança, vá para **Política** de Gerenciamento \> **de Ameaças** \> **Anti-phishing**.

2. Observe o valor na coluna **Status:**

   - Deslize a alternância para **Desabilitar** para desabilitar a política.

   - Deslize a alternância para **Ativado** para habilitar a política.

Não é possível desabilitar a política anti-phishing padrão.

### <a name="set-the-priority-of-custom-anti-phishing-policies"></a>Definir a prioridade de políticas anti-phishing personalizadas

Por padrão, as políticas anti-phishing têm uma prioridade baseada na ordem em que foram criadas (as políticas mais novas têm prioridade menor do que as políticas mais antigas). Um número de prioridade menor indica uma maior prioridade para a política (0 é a maior), e as políticas são processadas por ordem de prioridade (políticas com maior prioridade são processadas antes das políticas com menor prioridade). Duas políticas não podem ter a mesma prioridade, e o processamento da política será interrompido após a primeira política ser aplicada.

Para obter mais informações sobre a ordem de precedência e como várias políticas são avaliadas e aplicadas, confira [Ordem e precedência da proteção de email](how-policies-and-protections-are-combined.md).

As políticas anti-phishing personalizadas são exibidas na ordem em que são processadas (a primeira política tem o **valor** prioridade 0). A política antiphishing padrão chamada Office365 AntiPhish Default tem o valor de prioridade personalizado **Menor,** e você não pode alterá-la.

 **Observação:** no Centro de Conformidade & segurança, você só pode alterar a prioridade da política anti-phishing depois de criar a política. No PowerShell, você pode substituir a prioridade padrão ao criar a regra anti-phishing (que pode afetar a prioridade das regras existentes).

Para alterar a prioridade de  uma política, clique em Aumentar prioridade ou Diminuir prioridade  nas propriedades da política (não é possível modificar diretamente o número prioridade no Centro de Conformidade e Segurança &).  Alterar a prioridade de uma política só faz sentido se você tiver várias políticas.

1. No Centro de Conformidade & segurança,  vá para \>  \> **anti-phishing da Política de Gerenciamento** de Ameaças da ATP.

2. Selecione a política que você deseja modificar. Se ele já estiver selecionado, desmarque-o e selecione-o novamente.

3. O **flyout \<name\> Editar sua** política é exibido.

   - A política anti-phishing personalizada com o **valor** prioridade **0** tem apenas o **botão** Diminuir prioridade disponível.

   - A política anti-phishing personalizada com o menor valor **priority** (por exemplo, **3**) tem apenas o **botão** Aumentar prioridade disponível.

   - Se você tiver três ou mais políticas anti-phishing personalizadas, as  políticas  entre os valores de prioridade mais alta e mais baixa terão os botões Aumentar prioridade e Diminuir prioridade disponíveis.

4. Clique **em Aumentar prioridade** ou Diminuir **prioridade** para alterar o **valor prioridade.**

5. Quando terminar, clique em **Fechar**.

## <a name="use-the-security--compliance-center-to-view-anti-phishing-policies"></a>Usar o Centro de Conformidade & segurança para exibir políticas anti-phishing

1. No Centro de Conformidade & Segurança e vá para **Política** de Gerenciamento de Ameaças \>  \> **Anti-phishing**.

2. Faça uma das seguintes etapas:

   - Selecione uma política anti-phishing personalizada que você deseja exibir. Se ele já estiver selecionado, desmarque-o e selecione-o novamente.

   - Clique **em Política Padrão** para exibir a política anti-phishing padrão.

3. O **menu \<name\> Editar seu menu** desdoado de política é exibido, onde você pode exibir as configurações e os valores.

## <a name="use-the-security--compliance-center-to-remove-anti-phishing-policies"></a>Usar o Centro de Conformidade & segurança para remover políticas anti-phishing

1. No Centro de Conformidade & Segurança, vá para **Política** de Gerenciamento de \> **Ameaças** \> **Anti-phishing**.

2. Selecione a política que você deseja remover. Se ele já estiver selecionado, desmarque-o e selecione-o novamente.

3. No flyout **Editar a política \<name\>** exibida, clique em Excluir política e, em seguida, clique em **Sim** na caixa de diálogo de aviso exibida.

Não é possível remover a política padrão.

## <a name="use-exchange-online-powershell-to-configure-anti-phishing-policies"></a>Usar o PowerShell do Exchange Online para configurar políticas anti-phishing

Conforme descrito anteriormente, uma política anti-phishing consiste em uma política anti-phishing e uma regra anti-phishing.

No PowerShell do Exchange Online, a diferença entre políticas anti-phishing e regras anti-phishing é aparente. Você gerencia políticas anti-phishing usando os cmdlets **\* -AntiPhishPolicy** e gerencia regras antiphish usando os cmdlets **\* -AntiPhishRule.**

- No PowerShell, você cria primeiro a política anti-phishing e, em seguida, cria a regra anti-phishing que identifica a política à que a regra se aplica.
- No PowerShell, você modifica as configurações da política anti-phishing e da regra anti-phishing separadamente.
- Quando você remove uma política anti-phishing do PowerShell, a regra anti-phishing correspondente não é removida automaticamente e vice-versa.

> [!NOTE]
> Os procedimentos do PowerShell a seguir não estão disponíveis em organizações autônomas do EOP usando o PowerShell da Proteção do Exchange Online.

### <a name="use-powershell-to-create-anti-phishing-policies"></a>Usar o PowerShell para criar políticas anti-phishing

Criar uma política anti-phishing no PowerShell é um processo de duas etapas:

1. Crie a política anti-phishing.
2. Crie a regra anti-phishing que especifica a política anti-phishing à que a regra se aplica.

 **Observações**:

- Você pode criar uma nova regra anti-phishing e atribuir uma política anti-phishing existente e nãossociada a ela. Uma regra anti-phishing não pode ser associada a mais de uma política anti-phishing.

- Você pode definir as seguintes configurações em novas políticas anti-phishing no PowerShell que não estão disponíveis no Centro de Conformidade e Segurança até que você crie & a política:

  - Crie a nova política como desabilitada (_Habilitado_ no `$false` cmdlet **New-AntiPhishRule).**
  - Definir a prioridade da política durante a criação (_Prioridade_ _\<Number\>_ ) no cmdlet **New-AntiPhishRule).**

- Uma nova política anti-phishing que você cria no Power & Shell não fica visível no Centro de Conformidade e Segurança até que você atribua a política a uma regra anti-phishing.

#### <a name="step-1-use-powershell-to-create-an-anti-phish-policy"></a>Etapa 1: Usar o PowerShell para criar uma política anti-phishing

Para criar uma política anti-phishing, use esta sintaxe:

```PowerShell
New-AntiPhishPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-EnableSpoofIntelligence <$true | $false>] [-AuthenticationFailAction <MoveToJmf | Quarantine>] [-EnableUnauthenticatedSender <$true | $false>]
```

Este exemplo cria uma política anti-phishing chamada Quarentena de Pesquisa com as seguintes configurações:

- A descrição é: política do departamento de pesquisa.
- Altera a ação padrão de spoofing para Quarentena.

```powershell
New-AntiPhishPolicy -Name "Monitor Policy" -AdminDisplayName "Research department policy" -AuthenticationFailAction Quarantine
```

Para informações detalhadas de sintaxes e de parâmetros, consulte [New-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishPolicy).

#### <a name="step-2-use-powershell-to-create-an-anti-phish-rule"></a>Etapa 2: Usar o PowerShell para criar uma regra anti-phishing

Para criar uma regra anti-phishing, use esta sintaxe:

```PowerShell
New-AntiPhishRule -Name "<RuleName>" -AntiPhishPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

Este exemplo cria uma regra anti-phishing chamada Departamento de Pesquisa com as seguintes condições:

- A regra é associada à política anti-phishing chamada Quarentena de Pesquisa.
- A regra se aplica aos membros do grupo chamado Departamento de pesquisa.
- Como não estamos usando o parâmetro _Priority,_ a prioridade padrão é usada.

```powershell
New-AntiPhishRule -Name "Research Department" -AntiPhishPolicy "Research Quarantine" -SentToMemberOf "Research Department"
```

Para informações detalhadas de sintaxes e de parâmetros, consulte [New-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishRule).

### <a name="use-powershell-to-view-anti-phish-policies"></a>Usar o PowerShell para exibir políticas anti-phishing

Para exibir políticas anti-phishing existentes, use a seguinte sintaxe:

```PowerShell
Get-AntiPhishPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

Este exemplo retorna uma lista resumida de todas as políticas anti-phishing juntamente com as propriedades especificadas.

```PowerShell
Get-AntiPhishPolicy | Format-Table Name,IsDefault
```

Este exemplo retorna todos os valores de propriedade da política anti-phishing chamada Executives.

```PowerShell
Get-AntiPhishPolicy -Identity "Executives"
```

Para informações detalhadas de sintaxes e de parâmetros, [consulte Get-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishPolicy).

### <a name="use-powershell-to-view-anti-phish-rules"></a>Usar o PowerShell para exibir regras anti-phishing

Para exibir as regras anti-phishing existentes, use a seguinte sintaxe:

```PowerShell
Get-AntiPhishRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

Este exemplo retorna uma lista resumida de todas as regras anti-phishing juntamente com as propriedades especificadas.

```PowerShell
Get-AntiPhishRule | Format-Table Name,Priority,State
```

Para filtrar a lista por regras habilitadas ou desabilitadas, execute os seguintes comandos:

```PowerShell
Get-AntiPhishRule -State Disabled | Format-Table Name,Priority
```

```PowerShell
Get-AntiPhishRule -State Enabled | Format-Table Name,Priority
```

Este exemplo retorna todos os valores de propriedade da regra anti-phishing chamada Contoso Executives.

```PowerShell
Get-AntiPhishRule -Identity "Contoso Executives"
```

Para informações detalhadas de sintaxes e de parâmetros, consulte [Get-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishrule).

### <a name="use-powershell-to-modify-anti-phish-policies"></a>Usar o PowerShell para modificar políticas anti-phishing

Além dos itens a seguir, as mesmas configurações estão disponíveis quando você modifica uma política anti-phishing no PowerShell como quando você cria uma política conforme descrito na Etapa 1: Use o PowerShell para criar uma política [anti-phishing](#step-1-use-powershell-to-create-an-anti-phish-policy) anteriormente neste artigo.

- A _opção MakeDefault_ que transforma a política especificada na política  padrão (aplicada a todos, sempre com prioridade mais baixa e você não pode excluí-la) só estará disponível quando você modificar uma política anti-phishing no PowerShell.

- Não é possível renomear uma política antiphish (o cmdlet **Set-AntiPhishPolicy** não tem _parâmetro Name)._ Ao renomear uma política anti-phish & ing no Centro de Conformidade e Segurança, você está apenas renomeando a regra _anti-phishing._

Para modificar uma política anti-phishing, use esta sintaxe:

```PowerShell
Set-AntiPhishPolicy -Identity "<PolicyName>" <Settings>
```

Para informações detalhadas de sintaxes e de parâmetros, consulte [Set-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Set-AntiPhishPolicy).

### <a name="use-powershell-to-modify-anti-phish-rules"></a>Usar o PowerShell para modificar regras anti-phishing

A única configuração que não está disponível quando você modifica uma regra anti-phishing no PowerShell é o parâmetro _Enabled_ que permite criar uma regra desabilitada. Para habilitar ou desabilitar regras anti-phishing existentes, consulte a próxima seção.

Caso contrário, as mesmas configurações estarão disponíveis quando você criar uma regra conforme descrito na Etapa 2: usar o PowerShell para criar uma seção de regra [anti-phishing](#step-2-use-powershell-to-create-an-anti-phish-rule) anteriormente neste artigo.

Para modificar uma regra anti-phishing, use esta sintaxe:

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" <Settings>
```

Para informações detalhadas de sintaxes e de parâmetros, consulte [Set-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/set-antiphishrule).

### <a name="use-powershell-to-enable-or-disable-anti-phish-rules"></a>Usar o PowerShell para habilitar ou desabilitar regras anti-phishing

Habilitar ou desabilitar uma regra anti-phishing no PowerShell habilita ou desabilita toda a política anti-phishing (a regra anti-phishing e a política anti-phishing atribuída). Não é possível habilitar ou desabilitar a política anti-phishing padrão (ela sempre é aplicada a todos os destinatários).

Para habilitar ou desabilitar uma regra anti-phishing no PowerShell, use esta sintaxe:

```PowerShell
<Enable-AntiPhishRule | Disable-AntiPhishRule> -Identity "<RuleName>"
```

Este exemplo desabilita a regra anti-phishing chamada Departamento de Marketing.

```PowerShell
Disable-AntiPhishRule -Identity "Marketing Department"
```

Este exemplo habilita a mesma regra.

```PowerShell
Enable-AntiPhishRule -Identity "Marketing Department"
```

Para informações detalhadas de sintaxes e de parâmetros, consulte [Enable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/enable-antiphishrule) e [Disable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/disable-antiphishrule).

### <a name="use-powershell-to-set-the-priority-of-anti-phish-rules"></a>Usar o PowerShell para definir a prioridade das regras anti-phishing

O valor mais alto de prioridade que pode ser definido em uma regra é 0. O valor mais baixo que pode ser definido depende do número de regras. Por exemplo, se você tiver cinco regras, use os valores de prioridade de 0 a 4. Alterar a prioridade de uma regra existente pode ter um efeito cascata em outras regras. Por exemplo, se você tiver cinco regras personalizadas (prioridades de 0 a 4) e alterar a prioridade de uma regra para 2, a regra existente com prioridade 2 será alterada para a prioridade 3, e a regra com prioridade 3 será alterada para prioridade 4.

Para definir a prioridade de uma regra anti-phishing no PowerShell, use a seguinte sintaxe:

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" -Priority <Number>
```

Este exemplo define a prioridade da regra chamada Marketing Department como 2. Todas as regras existentes com prioridade inferior ou igual a 2 são reduzidas por 1 (seus números de prioridade são aumentados por 1).

```PowerShell
Set-AntiPhishRule -Identity "Marketing Department" -Priority 2
```

**Observações**:

- Para definir a prioridade de uma nova regra ao criar, use o parâmetro _Priority_ no cmdlet **New-AntiPhishRule.**

- A política anti-phishing padrão não tem uma regra anti-phishing correspondente e sempre tem o valor de prioridade inmodificável **Menor.**

### <a name="use-powershell-to-remove-anti-phish-policies"></a>Usar o PowerShell para remover políticas anti-phishing

Quando você usa o PowerShell para remover uma política anti-phishing, a regra anti-phishing correspondente não é removida.

Para remover uma política anti-phishing no PowerShell, use esta sintaxe:

```PowerShell
Remove-AntiPhishPolicy -Identity "<PolicyName>"
```

Este exemplo remove a política anti-phishing chamada Departamento de Marketing.

```PowerShell
Remove-AntiPhishPolicy -Identity "Marketing Department"
```

Para informações detalhadas de sintaxes e de parâmetros, [consulte Remove-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishPolicy).

### <a name="use-powershell-to-remove-anti-phish-rules"></a>Usar o PowerShell para remover regras anti-phishing

Quando você usa o PowerShell para remover uma regra anti-phishing, a política anti-phishing correspondente não é removida.

Para remover uma regra anti-phishing no PowerShell, use esta sintaxe:

```PowerShell
Remove-AntiPhishRule -Identity "<PolicyName>"
```

Este exemplo remove a regra anti-phishing chamada Departamento de Marketing.

```PowerShell
Remove-AntiPhishRule -Identity "Marketing Department"
```

Para informações detalhadas de sintaxes e de parâmetros, [consulte Remove-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishRule).

## <a name="how-do-you-know-these-procedures-worked"></a>Como saber se esses procedimentos funcionaram?

Para verificar se você configurou com êxito as políticas anti-phishing no Microsoft Defender para Office 365, faça uma das seguintes etapas:

- No Centro de Conformidade & Segurança, vá para **Política** de Gerenciamento de \> **Ameaças** \> **Anti-phishing**. Verifique a lista de políticas, seus valores **de Status** e seus **valores de** Prioridade. Para exibir mais detalhes, faça uma das seguintes etapas:

  - Selecione a política na lista e veja os detalhes no flyout.
  - Clique **em Política** Padrão e veja os detalhes no flyout.

- No PowerShell do Exchange Online, substitua pelo nome da política ou regra, execute o seguinte comando e \<Name\> verifique as configurações:

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-AntiPhishRule -Identity "<Name>"
  ```
