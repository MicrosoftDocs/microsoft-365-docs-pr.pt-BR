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
description: Os administradores podem aprender a criar, modificar e excluir as políticas anti-phishing disponíveis em organizações Proteção do Exchange Online (EOP) com ou sem Exchange Online caixas de correio.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 2aaeb10eaa3c06e721df3cf7a00658482e6ffc0c
ms.sourcegitcommit: c70067b4ef9c6f8f04aca68c35bb5141857c4e4b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/19/2021
ms.locfileid: "53029916"
---
# <a name="configure-anti-phishing-policies-in-eop"></a>Configurar políticas anti-phishing em EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
- [Proteção do Exchange Online](exchange-online-protection-overview.md)

Em organizações Microsoft 365 com caixas de correio em organizações Exchange Online ou autônomas do Proteção do Exchange Online (EOP) sem caixas de correio do Exchange Online, há uma política anti-phishing padrão que contém um número limitado de recursos antifalsagem habilitados por padrão. Para saber mais, confira [Configurações de inteligência contra falsificação nas políticas anti phishing](set-up-anti-phishing-policies.md#spoof-settings).

Os administradores podem exibir, editar e configurar (mas não excluir) a política anti-phishing padrão. Para maior granularidade, você também pode criar políticas anti-phishing personalizadas que se aplicam a usuários, grupos ou domínios específicos em sua organização. Políticas personalizadas sempre terão prioridade sobre a política padrão, mas você pode alterar a prioridade (ordem de execução) de suas políticas personalizadas.

As organizações Exchange Online caixas de correio podem configurar políticas anti-phishing no portal Microsoft 365 Defender ou Exchange Online PowerShell. As organizações EOP autônomas só podem usar o portal Microsoft 365 Defender autônomo.

Para obter informações sobre como criar e modificar as políticas anti-phishing mais avançadas disponíveis no Microsoft Defender para Office 365, consulte [Configure anti-phishing policies in Microsoft Defender for Office 365](configure-mdo-anti-phishing-policies.md).

Os elementos básicos de uma política anti-phishing são:

- **A política anti-phishing**: especifica as proteções de phishing para habilitar ou desabilitar e as ações para aplicar opções.
- **A regra anti-phishing**: especifica a prioridade e os filtros de destinatário (a quem a política se aplica) para uma política anti-phishing.

A diferença entre esses dois elementos não é óbvia ao gerenciar políticas anti-phishing no portal Microsoft 365 Defender:

- Ao criar uma política anti-phishing, você está criando uma regra anti-phishing e a política anti-phishing associada ao mesmo tempo usando o mesmo nome para ambos.
- Quando você modifica uma política anti-phishing, as configurações relacionadas ao nome, prioridade, habilitado ou desabilitado e filtros de destinatário modificam a regra anti-phishing. Todas as outras configurações modificam a política anti-phishing associada.
- Quando você remove uma política anti-phishing, a regra anti-phishing e a política anti-phishing associada são removidas.

No Exchange Online PowerShell, você gerencia a política e a regra separadamente. Para obter mais informações, consulte a seção Usar Exchange Online PowerShell para configurar políticas [anti-phishing](#use-exchange-online-powershell-to-configure-anti-phishing-policies) posteriormente neste artigo.

Cada organização tem uma política anti-phishing interna chamada Office365 AntiPhish Default que tem essas propriedades:

- A política é aplicada a todos os destinatários na organização, mesmo que não haja nenhuma regra anti-phishing (filtros de destinatário) associada à política.
- A política tem o valor de prioridade personalizado **Menor**, que não pode ser modificado (a política é sempre aplicada por último). As políticas personalizadas que você cria, sempre têm uma prioridade mais alta.
- A política é a padrão (a propriedade **IsDefault** tem o valor `True`), e não é possível excluir a política padrão.

Para aumentar a eficácia da proteção anti-phishing, você pode criar políticas anti-phishing personalizadas com configurações mais estritas que são aplicadas a usuários ou grupos específicos de usuários.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Do que você precisa saber para começar?

- Abra o portal do Microsoft 365 Defender em <https://security.microsoft.com>. Para ir diretamente para a página **Anti-phishing,** use <https://security.microsoft.com/antiphishing> .

- Para se conectar ao PowerShell do Exchange Online, confira [Conectar ao PowerShell do Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).

  Não é possível gerenciar políticas anti-phishing no EOP PowerShell autônomo.

- Você precisa de permissões em **Exchange Online** antes de poder realizar os procedimentos neste artigo:
  - Para adicionar, modificar e excluir políticas anti-phishing, você  precisa ser membro dos grupos de função Gerenciamento da Organização ou Administrador **de** Segurança.
  - Para acesso somente leitura a políticas anti-phishing, você precisa ser membro dos grupos de função Leitor **Global** ou **Leitor de** Segurança.

  Para obter mais informações, confira [Permissões no Exchange Online](/exchange/permissions-exo/permissions-exo).

  **Observações**:

  - Adicionar usuários à função correspondente do Azure Active Directory no Centro de administração do Microsoft 365 fornece aos usuários as permissões necessárias _e_ para outros recursos no Microsoft 365. Para obter mais informações, confira o artigo [Sobre funções de administrador](../../admin/add-users/about-admin-roles.md).
  - O **grupo de função Gerenciamento da Organização** Somente Exibição [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) também fornece acesso somente leitura ao recurso <sup>\*</sup> .

- Para nossas configurações recomendadas para políticas anti-phishing, consulte [EOP anti-phishing policy settings](recommended-settings-for-eop-and-office365.md#eop-anti-phishing-policy-settings).

- Permitir até 30 minutos para que a política atualizada seja aplicada.

- Para obter informações sobre onde as políticas anti-phishing são aplicadas no pipeline de filtragem, consulte [Order and precedence of email protection](how-policies-and-protections-are-combined.md).

## <a name="use-the-microsoft-365-defender-portal-to-create-anti-phishing-policies"></a>Usar o portal Microsoft 365 Defender para criar políticas anti-phishing

Criar uma política anti-phishing personalizada no portal Microsoft 365 Defender cria a regra anti-phishing e a política anti-phishing associada ao mesmo tempo usando o mesmo nome para ambos.

1. No portal Microsoft 365 Defender, acesse **Email & Políticas** de Colaboração & Políticas de Ameaças de Regras seção \>  \>  \>  \> **Anti-phishing**.

2. Na página **Anti-phishing,** clique em ![ Criar ícone ](../../media/m365-cc-sc-create-icon.png) **Criar**.

3. O assistente de política é aberto. Na página **Nome da** política, configure estas configurações:
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

5. Na página de proteção & de **phishing** exibida, use a caixa de seleção Habilitar inteligência de spoof para ativar ou desativar a inteligência de **spoof.** O valor padrão está em (selecionado) e recomendamos que você o deixe em. Você configura a ação a ser tomada em mensagens falsas bloqueadas na próxima página.

   Para desativar a inteligência de spoof, desempure a caixa de seleção.

   > [!NOTE]
   > Você não precisa desativar a proteção anti-spoofing se seu registro MX não apontar para Microsoft 365; em vez disso, você habilita a Filtragem Aprimorada para Conectores. Para obter instruções, [consulte Enhanced Filtering for Connectors in Exchange Online](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).

   Ao terminar, clique em **Avançar**.

6. Na página **Ações** exibida, de acordo com as seguintes configurações:
   - **Se a mensagem for detectada como** falsa : essa configuração estará disponível somente se você tiver selecionado Habilitar a inteligência de **spoof** na página anterior. Selecione uma das seguintes ações na listada para mensagens de envios com spoofed bloqueados:
     - **Mover mensagem para as pastas lixo eletrônico dos destinatários**
     - **Colocar em quarentena a mensagem**

   - **Dicas de segurança &** indicadores : Essa configuração só estará disponível se você selecionou Habilitar a inteligência de **spoof** na página anterior:
     - **Mostrar (?)** para remetentes não autenticados para spoof : adiciona um ponto de interrogação à foto do remetente na caixa De em  Outlook se a mensagem não passar verificações SPF ou DKIM e a mensagem não passar DMARC [ou](email-validation-and-authentication.md#composite-authentication)autenticação composta .
     - Mostrar a marca **"via":** adiciona uma marca via (chris@contoso.com via fabrikam.com) ao endereço From se for diferente do domínio na assinatura DKIM ou no endereço **MAIL FROM.**

     Para ativar uma configuração, marque a caixa de seleção. Para desativar, desempure a caixa de seleção.

   Ao terminar, clique em **Avançar**.

7. Na página **Revisão** exibida, revise suas configurações. Você pode selecionar **Editar** em cada seção para modificar as configurações da seção. Ou você pode clicar em **Voltar** ou selecionar a página específica no assistente.

   Quando terminar, clique em **Enviar**.

8. Na mensagem de confirmação exibida, clique em **Concluído**.

## <a name="use-the-microsoft-365-defender-portal-to-view-anti-phishing-policies"></a>Usar o portal Microsoft 365 Defender para exibir políticas anti-phishing

1. No portal Microsoft 365 Defender, acesse **Email & Políticas** de Colaboração & Políticas de Ameaças de Regras seção \>  \>  \>  \> **Anti-phishing**.

2. Na página **Anti-phishing,** as seguintes propriedades são exibidas na lista de políticas anti-phishing:

   - **Nome**
   - **Status**
   - **Prioridade**
   - **Última modificação**

3. Quando você seleciona uma política clicando no nome, as configurações de política são exibidas em um sobrevoo.

## <a name="use-the-microsoft-365-defender-portal-to-modify-anti-phishing-policies"></a>Usar o portal Microsoft 365 Defender para modificar políticas anti-phishing

1. No portal Microsoft 365 Defender, acesse **Email & Políticas** de Colaboração & Políticas de Ameaças de Regras seção \>  \>  \>  \> **Anti-phishing**.

2. Na página **Anti-phishing,** selecione uma política na lista clicando no nome.

3. No submenu de detalhes da política exibido, selecione **Editar** em cada seção para modificar as configurações da seção. Para obter mais informações sobre as configurações, consulte a seção Usar o portal Microsoft 365 Defender para criar políticas [anti-phishing](#use-the-microsoft-365-defender-portal-to-create-anti-phishing-policies) anteriormente neste artigo.  

   Para a política anti-phishing padrão, a seção Usuários, grupos e **domínios** não está disponível (a política se aplica a todos) e você não pode renomear a política.

Para habilitar ou desabilitar uma política ou definir a ordem de prioridade da política, consulte as seções a seguir.

### <a name="enable-or-disable-custom-anti-phishing-policies"></a>Habilitar ou desabilitar políticas anti-phishing personalizadas

Não é possível desabilitar a política anti-phishing padrão.

1. No portal Microsoft 365 Defender, acesse **Email & Políticas** de Colaboração & Políticas de Ameaças de Regras seção \>  \>  \>  \> **Anti-phishing**.

2. Na página **Anti-phishing,** selecione uma política personalizada na lista clicando no nome.

3. Na parte superior do submenu de detalhes da política exibido, você verá um dos seguintes valores:
   - **Política desativada**: para ativar a política, clique no ![ícone Ativar](../../media/m365-cc-sc-turn-on-off-icon.png) **Ativar** .
   - **Política ativada**: para desativar a política, clique no ![ícone Desativar](../../media/m365-cc-sc-turn-on-off-icon.png) **Desativar**.

4. Na caixa de diálogo de confirmação exibida, clique em **Ativar** ou **Desativar**.

5. Clique em **Fechar** no submenu de detalhes da política.

De volta à página da política principal, o valor **Status** da política será **Ativado** ou **Desativado**.

### <a name="set-the-priority-of-custom-anti-phishing-policies"></a>Definir a prioridade de políticas anti-phishing personalizadas

Por padrão, as políticas anti-phishing têm uma prioridade baseada na ordem em que foram criadas (as políticas mais novas têm prioridade menor do que as políticas mais antigas). Um número de prioridade menor indica uma maior prioridade para a política (0 é a maior), e as políticas são processadas por ordem de prioridade (políticas com maior prioridade são processadas antes das políticas com menor prioridade). Duas políticas não podem ter a mesma prioridade, e o processamento da política será interrompido após a primeira política ser aplicada.

Para alterar a prioridade de uma política, clique em **Aumentar prioridade** ou **Diminuir prioridade** nas propriedades da política (não é possível modificar diretamente o número da **Prioridade** no portal Microsoft 365 Defender). Alterar a prioridade de uma política só faz sentido se você tiver várias políticas.

 **Observações**:

- No portal Microsoft 365 Defender, você só pode alterar a prioridade da política anti-phishing após a criação. No PowerShell, você pode substituir a prioridade padrão ao criar a regra anti-phish (que pode afetar a prioridade das regras existentes).
- As políticas anti-phishing são processadas na ordem em que são exibidas (a primeira política tem o **valor priority** 0). A política anti-phishing padrão tem o valor de prioridade **Mais** Baixo e você não pode alterá-la.

1. No portal Microsoft 365 Defender, acesse **Email & Políticas** de Colaboração & Políticas de Ameaças de Regras seção \>  \>  \>  \> **Anti-phishing**.

2. Na página **Anti-phishing,** selecione uma política personalizada na lista clicando no nome.

3. Na parte superior do submenu de detalhes da política exibido, você verá **Aumentar a prioridade** ou **Diminuir a prioridade** com base no valor de prioridade atual e no número de políticas personalizadas:
   - A política com o **valor Priority** **0** tem apenas a **opção Diminuir prioridade** disponível.
   - A política com o menor **valor priority** (por exemplo, **3**) tem apenas a **opção Aumentar** prioridade disponível.
   - Se você tiver três ou mais políticas, as políticas entre os valores de prioridade mais alto e mais baixo terão as opções **Aumentar** prioridade e Diminuir **prioridade** disponíveis.

   Clique no ![ícone Aumentar prioridade](../../media/m365-cc-sc-increase-icon.png) **Aumentar prioridade** ou no ![ícone Diminuir prioridade](../../media/m365-cc-sc-decrease-icon.png) **Diminuir prioridade** para alterar o valor da **Prioridade**.

4. Quando terminar, clique em **Fechar** no submenu de detalhes da política.

## <a name="use-the-microsoft-365-defender-portal-to-remove-custom-anti-phishing-policies"></a>Usar o portal Microsoft 365 Defender para remover políticas anti-phishing personalizadas

Quando você usa o portal Microsoft 365 Defender para remover uma política anti-phishing personalizada, a regra anti-phishing e a política anti-phishing correspondente são excluídas. Não é possível remover a política anti-phishing padrão.

1. No portal Microsoft 365 Defender, acesse **Email & Políticas** de Colaboração & Políticas de Ameaças de Regras seção \>  \>  \>  \> **Anti-phishing**.

2. Selecione uma política personalizada na lista clicando no nome da política. Na parte superior do submenu de detalhes da política exibido, clique no ![ícone Mais ações](../../media/m365-cc-sc-more-actions-icon.png) **Mais ações** \> ![ícone Excluir política](../../media/m365-cc-sc-delete-icon.png) **Excluir política**.

3. Na caixa de diálogo de confirmação exibida, clique em **Sim**.

## <a name="use-exchange-online-powershell-to-configure-anti-phishing-policies"></a>Usar Exchange Online PowerShell para configurar políticas anti-phishing

Conforme descrito anteriormente, uma política anti-phishing consiste em uma política anti-phishing e uma regra anti-phishing.

No Exchange Online PowerShell, a diferença entre políticas anti-phishing e regras anti-phishing é aparente. Você gerencia políticas anti-phishing usando os cmdlets **\* -AntiPhishPolicy** e gerencia as regras anti-phishing usando os cmdlets **\* -AntiPhishRule.**

- No PowerShell, você cria primeiro a política anti-phishing e, em seguida, cria a regra anti-phish que identifica a política à que a regra se aplica.
- No PowerShell, você modifica as configurações na política anti-phishing e na regra anti-phishing separadamente.
- Quando você remove uma política anti-phishing do PowerShell, a regra anti-phishing correspondente não é removida automaticamente e vice-versa.

> [!NOTE]
> Os procedimentos a seguir do PowerShell não estão disponíveis em organizações EOP autônomas usando Proteção do Exchange Online PowerShell.

### <a name="use-powershell-to-create-anti-phishing-policies"></a>Usar o PowerShell para criar políticas anti-phishing

Criar uma política anti-phishing no PowerShell é um processo de duas etapas:

1. Crie a política anti-phishing.
2. Crie a regra anti-phish que especifica a política anti-phishing à que a regra se aplica.

 **Observações**:

- Você pode criar uma nova regra anti-phishing e atribuir uma política anti-phishing existente e nãossociada a ela. Uma regra anti-phishing não pode ser associada a mais de uma política anti-phishing.

- Você pode definir as seguintes configurações em novas políticas anti-phishing no PowerShell que não estão disponíveis no portal Microsoft 365 Defender até depois de criar a política:

  - Crie a nova política como desabilitada (_Habilitado_ `$false` no cmdlet **New-AntiPhishRule).**
  - De definir a prioridade da política durante a criação (_Prioridade_ _\<Number\>_ ) no cmdlet **New-AntiPhishRule).**

- Uma nova política anti-phishing que você cria no PowerShell não fica visível no portal Microsoft 365 Defender até que você atribua a política a uma regra anti-phishing.

#### <a name="step-1-use-powershell-to-create-an-anti-phish-policy"></a>Etapa 1: Usar o PowerShell para criar uma política anti-phishing

Para criar uma política anti-phishing, use esta sintaxe:

```PowerShell
New-AntiPhishPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-EnableSpoofIntelligence <$true | $false>] [-AuthenticationFailAction <MoveToJmf | Quarantine>] [-EnableUnauthenticatedSender <$true | $false>] [-EnableViaTag <$true | $false>]
```

Este exemplo cria uma política anti-phishing chamada Quarentena de Pesquisa com as seguintes configurações:

- A descrição é: Política do departamento de pesquisa.
- Altera a ação padrão para a spoofing para Quarentena.

```powershell
New-AntiPhishPolicy -Name "Monitor Policy" -AdminDisplayName "Research department policy" -AuthenticationFailAction Quarantine
```

Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [New-AntiPhishPolicy](/powershell/module/exchange/New-AntiPhishPolicy).

#### <a name="step-2-use-powershell-to-create-an-anti-phish-rule"></a>Etapa 2: Usar o PowerShell para criar uma regra anti-phishing

Para criar uma regra anti-phishing, use esta sintaxe:

```PowerShell
New-AntiPhishRule -Name "<RuleName>" -AntiPhishPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

Este exemplo cria uma regra anti-phishing chamada Departamento de Pesquisa com as seguintes condições:

- A regra está associada à política anti-phishing chamada Quarentena de Pesquisa.
- A regra se aplica aos membros do grupo chamado Departamento de pesquisa.
- Como não estamos usando o parâmetro _Priority,_ a prioridade padrão é usada.

```powershell
New-AntiPhishRule -Name "Research Department" -AntiPhishPolicy "Research Quarantine" -SentToMemberOf "Research Department"
```

Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [New-AntiPhishRule](/powershell/module/exchange/New-AntiPhishRule).

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

Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Get-AntiPhishPolicy](/powershell/module/exchange/Get-AntiPhishPolicy).

### <a name="use-powershell-to-view-anti-phish-rules"></a>Usar o PowerShell para exibir regras anti-phishing

Para exibir regras anti-phishing existentes, use a seguinte sintaxe:

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

Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Get-AntiPhishRule](/powershell/module/exchange/Get-AntiPhishrule).

### <a name="use-powershell-to-modify-anti-phish-policies"></a>Usar o PowerShell para modificar políticas anti-phishing

Além dos itens a seguir, as mesmas configurações estão disponíveis quando você modifica uma política anti-phishing no PowerShell como quando você cria uma política conforme descrito na Etapa 1: Use o PowerShell para criar uma política [anti-phishing](#step-1-use-powershell-to-create-an-anti-phish-policy) anteriormente neste artigo.

- A _opção MakeDefault_ que transforma a política especificada na política  padrão (aplicada a todos, sempre prioridade mais baixa e você não pode excluí-la) só está disponível quando você modifica uma política anti-phishing no PowerShell.
- Não é possível renomear uma política anti-phish (o cmdlet **Set-AntiPhishPolicy** não tem _parâmetro Name)._ Quando você renomeia uma política anti-phishing no portal Microsoft 365 Defender, você só está renomeando a regra _anti-phishing._

Para modificar uma política anti-phishing, use esta sintaxe:

```PowerShell
Set-AntiPhishPolicy -Identity "<PolicyName>" <Settings>
```

Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Set-AntiPhishPolicy](/powershell/module/exchange/Set-AntiPhishPolicy).

### <a name="use-powershell-to-modify-anti-phish-rules"></a>Usar o PowerShell para modificar regras anti-phishing

A única configuração que não está disponível quando você modifica uma regra anti-phishing no PowerShell é o parâmetro _Enabled_ que permite criar uma regra desabilitada. Para habilitar ou desabilitar as regras anti-phishing existentes, consulte a próxima seção.

Caso contrário, as mesmas configurações estarão disponíveis quando você criar uma regra conforme descrito na Etapa 2: Usar o PowerShell para criar uma seção de regra [anti-phishing](#step-2-use-powershell-to-create-an-anti-phish-rule) anteriormente neste artigo.

Para modificar uma regra anti-phishing, use esta sintaxe:

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" <Settings>
```

Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Set-AntiPhishRule](/powershell/module/exchange/set-antiphishrule).

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

Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Enable-AntiPhishRule](/powershell/module/exchange/enable-antiphishrule) e [Disable-AntiPhishRule](/powershell/module/exchange/disable-antiphishrule).

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
- A política anti-phishing padrão não tem uma regra anti-phishing correspondente e sempre tem o valor de prioridade nãomodificável **Mais Baixo**.

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

Para obter informações detalhadas sobre sintaxes e parâmetros, [consulte Remove-AntiPhishPolicy](/powershell/module/exchange/Remove-AntiPhishPolicy).

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

Para obter informações detalhadas sobre sintaxes e parâmetros, [consulte Remove-AntiPhishRule](/powershell/module/exchange/Remove-AntiPhishRule).

## <a name="how-do-you-know-these-procedures-worked"></a>Como saber se esses procedimentos funcionaram?

Para verificar se você configurou com êxito políticas anti-phishing no EOP, faça uma das seguintes etapas:

- No portal Microsoft 365 Defender, acesse **Email & Políticas** de Colaboração & Políticas de Ameaças de Regras seção \>  \>  \>  \> **Anti-phishing**. Verifique a lista de políticas, seus **valores de Status** e seus valores **priority.** Para exibir mais detalhes, selecione a política na lista clicando no nome e exibindo os detalhes no sobremenu que aparece.

- No Exchange Online PowerShell, substitua pelo nome da política ou regra, execute o seguinte comando e \<Name\> verifique as configurações:

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-AntiPhishRule -Identity "<Name>"
  ```
