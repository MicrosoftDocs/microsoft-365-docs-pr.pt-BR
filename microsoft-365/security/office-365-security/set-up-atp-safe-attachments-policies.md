---
title: Configurar políticas de anexos seguros no Microsoft defender para Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 078eb946-819a-4e13-8673-fe0c0ad3a775
ms.collection:
- M365-security-compliance
description: Saiba como definir políticas de anexos seguros para proteger sua organização contra arquivos mal-intencionados no email.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ca0bfb7ba91f86fee187cfe3445c0dd6c8d4ad56
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/03/2020
ms.locfileid: "48845487"
---
# <a name="set-up-safe-attachments-policies-in-microsoft-defender-for-office-365"></a>Configurar políticas de anexos seguros no Microsoft defender para Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

> [!IMPORTANT]
> Este artigo destina-se a clientes comerciais que têm [o Microsoft defender para Office 365](office-365-atp.md). Se você for um usuário doméstico que está procurando por informações sobre a verificação de anexos no Outlook, consulte [Advanced Outlook.com Security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).

Anexos seguros é um recurso do [Microsoft defender para Office 365](office-365-atp.md) que usa um ambiente virtual para verificar anexos em mensagens de email de entrada depois de terem sido verificados pela [proteção Antimalware no Exchange Online Protection (EOP)](anti-malware-protection.md), mas antes da entrega aos destinatários. Para obter mais informações, consulte [Safe Attachments in Microsoft defender for Office 365](atp-safe-attachments.md).

Não há nenhuma política de anexos confiáveis interna ou padrão. Para obter a verificação de anexos seguros de anexos de mensagens de email, você precisa criar uma ou mais políticas de anexos seguros, conforme descrito neste artigo.

Você pode configurar políticas de anexos seguros no centro de conformidade do & de segurança ou no PowerShell (Exchange Online PowerShell para organizações qualificadas da Microsoft 365 com caixas de correio no Exchange Online; EOP PowerShell autônomos para organizações sem caixas de correio do Exchange Online, mas com o defender for Office 365 Add-on subscriptions).

Os elementos básicos de uma política de anexos seguros são:

- **A política de anexo seguro** : especifica as ações para detecções de malware desconhecidas, se enviar mensagens com anexos de malware para um endereço de email especificado e se deseja entregar mensagens caso a verificação de anexos seguros não possa ser concluída.
- **A regra de anexo seguro** : especifica a prioridade e os filtros de destinatário (a qual a política se aplica).

A diferença entre esses dois elementos não é óbvia quando você gerencia políticas de anexos seguros no centro de conformidade de & de segurança:

- Ao criar uma política de anexos seguros, você realmente está criando uma regra de anexo seguro e a política de anexo seguro associada ao mesmo tempo usando o mesmo nome para ambos.
- Quando você modifica uma política de anexos seguros, as configurações relacionadas ao nome, prioridade, habilitado ou desabilitado e filtros de destinatário modificam a regra de anexo seguro. Todas as outras configurações modificam a política de anexo seguro associada.
- Quando você remove uma política de anexos seguros, a regra de anexo seguro e a política de anexo seguro associada são removidos.

No PowerShell do Exchange Online ou no PowerShell do EOP autônomo, a política e a regra são gerenciadas separadamente. Para obter mais informações, consulte a seção [usar o PowerShell do Exchange Online ou o PowerShell do EOP para configurar políticas de anexos seguros](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-attachments-policies) , posteriormente neste artigo.

> [!NOTE]
> Na área configurações globais das configurações de anexos seguros, você configura recursos que não são dependentes de políticas de anexos seguros. Para obter instruções, confira [Ativar ATP para SharePoint, onedrive e Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md) e [documentos seguros no Microsoft 365 E5](safe-docs.md).

## <a name="what-do-you-need-to-know-before-you-begin"></a>O que você precisa saber antes de começar?

- Abra o Centro de Conformidade e Segurança em <https://protection.office.com/>. Para ir diretamente para a página de **anexos seguros** , use <https://protection.office.com/safeattachmentv2> .

- Para se conectar ao PowerShell do Exchange Online, confira [Conectar ao PowerShell do Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell). Para se conectar ao EOP PowerShell autônomo, consulte [Conectar-se ao PowerShell do Exchange Online Protection.](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).

- Para exibir, criar, modificar e excluir políticas de anexos seguros, você precisa ser membro de um dos grupos de função a seguir:

  - **Gerenciamento de organizações** ou **Administrador de segurança** no [Centro de segurança e conformidade](permissions-in-the-security-and-compliance-center.md).
  - **Gerenciamento de organização** no [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).

- Para obter as configurações recomendadas para políticas de anexos seguros, consulte [configurações de anexos seguros](recommended-settings-for-eop-and-office365-atp.md#safe-attachments-settings).

- Aguarde até 30 minutos para que uma política nova ou atualizada seja aplicada.

## <a name="use-the-security--compliance-center-to-create-safe-attachments-policies"></a>Usar o centro de conformidade de & de segurança para criar políticas de anexos seguros

A criação de uma política de anexos seguros personalizada no centro de conformidade de & de segurança cria a regra de anexo seguro e a política de anexo seguro associada ao mesmo tempo usando o mesmo nome para ambos.

1. No centro de conformidade & segurança, vá para política de **Gerenciamento de ameaças** de \> **Policy** \> **anexos seguros de ATP**.

2. Na página **anexos seguros** , clique em **criar**.

3. O assistente de **nova política de anexos seguros** é aberto. Na página **nomear sua política** , defina as seguintes configurações:

   - **Nome** : insira um nome exclusivo e descritivo para a política.

   - **Descrição** : digite uma descrição opcional para a política.

   Quando terminar, clique em **Avançar**.

4. Na página **configurações** que aparece, defina as seguintes configurações:

   - **Resposta de malware desconhecido de anexos seguros** : selecione um dos seguintes valores:

     - **Off** : normalmente não é recomendável esse valor.
     - **Monitorar**
     - **Bloquear** : Este é o valor padrão e o valor recomendado em políticas de segurança padrão e estritas [predefinidas](preset-security-policies.md).
     - **Replace**
     - **Entrega dinâmica (recurso de visualização)**

     Esses valores são explicados em [configurações de política de anexos seguros](atp-safe-attachments.md#safe-attachments-policy-settings).

   - **Envie o anexo para o seguinte endereço de email** : para os valores de ação **Bloquear** , **monitorar** ou **substituir** , você pode selecionar **habilitar redirecionamento** para enviar mensagens que contenham anexos de malware para o endereço de email interno ou externo especificado para análise e investigação.

     A recomendação para as configurações de política padrão e estrita é habilitar o redirecionamento. Para obter mais informações, consulte [configurações de anexos seguros](recommended-settings-for-eop-and-office365-atp.md#safe-attachments-settings).

   - **Aplicar a seleção acima se a verificação de malware para anexos expirar ou ocorrer erro** : a ação especificada por **anexos seguros a resposta desconhecida** é tomada em mensagens, mesmo quando a verificação de anexos seguros não pode ser concluída. Sempre Selecione esta opção se você selecionar **redirecionamento habilitado**. Caso contrário, as mensagens poderão ser perdidas.

   Quando terminar, clique em **Avançar**.

5. Na página **aplicado a** que aparece, identifique os destinatários internos aos quais a política se aplica.

   Só é possível usar uma condição ou exceção uma vez; contudo, você pode especificar vários valores para a condição ou exceção. Vários valores da mesma condição ou exceção usam a lógica OU (por exemplo, _\<recipient1\>_ ou _\<recipient2\>_ ). Para diferentes condições ou exceções, use a lógica E (por exemplo, _\<recipient1\>_ e _\<member of group 1\>_ ).

   Clique em **Adicionar uma condição**. Na lista suspensa exibida, selecione uma condição em **aplicado se** :

   - **O destinatário é** : especifica uma ou mais caixas de correio, usuários de email ou contatos de email em sua organização.
   - **O destinatário é um membro de** : especifica um ou mais grupos na sua organização.
   - **O domínio do destinatário é** : Especifica os destinatários em um ou mais domínios aceitos configurados na sua organização. 

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

## <a name="use-the-security--compliance-center-to-view-safe-attachments-policies"></a>Usar o centro de conformidade de & de segurança para exibir políticas de anexos seguros

1. No centro de conformidade & segurança, vá para política de **Gerenciamento de ameaças** de \> **Policy** \> **anexos seguros de ATP**.

2. Na página **anexos seguros** , selecione uma política na lista e clique nela (não marque a caixa de seleção).

   Os detalhes da política aparecem em saída

## <a name="use-the-security--compliance-center-to-modify-safe-attachments-policies"></a>Usar o centro de conformidade de & de segurança para modificar políticas de anexos seguros

1. No centro de conformidade & segurança, vá para política de **Gerenciamento de ameaças** de \> **Policy** \> **anexos seguros de ATP**.

2. Na página **anexos seguros** , selecione uma política na lista e clique nela (não marque a caixa de seleção).

3. Nos detalhes da política que aparecem, clique em **Editar política**.

As configurações disponíveis na saída que aparecem são idênticas àquelas descritas na seção [usar o centro de conformidade de segurança & para criar políticas de anexos seguros](#use-the-security--compliance-center-to-create-safe-attachments-policies) .

Para habilitar ou desabilitar uma política ou definir a ordem de prioridade da política, consulte as seções a seguir.

### <a name="enable-or-disable-safe-attachments-policies"></a>Habilitar ou desabilitar políticas de anexos seguros

1. No centro de conformidade & segurança, vá para política de **Gerenciamento de ameaças** de \> **Policy** \> **anexos seguros de ATP**.

2. Observe o valor na coluna **status** :

   - Mover a alternância para a esquerda ![Desativar política](../../media/scc-toggle-off.png) para desabilitar a política.

   - Mover a alternância para a direita ![Ativar política](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) para habilitar a política.

### <a name="set-the-priority-of-safe-attachments-policies"></a>Definir a prioridade de políticas de anexos seguros

Por padrão, as políticas de anexos seguros recebem uma prioridade com base na ordem em que foram criadas (as políticas mais recentes são de prioridade mais baixa do que as diretivas mais antigas). Um número de prioridade menor indica uma maior prioridade para a política (0 é a maior), e as políticas são processadas por ordem de prioridade (políticas com maior prioridade são processadas antes das políticas com menor prioridade). Duas políticas não podem ter a mesma prioridade, e o processamento da política será interrompido após a primeira política ser aplicada.

Para obter mais informações sobre a ordem de precedência e como várias políticas são avaliadas e aplicadas, confira [Ordem e precedência da proteção de email](how-policies-and-protections-are-combined.md).

As políticas de anexos seguros são exibidas na ordem em que são processadas (a primeira política tem o valor de **prioridade** 0).

**Observação** : no centro de conformidade & segurança, você só pode alterar a prioridade da política de anexos seguros após criá-la. No PowerShell, você pode substituir a prioridade padrão ao criar a regra de anexo seguro (que pode afetar a prioridade das regras existentes).

Para alterar a prioridade de uma política, mova a política para cima ou para baixo na lista (não é possível modificar diretamente o número de **Prioridade** no Centro de Conformidade e Segurança).

1. No centro de conformidade & segurança, vá para política de **Gerenciamento de ameaças** de \> **Policy** \> **anexos seguros de ATP**.

2. Na página **anexos seguros** , selecione uma política na lista e clique nela (não marque a caixa de seleção).

3. Na saída detalhes da política que aparece, clique no botão prioridade disponível.

   - A política de anexos seguros com o valor de **prioridade** **0** tem apenas o botão **diminuir prioridade** disponível.

   - A política de anexos seguros com o menor valor de **prioridade** (por exemplo, **3** ) tem apenas o botão **aumentar prioridade** disponível.

   - Se você tiver três ou mais políticas de anexos confiáveis, as políticas entre os valores de prioridade mais alta e mais baixa terão os botões **aumentar prioridade** e **diminuir prioridade** disponíveis.

4. Clique em **aumentar prioridade** ou **diminuir prioridade** para alterar o valor de **prioridade** .

5. Quando terminar, clique em **Fechar**.

## <a name="use-the-security--compliance-center-to-remove-safe-attachments-policies"></a>Usar o centro de conformidade de & de segurança para remover políticas de anexos seguros

1. No centro de conformidade & segurança, vá para política de **Gerenciamento de ameaças** de \> **Policy** \> **anexos seguros de ATP**.

2. Na página **anexos seguros** , selecione uma política na lista e clique nela (não marque a caixa de seleção).

3. Nos detalhes da política de saída, clique em **excluir política** e clique em **Sim** na caixa de diálogo de aviso que aparece.

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-attachments-policies"></a>Usar o PowerShell do Exchange Online ou o PowerShell do EOP para configurar políticas de anexos seguros

Como descrito anteriormente, uma política de anexos seguros consiste em uma política de anexo seguro e uma regra de anexo seguro.

No PowerShell, a diferença entre políticas de anexo seguro e regras de anexo seguro é aparente. Você gerencia políticas de anexo seguro usando os cmdlets **\* -SafeAttachmentPolicy** e gerencia regras de anexo seguro usando os cmdlets **\* -SafeAttachmentRule** .

- No PowerShell, você cria a política de anexo seguro primeiro e, em seguida, cria a regra de anexo seguro que identifica a política à qual a regra se aplica.
- No PowerShell, modifique as configurações na política de anexo seguro e a regra de anexo seguro separadamente.
- Quando você remove uma política de anexo seguro do PowerShell, a regra de anexo seguro correspondente não é removida automaticamente e vice-versa.

### <a name="use-powershell-to-create-safe-attachments-policies"></a>Usar o PowerShell para criar políticas de anexos seguros

A criação de uma política de anexos seguros no PowerShell é um processo de duas etapas:

1. Criar a política de anexo seguro.
2. Crie a regra de anexo seguro que especifica a política de anexo seguro à qual a regra se aplica.

 **Observações** :

- Você pode criar uma nova regra de anexo seguro e atribuir uma política de anexo segura existente e não associada a ela. Uma regra de anexo seguro não pode ser associada a mais de uma política de anexo seguro.

- Você pode definir as seguintes configurações em novas políticas de anexo seguro no PowerShell que não estão disponíveis no centro de conformidade & de segurança até que a política seja criada:
  - Crie a nova política como desabilitada ( _habilitada_ `$false` no cmdlet **New-SafeAttachmentRule** ).
  - Definir a prioridade da política durante a criação ( _prioridade_ _\<Number\>_ ) no cmdlet **New-SafeAttachmentRule** ).

- Uma nova política de anexo segura que você cria no PowerShell não fica visível no centro de conformidade & segurança até que você atribua a política a uma regra de anexo seguro.

#### <a name="step-1-use-powershell-to-create-a-safe-attachment-policy"></a>Etapa 1: usar o PowerShell para criar uma política de anexo segura

Para criar uma política de anexo segura, use esta sintaxe:

```PowerShell
New-SafeAttachmentPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-Action <Allow | Block | Replace | DynamicDelivery>] [-Redirect <$true | $false>] [-RedirectAddress <SMTPEmailAddress>] [-ActionOnError <$true | $false>]
```

Este exemplo cria uma política de anexo segura chamada contoso todos com os seguintes valores:

- Bloquear mensagens que são encontradas para conter malware por verificação de documentos seguros (não estamos usando o parâmetro _Action_ , e o valor padrão é `Block` ).
- O redirecionamento é habilitado, e as mensagens que são encontradas para conter malware são enviadas para o sec-ops@contoso.com para análise e investigação.
- Se a verificação de anexos seguros não estiver disponível ou encontrar erros, não entregue a mensagem (não estamos usando o parâmetro _ActionOnError_ e o valor padrão é `$true` ).

```PowerShell
New-SafeAttachmentPolicy -Name "Contoso All" -Redirect $true -RedirectAddress sec-ops@contoso.com
```

Para informações detalhadas de sintaxes e de parâmetros, consulte [New-SafeAttachmentPolicy](https://docs.microsoft.com/powershell/module/exchange/new-safeattachmentpolicy).

#### <a name="step-2-use-powershell-to-create-a-safe-attachment-rule"></a>Etapa 2: usar o PowerShell para criar uma regra de anexo seguro

Para criar uma regra de anexo seguro, use esta sintaxe:

```PowerShell
New-SafeAttachmentRule -Name "<RuleName>" -SafeAttachmentPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"] [-Enabled <$true | $false>]
```

Este exemplo cria uma regra de anexo seguro chamada contoso todos com as seguintes condições:

- A regra é associada à política de anexo seguro chamada contoso ALL.
- A regra se aplica a todos os destinatários no domínio contoso.com.
- Como não estamos usando o parâmetro _Priority_ , a prioridade padrão é usada.
- A regra está habilitada (não estamos usando o parâmetro _Enabled_ e o valor padrão é `$true` ).

```powershell
New-SafeAttachmentRule -Name "Contoso All" -SafeAttachmentPolicy "Contoso All" -RecipientDomainIs contoso.com
```

Para informações detalhadas de sintaxes e de parâmetros, consulte [New-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/new-safeattachmentrule).

### <a name="use-powershell-to-view-safe-attachment-policies"></a>Usar o PowerShell para exibir políticas de anexo seguro

Para exibir as políticas de anexo seguro existentes, use a seguinte sintaxe:

```PowerShell
Get-SafeAttachmentPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

Este exemplo retorna uma lista resumida de todas as políticas de anexo seguro.

```PowerShell
Get-SafeAttachmentPolicy
```

Este exemplo retorna informações detalhadas sobre a política de anexo seguro chamada executivos da contoso.

```PowerShell
Get-SafeAttachmentPolicy -Identity "Contoso Executives" | Format-List
```

Para informações detalhadas de sintaxes e de parâmetros, consulte [Get-SafeAttachmentPolicy](https://docs.microsoft.com/powershell/module/exchange/get-safeattachmentpolicy).

### <a name="use-powershell-to-view-safe-attachment-rules"></a>Usar o PowerShell para exibir regras de anexo seguro

Para exibir as regras de anexo seguro existentes, use a sintaxe a seguir:

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

Este exemplo retorna informações detalhadas sobre a regra de anexo seguro chamada executivos da contoso.

```PowerShell
Get-SafeAttachmentRule -Identity "Contoso Executives" | Format-List
```

Para informações detalhadas de sintaxes e de parâmetros, consulte [Get-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/get-safeattachmentrule).

### <a name="use-powershell-to-modify-safe-attachment-policies"></a>Usar o PowerShell para modificar políticas de anexo seguro

Não é possível renomear uma política de anexo seguro no PowerShell (o cmdlet **set-SafeAttachmentPolicy** não tem nenhum parâmetro _Name_ ). Ao renomear uma política de anexos seguros no centro de conformidade e segurança &, você estará apenas renomeando a _regra_ de anexo seguro.

Caso contrário, as mesmas configurações estarão disponíveis quando você criar uma política de anexo seguro, conforme descrito na seção [etapa 1: usar o PowerShell para criar uma política de anexo seguro](#step-1-use-powershell-to-create-a-safe-attachment-policy) , anteriormente neste artigo.

Para modificar uma política de anexo seguro, use esta sintaxe:

```PowerShell
Set-SafeAttachmentPolicy -Identity "<PolicyName>" <Settings>
```

Para informações detalhadas de sintaxes e de parâmetros, consulte [set-SafeAttachmentPolicy](https://docs.microsoft.com/powershell/module/exchange/set-safeattachmentpolicy).

### <a name="use-powershell-to-modify-safe-attachment-rules"></a>Usar o PowerShell para modificar regras de anexo seguro

A única configuração que não está disponível quando você modifica uma regra de anexo seguro no PowerShell é o parâmetro _habilitado_ que permite criar uma regra desabilitada. Para habilitar ou desabilitar regras de anexo seguro existentes, consulte a próxima seção.

Caso contrário, as mesmas configurações estarão disponíveis quando você criar uma regra, conforme descrito na seção [etapa 2: usar o PowerShell para criar uma regra de anexo seguro](#step-2-use-powershell-to-create-a-safe-attachment-rule) , anteriormente neste artigo.

Para modificar uma regra de anexo seguro, use esta sintaxe:

```PowerShell
Set-SafeAttachmentRule -Identity "<RuleName>" <Settings>
```

Para informações detalhadas de sintaxes e de parâmetros, consulte [set-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/set-safeattachmentrule).

### <a name="use-powershell-to-enable-or-disable-safe-attachment-rules"></a>Usar o PowerShell para habilitar ou desabilitar regras de anexo seguro

Habilitar ou desabilitar uma regra de anexo seguro no PowerShell habilita ou desabilita toda a política de anexos seguros (a regra de anexo seguro e a política de anexo seguro atribuída).

Para habilitar ou desabilitar uma regra de anexo seguro no PowerShell, use esta sintaxe:

```PowerShell
<Enable-SafeAttachmentRule | Disable-SafeAttachmentRule> -Identity "<RuleName>"
```

Este exemplo desabilita a regra de anexo seguro chamada departamento de marketing.

```PowerShell
Disable-SafeAttachmentRule -Identity "Marketing Department"
```

Este exemplo habilita a mesma regra.

```PowerShell
Enable-SafeAttachmentRule -Identity "Marketing Department"
```

Para informações detalhadas de sintaxes e de parâmetros, consulte [Enable-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/enable-safeattachmentrule) e [Disable-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/disable-safeattachmentrule).

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

**Observação** : para definir a prioridade de uma nova regra ao criá-la, use o parâmetro _Priority_ no cmdlet **New-SafeAttachmentRule** .

Para informações detalhadas de sintaxes e de parâmetros, consulte [set-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/set-safeattachmentrule).

### <a name="use-powershell-to-remove-safe-attachment-policies"></a>Usar o PowerShell para remover políticas de anexo seguro

Quando você usa o PowerShell para remover uma política de anexo seguro, a regra de anexo seguro correspondente não é removida.

Para remover uma política de anexo seguro no PowerShell, use esta sintaxe:

```PowerShell
Remove-SafeAttachmentPolicy -Identity "<PolicyName>"
```

Este exemplo remove a política de anexo seguro chamada departamento de marketing.

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

Este exemplo remove a regra de anexo seguro chamada departamento de marketing.

```PowerShell
Remove-SafeAttachmentRule -Identity "Marketing Department"
```

Para informações detalhadas de sintaxes e de parâmetros, consulte [Remove-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/remove-safeattachmentrule).

## <a name="how-do-you-know-these-procedures-worked"></a>Como saber se esses procedimentos funcionaram?

Para verificar se você criou, modificou ou removeu com êxito as políticas de anexos confiáveis, execute uma das seguintes etapas:

- No centro de conformidade & segurança, vá para política de **Gerenciamento de ameaças** de \> **Policy** \> **anexos seguros de ATP**. Verifique a lista de políticas, seus valores de **status** e seus valores de **prioridade** . Para exibir mais detalhes, selecione a política na lista e exiba os detalhes na saída.

- No PowerShell do Exchange Online ou do Exchange Online Protection, substitua o \<Name\> nome da política ou regra, execute o seguinte comando e verifique as configurações:

  ```PowerShell
  Get-SafeAttachmentPolicy -Identity "<Name>" | Format-List
  ```

  ```PowerShell
  Get-SafeAttachmentRule -Identity "<Name>" | Format-List
  ```

Para verificar se os anexos seguros estão verificando mensagens, confira os relatórios do defender for Office 365 disponíveis. Para obter mais informações, consulte [View Reports for defender for Office 365](view-reports-for-atp.md) e [Use Explorer no centro de conformidade de & de segurança](threat-explorer.md).
