---
title: Configurar políticas de Anexos Seguros no Microsoft Defender para Office 365
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
description: Saiba mais sobre como definir políticas de Anexos seguros para proteger sua organização contra arquivos mal-intencionados no email.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 5a26d214fe99d0053bf178d7d85a0b526d64f887
ms.sourcegitcommit: cbe8724bd71d1c002395d98f1451c5f578c824f9
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/26/2021
ms.locfileid: "49988075"
---
# <a name="set-up-safe-attachments-policies-in-microsoft-defender-for-office-365"></a>Configurar políticas de Anexos Seguros no Microsoft Defender para Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

> [!IMPORTANT]
> Este artigo se destina a clientes empresariais que possuem o [Microsoft Defender para Office 365](office-365-atp.md). Se você for um usuário de residência procurando informações sobre a verificação de anexos no Outlook, consulte [Advanced Outlook.com security.](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)

Anexos Seguros é um recurso do [Microsoft Defender para Office 365](office-365-atp.md) que usa um ambiente virtual para verificar anexos em mensagens de email de entrada depois que eles são verificados pela proteção anti-malware no Proteção do Exchange Online [(EOP),](anti-malware-protection.md)mas antes da entrega aos destinatários. Para obter mais informações, consulte [Anexos seguros no Microsoft Defender para Office 365.](atp-safe-attachments.md)

Não há nenhuma política de Anexos Seguros interna ou padrão. Para obter a verificação de Anexos Seguros de anexos de mensagens de email, você precisa criar uma ou mais políticas de Anexos Seguros, conforme descrito neste artigo.

Você pode configurar políticas de Anexos Seguros no Centro de Conformidade e Segurança ou no PowerShell (PowerShell do Exchange Online para organizações qualificadas do Microsoft 365 com caixas de correio no Exchange Online; PowerShell do EOP autônomo para organizações sem caixas de correio do Exchange Online, mas com assinaturas de complemento do Defender para Office 365). &

Os elementos básicos de uma política de Anexos Seguros são:

- A política de anexo **seguro:** especifica as ações para detecções de malware desconhecidas, se é para enviar mensagens com anexos de malware para um endereço de email especificado e se a verificação de Anexos Seguros não pode ser concluída.
- **A regra de anexo seguro:** especifica os filtros de prioridade e destinatário (a quem a política se aplica).

A diferença entre esses dois elementos não é óbvia quando você gerencia as política de Anexos seguros no Centro de Conformidade & e Segurança:

- Ao criar uma política de Anexos Seguros, você está criando uma regra de anexo seguro e a política de anexo seguro associada ao mesmo tempo usando o mesmo nome para ambos.
- Quando você modifica uma política de Anexos Seguros, as configurações relacionadas ao nome, prioridade, habilitada ou desabilitada e filtros de destinatário modificam a regra de anexo seguro. Todas as outras configurações modificam a política de anexo seguro associada.
- Quando você remove uma política de Anexos Seguros, a regra de anexo seguro e a política de anexo seguro associada são removidas.

No PowerShell do Exchange Online ou no PowerShell do EOP autônomo, a política e a regra são gerenciadas separadamente. Para obter mais informações, consulte a seção Usar o PowerShell do Exchange Online ou [do EOP PowerShell](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-attachments-policies) autônomo para configurar políticas de Anexos seguros posteriormente neste artigo.

> [!NOTE]
> Na área de configurações globais das configurações de Anexos Seguros, você configura recursos que não dependem de políticas de Anexos Seguros. Para obter instruções, confira Ativar Anexos Seguros para [SharePoint, OneDrive](turn-on-atp-for-spo-odb-and-teams.md) e Microsoft Teams e Documentos Seguros no [Microsoft 365 E5.](safe-docs.md)

## <a name="what-do-you-need-to-know-before-you-begin"></a>O que você precisa saber antes de começar?

- Você abrir o Centro de conformidade e segurança em <https://protection.office.com/>. Para ir diretamente para a **página Anexos Seguros,** use <https://protection.office.com/safeattachmentv2> .

- Para se conectar ao PowerShell do Exchange Online, confira [Conectar ao PowerShell do Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell). Para se conectar ao EOP PowerShell autônomo, consulte [Conectar-se ao PowerShell do Exchange Online Protection.](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).

- Para fazer os procedimentos deste artigo, você precisa ter permissões:
  - Para criar, modificar e excluir políticas de Links seguros  &,  você precisa ser membro dos grupos de  função Gerenciamento  da Organização ou Administrador de Segurança no Centro de Conformidade e Segurança e membro do grupo de funções Gerenciamento da Organização no Exchange Online.
  - Para acesso somente leitura às políticas de Links seguros, você  precisa ser membro dos grupos de função Leitor & **Global** ou Leitor de Segurança no Centro de Conformidade e Segurança.

  Para obter mais informações, [consulte Permissões no Centro de conformidade e & segurança](permissions-in-the-security-and-compliance-center.md) no Exchange [Online.](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo)

  **Observações**:

  - Adicionar usuários à função correspondente do Azure Active Directory no Centro de administração do Microsoft 365 fornece aos usuários as permissões necessárias no Centro de Segurança e Conformidade _e_ permissões para outros recursos no Microsoft 365. Para obter mais informações, confira o artigo [Sobre funções de administrador](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).
  - O grupo de função **Gerenciamento de Organização Somente para Exibição** no [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) também fornece acesso somente leitura ao recurso.

- Para nossas configurações recomendadas para políticas de Anexos Seguros, consulte [configurações de Anexos Seguros.](recommended-settings-for-eop-and-office365-atp.md#safe-attachments-settings)

- Permita até 30 minutos para que uma política nova ou atualizada seja aplicada.

## <a name="use-the-security--compliance-center-to-create-safe-attachments-policies"></a>Usar o Centro de Conformidade & segurança para criar políticas de Anexos seguros

Criar uma política de Anexo & s Seguros personalizada no Centro de Conformidade e Segurança cria a regra de anexo seguro e a política de anexo seguro associada ao mesmo tempo usando o mesmo nome para ambos.

1. No Centro de Conformidade & Segurança, vá para **Anexos** Seguros da ATP da Política \>  \> **de Gerenciamento de Ameaças.**

2. Na página **Anexos Seguros,** clique em **Criar**.

3. O **assistente nova política de Anexos seguros** é aberto. Na página **Nomear sua política,** de configure as seguintes configurações:

   - **Nome**: insira um nome exclusivo e descritivo para a política.

   - **Descrição**: digite uma descrição opcional para a política.

   Quando terminar, clique em **Avançar**.

4. Na página **Configurações** exibida, de configure as seguintes configurações:

   - **Resposta de malware desconhecido anexos seguros:** selecione um dos seguintes valores:

     - **Off**: Normalmente, não recomendamos esse valor.
     - **Monitorar**
     - **Block:** este é o valor padrão e o valor recomendado nas políticas de segurança predefinidas Padrão [e Estrito.](preset-security-policies.md)
     - **Replace**
     - **Entrega Dinâmica (Recurso de Visualização)**

     Esses valores são explicados nas [configurações de política de Anexos seguros.](atp-safe-attachments.md#safe-attachments-policy-settings)

   - Envie o anexo para o seguinte endereço de  **email:** para os valores de ação **Bloquear**, **Monitorar** ou Substituir , você pode selecionar Habilitar redirecionamento para enviar mensagens que contenham anexos de malware para o endereço de email interno ou externo especificado para análise e investigação. 

     A recomendação para as configurações de política Padrão e Estrito é habilitar o redirecionamento. Para obter mais informações, consulte [configurações de Anexos seguros.](recommended-settings-for-eop-and-office365-atp.md#safe-attachments-settings)

   - Aplique a seleção acima se a verificação de anexos de **malware esgoter** ou ocorrer um erro: a ação especificada pela resposta de malware desconhecido **anexos** seguros é tomada em mensagens, mesmo quando a verificação de Anexos seguros não puder ser concluída. Se você selecionou essa opção, sempre selecione **Redirecionamento habilitado.** Caso contrário, as mensagens podem ser perdidas.

   Quando terminar, clique em **Avançar**.

5. Na página **Aplicado a** que aparece, identifique os destinatários internos aos quais a política se aplica.

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

6. Na página **Revisar as configurações** exibida, revise as configurações. Você pode clicar **em Editar** em cada configuração para modificá-la.

   Quando terminar, clique em **Concluir.**

## <a name="use-the-security--compliance-center-to-view-safe-attachments-policies"></a>Usar o Centro de Conformidade & segurança para exibir políticas de Anexos seguros

1. No Centro de Conformidade & Segurança, vá para **Anexos** Seguros da ATP da Política \>  \> **de Gerenciamento de Ameaças.**

2. Na página **Anexos Seguros,** selecione uma política na lista e clique nele (não marque a caixa de seleção).

   Os detalhes da política aparecem em um fly out

## <a name="use-the-security--compliance-center-to-modify-safe-attachments-policies"></a>Usar o Centro de Conformidade & Segurança para modificar políticas de Anexos Seguros

1. No Centro de Conformidade & Segurança, vá para **Anexos** Seguros da ATP da Política \>  \> **de Gerenciamento de Ameaças.**

2. Na página **Anexos Seguros,** selecione uma política na lista e clique nele (não marque a caixa de seleção).

3. Nos detalhes da política exibidos, clique em **Editar política.**

As configurações disponíveis no & menu explicativo exibido são idênticas às descritas na seção Usar o Centro de Conformidade e Segurança para criar políticas de [Anexos seguros.](#use-the-security--compliance-center-to-create-safe-attachments-policies)

Para habilitar ou desabilitar uma política ou definir a ordem de prioridade da política, consulte as seções a seguir.

### <a name="enable-or-disable-safe-attachments-policies"></a>Habilitar ou desabilitar políticas de Anexos Seguros

1. No Centro de Conformidade & Segurança, vá para **Anexos** Seguros da ATP da Política \>  \> **de Gerenciamento de Ameaças.**

2. Observe o valor na coluna **Status:**

   - Mover o alternância para a esquerda ![Desativar política](../../media/scc-toggle-off.png) para desabilitar a política.

   - Mover o alternância para a direita ![Ativar a política](../../media/scc-toggle-on.png) para habilitar a política.

### <a name="set-the-priority-of-safe-attachments-policies"></a>Definir a prioridade das políticas de Anexos Seguros

Por padrão, as políticas de Anexos Seguros têm uma prioridade baseada na ordem em que foram criadas (políticas mais novas têm prioridade menor do que as políticas mais antigas). Um número de prioridade menor indica uma maior prioridade para a política (0 é a maior), e as políticas são processadas por ordem de prioridade (políticas com maior prioridade são processadas antes das políticas com menor prioridade). Duas políticas não podem ter a mesma prioridade, e o processamento da política será interrompido após a primeira política ser aplicada.

Para obter mais informações sobre a ordem de precedência e como várias políticas são avaliadas e aplicadas, confira [Ordem e precedência da proteção de email](how-policies-and-protections-are-combined.md).

As políticas de Anexos Seguros são exibidas na ordem em que são processadas (a primeira política tem **o valor** prioridade 0).

**Observação:** no Centro de Conformidade & segurança, você só pode alterar a prioridade da política de Anexos seguros depois de criar a política. No PowerShell, você pode substituir a prioridade padrão ao criar a regra de anexo seguro (que pode afetar a prioridade das regras existentes).

Para alterar a prioridade de uma política, mova a política para cima ou para baixo na lista (não é possível modificar diretamente o número de **Prioridade** no Centro de Conformidade e Segurança).

1. No Centro de Conformidade & Segurança, vá para **Anexos** Seguros da ATP da Política \>  \> **de Gerenciamento de Ameaças.**

2. Na página **Anexos Seguros,** selecione uma política na lista e clique nele (não marque a caixa de seleção).

3. Nos detalhes da política exibidos, clique no botão de prioridade disponível.

   - A política de Anexos Seguros com o **valor** **prioridade 0** tem apenas o **botão** Diminuir prioridade disponível.

   - A política de Anexos Seguros com o menor valor **de** Prioridade (por exemplo, **3**) tem apenas o **botão** Aumentar prioridade disponível.

   - Se você tiver três ou mais políticas de Anexos Seguros,  as políticas  entre os valores de prioridade mais alta e mais baixa terão os botões Aumentar prioridade e Diminuir prioridade disponíveis.

4. Clique **em Aumentar prioridade** ou Diminuir **prioridade** para alterar o **valor prioridade.**

5. Quando terminar, clique em **Fechar**.

## <a name="use-the-security--compliance-center-to-remove-safe-attachments-policies"></a>Usar o Centro de Conformidade & segurança para remover políticas de Anexos seguros

1. No Centro de Conformidade & Segurança, vá para **Anexos** Seguros da ATP da Política \>  \> **de Gerenciamento de Ameaças.**

2. Na página **Anexos Seguros,** selecione uma política na lista e clique nele (não marque a caixa de seleção).

3. In the policy details fly out that appears, click **Delete policy**, and then click **Yes** in the warning dialog that appears.

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-attachments-policies"></a>Usar o PowerShell do Exchange Online ou o EOP PowerShell autônomo para configurar políticas de Anexos Seguros

Conforme descrito anteriormente, uma política de Anexos Seguros consiste em uma política de anexo seguro e uma regra de anexo seguro.

No PowerShell, a diferença entre políticas de anexo seguro e regras de anexo seguro é aparente. Você gerencia políticas de anexo seguro usando os cmdlets **\* -SafeAttachmentPolicy** e gerencia regras de anexo seguro usando os cmdlets **\* -SafeAttachmentRule.**

- No PowerShell, primeiro você cria a política de anexo seguro e, em seguida, cria a regra de anexo seguro que identifica a política à qual a regra se aplica.
- No PowerShell, você modifica as configurações da política de anexo seguro e da regra de anexo seguro separadamente.
- Quando você remove uma política de anexo seguro do PowerShell, a regra de anexo seguro correspondente não é removida automaticamente e vice-versa.

### <a name="use-powershell-to-create-safe-attachments-policies"></a>Usar o PowerShell para criar políticas de Anexos Seguros

Criar uma política de Anexos Seguros no PowerShell é um processo de duas etapas:

1. Crie a política de anexo seguro.
2. Crie a regra de anexo seguro que especifica a política de anexo seguro à qual a regra se aplica.

 **Observações**:

- Você pode criar uma nova regra de anexo seguro e atribuir uma política de anexo seguro existente e nãossociada a ela. Uma regra de anexo seguro não pode ser associada a mais de uma política de anexo seguro.

- Você pode definir as seguintes configurações em novas políticas de anexo seguro no PowerShell que não estarão disponíveis no Centro de Conformidade e Segurança até que você crie & a política:
  - Crie a nova política como desabilitada (_Habilitado_ no `$false` cmdlet **New-SafeAttachmentRule).**
  - Definir a prioridade da política durante a criação (_Prioridade_ ) no _\<Number\>_ cmdlet **New-SafeAttachmentRule).**

- Uma nova política de anexo seguro que você criar no PowerShell não será visível no Centro de Conformidade e Segurança & até que você atribua a política a uma regra de anexo seguro.

#### <a name="step-1-use-powershell-to-create-a-safe-attachment-policy"></a>Etapa 1: Usar o PowerShell para criar uma política de anexo seguro

Para criar uma política de anexo seguro, use esta sintaxe:

```PowerShell
New-SafeAttachmentPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-Action <Allow | Block | Replace | DynamicDelivery>] [-Redirect <$true | $false>] [-RedirectAddress <SMTPEmailAddress>] [-ActionOnError <$true | $false>]
```

Este exemplo cria uma política de anexo seguro chamada Contoso All com os seguintes valores:

- Bloquear mensagens que contêm malware pela verificação de Documentos Seguros (não estamos usando o parâmetro _Action_ e o valor padrão é `Block` ).
- O redirecionamento está habilitado, e as mensagens que contêm malware são enviadas sec-ops@contoso.com análise e investigação.
- Se a verificação de Anexos Seguros não estiver disponível ou encontrar erros, não entregue a mensagem (não estamos usando o parâmetro _ActionOnError_ e o valor padrão é `$true` ).

```PowerShell
New-SafeAttachmentPolicy -Name "Contoso All" -Redirect $true -RedirectAddress sec-ops@contoso.com
```

Para informações detalhadas de sintaxes e de parâmetros, consulte [New-SafeAttachmentPolicy](https://docs.microsoft.com/powershell/module/exchange/new-safeattachmentpolicy).

#### <a name="step-2-use-powershell-to-create-a-safe-attachment-rule"></a>Etapa 2: Usar o PowerShell para criar uma regra de anexo seguro

Para criar uma regra de anexo seguro, use esta sintaxe:

```PowerShell
New-SafeAttachmentRule -Name "<RuleName>" -SafeAttachmentPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"] [-Enabled <$true | $false>]
```

Este exemplo cria uma regra de anexo seguro chamada Contoso All com as seguintes condições:

- A regra é associada à política de anexo seguro chamada Contoso All.
- A regra se aplica a todos os destinatários no contoso.com domínio.
- Como não estamos usando o parâmetro _Priority,_ a prioridade padrão é usada.
- A regra está habilitada (não estamos usando o parâmetro _Enabled_ e o valor padrão é `$true` ).

```powershell
New-SafeAttachmentRule -Name "Contoso All" -SafeAttachmentPolicy "Contoso All" -RecipientDomainIs contoso.com
```

Para informações detalhadas de sintaxes e de parâmetros, consulte [New-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/new-safeattachmentrule).

### <a name="use-powershell-to-view-safe-attachment-policies"></a>Usar o PowerShell para exibir políticas de anexo seguro

Para exibir as políticas de anexos seguros existentes, use a seguinte sintaxe:

```PowerShell
Get-SafeAttachmentPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

Este exemplo retorna uma lista resumida de todas as políticas de anexo seguro.

```PowerShell
Get-SafeAttachmentPolicy
```

Este exemplo retorna informações detalhadas sobre a política de anexo seguro chamada Contoso Executives.

```PowerShell
Get-SafeAttachmentPolicy -Identity "Contoso Executives" | Format-List
```

Para informações detalhadas de sintaxes e de parâmetros, consulte [Get-SafeAttachmentPolicy](https://docs.microsoft.com/powershell/module/exchange/get-safeattachmentpolicy).

### <a name="use-powershell-to-view-safe-attachment-rules"></a>Usar o PowerShell para exibir regras de anexo seguro

Para exibir as regras existentes de anexo seguro, use a seguinte sintaxe:

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

Este exemplo retorna informações detalhadas sobre a regra de anexo seguro chamada Contoso Executives.

```PowerShell
Get-SafeAttachmentRule -Identity "Contoso Executives" | Format-List
```

Para informações detalhadas de sintaxes e de parâmetros, consulte [Get-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/get-safeattachmentrule).

### <a name="use-powershell-to-modify-safe-attachment-policies"></a>Usar o PowerShell para modificar políticas de anexo seguro

Não é possível renomear uma política de anexo seguro no PowerShell (o cmdlet **Set-SafeAttachmentPolicy** não tem parâmetro _Name)._ Ao renomear uma política de Anexos Seguros no Centro de & Conformidade e Segurança, você está apenas renomeando a regra de anexo _seguro._

Caso contrário, as mesmas configurações estarão disponíveis quando você criar uma política de anexo seguro conforme descrito na Etapa [1: usar](#step-1-use-powershell-to-create-a-safe-attachment-policy) o PowerShell para criar uma seção de política de anexo seguro anteriormente neste artigo.

Para modificar uma política de anexo seguro, use esta sintaxe:

```PowerShell
Set-SafeAttachmentPolicy -Identity "<PolicyName>" <Settings>
```

Para informações detalhadas de sintaxes e de parâmetros, consulte [Set-SafeAttachmentPolicy](https://docs.microsoft.com/powershell/module/exchange/set-safeattachmentpolicy).

### <a name="use-powershell-to-modify-safe-attachment-rules"></a>Usar o PowerShell para modificar regras de anexo seguro

A única configuração que não está disponível quando você modifica uma regra de anexo seguro no PowerShell é o parâmetro _Enabled_ que permite criar uma regra desabilitada. Para habilitar ou desabilitar regras de anexo seguro existentes, consulte a próxima seção.

Caso contrário, as mesmas configurações estarão disponíveis quando você criar uma regra conforme descrito na Etapa [2: Usar](#step-2-use-powershell-to-create-a-safe-attachment-rule) o PowerShell para criar uma seção de regra de anexo seguro anteriormente neste artigo.

Para modificar uma regra de anexo seguro, use esta sintaxe:

```PowerShell
Set-SafeAttachmentRule -Identity "<RuleName>" <Settings>
```

Para informações detalhadas de sintaxes e de parâmetros, consulte [Set-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/set-safeattachmentrule).

### <a name="use-powershell-to-enable-or-disable-safe-attachment-rules"></a>Usar o PowerShell para habilitar ou desabilitar regras de anexo seguro

Habilitar ou desabilitar uma regra de anexo seguro no PowerShell habilita ou desabilita toda a política de Anexos Seguros (a regra de anexo seguro e a política de anexo seguro atribuída).

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

Para informações detalhadas de sintaxes e de parâmetros, consulte [Enable-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/enable-safeattachmentrule) e [Disable-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/disable-safeattachmentrule).

### <a name="use-powershell-to-set-the-priority-of-safe-attachment-rules"></a>Usar o PowerShell para definir a prioridade de regras de anexo seguro

O valor mais alto de prioridade que pode ser definido em uma regra é 0. O valor mais baixo que pode ser definido depende do número de regras. Por exemplo, se você tiver cinco regras, use os valores de prioridade de 0 a 4. Alterar a prioridade de uma regra existente pode ter um efeito cascata em outras regras. Por exemplo, se você tiver cinco regras personalizadas (prioridades de 0 a 4) e alterar a prioridade de uma regra para 2, a regra existente com prioridade 2 será alterada para a prioridade 3, e a regra com prioridade 3 será alterada para prioridade 4.

Para definir a prioridade de uma regra de anexo seguro no PowerShell, use a seguinte sintaxe:

```PowerShell
Set-SafeAttachmentRule -Identity "<RuleName>" -Priority <Number>
```

Este exemplo define a prioridade da regra chamada Marketing Department como 2. Todas as regras existentes com prioridade inferior ou igual a 2 são reduzidas por 1 (seus números de prioridade são aumentados por 1).

```PowerShell
Set-SafeAttachmentRule -Identity "Marketing Department" -Priority 2
```

**Observação:** para definir a prioridade de uma nova regra ao criar, use o parâmetro _Priority_ no cmdlet **New-SafeAttachmentRule.**

Para informações detalhadas de sintaxes e de parâmetros, consulte [Set-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/set-safeattachmentrule).

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

Para informações detalhadas de sintaxes e de parâmetros, consulte [Remove-SafeAttachmentPolicy](https://docs.microsoft.com/powershell/module/exchange/remove-safeattachmentpolicy).

### <a name="use-powershell-to-remove-safe-attachment-rules"></a>Usar o PowerShell para remover regras de anexo seguro

Quando você usa o PowerShell para remover uma regra de anexo seguro, a política de anexo seguro correspondente não é removida.

Para remover uma regra de anexo seguro no PowerShell, use esta sintaxe:

```PowerShell
Remove-SafeAttachmentRule -Identity "<PolicyName>"
```

Este exemplo remove a regra de anexo seguro chamada Marketing Department.

```PowerShell
Remove-SafeAttachmentRule -Identity "Marketing Department"
```

Para informações detalhadas de sintaxes e de parâmetros, consulte [Remove-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/remove-safeattachmentrule).

## <a name="how-do-you-know-these-procedures-worked"></a>Como saber se esses procedimentos funcionaram?

Para verificar se você criou, modificou ou removeu com êxito as políticas de Anexos Seguros, faça uma das seguintes etapas:

- No Centro de Conformidade & Segurança, vá para **Anexos** Seguros da ATP da Política \>  \> **de Gerenciamento de Ameaças.** Verifique a lista de políticas, seus valores **de Status** e seus **valores de** Prioridade. Para exibir mais detalhes, selecione a política na lista e veja os detalhes no fly out.

- No PowerShell do Exchange Online ou no PowerShell da Proteção do Exchange Online, substitua o nome da política ou regra, execute o seguinte comando e \<Name\> verifique as configurações:

  ```PowerShell
  Get-SafeAttachmentPolicy -Identity "<Name>" | Format-List
  ```

  ```PowerShell
  Get-SafeAttachmentRule -Identity "<Name>" | Format-List
  ```

Para verificar se os Anexos Seguros estão verificando mensagens, verifique os relatórios disponíveis do Defender para Office 365. Para obter mais informações, consulte Exibir relatórios do [Defender para Office 365](view-reports-for-atp.md) e usar o Explorer no Centro de [Conformidade & Segurança.](threat-explorer.md)
