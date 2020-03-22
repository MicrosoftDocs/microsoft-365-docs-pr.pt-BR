---
title: Definir configurações de lixo eletrônico em caixas de correio do Exchange Online no Office 365
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.collection:
- M365-security-compliance
description: Os administradores podem aprender a definir as configurações de lixo eletrônico nas caixas de correio do Exchange Online. Muitas dessas configurações estão disponíveis para usuários no Outlook ou no Outlook na Web.
ms.openlocfilehash: 2b138830cff7337d7949606cc110ea8f7ae1c0ff
ms.sourcegitcommit: fce0d5cad32ea60a08ff001b228223284710e2ed
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/21/2020
ms.locfileid: "42897004"
---
# <a name="configure-junk-email-settings-on-exchange-online-mailboxes-in-office-365"></a>Definir configurações de lixo eletrônico em caixas de correio do Exchange Online no Office 365

As configurações antispam organizacionais do Exchange Online são controladas pela proteção do Exchange Online (EOP). Para obter mais informações, consulte [proteção antispam no Office 365](anti-spam-protection.md).

No entanto, há também configurações antispam específicas que os administradores podem configurar em caixas de correio individuais no Exchange Online:

- **Habilitar ou desabilitar a regra de lixo eletrônico**: a regra de lixo eletrônico é uma regra de caixa de entrada oculta chamada regra de lixo eletrônico habilitada por padrão em todas as caixas de correio. A regra de lixo eletrônico controla os seguintes recursos:

  - **Mover mensagens para a pasta lixo eletrônico com base nas políticas**antispam: quando uma política antispam é configurada com a ação **mover mensagem para a pasta lixo eletrônico** para uma veredicto de filtragem de spam, a regra de filtro de lixo eletrônico move a mensagem para a pasta lixo eletrônico após a mensagem ser entregue à caixa de correio. Para obter mais informações sobre a filtragem de spam verdicts em políticas antispam, consulte [Configure anti-spam Policies in Office 365](configure-your-spam-filter-policies.md). Da mesma forma, se a limpeza automática (ZAP) detectar spam ou phishing em uma mensagem já entregue, a regra de filtro de lixo eletrônico move a mensagem para a pasta lixo eletrônico para **mover a mensagem para a pasta lixo eletrônico** filtragem spam veredicto ações. Para saber mais sobre ZAP, confira [exclusão automática de zero horas (zap)-proteção contra spam e malware no Office 365](zero-hour-auto-purge.md).
  
  - **Configurações de lixo eletrônico que os usuários configuram para si mesmos no Outlook ou no Outlook na Web**: o _conjunto_ de listas seguras é a lista de remetentes confiáveis, a lista de destinatários confiáveis e a lista de remetentes bloqueados em cada caixa de correio. As entradas nessas listas determinam se a regra de lixo eletrônico move a mensagem para a caixa de entrada ou para a pasta lixo eletrônico. Os usuários podem configurar a coleção de lista segura para sua própria caixa de correio no Outlook ou no Outlook na Web (anteriormente conhecido como Outlook Web App). Os administradores podem configurar a coleção de lista segura na caixa de correio de qualquer usuário.

Quando a regra de lixo eletrônico está habilitada na caixa de correio, o EOP é capaz de mover mensagens para a pasta lixo eletrônico com base na ação de filtro de spam veredicto **mover mensagem para a pasta lixo** eletrônico ou para a lista de remetentes bloqueados na caixa de correio e impedir que mensagens sejam entregues à pasta lixo eletrônico (com base na lista de remetentes confiáveis na caixa de correio)

 Quando a regra de lixo eletrônico está desabilitada na caixa de correio, o EOP não pode mover mensagens para a pasta lixo eletrônico com base na ação veredicto de filtragem de spam **mover mensagem para a pasta lixo eletrônico ou para** a coleção de lista segura na caixa de correio.

Os administradores podem usar o PowerShell do Exchange Online para desabilitar, habilitar e exibir o status da regra de lixo eletrônico em caixas de correio. Os administradores também podem usar o PowerShell do Exchange Online para configurar entradas na coleção de lista segura em caixas de correio (a lista de remetentes confiáveis, a lista de destinatários confiáveis e a lista de remetentes bloqueados).

## <a name="what-do-you-need-to-know-before-you-begin"></a>O que você precisa saber antes de começar?

- Você só pode usar o PowerShell do Exchange Online para executar estes procedimentos. Para se conectar ao Exchange Online PowerShell, confira [Conectar ao Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).

- Você precisa ter permissões para poder executar estes procedimentos. Especificamente, você precisará da função de **destinatários de email** (atribuída aos grupos de função **Gerenciamento da organização**, gerenciamento de **destinatários**e **destinatários de email personalizados** por padrão) ou à função **Opções do usuário** (atribuída aos grupos de funções Gerenciamento da **organização** e **suporte técnico** por padrão). Para adicionar usuários a grupos de funções no Exchange Online, confira [modificar grupos de função no Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups). Observe que um usuário com permissões padrão pode executar esses mesmos procedimentos em suas próprias caixas de correio, desde que eles tenham [acesso ao PowerShell do Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online/disable-access-to-exchange-online-powershell).

- Em ambientes autônomos do EOP, onde o EOP protege as caixas de correio locais do Exchange, você precisa configurar regras de fluxo de emails (também conhecidas como regras de transporte) no Exchange local para traduzir o veredicto de filtragem de spam do EOP para que a regra de lixo eletrônico possa mover a mensagem para a pasta lixo eletrônico. Para obter detalhes, consulte [Configurar o EOP autônomo para fornecer spam à pasta lixo eletrônico em ambientes híbridos](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md).

## <a name="use-exchange-online-powershell-to-enable-or-disable-the-junk-email-rule-in-a-mailbox"></a>Usar o PowerShell do Exchange Online para habilitar ou desabilitar a regra de lixo eletrônico em uma caixa de correio

> [!NOTE]
> Você só pode usar o cmdlet **set-MailboxJunkEmailConfiguration** para desabilitar a regra de lixo eletrônico em uma caixa de correio aberta no Outlook (no modo cache do Exchange) ou no Outlook na Web. Se a caixa de correio não tiver sido aberta, você receberá `The Junk Email configuration couldn't be set. The user needs to sign in to Outlook Web App before they can modify their Safe Senders and Recipients or Blocked Senders lists.` o erro: se quiser suprimir esse erro para operações em massa, `-ErrorAction SlientlyContinue` você pode adicionar ao comando **set-MailboxJunkEmailConfiguration**

Para habilitar ou desabilitar a regra de lixo eletrônico em uma caixa de correio, use a seguinte sintaxe:

```PowerShell
Set-MailboxJunkEmailConfiguration -Identity <MailboxIdentity> -Enabled <$true | $false>
```

Este exemplo desabilita a regra de lixo eletrônico na caixa de correio de Ori Epstein.

```PowerShell
Set-MailboxJunkEmailConfiguration -Identity "Ori Epstein" -Enabled $false
```

Este exemplo desabilita a regra de lixo eletrônico em todas as caixas de correio de usuário da organização.

```PowerShell
$All = Get-Mailbox -RecipientTypeDetails UserMailbox -ResultSize Unlimited; $All | foreach {Set-MailboxJunkEmailConfiguration $_.Name -Enabled $false}
```

Para informações detalhadas de sintaxes e de parâmetros, consulte [set-MailboxJunkEmailConfiguration](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-mailboxjunkemailconfiguration).

 **Observações**:

- Se o usuário nunca abriu a caixa de correio, você pode receber um erro ao executar o comando anterior. Para suprimir esse erro para operações em massa `-ErrorAction SlientlyContinue` , adicione ao comando **set-MailboxJunkEmailConfiguration** .

- Mesmo que você desabilite a regra de lixo eletrônico, o filtro de lixo eletrônico do Outlook (dependendo de como ela é configurada) também pode determinar se uma mensagem é spam e se pode mover mensagens para a caixa de entrada ou pasta de lixo eletrônico com base no seu próprio spam veredicto e o conjunto de listas seguras em a caixa de correio. Para obter mais informações, consulte a seção [sobre configurações de lixo eletrônico no Outlook](#about-junk-email-settings-in-outlook) neste tópico.

### <a name="how-do-you-know-this-worked"></a>Como saber se funcionou?

Para verificar se você ativou ou desabilitou com êxito a regra de lixo eletrônico em uma caixa de correio, use qualquer um dos seguintes procedimentos:

- Substitua _ \<mailboxidentity pela\> _ pelo nome, alias ou endereço de email da caixa de correio e execute o seguinte comando para verificar o valor da propriedade **Enabled** :

  ```PowerShell
  Get-MailboxJunkEmailConfiguration -Identity "<MailboxIdentity>" | Format-List Enabled
  ```

- Substitua _ \<mailboxidentity pela\> _ pelo nome, alias ou endereço de email da caixa de correio e execute o seguinte comando para verificar o valor da propriedade **Enabled** da regra de lixo eletrônico.

  ```PowerShell
  Get-InboxRule "Junk E-mail Rule" -Mailbox "<MailboxIdentity>" -IncludeHidden
  ```

## <a name="use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox"></a>Usar o PowerShell do Exchange Online para configurar a coleção de lista segura em uma caixa de correio

A coleção de lista segura em uma caixa de correio inclui a lista de remetentes confiáveis, a lista de destinatários confiáveis e a lista de remetentes bloqueados. Por padrão, os usuários podem configurar a coleção de listas seguras em suas próprias caixas de correio no Outlook ou no Outlook na Web. Os administradores podem usar os parâmetros correspondentes no cmdlet **set-MailboxJunkEmailConfiguration** para configurar a coleção de lista segura na caixa de correio de um usuário. Esses parâmetros são descritos na tabela a seguir.

|||
|---|---|
|**Parâmetro no set-MailboxJunkEmailConfiguration**|**Configuração do Outlook na Web**|
|_BlockedSendersAndDomains_|**Mover email destes remetentes ou domínios para minha pasta lixo eletrônico**|
|_ContactsTrusted_|**Confiar em emails de meus contatos**|
|_TrustedListsOnly_|**Apenas confiar em emails de endereços em minha lista de remetentes confiáveis e domínios e listas de emails confiáveis**|
|_TrustedSendersAndDomains_<sup>\*</sup>|**Não mover email desses remetentes para a pasta lixo eletrônico**|
|

<sup>\*</sup>**Observações**:

- No Exchange Online, **as entradas de domínio** na lista de remetentes confiáveis ou no parâmetro _TrustedSendersAndDomains_ não são reconhecidas, portanto, somente use endereços de email. Em EOP autônomos com sincronização de diretório, as entradas de domínio não são sincronizadas por padrão, mas você pode habilitar a sincronização para domínios. Para obter mais informações, consulte [KB3019657](https://support.microsoft.com/help/3019657/domains-on-the-outlook-safe-senders-list-aren-t-recognized-by-exchange).

- Você não pode modificar diretamente a lista de destinatários confiáveis usando o cmdlet **set-MailboxJunkEmailConfiguration** (o parâmetro _TrustedRecipientsAndDomains_ não funciona). Você modifica a lista de remetentes confiáveis, e essas alterações são sincronizadas com a lista de destinatários confiáveis.

Para configurar a coleção de lista segura em uma caixa de correio, use a seguinte sintaxe:

```PowerShell
Set-MailboxJunkEmailConfiguration <MailboxIdentity> -BlockedSendersAndDomains <EmailAddressesOrDomains | $null> -ContactsTrusted <$true | $false> -TrustedListsOnly <$true | $false> -TrustedSendersAndDomains  <EmailAddresses | $null>
```

Para inserir vários valores e substituir quaisquer entradas existentes para os parâmetros _BlockedSendersAndDomains_ e _TrustedSendersAndDomains_ , use a seguinte sintaxe: `"<Value1>","<Value2>"...`. Para adicionar ou remover um ou mais valores sem afetar outras entradas existentes, use a seguinte sintaxe:`@{Add="<Value1>","<Value2>"... ; Remove="<Value3>","<Value4>...}`

Este exemplo configura as seguintes configurações para a coleção de lista segura na caixa de correio de Ori Epstein:

- Adicione o valor shopping@fabrikam.com à lista de remetentes bloqueados.

- Remova o valor chris@fourthcoffee.com da lista de remetentes confiáveis e da lista de destinatários confiáveis.

- Configura contatos na pasta contatos para serem tratados como remetentes confiáveis.

```PowerShell
Set-MailboxJunkEmailConfiguration "Ori Epstein" -BlockedSendersAndDomains @{Add="shopping@fabrikam.com"} -TrustedSendersAndDomains @{Remove="chris@fourthcoffee.com"} -ContactsTrusted $true
```

Este exemplo remove o domínio contoso.com da lista de remetentes bloqueados em todas as caixas de correio de usuário da organização.

```PowerShell
$All = Get-Mailbox -RecipientTypeDetails UserMailbox -ResultSize Unlimited; $All | foreach {Set-MailboxJunkEmailConfiguration $_.Name -BlockedSendersAndDomains @{Remove="contoso.com"}}
```

Para informações detalhadas de sintaxes e de parâmetros, consulte [set-MailboxJunkEmailConfiguration](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-mailboxjunkemailconfiguration).

 **Observações**:

- Se o usuário nunca abriu a caixa de correio, você pode receber um erro ao executar os comandos anteriores. Para suprimir esse erro para operações em massa `-ErrorAction SlientlyContinue` , adicione ao comando **set-MailboxJunkEmailConfiguration** .

- Mesmo se a regra de lixo eletrônico estiver desabilitada na caixa de correio, você ainda poderá configurar a coleção de listas seguras e o filtro de lixo eletrônico do Outlook poderá mover mensagens para a caixa de entrada ou para a pasta lixo eletrônico. Para obter mais informações, consulte a seção [sobre configurações de lixo eletrônico no Outlook](#about-junk-email-settings-in-outlook) neste tópico.

- O filtro de lixo eletrônico do Outlook tem configurações de coleção de listas seguras adicionais (por exemplo, **adicionar automaticamente pessoas que eu email à lista de remetentes confiáveis**). Para obter mais informações, consulte [usar filtros de lixo eletrônico para controlar quais mensagens você vê](https://support.office.com/article/274ae301-5db2-4aad-be21-25413cede077).

### <a name="how-do-you-know-this-worked"></a>Como saber se funcionou?

Para verificar se você configurou com êxito a coleção de lista segura em uma caixa de correio, use qualquer um dos seguintes procedimentos:

- Substitua _ \<mailboxidentity pela\> _ pelo nome, alias ou endereço de email da caixa de correio e execute o seguinte comando para verificar os valores de propriedade:

  ```PowerShell
  Get-MailboxJunkEmailConfiguration -Identity "<MailboxIdentity>" | Format-List trusted*,contacts*,blocked*
  ```

  Se a lista de valores for muito longa, use esta sintaxe:

  ```PowerShell
  (Get-MailboxJunkEmailConfiguration -Identity <MailboxIdentity>).BlockedSendersAndDomains
  ```

## <a name="about-junk-email-settings-in-outlook"></a>Sobre as configurações de lixo eletrônico no Outlook

Para habilitar, desabilitar e configurar as definições de filtro de lixo eletrônico do lado do cliente disponíveis no Outlook, use a política de grupo. Para obter mais informações, consulte [arquivos de modelo administrativo (admx/adml) e ferramenta de personalização do Office para o office 365 ProPlus, office 2019 e office 2016](https://www.microsoft.com/download/details.aspx?id=49030).

Quando o filtro de lixo eletrônico do Outlook está definido como o valor padrão **sem filtragem automática** nas **Opções**de **Opções** \> de **lixo** \> eletrônico **doméstica** \> , o Outlook não tenta classificar massages como spam, mas ainda usa a coleção de listas seguras (a lista de remetentes confiáveis, a lista de destinatários confiáveis e a lista de remetentes bloqueados) para mover mensagens para a pasta lixo eletrônico após a entrega. Para obter mais informações sobre essas configurações, consulte [visão geral do filtro de lixo eletrônico](https://support.office.com/article/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089).

Quando o filtro de lixo eletrônico do Outlook é definido como **baixo** ou **alto**, o filtro de lixo eletrônico do Outlook usa sua própria tecnologia de Filtro SmartScreen para identificar e mover spam para a pasta lixo eletrônico. Essa classificação de spam é separada do nível de confiança de spam (SCL) determinado pelo EOP. Na verdade, o Outlook ignora o SCL de EOP (a menos que EOP marcou a mensagem para ignorar a filtragem de spam) e usa seus próprios critérios para determinar se a mensagem é spam. Obviamente, é possível que o veredicto de spam do EOP e do Outlook seja o mesmo. Para obter mais informações sobre essas configurações, consulte [alterar o nível de proteção no filtro de lixo eletrônico](https://support.office.com/article/e89c12d8-9d61-4320-8c57-d982c8d52f6b).

> [!NOTE]
> Em novembro de 2016, a Microsoft parou de produzir atualizações de definição de spam para os filtros SmartScreen no Exchange e no Outlook. As definições existentes de spam do SmartScreen foram deixadas no local, mas sua eficácia provavelmente será prejudicada ao longo do tempo. Para obter mais informações, consulte [Substituição do suporte para SmartScreen no Outlook e no Exchange](https://techcommunity.microsoft.com/t5/exchange-team-blog/deprecating-support-for-smartscreen-in-outlook-and-exchange/ba-p/605332).

Portanto, o filtro de lixo eletrônico do Outlook pode usar a coleção de listas seguras da caixa de correio e sua própria classificação de spam para mover mensagens para a pasta lixo eletrônico, mesmo se a regra de lixo eletrônico estiver desabilitada na caixa de correio.

O Outlook e o Outlook na Web oferecem suporte à coleção SafeList. O conjunto de listas seguras é salvo na caixa de correio do Exchange Online, portanto, as alterações na coleção de listas seguras no Outlook aparecem no Outlook na Web e vice-versa.
