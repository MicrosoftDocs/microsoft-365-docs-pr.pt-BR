---
title: Definir as configurações de lixo eletrônico nas caixas de correio do Exchange Online
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.collection:
- M365-security-compliance
description: Os administradores podem aprender a configurar as configurações de lixo eletrônico em Exchange Online caixas de correio. Muitas dessas configurações estão disponíveis para os usuários Outlook ou Outlook na Web.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 5a401321645530d3d66ebcccd6b8aea27ce21d6e
ms.sourcegitcommit: 686f192e1a650ec805fe8e908b46ca51771ed41f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/24/2021
ms.locfileid: "52624796"
---
# <a name="configure-junk-email-settings-on-exchange-online-mailboxes"></a>Definir as configurações de lixo eletrônico nas caixas de correio do Exchange Online

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
- [Proteção do Exchange Online](exchange-online-protection-overview.md)
- [Plano 1 e plano 2 do Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Em Microsoft 365 com caixas de correio em Exchange Online, as configurações anti-spam organizacionais são controladas por Proteção do Exchange Online (EOP). Para obter mais informações, consulte [Proteção anti-spam no EOP](anti-spam-protection.md).

Porém, também há configurações anti-spam específicas que os administradores podem configurar em caixas de correio individuais em Exchange Online:

- **Habilitar** ou desabilitar a regra de lixo eletrônico : A regra de lixo eletrônico é uma regra de Caixa de Entrada oculta chamada Regra de Lixo Eletrônico que está habilitada por padrão em cada caixa de correio. A regra de lixo eletrônico controla os seguintes recursos:

  - Mover mensagens para a pasta Lixo Eletrônico com base em políticas **anti-spam**: quando uma política anti-spam é configurada com a ação **Mover** mensagem para a pasta Lixo Eletrônico para um veredito de filtragem de spam, a regra de filtro de lixo eletrônico move a mensagem para a pasta Lixo Eletrônico depois que a mensagem é entregue à caixa de correio. Para obter mais informações sobre vereditos de filtragem de spam em políticas anti-spam, consulte [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md). Da mesma forma, se a limpeza automática de hora zero (ZAP) determinar que uma mensagem entregue é spam ou phishing, a regra de filtro de lixo eletrônico move a mensagem para a pasta Lixo Eletrônico para **Mover** mensagem para Ações de filtragem de spam de pasta lixo eletrônico. Para obter mais informações sobre o ZAP, consulte [Zero-hour auto purge (ZAP) in Exchange Online](zero-hour-auto-purge.md).

  - Configurações de lixo eletrônico que os usuários configuram para si mesmos  no Outlook ou Outlook na Web : o conjunto de listas seguras é Cofre lista de **destinatários** do Cofre, a lista de destinatários do Cofre e a lista De envios bloqueados em cada caixa de correio. As entradas nessas listas determinam se a regra de lixo eletrônico move a mensagem para a Caixa de Entrada ou para a pasta Lixo Eletrônico. Os usuários podem configurar o conjunto de listas seguras para suas próprias caixas de correio Outlook ou Outlook na Web (anteriormente conhecido como Outlook Web App). Os administradores podem configurar o conjunto de listas seguras na caixa de correio de qualquer usuário.

Quando a regra de lixo eletrônico é habilitada na caixa de correio, o EOP  é capaz de mover mensagens para a pasta Lixo Eletrônico com base na ação de veredito de filtragem de spam Mover mensagem para a pasta Lixo Eletrônico ou a lista Remetentes Bloqueados na caixa de correio e impedir que mensagens são entregues na pasta Lixo Eletrônico (com base na lista de remetentes de Cofre na caixa de correio).

 Quando a regra de lixo eletrônico é desabilitada na caixa de correio, o EOP não pode mover mensagens para a pasta Lixo Eletrônico com base na ação de veredito de filtragem de spam **Mover** mensagem para a pasta Lixo Eletrônico ou o conjunto de listas seguras na caixa de correio.

Os administradores podem usar Exchange Online PowerShell para desabilitar, habilitar e exibir o status da regra de lixo eletrônico em caixas de correio. Os administradores também podem usar o Exchange Online PowerShell para configurar entradas na coleção de listas seguras em caixas de correio (a lista Cofre Senders, a lista Cofre Destinatários e a lista De envios bloqueados).

> [!NOTE]
> Mensagens de senders que os usuários adicionaram às suas próprias listas Cofre Senders ignorarão a filtragem de conexão como parte do EOP (o SCL é -1). Para impedir que os usuários adicionem entradas à sua lista Cofre Senders no Outlook, use a Política de Grupo conforme mencionado na seção Sobre as configurações de lixo eletrônico [na](#about-junk-email-settings-in-outlook) seção Outlook mais adiante neste artigo. A filtragem de política, a filtragem de conteúdo e o Defender Office 365 verificações ainda serão aplicadas às mensagens.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Do que você precisa saber para começar?

- Você só pode usar Exchange Online PowerShell para fazer os procedimentos neste artigo. Para se conectar ao PowerShell do Exchange Online, confira [Conectar ao PowerShell do Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).

- Você precisa ter permissões atribuídas Exchange Online antes de poder fazer os procedimentos neste artigo. Especificamente, você precisa da função **Destinatários** de Email (que é atribuída aos grupos de função Gerenciamento  da **Organização,** Gerenciamento de  Destinatários e Destinatários de Email **Personalizados** por padrão) ou a função Opções de Usuário (atribuída aos grupos de funções Gerenciamento da Organização e Help **Desk** por padrão).  Para adicionar usuários a grupos de função Exchange Online, consulte [Modificar grupos de função em Exchange Online](/Exchange/permissions-exo/role-groups#modify-role-groups). Observe que os usuários com permissões padrão podem fazer esses mesmos procedimentos em suas próprias caixas de correio, desde que tenham acesso [ao Exchange Online PowerShell](/powershell/exchange/disable-access-to-exchange-online-powershell).

- Em ambientes híbridos onde o EOP protege as caixas de correio locais do Exchange, você precisa configurar regras de fluxo de email (também conhecidas como regras de transporte) no Exchange local para traduzir o veredito de filtragem de spam do EOP para que a regra de lixo eletrônico possa mover a mensagem para o Lixo Pasta de email. Para obter detalhes, confira [Configurar o EOP para enviar spam para a pasta Lixo Eletrônico em ambientes híbridos](/exchange/standalone-eop/configure-eop-spam-protection-hybrid).

- Cofre Os destinatários de caixas de correio compartilhadas não são sincronizados com o Azure AD e o EOP por design.

## <a name="use-exchange-online-powershell-to-enable-or-disable-the-junk-email-rule-in-a-mailbox"></a>Use Exchange Online PowerShell para habilitar ou desabilitar a regra de lixo eletrônico em uma caixa de correio

> [!NOTE]
> Você só pode usar o cmdlet **Set-MailboxJunkEmailConfiguration** para desabilitar a regra de lixo eletrônico em uma caixa de correio que foi aberta no Outlook (no modo cache Exchange) ou Outlook na Web. Se a caixa de correio não tiver sido aberta, você receberá o erro: se quiser suprimir esse erro para operações em massa, você poderá adicionar ao comando `The Junk Email configuration couldn't be set. The user needs to sign in to Outlook Web App before they can modify their Safe Senders and Recipients or Blocked Senders lists.` `-ErrorAction SilentlyContinue` **Set-MailboxJunkEmailConfiguration.**

Para habilitar ou desabilitar a regra de lixo eletrônico em uma caixa de correio, use a seguinte sintaxe:

```PowerShell
Set-MailboxJunkEmailConfiguration -Identity <MailboxIdentity> -Enabled <$true | $false>
```

Este exemplo desabilita a regra de lixo eletrônico na caixa de correio de Ori Epstein.

```PowerShell
Set-MailboxJunkEmailConfiguration -Identity "Ori Epstein" -Enabled $false
```

Este exemplo desabilita a regra de lixo eletrônico em todas as caixas de correio de usuário na organização.

```PowerShell
$All = Get-Mailbox -RecipientTypeDetails UserMailbox -ResultSize Unlimited; $All | foreach {Set-MailboxJunkEmailConfiguration $_.Name -Enabled $false}
```

Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Set-MailboxJunkEmailConfiguration](/powershell/module/exchange/set-mailboxjunkemailconfiguration).

> [!NOTE]
>
> - Se o usuário nunca tiver aberto sua caixa de correio, você poderá receber um erro ao executar o comando anterior. Para suprimir esse erro para operações em massa, adicione `-ErrorAction SilentlyContinue` **ao comando Set-MailboxJunkEmailConfiguration.**
>
> - Mesmo que você desabilite a regra de lixo eletrônico, o Filtro de Lixo Eletrônico do Outlook (dependendo de como ele está configurado) também pode determinar se uma mensagem é spam e pode mover mensagens para a pasta Caixa de Entrada ou Lixo Eletrônico com base em seu próprio veredito de spam e na coleção de listas seguras na caixa de correio. Para obter mais informações, consulte a [seção Sobre configurações](#about-junk-email-settings-in-outlook) de lixo eletrônico Outlook neste artigo.

### <a name="how-do-you-know-this-worked"></a>Como saber se funcionou?

Para verificar se você habilitar ou desabilitar com êxito a regra de lixo eletrônico em uma caixa de correio, use qualquer um dos seguintes procedimentos:

- Substitua pelo nome, alias ou endereço de email da caixa de correio e execute o seguinte comando para verificar o _\<MailboxIdentity\>_ **valor da propriedade Enabled:**

  ```PowerShell
  Get-MailboxJunkEmailConfiguration -Identity "<MailboxIdentity>" | Format-List Enabled
  ```

## <a name="use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox"></a>Use Exchange Online PowerShell para configurar o conjunto de listas seguras em uma caixa de correio

A coleção de listas seguras em uma caixa de correio inclui a lista Cofre de Cofre, a lista Cofre destinatários e a lista De envios bloqueados. Por padrão, os usuários podem configurar o conjunto de listas seguras em suas próprias caixas de correio Outlook ou Outlook na Web. Os administradores podem usar os parâmetros correspondentes no cmdlet **Set-MailboxJunkEmailConfiguration** para configurar o conjunto de listas seguras na caixa de correio de um usuário. Esses parâmetros são descritos na tabela a seguir.

****

|Parâmetro no Set-MailboxJunkEmailConfiguration|Outlook na configuração da Web|
|---|---|
|_BlockedSendersAndDomains_|**Mover emails desses senders ou domínios para minha pasta Lixo Eletrônico**|
|_ContactsTrusted_|**Confiar emails de meus contatos**|
|_TrustedListsOnly_|**Confiar somente emails de endereços na minha lista de Cofre e domínios e Cofre de email**|
|_TrustedSendersAndDomains_<sup>\*</sup>|**Não mova emails desses envios para minha pasta Lixo Eletrônico**|
|

<sup>\*</sup>**Observações**:

- No **Exchange Online,** entradas de domínio na lista Cofre Senders ou _no parâmetro TrustedSendersAndDomains_ não são reconhecidas, portanto, use apenas endereços de email. No EOP autônomo com sincronização de diretório, as entradas de domínio não são sincronizadas por padrão, mas você pode habilitar a sincronização para domínios. Para obter mais informações, consulte [KB3019657](https://support.microsoft.com/help/3019657).

- Você não pode modificar diretamente a lista Cofre Destinatários usando o cmdlet **Set-MailboxJunkEmailConfiguration** (o parâmetro _TrustedRecipientsAndDomains_ não funciona). Você modifica a Cofre de envios e essas alterações são sincronizadas com a lista Cofre Destinatários.

Para configurar o conjunto de listas seguras em uma caixa de correio, use a seguinte sintaxe:

```PowerShell
Set-MailboxJunkEmailConfiguration <MailboxIdentity> -BlockedSendersAndDomains <EmailAddressesOrDomains | $null> -ContactsTrusted <$true | $false> -TrustedListsOnly <$true | $false> -TrustedSendersAndDomains  <EmailAddresses | $null>
```

Para inserir vários valores e substituir quaisquer entradas existentes para os _parâmetros BlockedSendersAndDomains_ e _TrustedSendersAndDomains,_ use a seguinte sintaxe: `"<Value1>","<Value2>"...` . Para adicionar ou remover um ou mais valores sem afetar outras entradas existentes, use a seguinte sintaxe: `@{Add="<Value1>","<Value2>"... ; Remove="<Value3>","<Value4>...}`

Este exemplo configura as seguintes configurações para a coleção safelist na caixa de correio de Ori Epstein:

- Adicione o valor shopping@fabrikam.com à lista De envios bloqueados.

- Remova o valor chris@fourthcoffee.com da lista Cofre Senders e a lista Cofre Destinatários.

- Configura contatos na pasta Contatos a serem tratados como senders confiáveis.

```PowerShell
Set-MailboxJunkEmailConfiguration "Ori Epstein" -BlockedSendersAndDomains @{Add="shopping@fabrikam.com"} -TrustedSendersAndDomains @{Remove="chris@fourthcoffee.com"} -ContactsTrusted $true
```

Este exemplo remove o domínio contoso.com da lista De envios bloqueados em todas as caixas de correio de usuário na organização.

```PowerShell
$All = Get-Mailbox -RecipientTypeDetails UserMailbox -ResultSize Unlimited; $All | foreach {Set-MailboxJunkEmailConfiguration $_.Name -BlockedSendersAndDomains @{Remove="contoso.com"}}
```

Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Set-MailboxJunkEmailConfiguration](/powershell/module/exchange/set-mailboxjunkemailconfiguration).

> [!NOTE]
>
> - Se o usuário nunca tiver aberto a caixa de correio, você poderá receber um erro ao executar os comandos anteriores. Para suprimir esse erro para operações em massa, adicione `-ErrorAction SilentlyContinue` **ao comando Set-MailboxJunkEmailConfiguration.**
>
> - Mesmo que Outlook regra de lixo eletrônico esteja desabilitada na caixa de correio, você ainda poderá configurar o conjunto de listas seguras. O Filtro de Lixo Eletrônico do Outlook pode mover mensagens para a Caixa de Entrada ou para a pasta Lixo Eletrônico. Para obter mais informações, consulte a [seção Sobre configurações](#about-junk-email-settings-in-outlook) de lixo eletrônico Outlook neste artigo.
>
> - O Outlook filtro de lixo eletrônico tem configurações adicionais de conjunto de listas seguras (por exemplo, adicionar automaticamente pessoas que eu email para a lista Cofre **Senders).** Para obter mais informações, [consulte Use Junk Email Filters to control which messages you see](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077).

### <a name="how-do-you-know-this-worked"></a>Como saber se funcionou?

Para verificar se você configurou com êxito o conjunto de listas seguras em uma caixa de correio, use qualquer um dos seguintes procedimentos:

- Substitua pelo nome, alias ou endereço de email da caixa de correio e execute o seguinte comando _\<MailboxIdentity\>_ para verificar os valores da propriedade:

  ```PowerShell
  Get-MailboxJunkEmailConfiguration -Identity "<MailboxIdentity>" | Format-List trusted*,contacts*,blocked*
  ```

  Se a lista de valores for muito longa, use esta sintaxe:

  ```PowerShell
  (Get-MailboxJunkEmailConfiguration -Identity <MailboxIdentity>).BlockedSendersAndDomains
  ```

## <a name="about-junk-email-settings-in-outlook"></a>Sobre as configurações de lixo eletrônico no Outlook

Para habilitar, desabilitar e configurar as configurações do Filtro de Lixo Eletrônico do lado do cliente que estão disponíveis no Outlook, use a Política de Grupo. Para obter mais informações, consulte Arquivos de Modelo Administrativo (ADMX/ADML) e Ferramenta de Personalização do Office para [Microsoft 365 Apps para Grandes Empresas, Office 2019 e Office 2016](https://www.microsoft.com/download/details.aspx?id=49030) e Como implantar configurações de lixo eletrônico, como a lista de Cofre [Senders,](https://support.microsoft.com/help/2252421)usando a Política de Grupo .

Quando o filtro de lixo eletrônico do  Outlook é definido  como o valor padrão Nenhuma filtragem automática em Home \> **Junk** \> **E-Mail Options** , o Outlook não tenta classificar as massagens como spam, mas ainda usa a coleção safelist (a lista de remetentes do Cofre, a lista de destinatários do Cofre e a lista \> remetentes bloqueados) para mover mensagens para a pasta Lixo Eletrônico após a entrega. Para obter mais informações sobre essas configurações, consulte [Overview of the Junk Email Filter](https://support.microsoft.com/office/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089).

Quando o filtro Outlook lixo eletrônico  é definido como Baixo ou Alto **,** o filtro de lixo eletrônico Outlook usa sua própria tecnologia de filtro SmartScreen para identificar e mover spam para a pasta Lixo Eletrônico. Essa classificação de spam é separada do nível de confiança de spam (SCL) determinado pelo EOP. Na verdade, Outlook ignora a SCL do EOP (a menos que o EOP tenha marcado a mensagem para ignorar a filtragem de spam) e usa seus próprios critérios para determinar se a mensagem é spam. Obviamente, é possível que o veredito de spam do EOP e Outlook seja o mesmo. Para obter mais informações sobre essas configurações, consulte [Change the level of protection in the Junk Email Filter](https://support.microsoft.com/office/e89c12d8-9d61-4320-8c57-d982c8d52f6b).

> [!NOTE]
> Em novembro de 2016, a Microsoft parou de produzir atualizações de definição de spam para os filtros SmartScreen Exchange e Outlook. As definições de spam do SmartScreen existentes foram deixadas no lugar, mas sua eficácia provavelmente se degrada com o tempo. Para obter mais informações, consulte [Substituição do suporte para SmartScreen no Outlook e no Exchange](https://techcommunity.microsoft.com/t5/exchange-team-blog/deprecating-support-for-smartscreen-in-outlook-and-exchange/ba-p/605332).

Portanto, o Outlook filtro de lixo eletrônico é capaz de usar a coleção de listas seguras da caixa de correio e sua própria classificação de spam para mover mensagens para a pasta Lixo Eletrônico, mesmo que a regra de lixo eletrônico seja desabilitada na caixa de correio.

Outlook e Outlook na Web suportam a coleção safelist. A coleção safelist é salva na caixa de correio Exchange Online, portanto, as alterações na coleção safelist no Outlook aparecem em Outlook na Web e vice-versa.

## <a name="limits-for-junk-email-settings"></a>Limites para configurações de lixo eletrônico

A coleção safelist (a lista Cofre Senders, Cofre de destinatários e a lista de Destinatários Bloqueados) armazenada na caixa de correio do usuário também é sincronizada com o EOP. Com a sincronização de diretório, a coleção safelist é sincronizada com o Azure AD.

- O conjunto de listas seguras na caixa de correio do usuário tem um limite de 510 KB, que inclui todas as listas, além de configurações adicionais de filtro de lixo eletrônico. Se um usuário exceder esse limite, ele receberá um erro Outlook com esta aparência:

  > Não é possível adicionar às listas de lixo eletrônico do servidor. Você está acima do tamanho permitido no servidor. O filtro lixo eletrônico no servidor será desabilitado até que suas listas de lixo eletrônico tenham sido reduzidas ao tamanho permitido pelo servidor.

  Para obter mais informações sobre esse limite e como alterá-lo, consulte [KB2669081](https://support.microsoft.com/help/2669081).

- A coleção de listas seguras sincronizadas no EOP tem os seguintes limites de sincronização:

  - 1024 entradas totais na lista Cofre Senders, a lista Cofre Destinatários e contatos externos se o email de confiança de meus **contatos** estiver habilitado.
  - 500 entradas totais na lista De envios bloqueados e na lista Domínios Bloqueados.

  Quando o limite de entrada 1024 é atingido, as seguintes coisas ocorrem:

  - A lista deixa de aceitar entradas no PowerShell e Outlook na Web, mas nenhum erro é exibido.

    Outlook usuários podem continuar a adicionar mais de 1.024 entradas até atingirem o limite Outlook de 510 KB. Outlook pode usar essas entradas adicionais, desde que um filtro EOP não bloqueie a mensagem antes da entrega à caixa de correio (regras de fluxo de emails, anti-spoofing, etc.).

- Com a sincronização de diretório, as entradas são sincronizadas com o Azure AD na seguinte ordem:

  1. Contatos de email se **o email de confiança de meus contatos** estiver habilitado.
  2. A Cofre sender e a lista de destinatários Cofre são combinadas, de duplicadas e ordenadas em ordem alfabética sempre que uma alteração é feita para as primeiras entradas 1024.

  As primeiras 1024 entradas são usadas e as informações relevantes são carimbadas nos headers da mensagem.

  As entradas com mais de 1024 que não foram sincronizadas com o Azure AD são processadas pelo Outlook (não Outlook na Web) e nenhuma informação é carimbada nos headers da mensagem.

Como você pode ver, a habilitação do **email** de confiança a partir da configuração de meus contatos reduz o número de Cofre destinatários Cofre que podem ser sincronizados. Se isso for uma preocupação, recomendamos usar a Política de Grupo para desativar esse recurso:

- Nome do arquivo: outlk16.opax
- Configuração de política: **Confiar emails de contatos**