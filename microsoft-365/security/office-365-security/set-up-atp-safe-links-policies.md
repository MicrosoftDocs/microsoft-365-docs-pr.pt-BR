---
title: Configurar políticas de links seguros no Microsoft defender para Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: how-to
ms.date: ''
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: bdd5372d-775e-4442-9c1b-609627b94b5d
ms.collection:
- M365-security-compliance
description: Os administradores podem aprender a exibir, criar, modificar e excluir políticas de links seguros e configurações globais de links seguros no Microsoft defender para Office 365.
ms.openlocfilehash: 8a6d8a7ad567b658f04cb0b28800d4edbc33ec67
ms.sourcegitcommit: f81ca61f74f11a7436a6172538c3bda81b484d62
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/15/2020
ms.locfileid: "49675236"
---
# <a name="set-up-safe-links-policies-in-microsoft-defender-for-office-365"></a>Configurar políticas de links seguros no Microsoft defender para Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

> [!IMPORTANT]
> Este artigo se destina a clientes empresariais que possuem o [Microsoft Defender para Office 365](office-365-atp.md). Se você for um usuário doméstico que procura informações sobre o Safelinks no Outlook, consulte [Advanced Outlook.com Security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).

Links seguros é um recurso do [Microsoft defender para Office 365](office-365-atp.md) que oferece verificação de URL de mensagens de email de entrada no fluxo de emails e a hora de clicar em verificação de URLs e links em mensagens de email e em outros locais. Para obter mais informações, consulte [links seguros no Microsoft defender para Office 365](atp-safe-links.md).

Não há nenhuma política interna ou de links seguros padrão. Para obter a verificação de URLs de links seguros, você precisa criar uma ou mais políticas de links seguros, conforme descrito neste artigo.

> [!NOTE]
> Você define as configurações globais para proteção de links seguros **fora** de políticas de links seguros. Para obter instruções, consulte [Configure Global Settings for Safe links in Microsoft defender for Office 365](configure-global-settings-for-safe-links.md).

Você pode configurar políticas de links seguros no centro de conformidade e segurança & ou no PowerShell (Exchange Online PowerShell para organizações qualificadas da Microsoft 365 com caixas de correio no Exchange Online; autônomo do EOP PowerShell para organizações sem caixas de correio do Exchange Online, mas com o Microsoft defender para Office 365 Add-on subscriptions).

Os elementos básicos de uma política de links seguros são:

- **A política de links seguros**: Ative a proteção de links seguros, ative a verificação de URL em tempo real, especifique se deve aguardar a conclusão da verificação em tempo real antes de entregar a mensagem, ative a verificação de mensagens internas, especifique se deseja rastrear cliques do usuário em URLs e especifique se deseja permitir que os usuários cliquem em Trough para a URL original.
- **A regra de links seguros**: especifica a prioridade e os filtros de destinatários (a qual a política se aplica).

A diferença entre esses dois elementos não é óbvia quando você gerencia políticas de links seguros no centro de conformidade de & de segurança:

- Ao criar uma política de links seguros, você realmente está criando uma regra de links seguros e a política de links seguros associada ao mesmo tempo usando o mesmo nome para ambos.
- Quando você modifica uma política de links seguros, as configurações relacionadas ao nome, prioridade, habilitado ou desabilitado e filtros de destinatário modificam a regra de links seguros. Todas as outras configurações modificam a política de links seguros associada.
- Quando você remove uma política de links seguros, a regra de links seguros e a política de links seguros associada são removidos.

No PowerShell do Exchange Online ou no PowerShell do EOP autônomo, a política e a regra são gerenciadas separadamente. Para obter mais informações, consulte a seção [usar o PowerShell do Exchange Online ou o PowerShell do EOP para configurar políticas de links seguros](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies) , posteriormente neste artigo.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Do que você precisa saber para começar?

- Abra o Centro de Conformidade e Segurança em <https://protection.office.com/>. Para ir diretamente para a página de **links seguros** , use <https://protection.office.com/safelinksv2> .

- Para se conectar ao PowerShell do Exchange Online, confira [Conectar ao PowerShell do Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell). Para se conectar ao EOP PowerShell autônomo, consulte [Conectar-se ao PowerShell do Exchange Online Protection.](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).

- Você precisa de permissões no Centro de Conformidade e Segurança antes de poder realizar os procedimentos deste artigo:
  - Para criar, modificar e excluir políticas de links seguros, você precisa ser membro dos grupos de função de **Gerenciamento da organização** ou de administrador de **segurança** .
  - Para acesso somente leitura a políticas de links seguros, você precisa ser membro dos grupos de função **leitor global** ou **leitor de segurança** .

  Para saber mais, confira [Permissões no Centro de Conformidade de Segurança](permissions-in-the-security-and-compliance-center.md).

  **Observações**:

  - Adicionar usuários à função correspondente do Azure Active Directory no Centro de administração do Microsoft 365 fornece aos usuários as permissões necessárias no Centro de Segurança e Conformidade _e_ permissões para outros recursos no Microsoft 365. Para obter mais informações, confira o artigo [Sobre funções de administrador](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).
  - O grupo de função **Gerenciamento de Organização Somente para Exibição** no [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) também fornece acesso somente leitura ao recurso.

- Para obter as configurações recomendadas para políticas de links seguros, consulte [configurações de política de links seguros](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings).

- Aguarde até 30 minutos para que uma política nova ou atualizada seja aplicada.

- [Novos recursos estão sempre sendo adicionados ao Microsoft defender para Office 365](office-365-atp.md#new-features-in-microsoft-defender-for-office-365). À medida que novos recursos são adicionados, talvez seja necessário fazer ajustes em suas políticas de links seguros existentes.

## <a name="use-the-security--compliance-center-to-create-safe-links-policies"></a>Usar o centro de conformidade de & de segurança para criar políticas de links seguros

A criação de uma política de links seguros personalizada no centro de conformidade de & de segurança cria a regra de links seguros e a política de links seguros associada ao mesmo tempo usando o mesmo nome para ambos.

1. No centro de conformidade & segurança, vá para política de **Gerenciamento de ameaças** de \>  \> **links seguros de ATP**.

2. Na página **links seguros** , clique em **criar**.

3. O assistente de **nova política de links seguros** é aberto. Na página **nomear sua política** , defina as seguintes configurações:

   - **Nome**: insira um nome exclusivo e descritivo para a política.

   - **Descrição**: digite uma descrição opcional para a política.

   Quando terminar, clique em **Avançar**.

4. Na página **configurações** que aparece, defina as seguintes configurações:

   - **Selecione a ação para URLs possivelmente mal-intencionadas desconhecidas nas mensagens**: selecione **ativado** para habilitar a proteção de links seguros para links em mensagens de email.

   - **Selecione a ação para URLs desconhecidas ou potencialmente mal-intencionadas no Microsoft Teams**: selecione **ativado** para habilitar a proteção de links seguros para links no Teams.

   - **Aplicar verificação de URL em tempo real para links suspeitos e links que apontam para arquivos**: Selecione essa configuração para habilitar a verificação em tempo real de links em mensagens de email.

   - **Aguarde a conclusão da verificação de URL antes de entregar a mensagem**: Selecione essa configuração para esperar a conclusão da verificação de URL em tempo real antes de entregar a mensagem.

   - **Aplicar links seguros a mensagens de email enviadas dentro da organização**: Selecione essa configuração para aplicar a política de links seguros a mensagens entre remetentes internos e destinatários internos.

   - **Não rastrear cliques do usuário**: Deixe essa configuração desmarcada para permitir que o usuário de acompanhamento clique em URLs nas mensagens de email.

   - **Não permitir que os usuários cliquem na URL original**: Selecione essa configuração para impedir que os usuários cliquem na URL original nas [páginas de aviso](atp-safe-links.md#warning-pages-from-safe-links).

   - **Não Reescreva as seguintes URLs**: permite acessar as URLs especificadas que, caso contrário, serão bloqueadas por links seguros.

     Na caixa, digite a URL ou o valor desejado e clique em ![Ícone Adicionar botão](../../media/ITPro-EAC-AddIcon.png).

     Para remover uma entrada existente, selecione-a e clique em ![Ícone Excluir botão](../../media/ITPro-EAC-DeleteIcon.png).

     Para obter a sintaxe de entrada, consulte a [sintaxe de entrada da lista "não reescrever as seguintes URLs"](atp-safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list).

   Para obter informações detalhadas sobre essas configurações, consulte [configurações de links seguros para mensagens de email](atp-safe-links.md#safe-links-settings-for-email-messages) e [configurações de links seguros para o Microsoft Teams](atp-safe-links.md#safe-links-settings-for-microsoft-teams).

   Para obter mais valores recomendados para configurações de política padrão e estrita, consulte [configurações de política de links seguros](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings).

   Quando terminar, clique em **Avançar**.

5. Na página **aplicado a** que aparece, identifique os destinatários internos aos quais a política se aplica.

   Só é possível usar uma condição ou exceção uma vez; contudo, você pode especificar vários valores para a condição ou exceção. Vários valores da mesma condição ou exceção usam a lógica OU (por exemplo, _\<recipient1\>_ ou _\<recipient2\>_). Para diferentes condições ou exceções, use a lógica E (por exemplo, _\<recipient1\>_ e _\<member of group 1\>_).

   Clique em **Adicionar uma condição**. Na lista suspensa exibida, selecione uma condição em **aplicado se**:

   - **O destinatário é**: especifica uma ou mais caixas de correio, usuários de email ou contatos de email em sua organização.
   - **O destinatário é um membro de**: especifica um ou mais grupos na sua organização.
   - **O domínio do destinatário é**: Especifica os destinatários em um ou mais domínios aceitos configurados na sua organização. 

   Após selecionar a condição, uma lista suspensa correspondente aparecerá com uma **destas** caixas.

   - Clique na caixa e role pela lista de valores para selecionar.
   - Clique na caixa e comece a digitar para filtrar a lista e selecione um valor.
   - Para adicionar valores adicionais, clique em uma área vazia na caixa.
   - Para remover entradas individuais, clique em **remover** ![ ícone de remoção ](../../media/scc-remove-icon.png) no valor.
   - Para remover toda a condição, clique em **remover** ![ ícone de remoção ](../../media/scc-remove-icon.png) na condição.

   Para adicionar uma condição adicional, clique em **Adicionar uma condição** e selecione um valor restante em **aplica If**.

   Para adicionar exceções, clique em **Adicionar uma condição** e selecione uma exceção em **exceto se**. As configurações e o comportamento são exatamente como as condições.

   Quando terminar, clique em **Avançar**.

6. Na página **revise suas configurações** exibidas, revise suas configurações. Você pode clicar em **Editar** em cada configuração para modificá-la.

   Quando tiver concluído, clique em **concluir**.

## <a name="use-the-security--compliance-center-to-view-safe-links-policies"></a>Usar o centro de conformidade de & de segurança para exibir políticas de links seguros

1. No centro de conformidade & segurança, vá para política de **Gerenciamento de ameaças** de \>  \> **links seguros de ATP**.

2. Na página de **links seguros** , selecione uma política na lista e clique nela (não marque a caixa de seleção).

   Os detalhes da política aparecem em saída

## <a name="use-the-security--compliance-center-to-modify-safe-links-policies"></a>Usar o centro de conformidade de & de segurança para modificar as políticas de links seguros

1. No centro de conformidade & segurança, vá para política de **Gerenciamento de ameaças** de \>  \> **links seguros de ATP**.

2. Na página de **links seguros** , selecione uma política na lista e clique nela (não marque a caixa de seleção).

3. Nos detalhes da política que aparecem, clique em **Editar política**.

As configurações disponíveis no menu suspenso que aparecem são idênticas às descritas na seção [usar o centro de conformidade de segurança & para criar políticas de links seguros](#use-the-security--compliance-center-to-create-safe-links-policies) .

Para habilitar ou desabilitar uma política ou definir a ordem de prioridade da política, consulte as seções a seguir.

### <a name="enable-or-disable-safe-links-policies"></a>Habilitar ou desabilitar políticas de links seguros

1. No centro de conformidade & segurança, vá para política de **Gerenciamento de ameaças** de \>  \> **links seguros de ATP**.

2. Observe o valor na coluna **status** :

   - Mova o botão de alternância para a esquerda para desabilitar a política: ![Desativar política](../../media/scc-toggle-off.png).

   - Mova o botão de alternância para a direita para habilitar a política: ![Ativar política](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png).

### <a name="set-the-priority-of-safe-links-policies"></a>Definir a prioridade das políticas de links seguros

Por padrão, as políticas de links seguros recebem uma prioridade com base na ordem em que foram criadas (as políticas mais recentes são de prioridade mais baixa do que as diretivas mais antigas). Um número de prioridade menor indica uma maior prioridade para a política (0 é a maior), e as políticas são processadas por ordem de prioridade (políticas com maior prioridade são processadas antes das políticas com menor prioridade). Duas políticas não podem ter a mesma prioridade, e o processamento da política será interrompido após a primeira política ser aplicada.

Para obter mais informações sobre a ordem de precedência e como várias políticas são avaliadas e aplicadas, confira [Ordem e precedência da proteção de email](how-policies-and-protections-are-combined.md).

As políticas de links seguros são exibidas na ordem em que são processadas (a primeira política tem o valor de **prioridade** 0).

**Observação**: no centro de conformidade & segurança, você só pode alterar a prioridade da política de links seguros após criá-la. No PowerShell, você pode substituir a prioridade padrão ao criar a regra de links seguros (que pode afetar a prioridade das regras existentes).

Para alterar a prioridade de uma política, mova a política para cima ou para baixo na lista (não é possível modificar diretamente o número de **Prioridade** no Centro de Conformidade e Segurança).

1. No centro de conformidade & segurança, vá para política de **Gerenciamento de ameaças** de \>  \> **links seguros de ATP**.

2. Na página de **links seguros** , selecione uma política na lista e clique nela (não marque a caixa de seleção).

3. Na saída detalhes da política exibida, clique no botão prioridade disponível:

   - A política de links seguros com o valor de **prioridade** **0** tem apenas o botão **diminuir prioridade** disponível.

   - A política de links seguros com o menor valor de **prioridade** (por exemplo, **3**) tem apenas o botão **aumentar prioridade** disponível.

   - Se você tiver três ou mais políticas de links seguros, as políticas entre os valores de prioridade mais alta e mais baixa terão os botões **aumentar prioridade** e **diminuir prioridade** disponíveis.

4. Clique em **aumentar prioridade** ou **diminuir prioridade** para alterar o valor de **prioridade** .

5. Quando terminar, clique em **Fechar**.

## <a name="use-the-security--compliance-center-to-remove-safe-links-policies"></a>Usar o centro de conformidade de & de segurança para remover políticas de links seguros

1. No centro de conformidade & segurança, vá para política de **Gerenciamento de ameaças** de \>  \> **links seguros de ATP**.

2. Na página de **links seguros** , selecione uma política na lista e clique nela (não marque a caixa de seleção).

3. Nos detalhes da política de saída, clique em **excluir política** e clique em **Sim** na caixa de diálogo de aviso que aparece.

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies"></a>Usar o PowerShell do Exchange Online ou o PowerShell do EOP para configurar políticas de links seguros

Como descrito anteriormente, uma política de links seguros consiste em uma política de links seguros e uma regra de links seguros.

No PowerShell, a diferença entre políticas de links seguros e regras de links seguros é aparente. Você gerencia as políticas de links seguros usando os cmdlets **\* -SafeLinksPolicy** e gerencia as regras de links seguros usando os cmdlets **\* -SafeLinksRule** .

- No PowerShell, você cria a política de links seguros primeiro e, em seguida, cria a regra de links seguros que identifica a política à qual a regra se aplica.
- No PowerShell, você modifica as configurações da política de links seguros e da regra de links seguros separadamente.
- Quando você remove uma política de links seguros do PowerShell, a regra de links seguros correspondente não é removida automaticamente e vice-versa.

### <a name="use-powershell-to-create-safe-links-policies"></a>Usar o PowerShell para criar políticas de links seguros

A criação de uma política de links seguros no PowerShell é um processo de duas etapas:

1. Criar a política de links seguros.
2. Crie a regra de links seguros que especifica a política de links seguros à qual a regra se aplica.

 **Observações**:

- Você pode criar uma nova regra de links seguros e atribuir uma política de links seguros sem associação existente a ela. Uma regra de links seguros não pode ser associada a mais de uma política de links seguros.

- Você pode definir as seguintes configurações em novas políticas de links seguros no PowerShell que não estão disponíveis no centro de conformidade & de segurança até que a política seja criada:

  - Crie a nova política como desabilitada (_habilitada_ `$false` no cmdlet **New-SafeLinksRule** ).
  - Definir a prioridade da política durante a criação (_prioridade_ _\<Number\>_ ) no cmdlet **New-SafeLinksRule** ).

- Uma nova política de links seguros que você cria no PowerShell não fica visível no centro de conformidade & segurança até que você atribua a política a uma regra de links seguros.

#### <a name="step-1-use-powershell-to-create-a-safe-links-policy"></a>Etapa 1: usar o PowerShell para criar uma política de links seguros

Para criar uma política de links seguros, use esta sintaxe:

```PowerShell
New-SafeLinksPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-IsEnabled <$true | $false>] [-EnableSafeLinksForTeams <$true | $false>] [-ScanUrls <$true | $false>] [-DeliverMessageAfterScan <$true | $false>] [-EnableForInternalSenders <$true | $false>] [-DoNotAllowClickThrough <$true | $false>] [-DoNotTrackUserClicks <$true | $false>] [-DoNotRewriteUrls "Entry1","Entry2",..."EntryN"]
```

**Observações**:

- Para obter detalhes sobre a sintaxe de entrada a ser usada para o parâmetro _DoNotRewriteUrls_ , consulte [a sintaxe de entrada da lista "não reescrever as seguintes URLs"](atp-safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list).

- Para obter sintaxe adicional que você pode usar para o parâmetro _DoNotRewriteUrls_ ao modificar as políticas de links seguros existentes usando o cmdlet **set-SafeLinksPolicy** , consulte a seção [usar o PowerShell para modificar as políticas de links seguros](#use-powershell-to-modify-safe-links-policies) mais adiante neste artigo.

Este exemplo cria uma política de links seguros chamada contoso todos com os seguintes valores:

- Ative a verificação de URL e reescreva em mensagens de email.
- Ative a verificação de URL no Microsoft Teams (toque apenas em visualização).
- Ative a verificação em tempo real de URLs clicadas, incluindo links clicados apontando para arquivos.
- Aguarde a conclusão da verificação de URL antes de entregar a mensagem.
- Ative a verificação de URL e a reconfiguração de mensagens internas.
- Rastrear cliques do usuário relacionados à proteção de links seguros (não estamos usando o parâmetro _DoNotTrackUserClicks_ , e o valor padrão é $false, o que significa que os cliques do usuário são controlados).
- Não permita que os usuários cliquem até a URL original.

```PowerShell
New-SafeLinksPolicy -Name "Contoso All" -IsEnabled $true -EnableSafeLinksForTeams $true -ScanUrls $true -DeliverMessageAfterScan $true -EnableForInternalSenders $true -DoNotAllowClickThrough $true
```

Para informações detalhadas de sintaxes e de parâmetros, consulte [New-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/new-safelinkspolicy).

#### <a name="step-2-use-powershell-to-create-a-safe-links-rule"></a>Etapa 2: usar o PowerShell para criar uma regra de links seguros

Para criar uma regra de links seguros, use esta sintaxe:

```PowerShell
New-SafeLinksRule -Name "<RuleName>" -SafeLinksPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"] [-Enabled <$true | $false>]
```

Este exemplo cria uma regra de links seguros chamada contoso com as seguintes condições:

- A regra é associada à política de links seguros chamada contoso ALL.
- A regra se aplica a todos os destinatários no domínio contoso.com.
- Como não estamos usando o parâmetro _Priority_ , a prioridade padrão é usada.
- A regra está habilitada (não estamos usando o parâmetro _Enabled_ e o valor padrão é `$true` ).

```powershell
New-SafeLinksRule -Name "Contoso All" -SafeLinksPolicy "Contoso All" -RecipientDomainIs contoso.com
```

Para informações detalhadas de sintaxes e de parâmetros, consulte [New-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/new-safelinksrule).

### <a name="use-powershell-to-view-safe-links-policies"></a>Usar o PowerShell para exibir políticas de links seguros

Para exibir as políticas de links seguros existentes, use a seguinte sintaxe:

```PowerShell
Get-SafeLinksPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

Este exemplo retorna uma lista resumida de todas as políticas de links seguros.

```PowerShell
Get-SafeLinksPolicy | Format-Table Name
```

Este exemplo retorna informações detalhadas sobre a política de links seguros chamada executivos da contoso.

```PowerShell
Get-SafeLinksPolicy -Identity "Contoso Executives"
```

Para informações detalhadas de sintaxes e de parâmetros, consulte [Get-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/get-safelinkspolicy).

### <a name="use-powershell-to-view-safe-links-rules"></a>Usar o PowerShell para exibir regras de links seguros

Para exibir regras de links seguros existentes, use a seguinte sintaxe:

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

Este exemplo retorna informações detalhadas sobre a regra de links seguros chamada executivos da contoso.

```PowerShell
Get-SafeLinksRule -Identity "Contoso Executives"
```

Para informações detalhadas de sintaxes e de parâmetros, consulte [Get-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/get-safelinksrule).

### <a name="use-powershell-to-modify-safe-links-policies"></a>Usar o PowerShell para modificar as políticas de links seguros

Não é possível renomear uma política de links seguros no PowerShell (o cmdlet **set-SafeLinksPolicy** não tem nenhum parâmetro _Name_ ). Ao renomear uma política de links seguros no centro de conformidade e segurança &, você estará apenas renomeando a _regra_ de links seguros.

A única consideração adicional para modificar as políticas de links seguros no PowerShell é a sintaxe disponível para o parâmetro _DoNotRewriteUrls_ (a [lista "não reescrever as seguintes URLs"](atp-safe-links.md#do-not-rewrite-the-following-urls-lists-in-safe-links-policies)):

- Para adicionar valores que substituirão as entradas existentes, use a seguinte sintaxe: `"Entry1","Entry2,..."EntryN"` .
- Para adicionar ou remover valores sem afetar outras entradas existentes, use a seguinte sintaxe: `@{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}`

Caso contrário, as mesmas configurações estarão disponíveis quando você criar uma política de links seguros, conforme descrito na seção [etapa 1: usar o PowerShell para criar uma política de links seguros](#step-1-use-powershell-to-create-a-safe-links-policy) , anteriormente neste artigo.

Para modificar uma política de links seguros, use esta sintaxe:

```PowerShell
Set-SafeLinksPolicy -Identity "<PolicyName>" <Settings>
```

Para informações detalhadas de sintaxes e de parâmetros, consulte [set-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/set-safelinkspolicy).

### <a name="use-powershell-to-modify-safe-links-rules"></a>Usar o PowerShell para modificar regras de links seguros

A única configuração que não está disponível quando você modifica uma regra de links seguros no PowerShell é o parâmetro _habilitado_ que permite criar uma regra desabilitada. Para habilitar ou desabilitar regras de links seguros existentes, consulte a próxima seção.

Caso contrário, as mesmas configurações estarão disponíveis quando você criar uma regra, conforme descrito na seção [etapa 2: usar o PowerShell para criar uma regra de links seguros](#step-2-use-powershell-to-create-a-safe-links-rule) , anteriormente neste artigo.

Para modificar uma regra de links seguros, use esta sintaxe:

```PowerShell
Set-SafeLinksRule -Identity "<RuleName>" <Settings>
```

Para informações detalhadas de sintaxes e de parâmetros, consulte [set-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/set-safelinksrule).

### <a name="use-powershell-to-enable-or-disable-safe-links-rules"></a>Usar o PowerShell para habilitar ou desabilitar regras de links seguros

Habilitar ou desabilitar uma regra de links seguros no PowerShell habilita ou desabilita toda a política de links seguros (a regra de links seguros e a política de links seguros atribuídas).

Para habilitar ou desabilitar uma regra de links seguros no PowerShell, use esta sintaxe:

```PowerShell
<Enable-SafeLinksRule | Disable-SafeLinksRule> -Identity "<RuleName>"
```

Este exemplo desabilita a regra de links seguros chamada departamento de marketing.

```PowerShell
Disable-SafeLinksRule -Identity "Marketing Department"
```

Este exemplo habilita a mesma regra.

```PowerShell
Enable-SafeLinksRule -Identity "Marketing Department"
```

Para informações detalhadas de sintaxes e de parâmetros, consulte [Enable-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/enable-safelinksrule) e [Disable-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/disable-safelinksrule).

### <a name="use-powershell-to-set-the-priority-of-safe-links-rules"></a>Usar o PowerShell para definir a prioridade de regras de links seguros

O valor mais alto de prioridade que pode ser definido em uma regra é 0. O valor mais baixo que pode ser definido depende do número de regras. Por exemplo, se você tiver cinco regras, use os valores de prioridade de 0 a 4. Alterar a prioridade de uma regra existente pode ter um efeito cascata em outras regras. Por exemplo, se você tiver cinco regras personalizadas (prioridades de 0 a 4) e alterar a prioridade de uma regra para 2, a regra existente com prioridade 2 será alterada para a prioridade 3, e a regra com prioridade 3 será alterada para prioridade 4.

Para definir a prioridade de uma regra de links seguros no PowerShell, use a seguinte sintaxe:

```PowerShell
Set-SafeLinksRule -Identity "<RuleName>" -Priority <Number>
```

Este exemplo define a prioridade da regra chamada Marketing Department como 2. Todas as regras existentes com prioridade inferior ou igual a 2 são reduzidas por 1 (seus números de prioridade são aumentados por 1).

```PowerShell
Set-SafeLinksRule -Identity "Marketing Department" -Priority 2
```

**Observação**: para definir a prioridade de uma nova regra ao criá-la, use o parâmetro _Priority_ no cmdlet **New-SafeLinksRule** .

Para informações detalhadas de sintaxes e de parâmetros, consulte [set-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/set-safelinksrule).

### <a name="use-powershell-to-remove-safe-links-policies"></a>Usar o PowerShell para remover políticas de links seguros

Quando você usa o PowerShell para remover uma política de links seguros, a regra de links seguros correspondente não é removida.

Para remover uma política de links seguros no PowerShell, use esta sintaxe:

```PowerShell
Remove-SafeLinksPolicy -Identity "<PolicyName>"
```

Este exemplo remove a política de links seguros chamada departamento de marketing.

```PowerShell
Remove-SafeLinksPolicy -Identity "Marketing Department"
```

Para informações detalhadas de sintaxes e de parâmetros, consulte [Remove-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/remove-safelinkspolicy).

### <a name="use-powershell-to-remove-safe-links-rules"></a>Usar o PowerShell para remover regras de links seguros

Quando você usa o PowerShell para remover uma regra de links seguros, a política de links seguros correspondente não é removida.

Para remover uma regra de links seguros no PowerShell, use esta sintaxe:

```PowerShell
Remove-SafeLinksRule -Identity "<PolicyName>"
```

Este exemplo remove a regra de links seguros chamada departamento de marketing.

```PowerShell
Remove-SafeLinksRule -Identity "Marketing Department"
```

Para informações detalhadas de sintaxes e de parâmetros, consulte [Remove-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/remove-safelinksrule).

Para verificar se os links seguros estão verificando mensagens, confira os relatórios disponíveis do Microsoft defender for Office 365. Para obter mais informações, consulte [View Reports for defender for Office 365](view-reports-for-atp.md) e [Use Explorer no centro de conformidade de & de segurança](threat-explorer.md).

## <a name="how-do-you-know-these-procedures-worked"></a>Como saber se esses procedimentos funcionaram?

Para verificar se as políticas de links seguros foram criadas, modificadas ou removidas com êxito, execute uma das seguintes etapas:

- No centro de conformidade & segurança, vá para política de **Gerenciamento de ameaças** de \>  \> **links seguros de ATP**. Verifique a lista de políticas, seus valores de **status** e seus valores de **prioridade** . Para exibir mais detalhes, selecione a política na lista e exiba os detalhes na saída.

- No PowerShell do Exchange Online ou do Exchange Online Protection, substitua o \<Name\> nome da política ou regra, execute o seguinte comando e verifique as configurações:

  ```PowerShell
  Get-SafeLinksPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-SafeLinksRule -Identity "<Name>"
  ```
