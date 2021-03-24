---
title: Configurar políticas de Links Seguros no Microsoft Defender para Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: how-to
ms.date: ''
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: bdd5372d-775e-4442-9c1b-609627b94b5d
ms.collection:
- M365-security-compliance
description: Os administradores podem aprender a exibir, criar, modificar e excluir políticas de Links Seguros e configurações globais de Links Seguros no Microsoft Defender para Office 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c8b2cb8b57dcf630b3e07ac387e96ab099ca7403
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51053465"
---
# <a name="set-up-safe-links-policies-in-microsoft-defender-for-office-365"></a>Configurar políticas de Links Seguros no Microsoft Defender para Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
- [Plano 1 e plano 2 do Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!IMPORTANT]
> Este artigo se destina a clientes empresariais que possuem o [Microsoft Defender para Office 365](defender-for-office-365.md). Se você for um usuário de residência procurando informações sobre Safelinks no Outlook, consulte [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).

Links Seguros é um recurso do [Microsoft Defender para Office 365](defender-for-office-365.md) que fornece verificação de URL de mensagens de email de entrada no fluxo de emails e hora de verificação de clique em URLs e links em mensagens de email e em outros locais. Para obter mais informações, consulte [Links seguros no Microsoft Defender para Office 365](safe-links.md).

Não há nenhuma política interna ou padrão de Links Seguros. Para obter a verificação de URLs de Links Seguros, você precisa criar uma ou mais políticas de Links Seguros, conforme descrito neste artigo.

> [!NOTE]
> Você configura as configurações globais para proteção de Links Seguros **fora das** políticas de Links Seguros. Para obter instruções, consulte [Configure global settings for Safe Links in Microsoft Defender for Office 365](configure-global-settings-for-safe-links.md).

Você pode configurar políticas de Links Seguros no Centro de Conformidade de Segurança & ou no PowerShell (PowerShell do Exchange Online para organizações qualificadas do Microsoft 365 com caixas de correio no Exchange Online; PowerShell autônomo do EOP para organizações sem caixas de correio do Exchange Online, mas com assinaturas de complemento do Microsoft Defender para Office 365).

Os elementos básicos de uma política de Links Seguros são:

- A política de **links** seguros : ativar a proteção de Links Seguros, ativar a verificação de URL em tempo real, especificar se a verificação em tempo real deve ser concluída antes de entregar a mensagem, ativar a verificação de mensagens internas, especificar se deve rastrear os cliques do usuário em URLs e especificar se os usuários devem clicar na URL original.
- **A regra de links seguros**: especifica a prioridade e os filtros de destinatário (a quem a política se aplica).

A diferença entre esses dois elementos não é óbvia quando você gerencia as polícias de Links Seguros no Centro de Conformidade & Segurança:

- Ao criar uma política de Links Seguros, você está realmente criando uma regra de links seguros e a política de links seguros associados ao mesmo tempo usando o mesmo nome para ambos.
- Quando você modifica uma política de Links Seguros, as configurações relacionadas ao nome, prioridade, habilitado ou desabilitado e filtros de destinatário modificam a regra de links seguros. Todas as outras configurações modificam a política de links seguros associados.
- Quando você remove uma política de Links Seguros, a regra de links seguros e a política de links seguros associados são removidas.

No PowerShell do Exchange Online ou no PowerShell do EOP autônomo, a política e a regra são gerenciadas separadamente. Para obter mais informações, consulte a seção Usar o PowerShell do Exchange Online ou [o EOP PowerShell](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies) autônomo para configurar políticas de Links Seguros posteriormente neste artigo.

## <a name="what-do-you-need-to-know-before-you-begin"></a>O que você precisa saber antes de começar?

- Abra o Centro de Conformidade e Segurança em <https://protection.office.com/>. Para ir diretamente para a página **Links Seguros,** use <https://protection.office.com/safelinksv2> .

- Para se conectar ao PowerShell do Exchange Online, confira [Conectar ao PowerShell do Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell). Para se conectar ao EOP PowerShell autônomo, consulte [Conectar-se ao PowerShell do Exchange Online Protection.](/powershell/exchange/connect-to-exchange-online-protection-powershell).

- Você precisa ter permissões atribuídas antes de poder fazer os procedimentos neste artigo:
  - Para criar, modificar e excluir políticas de Links Seguros  &,  você precisa ser membro dos grupos de  função Gerenciamento  da Organização ou Administrador de Segurança no Centro de Conformidade e Segurança e membro do grupo de função Gerenciamento da Organização no Exchange Online.
  - Para acesso somente leitura a políticas de Links Seguros, você precisa ser membro dos grupos de função Leitor **Global ou** **Leitor de** Segurança.

  Para obter mais informações, consulte [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md) and [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).

  > [!NOTE]
  > 
  > - Adicionar usuários à função correspondente do Azure Active Directory no Centro de administração do Microsoft 365 fornece aos usuários as permissões necessárias no Centro de Segurança e Conformidade _e_ permissões para outros recursos no Microsoft 365. Para obter mais informações, confira o artigo [Sobre funções de administrador](../../admin/add-users/about-admin-roles.md).
  . - O **grupo de função Gerenciamento** de Organização Somente Exibição no Exchange [Online](/Exchange/permissions-exo/permissions-exo#role-groups) também fornece acesso somente leitura ao recurso.

- Para nossas configurações recomendadas para políticas de Links Seguros, consulte Configurações de política [de Links Seguros.](recommended-settings-for-eop-and-office365.md#safe-links-policy-settings)

- Permitir até 30 minutos para que uma política nova ou atualizada seja aplicada.

- [Novos recursos estão sendo adicionados continuamente ao Microsoft Defender para Office 365](defender-for-office-365.md#new-features-in-microsoft-defender-for-office-365). À medida que novos recursos são adicionados, talvez seja necessário fazer ajustes nas políticas existentes de Links Seguros.

## <a name="use-the-security--compliance-center-to-create-safe-links-policies"></a>Use o Centro de Conformidade & segurança para criar políticas de Links Seguros

A criação de uma política & de Links Seguros personalizada no Centro de Conformidade e Segurança cria a regra de links seguros e a política de links seguros associados ao mesmo tempo usando o mesmo nome para ambos.

1. No Centro de Conformidade & segurança, vá para **Política** de Gerenciamento de Ameaças \>  \> **ATP Links seguros**.

2. Na página **Links Seguros,** clique em **Criar**.

3. O **assistente de política Novos Links Seguros** é aberto. Na página **Nomear sua política,** configure as seguintes configurações:

   - **Nome**: insira um nome exclusivo e descritivo para a política.

   - **Descrição**: digite uma descrição opcional para a política.

   Quando terminar, clique em **Avançar**.

4. Na página **Configurações** exibida, configure as seguintes configurações:

   - **Selecione a ação para URLs** mal-intencionadas desconhecidas em mensagens : Selecione **Ativado** para habilitar a proteção de Links Seguros para links em mensagens de email.

   - **Selecione a ação para URLs desconhecidas** ou potencialmente mal-intencionadas no Microsoft Teams : Selecione **Ativado** para habilitar a proteção de Links Seguros para links no Teams.

   - **Aplicar verificação de URL** em tempo real para links suspeitos e links que apontam para arquivos : Selecione essa configuração para habilitar a verificação em tempo real de links em mensagens de email.

   - **Aguarde a conclusão da** verificação de URL antes de entregar a mensagem : Selecione essa configuração para aguardar a conclusão da verificação de URL em tempo real antes de entregar a mensagem.

   - **Aplicar Links Seguros a mensagens de email** enviadas dentro da organização : Selecione essa configuração para aplicar a política de Links Seguros a mensagens entre os destinatários internos e os destinatários internos.

   - **Não acompanhar cliques do usuário**: Deixe essa configuração não eleita para habilitar os cliques do usuário de controle em URLs em mensagens de email.

   - **Não permita que os usuários cliquem** na URL original : Selecione essa configuração para impedir que os usuários cliquem na URL original em páginas [de aviso.](safe-links.md#warning-pages-from-safe-links)

   - **Não reescreva as SEGUINTES URLs**: Permite acessar as URLs especificadas que seriam bloqueadas por Links Seguros.

     Na caixa, digite a URL ou o valor que você deseja e clique em ![Adicionar ícone de botão](../../media/ITPro-EAC-AddIcon.png).

     Para remover uma entrada existente, selecione-a e clique em ![Excluir ícone de botão](../../media/ITPro-EAC-DeleteIcon.png).

     Para a sintaxe de entrada, consulte [Sintaxe de entrada para a lista "Não reescrever as URLs a seguir".](safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list)

   Para obter informações detalhadas sobre essas configurações, consulte [Configurações](safe-links.md#safe-links-settings-for-email-messages) de Links Seguros para mensagens de email e configurações de Links Seguros [para o Microsoft Teams.](safe-links.md#safe-links-settings-for-microsoft-teams)

   Para obter mais valores recomendados para configurações de política Padrão e Estrita, consulte Configurações de política [de Links Seguros.](recommended-settings-for-eop-and-office365.md#safe-links-policy-settings)

   Quando terminar, clique em **Avançar**.

5. Na página **Aplicada à** que aparece, identifique os destinatários internos aos quais a política se aplica.

   Só é possível usar uma condição ou exceção uma vez; contudo, você pode especificar vários valores para a condição ou exceção. Vários valores da mesma condição ou exceção usam a lógica OU (por exemplo, _\<recipient1\>_ ou _\<recipient2\>_). Para diferentes condições ou exceções, use a lógica E (por exemplo, _\<recipient1\>_ e _\<member of group 1\>_).

   Clique **em Adicionar uma condição**. No menu suspenso exibido, selecione uma condição em **Aplicado se**:

   - **O destinatário é**: Especifica uma ou mais caixas de correio, usuários de email ou contatos de email em sua organização.
   - **O destinatário é membro de**: Especifica um ou mais grupos em sua organização.
   - **O domínio do destinatário é**: Especifica os destinatários em um ou mais domínios aceitos configurados na sua organização. 

   Depois de selecionar a condição, um menu suspenso correspondente será exibido com **uma caixa Qualquer uma dessas.**

   - Clique na caixa e role a lista de valores a ser selecionado.
   - Clique na caixa e comece a digitar para filtrar a lista e selecionar um valor.
   - Para adicionar valores adicionais, clique em uma área vazia na caixa.
   - Para remover entradas individuais, clique em **Remover** ![ ícone remover no ](../../media/scc-remove-icon.png) valor.
   - Para remover toda a condição, clique em **Remover** ![ ícone remover na ](../../media/scc-remove-icon.png) condição.

   Para adicionar uma condição adicional, clique em **Adicionar uma condição** e selecione um valor restante em **Applied if**.

   Para adicionar exceções, clique em **Adicionar uma condição** e selecione uma exceção em Except **if**. As configurações e o comportamento são exatamente como as condições.

   Quando terminar, clique em **Avançar**.

6. Na página **Revisar suas configurações** que aparece, revise suas configurações. Você pode clicar **em Editar** em cada configuração para modificá-la.

   Quando terminar, clique em **Concluir**.

## <a name="use-the-security--compliance-center-to-view-safe-links-policies"></a>Use o Centro de Conformidade & segurança para exibir políticas de Links Seguros

1. No Centro de Conformidade & segurança, vá para **Política** de Gerenciamento de Ameaças \>  \> **ATP Links seguros**.

2. Na página **Links Seguros,** selecione uma política na lista e clique nele (não marque a caixa de seleção).

   Os detalhes da política aparecem em um fly-out

## <a name="use-the-security--compliance-center-to-modify-safe-links-policies"></a>Use o Centro de Conformidade & segurança para modificar políticas de Links Seguros

1. No Centro de Conformidade & segurança, vá para **Política** de Gerenciamento de Ameaças \>  \> **ATP Links seguros**.

2. Na página **Links Seguros,** selecione uma política na lista e clique nele (não marque a caixa de seleção).

3. Nos detalhes da política exibidos, clique em **Editar política**.

As configurações disponíveis no sobrevoo que aparece são idênticas às descritas na seção Usar o Centro de Conformidade & Segurança para criar políticas [de Links](#use-the-security--compliance-center-to-create-safe-links-policies) Seguros.

Para habilitar ou desabilitar uma política ou definir a ordem de prioridade da política, consulte as seções a seguir.

### <a name="enable-or-disable-safe-links-policies"></a>Habilitar ou desabilitar políticas de Links Seguros

1. No Centro de Conformidade & segurança, vá para **Política** de Gerenciamento de Ameaças \>  \> **ATP Links seguros**.

2. Observe o valor na coluna **Status:**

   - Mova o botão de alternância para a esquerda para desabilitar a política: ![Desativar a política](../../media/scc-toggle-off.png).

   - Mova o botão de alternância para a direita para habilitar a política: ![Ativar a política](../../media/scc-toggle-on.png).

### <a name="set-the-priority-of-safe-links-policies"></a>Definir a prioridade das políticas de Links Seguros

Por padrão, as políticas de Links Seguros têm uma prioridade baseada na ordem em que foram criadas (as políticas mais novas têm prioridade menor do que as políticas mais antigas). Um número de prioridade menor indica uma maior prioridade para a política (0 é a maior), e as políticas são processadas por ordem de prioridade (políticas com maior prioridade são processadas antes das políticas com menor prioridade). Duas políticas não podem ter a mesma prioridade, e o processamento da política será interrompido após a primeira política ser aplicada.

Para obter mais informações sobre a ordem de precedência e como várias políticas são avaliadas e aplicadas, confira [Ordem e precedência da proteção de email](how-policies-and-protections-are-combined.md).

As políticas de Links Seguros são exibidas na ordem em que são processadas (a primeira política tem o **valor Priority** 0).

> [!NOTE]
> No Centro de Conformidade & segurança, você só pode alterar a prioridade da política links seguros após a criação. No PowerShell, você pode substituir a prioridade padrão ao criar a regra de links seguros (que pode afetar a prioridade das regras existentes).

Para alterar a prioridade de uma política, mova a política para cima ou para baixo na lista (não é possível modificar diretamente o número de **Prioridade** no Centro de Conformidade e Segurança).

1. No Centro de Conformidade & segurança, vá para **Política** de Gerenciamento de Ameaças \>  \> **ATP Links seguros**.

2. Na página **Links Seguros,** selecione uma política na lista e clique nele (não marque a caixa de seleção).

3. Nos detalhes da política exibidos, clique no botão de prioridade disponível:

   - A política links seguros com o **valor Prioridade** **0** tem apenas o **botão Diminuir** prioridade disponível.

   - A política Links Seguros com o menor valor **priority** (por exemplo, **3**) tem apenas o **botão Aumentar prioridade** disponível.

   - Se você tiver três ou mais políticas de Links Seguros, as políticas  entre os valores de prioridade mais altos e mais baixos terão os botões **Aumentar** prioridade e Diminuir prioridade disponíveis.

4. Clique **em Aumentar prioridade** ou Diminuir **prioridade** para alterar o **valor Priority.**

5. Quando terminar, clique em **Fechar**.

## <a name="use-the-security--compliance-center-to-remove-safe-links-policies"></a>Use o Centro de Conformidade & segurança para remover políticas de Links Seguros

1. No Centro de Conformidade & segurança, vá para **Política** de Gerenciamento de Ameaças \>  \> **ATP Links seguros**.

2. Na página **Links Seguros,** selecione uma política na lista e clique nele (não marque a caixa de seleção).

3. Nos detalhes da política exibidos, clique em **Excluir política** e clique em **Sim** na caixa de diálogo de aviso exibida.

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies"></a>Usar o PowerShell do Exchange Online ou o EOP PowerShell autônomo para configurar políticas de Links Seguros

Conforme descrito anteriormente, uma política de Links Seguros consiste em uma política de links seguros e uma regra de links seguros.

No PowerShell, a diferença entre políticas de links seguros e regras de links seguros é aparente. Você gerencia políticas de links seguros usando os cmdlets **\* -SafeLinksPolicy** e gerencia as regras de links seguros usando os cmdlets **\* -SafeLinksRule.**

- No PowerShell, primeiro você cria a política de links seguros e, em seguida, cria a regra de links seguros que identifica a política à que a regra se aplica.
- No PowerShell, você modifica as configurações na política de links seguros e a regra de links seguros separadamente.
- Quando você remove uma política de links seguros do PowerShell, a regra de links seguros correspondente não é removida automaticamente e vice-versa.

### <a name="use-powershell-to-create-safe-links-policies"></a>Usar o PowerShell para criar políticas de Links Seguros

Criar uma política de Links Seguros no PowerShell é um processo de duas etapas:

1. Crie a política de links seguros.
2. Crie a regra de links seguros que especifica a política de links seguros à que a regra se aplica.

> [!NOTE]
> 
> - Você pode criar uma nova regra de links seguros e atribuir uma política de links seguros existente e nãossociada a ela. Uma regra de links seguros não pode ser associada a mais de uma política de links seguros.
> 
> - Você pode configurar as configurações a seguir em novas políticas de links seguros no PowerShell que não estão disponíveis no Centro de Conformidade de Segurança & até depois de criar a política:
> 
>   - Crie a nova política como desabilitada (_Habilitado_ `$false` no cmdlet **New-SafeLinksRule).**
>   - Definir a prioridade da política durante a criação (_Prioridade_ _\<Number\>_ ) no cmdlet **New-SafeLinksRule).**
> 
> - Uma nova política de links seguros que você cria no PowerShell não fica visível no Centro de Conformidade & segurança até que você atribua a política a uma regra de links seguros.

#### <a name="step-1-use-powershell-to-create-a-safe-links-policy"></a>Etapa 1: Usar o PowerShell para criar uma política de links seguros

Para criar uma política de links seguros, use esta sintaxe:

```PowerShell
New-SafeLinksPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-IsEnabled <$true | $false>] [-EnableSafeLinksForTeams <$true | $false>] [-ScanUrls <$true | $false>] [-DeliverMessageAfterScan <$true | $false>] [-EnableForInternalSenders <$true | $false>] [-DoNotAllowClickThrough <$true | $false>] [-DoNotTrackUserClicks <$true | $false>] [-DoNotRewriteUrls "Entry1","Entry2",..."EntryN"]
```

> [!NOTE]
> 
> - Para obter detalhes sobre a sintaxe de entrada a ser usada para o parâmetro _DoNotRewriteUrls,_ consulte Sintaxe de entrada para a lista "Não reescrever as [URLs a seguir".](safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list)
> 
> - Para obter uma sintaxe adicional que você pode usar para o parâmetro _DoNotRewriteUrls_ ao modificar políticas de links seguros existentes usando o cmdlet **Set-SafeLinksPolicy,** consulte a seção [Usar o PowerShell](#use-powershell-to-modify-safe-links-policies) para modificar políticas de links seguros posteriormente neste artigo.

Este exemplo cria uma política de links seguros chamada Contoso All com os seguintes valores:

- Ativar a verificação e a reescrita de URL em mensagens de email.
- Ativar a verificação de URL no Teams (somente visualização do TAP).
- Ativar a verificação em tempo real de URLs clicadas, incluindo links clicados que apontam para arquivos.
- Aguarde a conclusão da verificação de URL antes de entregar a mensagem.
- Ativar a verificação de URL e a reescrita de mensagens internas.
- Rastrear cliques do usuário relacionados à proteção de Links Seguros (não estamos usando o parâmetro _DoNotTrackUserClicks_ e o valor padrão é $false, o que significa que os cliques do usuário são rastreados).
- Não permita que os usuários cliquem na URL original.

```PowerShell
New-SafeLinksPolicy -Name "Contoso All" -IsEnabled $true -EnableSafeLinksForTeams $true -ScanUrls $true -DeliverMessageAfterScan $true -EnableForInternalSenders $true -DoNotAllowClickThrough $true
```

Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [New-SafeLinksPolicy](/powershell/module/exchange/new-safelinkspolicy).

#### <a name="step-2-use-powershell-to-create-a-safe-links-rule"></a>Etapa 2: Usar o PowerShell para criar uma regra de links seguros

Para criar uma regra de links seguros, use esta sintaxe:

```PowerShell
New-SafeLinksRule -Name "<RuleName>" -SafeLinksPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"] [-Enabled <$true | $false>]
```

Este exemplo cria uma regra de links seguros chamada Contoso All com as seguintes condições:

- A regra está associada à política de links seguros chamada Contoso All.
- A regra se aplica a todos os destinatários no contoso.com domínio.
- Como não estamos usando o parâmetro _Priority,_ a prioridade padrão é usada.
- A regra está habilitada (não estamos usando o parâmetro _Enabled_ e o valor padrão é `$true` ).

```powershell
New-SafeLinksRule -Name "Contoso All" -SafeLinksPolicy "Contoso All" -RecipientDomainIs contoso.com
```

Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [New-SafeLinksRule](/powershell/module/exchange/new-safelinksrule).

### <a name="use-powershell-to-view-safe-links-policies"></a>Usar o PowerShell para exibir políticas de links seguros

Para exibir políticas de links seguros existentes, use a seguinte sintaxe:

```PowerShell
Get-SafeLinksPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

Este exemplo retorna uma lista resumida de todas as políticas de links seguros.

```PowerShell
Get-SafeLinksPolicy | Format-Table Name
```

Este exemplo retorna informações detalhadas para a política de links seguros chamada Contoso Executives.

```PowerShell
Get-SafeLinksPolicy -Identity "Contoso Executives"
```

Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Get-SafeLinksPolicy](/powershell/module/exchange/get-safelinkspolicy).

### <a name="use-powershell-to-view-safe-links-rules"></a>Usar o PowerShell para exibir regras de links seguros

Para exibir as regras de links seguros existentes, use a seguinte sintaxe:

```PowerShell
Get-SafeLinksRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

Este exemplo retorna uma lista resumida de todas as regras de links seguros.

```PowerShell
Get-SafeLinksRule | Format-Table Name,State
```

Para filtrar a lista por regras habilitadas ou desabilitadas, execute os seguintes comandos:

```PowerShell
Get-SafeLinksRule -State Disabled
```

```PowerShell
Get-SafeLinksRule -State Enabled
```

Este exemplo retorna informações detalhadas para a regra de links seguros chamada Contoso Executives.

```PowerShell
Get-SafeLinksRule -Identity "Contoso Executives"
```

Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Get-SafeLinksRule](/powershell/module/exchange/get-safelinksrule).

### <a name="use-powershell-to-modify-safe-links-policies"></a>Usar o PowerShell para modificar políticas de links seguros

Não é possível renomear uma política de links seguros no PowerShell (o cmdlet **Set-SafeLinksPolicy** não tem _parâmetro Name)._ Ao renomear uma política de Links Seguros no Centro de Conformidade & segurança, você está renomeando apenas a regra de links _seguros._

A única consideração adicional para modificar políticas de links seguros no PowerShell é a sintaxe disponível para o parâmetro _DoNotRewriteUrls_ (a lista "Não reescrever as [URLs a seguir"](safe-links.md#do-not-rewrite-the-following-urls-lists-in-safe-links-policies)):

- Para adicionar valores que substituirão quaisquer entradas existentes, use a seguinte sintaxe: `"Entry1","Entry2,..."EntryN"` .
- Para adicionar ou remover valores sem afetar outras entradas existentes, use a seguinte sintaxe: `@{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}`

Caso contrário, as mesmas configurações estarão disponíveis quando você criar uma política de links seguros, conforme descrito na Etapa [1: Usar](#step-1-use-powershell-to-create-a-safe-links-policy) o PowerShell para criar uma seção de política de links seguros anteriormente neste artigo.

Para modificar uma política de links seguros, use esta sintaxe:

```PowerShell
Set-SafeLinksPolicy -Identity "<PolicyName>" <Settings>
```

Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Set-SafeLinksPolicy](/powershell/module/exchange/set-safelinkspolicy).

### <a name="use-powershell-to-modify-safe-links-rules"></a>Usar o PowerShell para modificar regras de links seguros

A única configuração que não está disponível quando você modifica uma regra de links seguros no PowerShell é o parâmetro _Enabled_ que permite criar uma regra desabilitada. Para habilitar ou desabilitar as regras de links seguros existentes, consulte a próxima seção.

Caso contrário, as mesmas configurações estarão disponíveis quando você criar uma regra conforme descrito na Etapa [2: Use](#step-2-use-powershell-to-create-a-safe-links-rule) o PowerShell para criar uma seção de regra de links seguros anteriormente neste artigo.

Para modificar uma regra de links seguros, use esta sintaxe:

```PowerShell
Set-SafeLinksRule -Identity "<RuleName>" <Settings>
```

Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Set-SafeLinksRule](/powershell/module/exchange/set-safelinksrule).

### <a name="use-powershell-to-enable-or-disable-safe-links-rules"></a>Usar o PowerShell para habilitar ou desabilitar regras de links seguros

Habilitar ou desabilitar uma regra de links seguros no PowerShell habilita ou desabilita toda a política de Links Seguros (a regra de links seguros e a política de links seguros atribuídos).

Para habilitar ou desabilitar uma regra de links seguros no PowerShell, use esta sintaxe:

```PowerShell
<Enable-SafeLinksRule | Disable-SafeLinksRule> -Identity "<RuleName>"
```

Este exemplo desabilita a regra de links seguros chamada Departamento de Marketing.

```PowerShell
Disable-SafeLinksRule -Identity "Marketing Department"
```

Este exemplo habilita a mesma regra.

```PowerShell
Enable-SafeLinksRule -Identity "Marketing Department"
```

Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Enable-SafeLinksRule](/powershell/module/exchange/enable-safelinksrule) e [Disable-SafeLinksRule](/powershell/module/exchange/disable-safelinksrule).

### <a name="use-powershell-to-set-the-priority-of-safe-links-rules"></a>Usar o PowerShell para definir a prioridade das regras de links seguros

O valor mais alto de prioridade que pode ser definido em uma regra é 0. O valor mais baixo que pode ser definido depende do número de regras. Por exemplo, se você tiver cinco regras, use os valores de prioridade de 0 a 4. Alterar a prioridade de uma regra existente pode ter um efeito cascata em outras regras. Por exemplo, se você tiver cinco regras personalizadas (prioridades de 0 a 4) e alterar a prioridade de uma regra para 2, a regra existente com prioridade 2 será alterada para a prioridade 3, e a regra com prioridade 3 será alterada para prioridade 4.

Para definir a prioridade de uma regra de links seguros no PowerShell, use a seguinte sintaxe:

```PowerShell
Set-SafeLinksRule -Identity "<RuleName>" -Priority <Number>
```

Este exemplo define a prioridade da regra chamada Marketing Department como 2. Todas as regras existentes com prioridade inferior ou igual a 2 são reduzidas por 1 (seus números de prioridade são aumentados por 1).

```PowerShell
Set-SafeLinksRule -Identity "Marketing Department" -Priority 2
```

> [!NOTE]
> Para definir a prioridade de uma nova regra ao criar, use o parâmetro _Priority_ no cmdlet **New-SafeLinksRule.**

Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Set-SafeLinksRule](/powershell/module/exchange/set-safelinksrule).

### <a name="use-powershell-to-remove-safe-links-policies"></a>Usar o PowerShell para remover políticas de links seguros

Quando você usa o PowerShell para remover uma política de links seguros, a regra de links seguros correspondente não é removida.

Para remover uma política de links seguros no PowerShell, use esta sintaxe:

```PowerShell
Remove-SafeLinksPolicy -Identity "<PolicyName>"
```

Este exemplo remove a política de links seguros chamada Departamento de Marketing.

```PowerShell
Remove-SafeLinksPolicy -Identity "Marketing Department"
```

Para obter informações detalhadas sobre sintaxes e parâmetros, [consulte Remove-SafeLinksPolicy](/powershell/module/exchange/remove-safelinkspolicy).

### <a name="use-powershell-to-remove-safe-links-rules"></a>Usar o PowerShell para remover regras de links seguros

Quando você usa o PowerShell para remover uma regra de links seguros, a política de links seguros correspondente não é removida.

Para remover uma regra de links seguros no PowerShell, use esta sintaxe:

```PowerShell
Remove-SafeLinksRule -Identity "<PolicyName>"
```

Este exemplo remove a regra de links seguros chamada Departamento de Marketing.

```PowerShell
Remove-SafeLinksRule -Identity "Marketing Department"
```

Para obter informações detalhadas sobre sintaxes e parâmetros, [consulte Remove-SafeLinksRule](/powershell/module/exchange/remove-safelinksrule).

Para verificar se Os Links Seguros estão verificando mensagens, verifique os relatórios disponíveis do Microsoft Defender para Office 365. Para obter mais informações, consulte [View reports for Defender for Office 365](view-reports-for-mdo.md) and Use Explorer in the Security & Compliance [Center](threat-explorer.md).

## <a name="how-do-you-know-these-procedures-worked"></a>Como saber se esses procedimentos funcionaram?

Para verificar se você criou, modificou ou removeu políticas de Links Seguros com êxito, faça uma das seguintes etapas:

- No Centro de Conformidade & segurança, vá para **Política** de Gerenciamento de Ameaças \>  \> **ATP Links seguros**. Verifique a lista de políticas, seus **valores de Status** e seus valores **priority.** Para exibir mais detalhes, selecione a política na lista e veja os detalhes no fly-out.

- No PowerShell do Exchange Online ou no PowerShell da Proteção do Exchange Online, substitua pelo nome da política ou regra, execute o seguinte comando e \<Name\> verifique as configurações:

  ```PowerShell
  Get-SafeLinksPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-SafeLinksRule -Identity "<Name>"
  ```