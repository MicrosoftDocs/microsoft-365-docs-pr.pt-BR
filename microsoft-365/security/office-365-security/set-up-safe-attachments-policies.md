---
title: Configurar políticas Cofre anexos no Microsoft Defender para Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 078eb946-819a-4e13-8673-fe0c0ad3a775
ms.collection:
- M365-security-compliance
description: Saiba como definir as Cofre de anexos para proteger sua organização contra arquivos mal-intencionados no email.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e7220140c25ecf457b42514356e41aabdf5481bb
ms.sourcegitcommit: fa9efab24a84f71fec7d001f2ad8949125fa8eee
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/22/2021
ms.locfileid: "53054327"
---
# <a name="set-up-safe-attachments-policies-in-microsoft-defender-for-office-365"></a>Configurar políticas Cofre anexos no Microsoft Defender para Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
- [Plano 1 e plano 2 do Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!IMPORTANT]
> Este artigo se destina a clientes empresariais que possuem o [Microsoft Defender para Office 365](whats-new-in-defender-for-office-365.md). Se você for um usuário de residência procurando informações sobre a verificação de anexos no Outlook, consulte [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).

Cofre Os anexos são um recurso do [Microsoft Defender](whats-new-in-defender-for-office-365.md) para Office 365 que usa um ambiente virtual para verificar anexos em mensagens de email de entrada depois que eles foram verificados pela proteção anti-malware no [Proteção do Exchange Online (EOP),](anti-malware-protection.md)mas antes da entrega aos destinatários. Para obter mais informações, [consulte Cofre Anexos no Microsoft Defender para Office 365](safe-attachments.md).

Não há política de anexos interna ou Cofre padrão. Para obter Cofre de Anexos de anexos de mensagem de email, você precisa criar uma ou mais Cofre políticas de anexos, conforme descrito neste artigo.

Você pode configurar políticas de anexos do Cofre no portal do Microsoft 365 Defender ou no PowerShell (Exchange Online PowerShell para organizações de Microsoft 365 qualificadas com caixas de correio no Exchange Online; EOP PowerShell autônomo para organizações sem caixas de correio Exchange Online, mas com o Defender para assinaturas de complemento de Office 365).

Os elementos básicos de uma política Cofre Attachments são:

- A **política** de anexo seguro : especifica as ações para detecções de malware desconhecidas, se o envio de mensagens com anexos de malware para um endereço de email especificado e se a entrega de mensagens se Cofre verificação de anexos não puder ser concluída.
- **A regra de anexo seguro**: especifica a prioridade e os filtros de destinatário (a quem a política se aplica).

A diferença entre esses dois elementos não é óbvia quando você gerencia Cofre políticas de anexos no portal Microsoft 365 Defender:

- Quando você cria uma política de Cofre de anexos, você está realmente criando uma regra de anexo seguro e a política de anexo segura associada ao mesmo tempo usando o mesmo nome para ambos.
- Quando você modifica uma Cofre de anexos, as configurações relacionadas ao nome, prioridade, habilitado ou desabilitado e filtros de destinatário modificam a regra de anexo seguro. Todas as outras configurações modificam a política de anexo seguro associada.
- Quando você remove uma Cofre de anexos, a regra de anexo seguro e a política de anexo seguro associada são removidas.

No PowerShell do Exchange Online ou no PowerShell do EOP autônomo, a política e a regra são gerenciadas separadamente. Para obter mais informações, consulte a seção Usar Exchange Online PowerShell ou [EOP PowerShell](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-attachments-policies) autônomo para configurar Cofre políticas de anexos posteriormente neste artigo.

> [!NOTE]
> Na área de configurações globais de Cofre De anexos, você configura recursos que não dependem de políticas Cofre Anexos. Para obter instruções, consulte Ativar Cofre anexos para [SharePoint, OneDrive e Microsoft Teams](turn-on-mdo-for-spo-odb-and-teams.md) e Cofre documentos [Microsoft 365 E5](safe-docs.md).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Do que você precisa saber para começar?

- Abra o portal do Microsoft 365 Defender em <https://security.microsoft.com>. Para ir diretamente para a página **Cofre Anexos,** use <https://security.microsoft.com/safeattachmentv2> .

- Para se conectar ao PowerShell do Exchange Online, confira [Conectar ao PowerShell do Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell). Para se conectar ao EOP PowerShell autônomo, consulte [Conectar-se ao PowerShell do Exchange Online Protection.](/powershell/exchange/connect-to-exchange-online-protection-powershell).

- Você precisa de permissões antes de poder fazer os procedimentos neste artigo:
  - Para criar, modificar e excluir Cofre de anexos, você precisa  ser membro  dos grupos de função Gerenciamento da Organização ou  Administrador de Segurança no **portal** Microsoft 365 Defender e membro do grupo de função Gerenciamento da Organização no Exchange Online.
  - Para acessar somente leitura Cofre políticas de Anexos, você precisa ser  membro dos grupos de função Leitor **Global** ou Leitor de Segurança no portal Microsoft 365 Defender.

  Para obter mais informações, consulte [Permissões no portal Microsoft 365 Defender e](permissions-microsoft-365-security-center.md) Permissões no [Exchange Online](/exchange/permissions-exo/permissions-exo).

  **Observações**:

  - Adicionar usuários à função Azure Active Directory correspondente no Centro de administração do Microsoft 365 fornece aos usuários as permissões necessárias no _portal_ Microsoft 365 Defender e permissões para outros recursos no Microsoft 365. Para obter mais informações, confira o artigo [Sobre funções de administrador](../../admin/add-users/about-admin-roles.md).
  - O grupo de função **Gerenciamento de Organização Somente para Exibição** no [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) também fornece acesso somente leitura ao recurso.

- Para nossas configurações recomendadas para Cofre de anexos, [consulte Cofre Configurações de anexos](recommended-settings-for-eop-and-office365.md#safe-attachments-settings).

- Permitir até 30 minutos para que uma política nova ou atualizada seja aplicada.

## <a name="use-the-microsoft-365-defender-portal-to-create-safe-attachments-policies"></a>Usar o portal Microsoft 365 Defender para criar Cofre de anexos

A criação de uma política Cofre anexos personalizados no portal Microsoft 365 Defender cria a regra de anexo seguro e a política de anexo seguro associada ao mesmo tempo usando o mesmo nome para ambos.

1. No portal Microsoft 365 Defender, vá para **Email & políticas** de colaboração & políticas de ameaça seção Políticas de ameaças \>  \>  \>  \> **Cofre Anexos**.

2. Na página **Cofre Anexos,** clique em ![ Criar ícone ](../../media/m365-cc-sc-create-icon.png) **Criar**.

3. O assistente de política é aberto. Na página **Nomear sua política,** configure as seguintes configurações:
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

   - **Excluir estes usuários, grupos e domínios**: para adicionar exceções para os destinatários internos aos quais a política se aplica (exceções de destinatários), selecione essa opção e configure as exceções. As configurações e o comportamento são exatamente como as condições.

   Ao terminar, clique em **Avançar**.

5. Na página **Configurações,** configure as seguintes configurações:

   - Cofre resposta de **malware desconhecido anexos**: selecione um dos seguintes valores:
     - **Off**: Normalmente, não recomendamos esse valor.
     - **Monitorar**
     - **Bloquear**: esse é o valor padrão e o valor recomendado em Políticas de segurança predefinidas padrão [e estritas.](preset-security-policies.md)
     - **Replace**
     - **Entrega Dinâmica (Recurso de Visualização)**

     Esses valores são explicados [Cofre configurações de política de anexos.](safe-attachments.md#safe-attachments-policy-settings)

   - Redirecionar mensagens com **anexos detectados**: se você selecionar Habilitar redirecionamento, poderá especificar um endereço de email na caixa Enviar mensagens que contenham **anexos bloqueados, monitorados** ou substituídos na caixa de endereços de email especificado para enviar mensagens que contenham anexos de malware para análise e investigação.

     A recomendação para configurações de política padrão e estrita é habilitar o redirecionamento. Para obter mais informações, [consulte Cofre Configurações de anexos](recommended-settings-for-eop-and-office365.md#safe-attachments-settings).

   - Aplique a resposta de detecção de **anexos** do Cofre se a verificação não puder ser concluída (tempo de conclusão ou erros) : a ação especificada pelo **Cofre Anexos** resposta de malware desconhecido é tomada em mensagens mesmo quando Cofre verificação de Anexos não pode ser concluída. Se você selecionou essa opção, selecione Sempre **Habilitar redirecionamento** e especificar um endereço de email para enviar mensagens que contenham anexos de malware. Caso contrário, as mensagens podem ser perdidas.

   Ao terminar, clique em **Avançar**.

6. Na página **Revisão** exibida, revise suas configurações. Você pode selecionar **Editar** em cada seção para modificar as configurações da seção. Ou você pode clicar em **Voltar** ou selecionar a página específica no assistente.

   Quando terminar, clique em **Enviar**.

7. Na mensagem de confirmação exibida, clique em **Concluído**.

## <a name="use-the-microsoft-365-defender-portal-to-view-safe-attachments-policies"></a>Use o portal Microsoft 365 Defender para exibir Cofre de anexos

1. No portal Microsoft 365 Defender, vá para **Email & políticas** de colaboração & políticas de ameaça seção Políticas de ameaças \>  \>  \>  \> **Cofre Anexos**.

2. Na página **Cofre Anexos,** as seguintes propriedades são exibidas na lista de políticas:
   - **Nome**
   - **Status**
   - **Prioridade**

3. Quando você seleciona uma política clicando no nome, as configurações de política são exibidas em um sobrevoo.

## <a name="use-the-microsoft-365-defender-portal-to-modify-safe-attachments-policies"></a>Usar o portal Microsoft 365 Defender para modificar Cofre de anexos

1. No portal Microsoft 365 Defender, vá para **Email & políticas** de colaboração & políticas de ameaça seção Políticas de ameaças \>  \>  \>  \> **Cofre Anexos**.

2. Na página **Cofre Anexos,** selecione uma política na lista clicando no nome.

3. No submenu de detalhes da política exibido, selecione **Editar** em cada seção para modificar as configurações da seção. Para obter mais informações sobre as configurações, consulte a seção Usar o portal Microsoft 365 Defender para criar Cofre [de anexos](#use-the-microsoft-365-defender-portal-to-create-safe-attachments-policies) anteriormente neste artigo.  

Para habilitar ou desabilitar uma política ou definir a ordem de prioridade da política, consulte as seções a seguir.

### <a name="enable-or-disable-safe-attachments-policies"></a>Habilitar ou desabilitar Cofre de anexos

1. No portal Microsoft 365 Defender, vá para **Email & políticas** de colaboração & políticas de ameaça seção Políticas de ameaças \>  \>  \>  \> **Cofre Anexos**.

2. Na página **Cofre Anexos,** selecione uma política na lista clicando no nome.

3. Na parte superior do submenu de detalhes da política exibido, você verá um dos seguintes valores:
   - **Política desativada**: para ativar a política, clique no ![ícone Ativar](../../media/m365-cc-sc-turn-on-off-icon.png) **Ativar** .
   - **Política ativada**: para desativar a política, clique no ![ícone Desativar](../../media/m365-cc-sc-turn-on-off-icon.png) **Desativar**.

4. Na caixa de diálogo de confirmação exibida, clique em **Ativar** ou **Desativar**.

5. Clique em **Fechar** no submenu de detalhes da política.

De volta à página da política principal, o valor **Status** da política será **Ativado** ou **Desativado**.

### <a name="set-the-priority-of-safe-attachments-policies"></a>Definir a prioridade das políticas de Cofre Anexos

Por padrão, Cofre de anexos recebe uma prioridade baseada na ordem em que foram criadas (as políticas mais novas têm prioridade menor do que as políticas mais antigas). Um número de prioridade menor indica uma maior prioridade para a política (0 é a maior), e as políticas são processadas por ordem de prioridade (políticas com maior prioridade são processadas antes das políticas com menor prioridade). Duas políticas não podem ter a mesma prioridade, e o processamento da política será interrompido após a primeira política ser aplicada.

Para obter mais informações sobre a ordem de precedência e como várias políticas são avaliadas e aplicadas, confira [Ordem e precedência da proteção de email](how-policies-and-protections-are-combined.md).

Cofre As políticas de anexos são exibidas na ordem em que são processadas (a primeira política tem o **valor Priority** 0).

**Observação**: no portal Microsoft 365 Defender, você só pode alterar a prioridade da política Cofre Anexos após a criação. No PowerShell, você pode substituir a prioridade padrão ao criar a regra de anexo seguro (que pode afetar a prioridade das regras existentes).

Para alterar a prioridade de uma política, clique em **Aumentar prioridade** ou **Diminuir prioridade** nas propriedades da política (não é possível modificar diretamente o número da **Prioridade** no portal Microsoft 365 Defender). Alterar a prioridade de uma política só faz sentido se você tiver várias políticas.

1. No portal Microsoft 365 Defender, vá para **Email & políticas** de colaboração & políticas de ameaça seção Políticas de ameaças \>  \>  \>  \> **Cofre Anexos**.

2. Na página **Cofre Anexos,** selecione uma política na lista clicando no nome.

3. Na parte superior do sobremenu de detalhes  da política  exibido, você verá Aumentar prioridade ou Diminuir prioridade com base no valor de prioridade atual e no número de políticas:
   - A política com o **valor Priority** **0** tem apenas a **opção Diminuir prioridade** disponível.
   - A política com o menor **valor priority** (por exemplo, **3**) tem apenas a **opção Aumentar** prioridade disponível.
   - Se você tiver três ou mais políticas, as políticas entre os valores de prioridade mais alto e mais baixo terão as opções **Aumentar** prioridade e Diminuir **prioridade** disponíveis.

   Clique no ![ícone Aumentar prioridade](../../media/m365-cc-sc-increase-icon.png) **Aumentar prioridade** ou no ![ícone Diminuir prioridade](../../media/m365-cc-sc-decrease-icon.png) **Diminuir prioridade** para alterar o valor da **Prioridade**.

4. Quando terminar, clique em **Fechar** no submenu de detalhes da política.

## <a name="use-the-microsoft-365-defender-portal-to-remove-safe-attachments-policies"></a>Use o portal Microsoft 365 Defender para remover Cofre de anexos

1. No portal Microsoft 365 Defender, vá para **Email & políticas** de colaboração & políticas de ameaça seção Políticas de ameaças \>  \>  \>  \> **Cofre Anexos**.

2. Na página **Cofre Anexos,** selecione uma política personalizada na lista clicando no nome da política.

3. Na parte superior do submenu de detalhes da política exibido, clique no ![ícone Mais ações](../../media/m365-cc-sc-more-actions-icon.png) **Mais ações** \> ![ícone Excluir política](../../media/m365-cc-sc-delete-icon.png) **Excluir política**.

4. Na caixa de diálogo de confirmação exibida, clique em **Sim**.

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-attachments-policies"></a>Use Exchange Online PowerShell ou EOP PowerShell autônomo para configurar Cofre de anexos

Conforme descrito anteriormente, uma política Cofre Attachments consiste em uma política de anexo seguro e uma regra de anexo seguro.

No PowerShell, a diferença entre políticas de anexo seguro e regras de anexo seguro é aparente. Você gerencia políticas de anexo seguro usando os cmdlets **\* -SafeAttachmentPolicy** e gerencia regras de anexo segura usando os cmdlets **\* -SafeAttachmentRule.**

- No PowerShell, primeiro você cria a política de anexo seguro e, em seguida, cria a regra de anexo seguro que identifica a política à qual a regra se aplica.
- No PowerShell, você modifica as configurações na política de anexo seguro e a regra de anexo seguro separadamente.
- Quando você remove uma política de anexo seguro do PowerShell, a regra de anexo seguro correspondente não é removida automaticamente e vice-versa.

### <a name="use-powershell-to-create-safe-attachments-policies"></a>Usar o PowerShell para criar Cofre de anexos

Criar uma Cofre de anexos no PowerShell é um processo de duas etapas:

1. Crie a política de anexo seguro.
2. Crie a regra de anexo seguro que especifica a política de anexo seguro à qual a regra se aplica.

 **Observações**:

- Você pode criar uma nova regra de anexo seguro e atribuir uma política de anexo seguro existente e nãossociada a ela. Uma regra de anexo seguro não pode ser associada a mais de uma política de anexo seguro.

- Você pode definir as seguintes configurações em novas políticas de anexo seguro no PowerShell que não estão disponíveis no portal Microsoft 365 Defender até depois de criar a política:
  - Crie a nova política como desabilitada (_Habilitado_ `$false` no cmdlet **New-SafeAttachmentRule).**
  - Definir a prioridade da política durante a criação (_Prioridade_ _\<Number\>_ ) no cmdlet **New-SafeAttachmentRule).**

- Uma nova política de anexo seguro que você cria no PowerShell não fica visível no portal Microsoft 365 Defender até que você atribua a política a uma regra de anexo seguro.

#### <a name="step-1-use-powershell-to-create-a-safe-attachment-policy"></a>Etapa 1: Usar o PowerShell para criar uma política de anexo seguro

Para criar uma política de anexo seguro, use esta sintaxe:

```PowerShell
New-SafeAttachmentPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-Action <Allow | Block | Replace | DynamicDelivery>] [-Redirect <$true | $false>] [-RedirectAddress <SMTPEmailAddress>] [-ActionOnError <$true | $false>]
```

Este exemplo cria uma política de anexo seguro chamada Contoso All com os seguintes valores:

- Bloquear mensagens que são encontradas para conter malware Cofre verificação de documentos (não estamos usando o parâmetro _Action_ e o valor padrão é `Block` ).
- O redirecionamento está habilitado e as mensagens que são encontradas com malware são enviadas sec-ops@contoso.com análise e investigação.
- Se Cofre verificação de anexos não estiver disponível ou encontrar erros, não entregue a mensagem (não estamos usando o parâmetro _ActionOnError_ e o valor padrão é `$true` ).

```PowerShell
New-SafeAttachmentPolicy -Name "Contoso All" -Redirect $true -RedirectAddress sec-ops@contoso.com
```

Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [New-SafeAttachmentPolicy](/powershell/module/exchange/new-safeattachmentpolicy).

#### <a name="step-2-use-powershell-to-create-a-safe-attachment-rule"></a>Etapa 2: Usar o PowerShell para criar uma regra de anexo seguro

Para criar uma regra de anexo seguro, use esta sintaxe:

```PowerShell
New-SafeAttachmentRule -Name "<RuleName>" -SafeAttachmentPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"] [-Enabled <$true | $false>]
```

Este exemplo cria uma regra de anexo segura chamada Contoso All com as seguintes condições:

- A regra é associada à política de anexo seguro chamada Contoso All.
- A regra se aplica a todos os destinatários no contoso.com domínio.
- Como não estamos usando o parâmetro _Priority,_ a prioridade padrão é usada.
- A regra está habilitada (não estamos usando o parâmetro _Enabled_ e o valor padrão é `$true` ).

```powershell
New-SafeAttachmentRule -Name "Contoso All" -SafeAttachmentPolicy "Contoso All" -RecipientDomainIs contoso.com
```

Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [New-SafeAttachmentRule](/powershell/module/exchange/new-safeattachmentrule).

### <a name="use-powershell-to-view-safe-attachment-policies"></a>Usar o PowerShell para exibir políticas de anexo seguro

Para exibir políticas de anexo seguras existentes, use a seguinte sintaxe:

```PowerShell
Get-SafeAttachmentPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

Este exemplo retorna uma lista resumida de todas as políticas de anexo seguro.

```PowerShell
Get-SafeAttachmentPolicy
```

Este exemplo retorna informações detalhadas para a política de anexo seguro chamada Contoso Executives.

```PowerShell
Get-SafeAttachmentPolicy -Identity "Contoso Executives" | Format-List
```

Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Get-SafeAttachmentPolicy](/powershell/module/exchange/get-safeattachmentpolicy).

### <a name="use-powershell-to-view-safe-attachment-rules"></a>Usar o PowerShell para exibir regras de anexo seguro

Para exibir as regras de anexo seguro existentes, use a seguinte sintaxe:

```PowerShell
Get-SafeAttachmentRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled>] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

Este exemplo retorna uma lista resumida de todas as regras de anexo seguro.

```PowerShell
Get-SafeAttachmentRule
```

Para filtrar a lista por regras habilitadas ou desabilitadas, execute os seguintes comandos:

```PowerShell
Get-SafeAttachmentRule -State Disabled
```

```PowerShell
Get-SafeAttachmentRule -State Enabled
```

Este exemplo retorna informações detalhadas para a regra de anexo seguro chamada Contoso Executives.

```PowerShell
Get-SafeAttachmentRule -Identity "Contoso Executives" | Format-List
```

Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Get-SafeAttachmentRule](/powershell/module/exchange/get-safeattachmentrule).

### <a name="use-powershell-to-modify-safe-attachment-policies"></a>Usar o PowerShell para modificar políticas de anexo seguro

Não é possível renomear uma política de anexo seguro no PowerShell (o cmdlet **Set-SafeAttachmentPolicy** não tem _parâmetro Name)._ Ao renomear uma política Cofre Anexos no portal Microsoft 365 Defender, você só está renomeando a regra de anexo _seguro._

Caso contrário, as mesmas configurações estarão disponíveis quando você criar uma política de anexo seguro, conforme descrito na Etapa [1: Usar](#step-1-use-powershell-to-create-a-safe-attachment-policy) o PowerShell para criar uma seção de política de anexo seguro anteriormente neste artigo.

Para modificar uma política de anexo seguro, use esta sintaxe:

```PowerShell
Set-SafeAttachmentPolicy -Identity "<PolicyName>" <Settings>
```

Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Set-SafeAttachmentPolicy](/powershell/module/exchange/set-safeattachmentpolicy).

### <a name="use-powershell-to-modify-safe-attachment-rules"></a>Usar o PowerShell para modificar regras de anexo seguras

A única configuração que não está disponível quando você modifica uma regra de anexo seguro no PowerShell é o parâmetro _Enabled_ que permite criar uma regra desabilitada. Para habilitar ou desabilitar as regras de anexo segura existentes, consulte a próxima seção.

Caso contrário, as mesmas configurações estarão disponíveis quando você criar uma regra conforme descrito na Etapa [2: Use](#step-2-use-powershell-to-create-a-safe-attachment-rule) o PowerShell para criar uma seção de regra de anexo seguro anteriormente neste artigo.

Para modificar uma regra de anexo seguro, use esta sintaxe:

```PowerShell
Set-SafeAttachmentRule -Identity "<RuleName>" <Settings>
```

Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Set-SafeAttachmentRule](/powershell/module/exchange/set-safeattachmentrule).

### <a name="use-powershell-to-enable-or-disable-safe-attachment-rules"></a>Usar o PowerShell para habilitar ou desabilitar regras de anexo seguro

Habilitar ou desabilitar uma regra de anexo seguro no PowerShell habilita ou desabilita toda a política Cofre Anexos do Cofre (a regra de anexo seguro e a política de anexo seguro atribuída).

Para habilitar ou desabilitar uma regra de anexo seguro no PowerShell, use esta sintaxe:

```PowerShell
<Enable-SafeAttachmentRule | Disable-SafeAttachmentRule> -Identity "<RuleName>"
```

Este exemplo desabilita a regra de anexo seguro chamada Departamento de Marketing.

```PowerShell
Disable-SafeAttachmentRule -Identity "Marketing Department"
```

Este exemplo habilita a mesma regra.

```PowerShell
Enable-SafeAttachmentRule -Identity "Marketing Department"
```

Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Enable-SafeAttachmentRule](/powershell/module/exchange/enable-safeattachmentrule) e [Disable-SafeAttachmentRule](/powershell/module/exchange/disable-safeattachmentrule).

### <a name="use-powershell-to-set-the-priority-of-safe-attachment-rules"></a>Usar o PowerShell para definir a prioridade das regras de anexo seguro

O valor mais alto de prioridade que pode ser definido em uma regra é 0. O valor mais baixo que pode ser definido depende do número de regras. Por exemplo, se você tiver cinco regras, use os valores de prioridade de 0 a 4. Alterar a prioridade de uma regra existente pode ter um efeito cascata em outras regras. Por exemplo, se você tiver cinco regras personalizadas (prioridades de 0 a 4) e alterar a prioridade de uma regra para 2, a regra existente com prioridade 2 será alterada para a prioridade 3, e a regra com prioridade 3 será alterada para prioridade 4.

Para definir a prioridade de uma regra de anexo seguro no PowerShell, use a seguinte sintaxe:

```PowerShell
Set-SafeAttachmentRule -Identity "<RuleName>" -Priority <Number>
```

Este exemplo define a prioridade da regra chamada Marketing Department como 2. Todas as regras existentes com prioridade inferior ou igual a 2 são reduzidas por 1 (seus números de prioridade são aumentados por 1).

```PowerShell
Set-SafeAttachmentRule -Identity "Marketing Department" -Priority 2
```

**Observação**: para definir a prioridade de uma nova regra ao criar, use o parâmetro _Priority_ no cmdlet **New-SafeAttachmentRule.**

Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Set-SafeAttachmentRule](/powershell/module/exchange/set-safeattachmentrule).

### <a name="use-powershell-to-remove-safe-attachment-policies"></a>Usar o PowerShell para remover políticas de anexo seguro

Quando você usa o PowerShell para remover uma política de anexo seguro, a regra de anexo seguro correspondente não é removida.

Para remover uma política de anexo seguro no PowerShell, use esta sintaxe:

```PowerShell
Remove-SafeAttachmentPolicy -Identity "<PolicyName>"
```

Este exemplo remove a política de anexo seguro chamada Departamento de Marketing.

```PowerShell
Remove-SafeAttachmentPolicy -Identity "Marketing Department"
```

Para obter informações detalhadas sobre sintaxes e parâmetros, [consulte Remove-SafeAttachmentPolicy](/powershell/module/exchange/remove-safeattachmentpolicy).

### <a name="use-powershell-to-remove-safe-attachment-rules"></a>Usar o PowerShell para remover regras de anexo seguro

Quando você usa o PowerShell para remover uma regra de anexo seguro, a política de anexo seguro correspondente não é removida.

Para remover uma regra de anexo seguro no PowerShell, use esta sintaxe:

```PowerShell
Remove-SafeAttachmentRule -Identity "<PolicyName>"
```

Este exemplo remove a regra de anexo seguro chamada Departamento de Marketing.

```PowerShell
Remove-SafeAttachmentRule -Identity "Marketing Department"
```

Para obter informações detalhadas sobre sintaxes e parâmetros, [consulte Remove-SafeAttachmentRule](/powershell/module/exchange/remove-safeattachmentrule).

## <a name="how-do-you-know-these-procedures-worked"></a>Como saber se esses procedimentos funcionaram?

Para verificar se você criou, modificou ou removeu com êxito Cofre políticas de Anexos, faça qualquer uma das seguintes etapas:

- No portal Microsoft 365 Defender, vá para **Email & políticas** de colaboração & políticas de ameaça seção Políticas de ameaças \>  \>  \>  \> **Cofre Anexos**. Verifique a lista de políticas, seus **valores de Status** e seus valores **priority.** Para exibir mais detalhes, selecione a política na lista clicando no nome e exibindo os detalhes no fly-out.

- Em Exchange Online PowerShell ou Proteção do Exchange Online PowerShell, substitua pelo nome da política ou regra, execute o seguinte comando e verifique \<Name\> as configurações:

  ```PowerShell
  Get-SafeAttachmentPolicy -Identity "<Name>" | Format-List
  ```

  ```PowerShell
  Get-SafeAttachmentRule -Identity "<Name>" | Format-List
  ```

Para verificar se Cofre anexos está verificando mensagens, verifique o Defender disponível para Office 365 relatórios. Para obter mais informações, [consulte View reports for Defender for Office 365](view-reports-for-mdo.md) and Use Explorer in the Microsoft 365 Defender [portal](threat-explorer.md).
