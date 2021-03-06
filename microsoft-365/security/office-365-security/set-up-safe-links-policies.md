---
title: Configurar políticas Cofre links no Microsoft Defender para Office 365
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
description: Os administradores podem aprender a exibir, criar, modificar e excluir Cofre políticas de links e configurações globais Cofre Links no Microsoft Defender para Office 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 8d42051d2ca4f26758cbe7334d427f3f93178f97
ms.sourcegitcommit: ebb1c3b4d94058a58344317beb9475c8a2eae9a7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/24/2021
ms.locfileid: "53108206"
---
# <a name="set-up-safe-links-policies-in-microsoft-defender-for-office-365"></a>Configurar políticas Cofre links no Microsoft Defender para Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
- [Plano 1 e plano 2 do Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!IMPORTANT]
> Este artigo se destina a clientes empresariais que possuem o [Microsoft Defender para Office 365](defender-for-office-365.md). Se você for um usuário de residência procurando informações sobre Safelinks no Outlook, consulte [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).

Cofre Links no [Microsoft Defender para Office 365](defender-for-office-365.md) fornece verificação de URL de mensagens de email de entrada no fluxo de emails e hora de verificação de clique de URLs e links em mensagens de email e em outros locais. Para obter mais informações, [consulte Cofre Links no Microsoft Defender para Office 365](safe-links.md).

Não há política de links interna ou padrão Cofre Links. Para obter Cofre verificação de links de URLs, você precisa criar uma ou mais políticas Cofre Links conforme descrito neste artigo.

> [!NOTE]
>
> Você configura as configurações globais para a proteção Cofre Links **fora** das políticas Cofre Links. Para obter instruções, consulte [Configure global settings for Cofre Links in Microsoft Defender for Office 365](configure-global-settings-for-safe-links.md).
>
> Os administradores devem considerar as diferentes configurações para Cofre Links. Uma das opções disponíveis é incluir informações de identificação do usuário em Cofre Links. Esse recurso permite que as *equipes de Operações* de Segurança investiguem possíveis comprometimentos do usuário, tome medidas corretivas e limitem violações custosas.

Você pode configurar políticas de Links do Cofre no portal do Microsoft 365 Defender ou no PowerShell (Exchange Online PowerShell para organizações de Microsoft 365 qualificadas com caixas de correio no Exchange Online; PowerShell autônomo do EOP para organizações sem caixas de correio Exchange Online, mas com o Microsoft Defender para assinaturas de complementos do Office 365).

Os elementos básicos de uma política Cofre Links são:

- A política de **links** seguros : ativar a proteção de links do Cofre, ativar a verificação de URL em tempo real, especificar se a verificação em tempo real deve ser concluída antes de entregar a mensagem, ativar a verificação de mensagens internas, especificar se deve rastrear os cliques do usuário em URLs e especificar se os usuários devem clicar na URL original.
- **A regra de links seguros**: especifica a prioridade e os filtros de destinatário (a quem a política se aplica).

A diferença entre esses dois elementos não é óbvia quando você gerencia Cofre políticas de Links no portal Microsoft 365 Defender portal:

- Ao criar uma política Cofre Links, você está realmente criando uma regra de links seguros e a política de links seguros associados ao mesmo tempo usando o mesmo nome para ambos.
- Quando você modifica uma política Cofre Links, as configurações relacionadas ao nome, prioridade, habilitado ou desabilitado e filtros de destinatário modificam a regra de links seguros. Todas as outras configurações modificam a política de links seguros associados.
- Quando você remove uma política Cofre Links, a regra de links seguros e a política de links seguros associados são removidas.

No PowerShell do Exchange Online ou no PowerShell do EOP autônomo, a política e a regra são gerenciadas separadamente. Para obter mais informações, consulte a seção Usar Exchange Online PowerShell ou [EOP PowerShell](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies) autônomo para configurar Cofre políticas de Links posteriormente neste artigo.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Do que você precisa saber para começar?

- Abra o portal do Microsoft 365 Defender em <https://security.microsoft.com/>. Para ir diretamente para a página **Cofre Links,** use <https://security.microsoft.com/safelinksv2> .

- Para se conectar ao PowerShell do Exchange Online, confira [Conectar ao PowerShell do Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell). Para se conectar ao EOP PowerShell autônomo, consulte [Conectar-se ao PowerShell do Exchange Online Protection.](/powershell/exchange/connect-to-exchange-online-protection-powershell).

- Você precisa ter permissões atribuídas antes de poder fazer os procedimentos neste artigo:
  - Para criar, modificar e excluir Cofre políticas de Links, você  precisa ser  membro dos grupos de função Gerenciamento da Organização  ou Administrador de Segurança no **portal** Microsoft 365 Defender e membro do grupo de função Gerenciamento da Organização no Exchange Online.
  - Para acesso somente leitura às políticas Cofre Links, você precisa ser membro dos grupos de função Leitor **Global** ou **Leitor de** Segurança.

  Para obter mais informações, consulte [Permissões no portal Microsoft 365 Defender e](permissions-microsoft-365-security-center.md) Permissões no [Exchange Online](/exchange/permissions-exo/permissions-exo).

  > [!NOTE]
  >
  > - Adicionar usuários à função Azure Active Directory correspondente no Centro de administração do Microsoft 365 fornece aos usuários as permissões necessárias no _portal_ Microsoft 365 Defender e permissões para outros recursos no Microsoft 365. Para obter mais informações, confira [Sobre funções de administrador](../../admin/add-users/about-admin-roles.md).
  . - O **grupo de função gerenciamento** de organização somente exibição no [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) também fornece acesso somente leitura ao recurso.

- Para nossas configurações recomendadas para políticas Cofre Links, [consulte Cofre configurações da](recommended-settings-for-eop-and-office365.md#safe-links-policy-settings)política links.

- Permitir até 30 minutos para que uma política nova ou atualizada seja aplicada.

- [Novos recursos estão sendo adicionados continuamente ao Microsoft Defender para](defender-for-office-365.md#new-features-in-microsoft-defender-for-office-365)Office 365 . À medida que novos recursos são adicionados, talvez seja necessário fazer ajustes nas políticas de links Cofre existentes.

## <a name="use-the-microsoft-365-defender-portal-to-create-safe-links-policies"></a>Usar o portal Microsoft 365 Defender para criar políticas Cofre Links

A criação de uma política Cofre links personalizada no portal Microsoft 365 Defender cria a regra de links seguros e a política de links seguros associados ao mesmo tempo usando o mesmo nome para ambos.

1. No portal Microsoft 365 Defender, vá até Políticas & **políticas políticas** de ameaças seção Cofre \>  \>  \> **Links**.

2. Na página **Cofre Links,** clique em ![ Criar ícone ](../../media/m365-cc-sc-create-icon.png) **Criar**.

3. O **assistente de política Cofre Novos Links** é aberto. Na página **Nomear sua política,** configure as seguintes configurações:

   - **Nome**: insira um nome exclusivo e descritivo para a política.
   - **Descrição**: insira uma descrição opcional para a política.

   Ao terminar, clique em **Avançar**.

4. Na página **Usuários e domínios** que aparece, identifique os destinatários internos aos quais a política se aplica (condições de destinatário):
   - **Usuários**: as caixas de correio, os usuários de email, ou os contatos de email especificados na organização.
   - **Grupos**: os grupos de distribuição, os grupos de segurança habilitados para email ou os grupos do Microsoft 365 habilitados na organização.
   - **Domínios**: todos os destinatários nos [domínios aceitos](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) especificados na organização.

   Clique na caixa apropriada, comece a digitar um valor e selecione o valor desejado dos resultados. Repita esse processo quantas vezes for necessário. Para remover uma entrada existente, clique em Remover ![Ícone Remover](../../media/m365-cc-sc-remove-selection-icon.png) ao lado do valor.

   Para usuários ou grupos, você pode usar a maioria dos identificadores (nome, nome de exibição, alias, endereço de email, nome da conta etc.), mas o nome de exibição correspondente será mostrado nos resultados. Para os usuários, insira um asterisco (\*) por si só para ver todos os valores disponíveis.

   Vários valores na mesma condição ou exceção usam a lógica OR (por exemplo, _\<recipient1\>_ ou _\<recipient2\>_). Diferentes condições usam a lógica AND (por exemplo, _\<recipient1\>_ e _\<member of group 1\>_).

   - **Excluir esses usuários, grupos** e domínios : Para adicionar exceções para os destinatários internos aos quais a política se aplica (exceções de destinatário), selecione essa opção e configure as exceções. As configurações e o comportamento são exatamente como as condições.

   Ao terminar, clique em **Avançar**.

5. Na página **Configurações de Proteção** exibida, configure as seguintes configurações:
   - **Selecione a ação para URLs** mal-intencionadas desconhecidas em mensagens : **Selecione** Ativar para habilitar Cofre de links para links em mensagens de email. Se você ativar essa configuração, as seguintes configurações estarão disponíveis:
     - **Aplicar verificação de URL** em tempo real para links suspeitos e links que apontam para arquivos : Selecione essa opção para habilitar a verificação em tempo real de links em mensagens de email. Se você ativar essa configuração na configuração a seguir está disponível:
       - **Aguarde a conclusão da** verificação de URL antes de entregar a mensagem : Selecione essa opção para aguardar a conclusão da verificação de URL em tempo real antes de entregar a mensagem.
     - **Aplicar Cofre Links** para mensagens de email enviadas dentro da organização : Selecione essa opção para aplicar a política Cofre Links para mensagens entre destinatários internos e destinatários internos.
   - **Selecione a ação para URLs desconhecidas** ou potencialmente  mal-intencionadas em Microsoft Teams : Selecione Ativado para habilitar Cofre Proteção de links para links Teams.
   - **Não acompanhar cliques do usuário**: Deixe essa configuração não eleita para habilitar os cliques do usuário de controle em URLs em mensagens de email.
   - **Não permita que os usuários cliquem** na URL original : Selecione essa opção para impedir que os usuários cliquem na URL original em páginas [de aviso.](safe-links.md#warning-pages-from-safe-links)
   - **Não reescreva as SEGUINTES URLs**: Permite acessar as URLs especificadas que, de outra forma, seriam bloqueadas por Cofre Links.

     Na caixa, digite a URL ou o valor que você deseja e clique em **Adicionar**. Repita essa etapa quantas vezes forem necessárias.

     Para remover uma entrada existente, clique em ![Ícone Remover](../../media/m365-cc-sc-remove-selection-icon.png) ao lado da entrada.

     Para a sintaxe de entrada, consulte [Sintaxe de entrada para a lista "Não reescrever as URLs a seguir".](safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list)

   Para obter informações detalhadas sobre essas configurações, consulte [Cofre Configurações](safe-links.md#safe-links-settings-for-email-messages) de Links para mensagens de email e Cofre [Configurações](safe-links.md#safe-links-settings-for-microsoft-teams)de links para Microsoft Teams .

   Para obter mais valores recomendados para configurações de política padrão e estritas, [consulte Cofre Configurações de](recommended-settings-for-eop-and-office365.md#safe-links-policy-settings)política links.

   Ao terminar, clique em **Avançar**.

6. Na página **Notificação** exibida, selecione um dos seguintes valores para **Como você gostaria de notificar seus usuários?**:
   - **Usar o texto de notificação padrão**
   - **Use texto de notificação personalizado**: Se você selecionar esse valor (o comprimento não pode exceder 200 caracteres), as seguintes configurações aparecerão:
     - **Usar Microsoft Translator para localização automática**
     - **Texto de notificação personalizado**: Insira o texto de notificação personalizado nesta caixa.

   Ao terminar, clique em **Avançar**.

7. Na página **Revisão** exibida, revise suas configurações. Você pode selecionar **Editar** em cada seção para modificar as configurações da seção. Ou você pode clicar em **Voltar** ou selecionar a página específica no assistente.

   Quando terminar, clique em **Enviar**.

8. Na mensagem de confirmação exibida, clique em **Concluído**.

## <a name="use-the-microsoft-365-defender-portal-to-view-safe-links-policies"></a>Use o portal Microsoft 365 Defender para exibir Cofre Links

1. No portal Microsoft 365 Defender, vá até Políticas & **políticas políticas** de ameaças seção Cofre \>  \>  \> **Links**.

2. Na página **Cofre Links,** as seguintes propriedades são exibidas na lista de políticas Cofre Links:
   - **Nome**
   - **Status**
   - **Prioridade**

3. Quando você seleciona uma política clicando no nome, as configurações de política são exibidas em um sobrevoo.

## <a name="use-the-microsoft-365-defender-portal-to-modify-safe-links-policies"></a>Usar o portal Microsoft 365 Defender para modificar as políticas Cofre Links

1. No portal Microsoft 365 Defender, vá até Políticas & **políticas políticas** de ameaças seção Cofre \>  \>  \> **Links**.

2. Na página **Cofre Links,** selecione uma política na lista clicando no nome.

3. No submenu de detalhes da política exibido, selecione **Editar** em cada seção para modificar as configurações da seção. Para obter mais informações sobre as configurações, consulte a seção [anterior Usar](#use-the-microsoft-365-defender-portal-to-create-safe-links-policies) o portal Microsoft 365 Defender para criar políticas Cofre Links neste artigo.  

Para habilitar ou desabilitar uma política ou definir a ordem de prioridade da política, consulte as seções a seguir.

### <a name="enable-or-disable-safe-links-policies"></a>Habilitar ou desabilitar Cofre de links

1. No portal Microsoft 365 Defender, acesse **Email & Políticas** de Colaboração & Políticas de Ameaças de Regras seção \>  \>  \> **Políticas** \> **Cofre Links**.

2. Na página **Cofre Links,** selecione uma política na lista clicando no nome.

3. Na parte superior do submenu de detalhes da política exibido, você verá um dos seguintes valores:
   - **Política desativada**: para ativar a política, clique no ![ícone Ativar](../../media/m365-cc-sc-turn-on-off-icon.png) **Ativar** .
   - **Política ativada**: para desativar a política, clique no ![ícone Desativar](../../media/m365-cc-sc-turn-on-off-icon.png) **Desativar**.

4. Na caixa de diálogo de confirmação exibida, clique em **Ativar** ou **Desativar**.

5. Clique em **Fechar** no submenu de detalhes da política.

De volta à página da política principal, o valor **Status** da política será **Ativado** ou **Desativado**.

### <a name="set-the-priority-of-safe-links-policies"></a>Definir a prioridade das políticas Cofre Links

Por padrão, Cofre links recebe uma prioridade baseada na ordem em que foram criados (as políticas mais novas têm prioridade menor do que as políticas mais antigas). Um número de prioridade menor indica uma maior prioridade para a política (0 é a maior), e as políticas são processadas por ordem de prioridade (políticas com maior prioridade são processadas antes das políticas com menor prioridade). Duas políticas não podem ter a mesma prioridade, e o processamento da política será interrompido após a primeira política ser aplicada.

Para alterar a prioridade de uma política, clique em **Aumentar prioridade** ou **Diminuir prioridade** nas propriedades da política (não é possível modificar diretamente o número da **Prioridade** no portal Microsoft 365 Defender). Alterar a prioridade de uma política só faz sentido se você tiver várias políticas.

**Observação**:

- No portal Microsoft 365 Defender, você só pode alterar a prioridade da política Cofre Links após a criação. No PowerShell, você pode substituir a prioridade padrão ao criar a regra de links seguros (que pode afetar a prioridade das regras existentes).
- Cofre As políticas de links são processadas na ordem em que são exibidas (a primeira política tem **o valor Priority** 0). Para obter mais informações sobre a ordem de precedência e como várias políticas são avaliadas e aplicadas, confira [Ordem e precedência da proteção de email](how-policies-and-protections-are-combined.md).

1. No portal Microsoft 365 Defender, acesse **Email & Políticas** de Colaboração & Políticas de Ameaças de Regras seção \>  \>  \> **Políticas** \> **Cofre Links**.

2. Na página **Cofre Links,** selecione uma política na lista clicando no nome.

3. Na parte superior do submenu de detalhes da política exibido, você verá **Aumentar a prioridade** ou **Diminuir a prioridade** com base no valor de prioridade atual e no número de políticas personalizadas:
   - A política com o **valor Priority** **0** tem apenas a **opção Diminuir prioridade** disponível.
   - A política com o menor **valor priority** (por exemplo, **3**) tem apenas a **opção Aumentar** prioridade disponível.
   - Se você tiver três ou mais políticas, as políticas entre os valores de prioridade mais alto e mais baixo terão as opções **Aumentar** prioridade e Diminuir **prioridade** disponíveis.

   Clique no ![ícone Aumentar prioridade](../../media/m365-cc-sc-increase-icon.png) **Aumentar prioridade** ou no ![ícone Diminuir prioridade](../../media/m365-cc-sc-decrease-icon.png) **Diminuir prioridade** para alterar o valor da **Prioridade**.

4. Quando terminar, clique em **Fechar** no submenu de detalhes da política.

## <a name="use-the-microsoft-365-defender-portal-to-remove-safe-links-policies"></a>Usar o portal Microsoft 365 Defender para remover as políticas Cofre Links

1. No portal Microsoft 365 Defender, acesse **Email & Políticas** de Colaboração & Políticas de Ameaças de Regras seção \>  \>  \> **Políticas** \> **Cofre Links**.

2. Na página **Cofre Links,** selecione uma política na lista clicando no nome. Na parte superior do submenu de detalhes da política exibido, clique no ![ícone Mais ações](../../media/m365-cc-sc-more-actions-icon.png) **Mais ações** \> ![ícone Excluir política](../../media/m365-cc-sc-delete-icon.png) **Excluir política**.

3. Na caixa de diálogo de confirmação exibida, clique em **Sim**.

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies"></a>Use Exchange Online PowerShell ou EOP PowerShell autônomo para configurar Cofre links

Conforme descrito anteriormente, uma política Cofre Links consiste em uma política de links seguros e uma regra de links seguros.

No PowerShell, a diferença entre políticas de links seguros e regras de links seguros é aparente. Você gerencia políticas de links seguros usando os cmdlets **\* -SafeLinksPolicy** e gerencia as regras de links seguros usando os cmdlets **\* -SafeLinksRule.**

- No PowerShell, primeiro você cria a política de links seguros e, em seguida, cria a regra de links seguros que identifica a política à que a regra se aplica.
- No PowerShell, você modifica as configurações na política de links seguros e a regra de links seguros separadamente.
- Quando você remove uma política de links seguros do PowerShell, a regra de links seguros correspondente não é removida automaticamente e vice-versa.

### <a name="use-powershell-to-create-safe-links-policies"></a>Usar o PowerShell para criar políticas Cofre Links

Criar uma Cofre de links no PowerShell é um processo de duas etapas:

1. Crie a política de links seguros.
2. Crie a regra de links seguros que especifica a política de links seguros à que a regra se aplica.

> [!NOTE]
>
> - Você pode criar uma nova regra de links seguros e atribuir uma política de links seguros existente e nãossociada a ela. Uma regra de links seguros não pode ser associada a mais de uma política de links seguros.
>
> - Você pode configurar as seguintes configurações em novas políticas de links seguros no PowerShell que não estão disponíveis no portal Microsoft 365 Defender até depois de criar a política:
>   - Crie a nova política como desabilitada (_Habilitado_ `$false` no cmdlet **New-SafeLinksRule).**
>   - Definir a prioridade da política durante a criação (_Prioridade_ _\<Number\>_ ) no cmdlet **New-SafeLinksRule).**
>
> - Uma nova política de links seguros que você cria no PowerShell não fica visível no portal Microsoft 365 Defender até atribuir a política a uma regra de links seguros.

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
- Rastrear cliques do usuário relacionados à proteção de links do Cofre (não estamos usando o parâmetro _DoNotTrackUserClicks_ e o valor padrão é $false, o que significa que os cliques do usuário são rastreados).
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

Não é possível renomear uma política de links seguros no PowerShell (o cmdlet **Set-SafeLinksPolicy** não tem _parâmetro Name)._ Quando você renomea uma política Cofre Links no portal Microsoft 365 Defender, você está renomeando apenas a regra de links _seguros._

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

Habilitar ou desabilitar uma regra de links seguros no PowerShell habilita ou desabilita toda a política Cofre Links (a regra de links seguros e a política de links seguros atribuídos).

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

Para verificar se Cofre links está verificando mensagens, verifique os relatórios disponíveis do Microsoft Defender Office 365. Para obter mais informações, [consulte View reports for Defender for Office 365](view-reports-for-mdo.md) and Use Explorer in the Microsoft 365 Defender [portal](threat-explorer.md).

## <a name="how-do-you-know-these-procedures-worked"></a>Como saber se esses procedimentos funcionaram?

Para verificar se você criou, modificou ou removeu com êxito Cofre políticas de Links, faça qualquer uma das seguintes etapas:

- No portal Microsoft 365 Defender, acesse Políticas & **regras** \> **Políticas de** ameaça Cofre \> **Links**. Verifique a lista de políticas, seus **valores de Status** e seus valores **priority.** Para exibir mais detalhes, selecione a política na lista e veja os detalhes no fly-out.

- Em Exchange Online PowerShell ou Proteção do Exchange Online PowerShell, substitua pelo nome da política ou regra, execute o seguinte comando e verifique \<Name\> as configurações:

  ```PowerShell
  Get-SafeLinksPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-SafeLinksRule -Identity "<Name>"
  ```
