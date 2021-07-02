---
title: Configurar a entrega de simulações de phishing de terceiros para usuários e mensagens não filtradas para caixas de correio SecOps
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
ms.collection:
- M365-security-compliance
ms.custom: ''
description: Os administradores podem aprender a usar a política de entrega avançada no Proteção do Exchange Online (EOP) para identificar mensagens que não devem ser filtradas em cenários com suporte específico (simulações de phishing de terceiros e mensagens entregues às caixas de correio de operações de segurança (SecOps).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 053f88da96983b03ad03e75c11a4fa692ac6a850
ms.sourcegitcommit: a4c93a4c7d7db08fe3b032b58d5c7dbbb9476e90
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2021
ms.locfileid: "53256862"
---
# <a name="configure-the-delivery-of-third-party-phishing-simulations-to-users-and-unfiltered-messages-to-secops-mailboxes"></a>Configurar a entrega de simulações de phishing de terceiros para usuários e mensagens não filtradas para caixas de correio SecOps

**Aplica-se a**
- [Proteção do Exchange Online](exchange-online-protection-overview.md)
- [Plano 1 e plano 2 do Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!NOTE]
> O recurso descrito neste artigo está em Visualização, não está disponível para todos e está sujeito a alterações.

Para manter sua organização segura por [padrão,](secure-by-default.md)o Proteção do Exchange Online (EOP) não permite listas seguras ou bypass de filtragem para mensagens identificadas como malware ou phishing de alta confiança. Porém, há cenários específicos que exigem a entrega de mensagens não filtradas. Por exemplo:

- **Simulações de phishing de** terceiros : Ataques simulados podem ajudá-lo a identificar usuários vulneráveis antes que um ataque real impacte sua organização.
- Caixas de correio de operações de segurança **(SecOps)**: Caixas de correio dedicadas que são usadas pelas equipes de segurança para coletar e analisar mensagens não filtradas (boas e ruins).

Você usa a _política de entrega_ avançada Microsoft 365 impedir que essas mensagens nesses _cenários específicos_ seja filtrada. <sup>\*</sup> A política de entrega avançada garante que as mensagens nesses cenários alcancem os seguintes resultados:

- Os filtros no EOP e no Microsoft Defender Office 365 tomar nenhuma ação nessas mensagens.<sup>\*</sup>
- [A limpeza zero hora (ZAP)](zero-hour-auto-purge.md) para spam e phishing não toma nenhuma ação nessas mensagens.<sup>\*</sup>
- [Os alertas padrão do](alerts.md) sistema não são disparados para esses cenários.
- [AIR e clustering no Defender para Office 365](office-365-air.md) ignora essas mensagens.
- Especificamente para simulações de phishing de terceiros:
  - [Os envios de administrador](admin-submission.md) geram uma resposta automática dizendo que a mensagem faz parte de uma campanha de simulação de phishing e não é uma ameaça real. Os alertas e o AIR não serão disparados.
  - [Cofre Links no Defender para Office 365](safe-links.md) não bloqueia ou detona as URLs especificamente identificadas nessas mensagens.
  - [Cofre Anexos no Defender para](safe-attachments.md) Office 365 não detona anexos nessas mensagens.

<sup>\*</sup> Não é possível ignorar a filtragem de malware ou o ZAP para malware.

As mensagens identificadas pela política de entrega avançada não são ameaças de segurança, portanto, as mensagens são marcadas como substituições do sistema. Os administradores podem filtrar e analisar essas substituições do sistema nas seguintes experiências:

- [Explorador de Ameaças/Detecções em tempo real no Defender para Office 365 plano 2](threat-explorer.md)
- A [Página da entidade email no Explorador de Ameaças/Detecções em tempo real](mdo-email-entity-page.md)
- O [relatório de status de proteção contra ameaças](view-email-security-reports.md#threat-protection-status-report)
- [Busca avançada no Microsoft Defender para Ponto de Extremidade](../defender-endpoint/advanced-hunting-overview.md)
- [Modos de Exibição de Campanha](campaigns.md)

## <a name="what-do-you-need-to-know-before-you-begin"></a>Do que você precisa saber para começar?

- Abra o portal do Microsoft 365 Defender em <https://security.microsoft.com>. Para ir diretamente para a **página Entrega** Avançada, abra <https://security.microsoft.com/advanceddelivery> .

- Para se conectar ao PowerShell do Exchange Online, confira [Conectar ao PowerShell do Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).

- Você precisa ter permissões atribuídas antes de poder fazer os procedimentos neste artigo:
  - Para criar, modificar ou remover configurações configuradas na política de entrega  avançada, você precisa ser membro do grupo de  função Administrador de Segurança no **portal do Microsoft 365 Defender** e membro do grupo de função Gerenciamento da Organização **no Exchange Online**.
  - Para acesso somente leitura à política de entrega avançada, você precisa ser membro dos grupos de função Leitor **Global** ou **Leitor de** Segurança.

  Para obter mais informações, consulte [Permissões no portal Microsoft 365 Defender e](permissions-microsoft-365-security-center.md) Permissões no [Exchange Online](/exchange/permissions-exo/permissions-exo).

  > [!NOTE]
  > Adicionar usuários à função Azure Active Directory correspondente fornece aos usuários as permissões necessárias no _portal_ Microsoft 365 Defender e permissões para outros recursos no Microsoft 365. Para obter mais informações, confira o artigo [Sobre funções de administrador](../../admin/add-users/about-admin-roles.md).

## <a name="use-the-microsoft-365-defender-portal-to-configure-secops-mailboxes-in-the-advanced-delivery-policy"></a>Use o portal Microsoft 365 Defender para configurar caixas de correio SecOps na política de entrega avançada

1. No portal Microsoft 365 Defender, vá para **Email & Políticas** de Colaboração & Regras De acordo com a página Regras seção Entrega \>  \>  \>  \> **avançada**.

2. Na página **Entrega Avançada,** verifique se a guia caixa de correio **SecOps** está selecionada e, em seguida, faça uma das seguintes etapas:
   - Clique ![ em Editar ícone ](../../media/m365-cc-sc-edit-icon.png) **Editar**.
   - Se não houver simulações de phishing configuradas, clique em **Adicionar**.

3. No sobrevoo Editar caixas de correio **SecOps** que são abertas, insira uma caixa de correio Exchange Online existente que você deseja designar como caixa de correio SecOps, seguindo uma das seguintes etapas:
   - Clique na caixa, deixe a lista de caixas de correio resolver e selecione a caixa de correio.
   - Clique na caixa comece a digitar um identificador para a caixa de correio (nome, nome de exibição, alias, endereço de email, nome da conta etc.) e selecione a caixa de correio (nome de exibição) dos resultados.

     Repita essa etapa quantas vezes forem necessárias. Grupos de distribuição não são permitidos.

     Para remover uma entrada existente, clique em Remover ![Ícone Remover](../../media/m365-cc-sc-remove-selection-icon.png) ao lado do valor.

4. Quando concluir, clique em **Salvar**.

As entradas de caixa de correio SecOps que você configurou são exibidas na guia caixa de **correio SecOps.** Para fazer alterações, clique em ![ Editar ícone ](../../media/m365-cc-sc-edit-icon.png) **Editar** na guia.

## <a name="use-the-microsoft-365-defender-portal-to-configure-third-party-phishing-simulations-in-the-advanced-delivery-policy"></a>Use o Microsoft 365 Defender portal para configurar simulações de phishing de terceiros na política de entrega avançada

1. No portal Microsoft 365 Defender, vá para **Email & Políticas** de Colaboração & Regras De acordo com a página Regras seção Entrega \>  \>  \>  \> **avançada**.

2. Na página **Entrega Avançada,** selecione a guia **Simulação de Phishing** e, em seguida, faça uma das seguintes etapas:
   - Clique ![ em Editar ícone ](../../media/m365-cc-sc-edit-icon.png) **Editar**.
   - Se não houver simulações de phishing configuradas, clique em **Adicionar**.

3. No **sub-sublinhado Editar simulação de phishing** de terceiros que é aberto, configure as seguintes configurações:

   - **Domínio** de envio : expanda essa configuração e insira pelo menos um domínio de endereço de email (por exemplo, contoso.com) clicando na caixa, inserindo um valor e pressionando Enter ou selecionando o valor exibido abaixo da caixa. Repita essa etapa quantas vezes forem necessárias. Você pode adicionar até 10 entradas.
   - **Envio de IP**: expanda essa configuração e insira pelo menos um endereço IPv4 válido é necessário clicando na caixa, inserindo um valor e pressionando Enter ou selecionando o valor exibido abaixo da caixa. Repita essa etapa quantas vezes forem necessárias. Você pode adicionar até 10 entradas. Os valores válidos são:
     - IP único: por exemplo, 192.168.1.1.
     - Intervalo ip: por exemplo, 192.168.0.1-192.168.0.254.
     - IP CIDR: Por exemplo, 192.168.0.1/25.
   - **URLs** de simulação para permitir : Expanda essa configuração e, opcionalmente, insira URLs específicas que fazem parte da sua campanha de simulação de phishing que não devem ser bloqueadas ou detonadas clicando na caixa, inserindo um valor e pressionando Enter ou selecionando o valor exibido abaixo da caixa. Você pode adicionar até 10 entradas.

   Para remover uma entrada existente, clique em Remover ![Ícone Remover](../../media/m365-cc-sc-remove-selection-icon.png) ao lado do valor.

4. Quando terminar, faça uma das seguintes etapas:
   - **Primeira vez:** clique **em Adicionar** e clique em **Fechar**.
   - **Editar existente**: clique em **Salvar** e clique em **Fechar**.

As entradas de simulação de phishing de terceiros que você configurou são exibidas na guia **Simulação de Phishing.** Para fazer alterações, clique em ![ Editar ícone ](../../media/m365-cc-sc-edit-icon.png) **Editar** na guia.

## <a name="additional-scenarios-that-require-filtering-bypass"></a>Cenários adicionais que exigem bypass de filtragem

Além dos dois cenários em que a política de entrega avançada pode ajudá-lo, há outros cenários que podem exigir que você ignore a filtragem:

- **Filtros de** terceiros : Se o  registro MX do seu domínio não apontar para o Office 365 (as mensagens são roteadas primeiro para outro [lugar),](secure-by-default.md) a segurança por padrão não está *disponível*. Se você quiser adicionar proteção, será necessário habilitar a Filtragem Aprimorada para Conectores (também conhecida como *lista de ignorar).* Para obter mais informações, consulte [Manage mail flow using a third-party cloud service with Exchange Online](/exchange/mail-flow-best-practices/manage-mail-flow-using-third-party-cloud). Se você não quiser Filtragem Aprimorada para Conectores, use regras de fluxo de emails (também conhecidas como regras de transporte) para ignorar a filtragem da Microsoft para mensagens que já foram avaliadas pela filtragem de terceiros. Para obter mais informações, [consulte Use mail flow rules to set the SCL in messages](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-set-scl.md).

- **Falsos positivos** em revisão : talvez você queira permitir temporariamente determinadas mensagens que ainda estão sendo analisadas pela Microsoft por meio de envios de administrador para relatar mensagens boas [conhecidas](admin-submission.md) que estão sendo marcadas incorretamente como ruins para a Microsoft (falsos positivos). Como com todas as substituições, é **_altamente recomendável_** que essas concessões sejam temporárias.

## <a name="exchange-online-powershell-procedures-for-secops-mailboxes-in-the-advanced-delivery-policy"></a>Exchange Online Procedimentos do PowerShell para caixas de correio SecOps na política de entrega avançada

No Exchange Online PowerShell, os elementos básicos das caixas de correio SecOps na política de entrega avançada são:

- **A política de substituição de SecOps**: Controlada pelos cmdlets **\* -SecOpsOverridePolicy.**
- **A regra de substituição SecOps**: Controlada pelos cmdlets **\* -SecOpsOverrideRule.**

Esse comportamento tem os seguintes resultados:

- Primeiro você cria a política e, em seguida, cria a regra que identifica a política à que a regra se aplica.
- Quando você remove uma política do PowerShell, a regra correspondente também é removida.
- Quando você remove uma regra do PowerShell, a política correspondente não é removida. Você precisa remover a política correspondente manualmente.

### <a name="use-powershell-to-configure-secops-mailboxes"></a>Usar o PowerShell para configurar caixas de correio SecOps

Configurar uma caixa de correio SecOps na política de entrega avançada no PowerShell é um processo de duas etapas:

1. Crie a política de substituição SecOps.
2. Crie a regra de substituição SecOps que especifica a política à que a regra se aplica.

#### <a name="step-1-use-powershell-to-create-the-secops-override-policy"></a>Etapa 1: Usar o PowerShell para criar a política de substituição de SecOps

Para criar a política de substituição SecOps, use a seguinte sintaxe:

```powershell
New-SecOpsOverridePolicy -Name SecOpsOverridePolicy -SentTo <EmailAddress1>,<EmailAddress2>,...<EmailAddressN>
```

**Observação**: independentemente do valor Name que você especificar, o nome da política será SecOpsOverridePolicy, portanto, é melhor usar esse valor.

Este exemplo cria a política de caixa de correio SecOps.

```powershell
New-SecOpsOverridePolicy -Name SecOpsOverridePolicy -SentTo secops@contoso.com
```

Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [New-SecOpsOverridePolicy](/powershell/module/exchange/new-secopsoverridepolicy).

#### <a name="step-2-use-powershell-to-create-the-secops-override-rule"></a>Etapa 2: Usar o PowerShell para criar a regra de substituição SecOps

Este exemplo cria a regra de caixa de correio SecOps com as configurações especificadas.

```powershell
New-SecOpsOverrideRule -Name SecOpsOverrideRule -Policy SecOpsOverridePolicy
```

**Observação**: **Independentemente do valor name especificado, o nome da regra será SecOpsOverrideRule, onde é um valor GUID exclusivo \<GUID\> \<GUID\> (por exemplo, 6fed4b63-3563-495d-a481-b24a311f8329).

Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [New-SecOpsOverrideRule](/powershell/module/exchange/new-secopsoverriderule).

### <a name="use-powershell-to-view-the-secops-override-policy"></a>Use o PowerShell para exibir a política de substituição SecOps

Este exemplo retorna informações detalhadas sobre a única e única política de caixa de correio SecOps.

```powershell
Get-SecOpsOverridePolicy
```

Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Get-SecOpsOverridePolicy](/powershell/module/exchange/get-secopsoverridepolicy).

### <a name="use-powershell-to-view-secops-override-rules"></a>Usar o PowerShell para exibir regras de substituição de SecOps

Este exemplo retorna informações detalhadas sobre regras de substituição de SecOps.

```powershell
Get-SecOpsOverrideRule
```

Embora o comando anterior deva retornar apenas uma regra, todas as regras que estão pendentes de exclusão também podem ser incluídas nos resultados.

Este exemplo identifica a regra válida (uma) e quaisquer regras inválidas.

```powershell
Get-SecOpsOverrideRule | Format-Table Name,Mode
```

Depois de identificar as regras inválidas, você pode removê-las usando o cmdlet **Remove-SecOpsOverrideRule** conforme descrito posteriormente [neste artigo](#use-powershell-to-remove-secops-override-rules).

Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Get-SecOpsOverrideRule](/powershell/module/exchange/get-secopsoverriderule)

### <a name="use-powershell-to-modify-the-secops-override-policy"></a>Usar o PowerShell para modificar a política de substituição de SecOps

Para modificar a política de substituição SecOps, use a seguinte sintaxe:

```powershell
Set-SecOpsOverridePolicy -Identity SecOpsOverridePolicy [-AddSentTo <EmailAddress1>,<EmailAddress2>,...<EmailAddressN>] [-RemoveSentTo <EmailAddress1>,<EmailAddress2>,...<EmailAddressN>]
```

Este exemplo adiciona secops2@contoso.com à política de substituição SecOps.

```powershell
Set-SecOpsOverridePolicy -Identity SecOpsOverridePolicy -AddSentTo secops2@contoso.com
```

**Observação**: se existir uma regra de substituição secOps associada e válida, os endereços de email na regra também serão atualizados.

Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Set-SecOpsOverridePolicy](/powershell/module/exchange/set-secopsoverridepolicy).

### <a name="use-powershell-to-modify-a-secops-override-rule"></a>Usar o PowerShell para modificar uma regra de substituição SecOps

O cmdlet **Set-SecOpsOverrideRule** não modifica os endereços de email na regra de substituição SecOps. Para modificar os endereços de email na regra de substituição SecOps, use o cmdlet **Set-SecOpsOverridePolicy.**

Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Set-SecOpsOverrideRule](/powershell/module/exchange/set-secopsoverriderule).

### <a name="use-powershell-to-remove-the-secops-override-policy"></a>Use o PowerShell para remover a política de substituição SecOps

Este exemplo remove a política de Caixa de Correio SecOps e a regra correspondente.

```powershell
Remove-SecOpsOverridePolicy -Identity SecOpsOverridePolicy
```

Para obter informações detalhadas sobre sintaxes e parâmetros, [consulte Remove-SecOpsOverridePolicy](/powershell/module/exchange/remove-secopsoverridepolicy).

### <a name="use-powershell-to-remove-secops-override-rules"></a>Usar o PowerShell para remover regras de substituição de SecOps

Para remover uma regra de substituição SecOps, use a seguinte sintaxe:

```powershell
Remove-SecOpsOverrideRule -Identity <RuleIdentity>
```

Este exemplo remove a regra de substituição SecOps especificada.

```powershell
Remove-SecOpsOverrideRule -Identity SecOpsOverrideRule6fed4b63-3563-495d-a481-b24a311f8329
```

Para obter informações detalhadas sobre sintaxes e parâmetros, [consulte Remove-SecOpsOverrideRule](/powershell/module/exchange/remove-secopsoverriderule).

## <a name="exchange-online-powershell-procedures-for-third-party-phishing-simulations-in-the-advanced-delivery-policy"></a>Exchange Online Procedimentos do PowerShell para simulações de phishing de terceiros na política de entrega avançada

No Exchange Online PowerShell, os elementos básicos de simulações de phishing de terceiros na política de entrega avançada são:

- **A política de substituição de simulação de phishing**: Controlada pelos cmdlets **\* -PhishSimOverridePolicy.**
- **A regra de substituição de simulação de phishing**: Controlada pelos cmdlets **\* -PhishSimOverrideRule.**

Esse comportamento tem os seguintes resultados:

- Primeiro você cria a política e, em seguida, cria a regra que identifica a política à que a regra se aplica.
- Você modifica as configurações da política e da regra separadamente.
- Quando você remove uma política do PowerShell, a regra correspondente também é removida.
- Quando você remove uma regra do PowerShell, a política correspondente não é removida. Você precisa remover a política correspondente manualmente.

### <a name="use-powershell-to-configure-third-party-phishing-simulations"></a>Usar o PowerShell para configurar simulações de phishing de terceiros

Configurar uma simulação de phishing de terceiros na política de entrega avançada no PowerShell é um processo de duas etapas:

1. Crie a política de substituição de simulação de phishing.
2. Crie a regra de substituição de simulação de phishing que especifica a política à que a regra se aplica.

#### <a name="step-1-use-powershell-to-create-the-phishing-simulation-override-policy"></a>Etapa 1: Usar o PowerShell para criar a política de substituição de simulação de phishing

Este exemplo cria a política de substituição de simulação de phishing.

```powershell
New-PhishSimOverridePolicy -Name PhishSimOverridePolicy
```

**Observação**: independentemente do valor Name especificado, o nome da política será PhishSimOverridePolicy, portanto, é melhor usar esse valor.

Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [New-PhishSimOverridePolicy](/powershell/module/exchange/new-phishsimoverridepolicy).

#### <a name="step-2-use-powershell-to-create-the-phishing-simulation-override-rule"></a>Etapa 2: usar o PowerShell para criar a regra de substituição de simulação de phishing

Use a seguinte sintaxe:

```powershell
New-PhishSimOverrideRule -Name PhishSimOverrideRule -Policy PhishSimOverridePolicy -SenderDomainIs <Domain1>,<Domain2>,...<DomainN> -SenderIpRanges <IPAddressEntry1>,<IPAddressEntry2>,...<IPAddressEntryN>
```

Independentemente do valor name especificado, o nome da regra será PhishSimOverrideRule, onde é um valor GUID exclusivo \<GUID\> \<GUID\> (por exemplo, a0eae53e-d755-4a42-9320-b9c6b55c5011).

Uma entrada de endereço IP válida é um dos seguintes valores:

- IP único: por exemplo, 192.168.1.1.
- Intervalo ip: por exemplo, 192.168.0.1-192.168.0.254.
- IP CIDR: Por exemplo, 192.168.0.1/25.

Este exemplo cria a regra de substituição de simulação de phishing com as configurações especificadas.

```powershell
New-PhishSimOverrideRule -Name PhishSimOverrideRule -Policy PhishSimOverridePolicy -SenderDomainIs fabrikam.com,wingtiptoys.com -SenderIpRanges 192.168.1.55
```

Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [New-PhishSimOverrideRule](/powershell/module/exchange/new-phishsimoverriderule).

### <a name="use-powershell-to-view-the-phishing-simulation-override-policy"></a>Usar o PowerShell para exibir a política de substituição de simulação de phishing

Este exemplo retorna informações detalhadas sobre a política de substituição de simulação de phishing única e única.

```powershell
Get-PhishSimOverridePolicy
```

Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Get-PhishSimOverridePolicy](/powershell/module/exchange/get-phishsimoverridepolicy).

### <a name="use-powershell-to-view-phishing-simulation-override-rules"></a>Usar o PowerShell para exibir regras de substituição de simulação de phishing

Este exemplo retorna informações detalhadas sobre regras de substituição de simulação de phishing.

```powershell
Get-PhishSimOverrideRule
```

Embora o comando anterior deva retornar apenas uma regra, todas as regras que estão pendentes de exclusão também podem ser incluídas nos resultados.

Este exemplo identifica a regra válida (uma) e quaisquer regras inválidas.

```powershell
Get-PhishSimOverrideRule | Format-Table Name,Mode
```

Depois de identificar as regras inválidas, você pode removê-las usando o cmdlet **Remove-PhisSimOverrideRule** conforme descrito posteriormente [neste artigo](#use-powershell-to-remove-phishing-simulation-override-rules).

Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Get-PhishSimOverrideRule](/powershell/module/exchange/get-phishsimoverriderule).

### <a name="use-powershell-to-modify-the-phishing-simulation-override-policy"></a>Usar o PowerShell para modificar a política de substituição de simulação de phishing

Para modificar a política de substituição de simulação de phishing, use a seguinte sintaxe:

```powershell
Set-PhishSimOverridePolicy -Identity PhishSimOverridePolicy [-Comment "<DescriptiveText>"] [-Enabled <$true | $false>]
```

Este exemplo desabilita a política de substituição de simulação de phishing.

```powershell
Set-PhishSimOverridePolicy -Identity PhishSimOverridePolicy -Enabled $false
```

Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Set-PhishSimOverridePolicy](/powershell/module/exchange/set-phishsimoverridepolicy).

### <a name="use-powershell-to-modify-a-phishing-simulation-override-rule"></a>Usar o PowerShell para modificar uma regra de substituição de simulação de phishing

Para modificar a regra de substituição de simulação de phishing, use a seguinte sintaxe:

```powershell
Set-PhishSimOverrideRule -Identity PhishSimOverrideRulea0eae53e-d755-4a42-9320-b9c6b55c5011 [-Comment "<DescriptiveText>"] [-AddSenderDomainIs <DomainEntry1>,<DomainEntry2>,...<DomainEntryN>] [-RemoveSenderDomainIs <DomainEntry1>,<DomainEntry2>,...<DomainEntryN>] [-AddSenderIpRanges <IPAddressEntry1>,<IPAddressEntry2>,...<IPAddressEntryN>] [-RemoveSenderIpRanges <IPAddressEntry1>,<IPAddressEntry2>,...<IPAddressEntryN>]
```

Este exemplo modifica a regra de substituição de simulação de phishing especificada com as seguintes configurações:

- Adicione a entrada de domínio blueyonderairlines.com.
- Remova a entrada de endereço IP 192.168.1.55.

Observe que essas alterações não afetam entradas existentes.

```powershell
Set-PhishSimOverrideRule -Identity PhishSimOverrideRulea0eae53e-d755-4a42-9320-b9c6b55c5011 -AddSenderDomainIs blueyonderairlines.com -RemoveSenderIpRanges 192.168.1.55
```

Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Set-PhishSimOverrideRule](/powershell/module/exchange/set-phishsimoverriderule).

### <a name="use-powershell-to-remove-a-phishing-simulation-override-policy"></a>Usar o PowerShell para remover uma política de substituição de simulação de phishing

Este exemplo remove a política de substituição de simulação de phishing e a regra correspondente.

```powershell
Remove-PhishSimOverridePolicy -Identity PhishSimOverridePolicy
```

Para obter informações detalhadas sobre sintaxes e parâmetros, [consulte Remove-PhishSimOverridePolicy](/powershell/module/exchange/remove-phishsimoverridepolicy).

### <a name="use-powershell-to-remove-phishing-simulation-override-rules"></a>Usar o PowerShell para remover regras de substituição de simulação de phishing

Para remover uma regra de substituição de simulação de phishing, use a seguinte sintaxe:

```powershell
Remove-PhishSimOverrideRule -Identity <RuleIdentity>
```

Este exemplo remove a regra de substituição de simulação de phishing especificada.

```powershell
Remove-PhishSimOverrideRule -Identity PhishSimOverrideRulea0eae53e-d755-4a42-9320-b9c6b55c5011
```

Para obter informações detalhadas sobre sintaxes e parâmetros, [consulte Remove-PhishSimOverrideRule](/powershell/module/exchange/remove-phishsimoverriderule).
