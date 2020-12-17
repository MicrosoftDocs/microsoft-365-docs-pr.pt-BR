---
title: Recomendações da Microsoft para as configurações de segurança do EOP e do defender para Office 365
keywords: Recomendações de segurança do Office 365, estrutura de política de remetente, relatórios e conformidade de mensagens baseados em domínio, DomainKeys identificadas por email, etapas, como funciona, linhas de base de segurança, linhas de base para o EOP, linhas de base para o defender para Office 365, configurar o defender para Office 365, configurar o EOP, configurar o defender para Office 365, definir a configuração de segurança
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
ms.date: ''
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 6f64f2de-d626-48ed-8084-03cc72301aa4
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
description: Quais são as práticas recomendadas para as configurações de segurança do Exchange Online Protection (EOP) e do defender para Office 365? Quais são as recomendações atuais para a proteção padrão? O que deve ser usado se você deseja ser mais estrito? E quais são os extras que você obtém se usa também o defender para o Office 365?
ms.openlocfilehash: d731b75e05dcecc513c72b390b106491f7601c71
ms.sourcegitcommit: 884ac262443c50362d0c3ded961d36d6b15d8b73
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/16/2020
ms.locfileid: "49698682"
---
# <a name="recommended-settings-for-eop-and-microsoft-defender-for-office-365-security"></a>Configurações recomendadas para a segurança do EOP e do Microsoft defender para Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

O **Exchange Online Protection (EOP)** é o núcleo de segurança para assinaturas do Microsoft 365 e ajuda a impedir que emails mal-intencionados cheguem às caixas de entrada do funcionário. Mas com ataques novos e mais sofisticados surgindo todos os dias, as proteções aprimoradas costumam ser necessárias. **Microsoft defender para Office 365** O plano 1 ou o plano 2 contêm recursos adicionais que dão aos administradores mais camadas de segurança, controle e investigação.

Embora possamos permitir que os administradores de segurança personalizem suas configurações de segurança, há dois níveis de segurança no EOP e o Microsoft defender para Office 365 que recomendamos: **padrão** e **estrito**. O ambiente e as necessidades de cada cliente são diferentes, mas acreditamos que esses níveis de filtragem ajudarão a impedir que emails indesejados cheguem à caixa de entrada dos seus funcionários na maioria das situações.

Para aplicar automaticamente as configurações padrão ou estritas aos usuários, consulte [predefinições de diretivas de segurança no EOP e Microsoft defender para Office 365](preset-security-policies.md).

> [!NOTE]
> A regra de lixo eletrônico precisa estar habilitada em caixas de correio para que a filtragem funcione corretamente. Ele é habilitado por padrão, mas você deve verificá-lo se a filtragem não estiver funcionando. Para obter mais informações, confira [Definir as configurações de lixo eletrônico nas caixas de correio do Exchange Online no Office 365](configure-junk-email-settings-on-exo-mailboxes.md).

Este artigo descreve as configurações padrão e também as configurações padrão e estritas recomendadas para ajudar a proteger seus usuários.

> [!TIP]
> O módulo de análise recomendada de proteção avançada contra ameaças do Office 365 (ORCA) para PowerShell pode ajudar você (administradores) a localizar os valores atuais dessas configurações. Especificamente, o cmdlet **Get-ORCAReport** gera uma avaliação de antispam, anti-phishing e outras configurações de higiene de mensagem. Você pode baixar o módulo ORCA em <https://www.powershellgallery.com/packages/ORCA/> .

## <a name="anti-spam-anti-malware-and-anti-phishing-protection-in-eop"></a>Anti-spam, Antimalware e proteção contra phishing no EOP

Anti-spam, Antimalware e anti-phishing são recursos do EOP que podem ser configurados pelos administradores. Recomendamos as seguintes configurações padrão ou estritas.

### <a name="eop-anti-spam-policy-settings"></a>Configurações de política antispam do EOP

Para criar e configurar políticas antispam, consulte [Configure anti-spam Policies in Office 365](configure-your-spam-filter-policies.md).

****

|Nome do recurso de segurança|Padrão|Padrão|Impede|Comentário|
|---|:---:|:---:|:---:|---|
|Ação de detecção de **spam** <p> _Spam_|**Mover mensagem para a pasta Lixo Eletrônico** <p> `MoveToJmf`|**Mover mensagem para a pasta Lixo Eletrônico** <p> `MoveToJmf`|**Mensagem em quarentena** <p> `Quarantine`||
|Ação de detecção de **spam de alta confiança** <p> _HighConfidenceSpamAction_|**Mover mensagem para a pasta Lixo Eletrônico** <p> `MoveToJmf`|**Mensagem em quarentena** <p> `Quarantine`|**Mensagem em quarentena** <p> `Quarantine`||
|Ação de detecção de **email de phishing** <p> _PhishSpamAction_|**Mover mensagem para a pasta Lixo Eletrônico** <p> `MoveToJmf`|**Mensagem em quarentena** <p> `Quarantine`|**Mensagem em quarentena** <p> `Quarantine`||
|Ação de detecção de **email phishing de alta confiança** <p> _HighConfidencePhishAction_|**Mensagem em quarentena** <p> `Quarantine`|**Mensagem em quarentena** <p> `Quarantine`|**Mensagem em quarentena** <p> `Quarantine`||
|Ação de detecção de **email em massa** <p> _BulkSpamAction_|**Mover mensagem para a pasta Lixo Eletrônico** <p> `MoveToJmf`|**Mover mensagem para a pasta Lixo Eletrônico** <p> `MoveToJmf`|**Mensagem em quarentena** <p> `Quarantine`||
|Limite de email em massa <p> _BulkThreshold_|7 |6 |4 |Para obter detalhes, consulte o [nível de reclamação em massa (BCL) no Office 365](bulk-complaint-level-values.md).|
|Período de retenção de quarentena <p> _QuarantineRetentionPeriod_|15 dias|30 dias|30 dias||
|**Dicas de segurança** <p> _InlineSafetyTipsEnabled_|Habilitado <p> `$true`|Habilitado <p> `$true`|Habilitado <p> `$true`||
|Remetentes permitidos <p> _AllowedSenders_|Nenhum|Nenhum|Nenhum||
|Domínios de remetente permitidos <p> _AllowedSenderDomains_|Nenhum|Nenhum|Nenhum|A adição de domínios à lista de remetentes permitidos é uma boa ideia. Os invasores podem enviar emails que seriam filtrados de outra forma. <p> Use a [inteligência de falsificação](learn-about-spoof-intelligence.md) no centro de conformidade & segurança da página **configurações antispam** para examinar todos os remetentes que estão falsificando endereços de email de remetente nos domínios de email da sua organização ou endereços de email de remetentes falsificados em domínios externos.|
|Remetentes bloqueados <p> _BlockedSenders_|Nenhum|Nenhum|Nenhum||
|Domínios de remetentes bloqueados <p> _BlockedSenderDomains_|Nenhum|Nenhum|Nenhum||
|**Habilitar notificações de spam para o usuário final** <p> _EnableEndUserSpamNotifications_|Desabilitado <p> `$false`|Habilitado <p> `$true`|Habilitado <p> `$true`||
|**Envie notificações de spam para o usuário final a cada (dias)** <p> _EndUserSpamNotificationFrequency_|3 dias|3 dias|3 dias||
|**ZAP de spam** <p> _SpamZapEnabled_|Habilitado <p> `$true`|Habilitado <p> `$true`|Habilitado <p> `$true`||
|**Phish de phishing** <p> _PhishZapEnabled_|Habilitado <p> `$true`|Habilitado <p> `$true`|Habilitado <p> `$true`||
|_MarkAsSpamBulkMail_|Habilitado|Habilitado|Habilitado|Essa configuração só está disponível no PowerShell.|
|

Há várias outras configurações avançadas de filtro de spam (ASF) em políticas antispam que estão em processo de ser preteridas. Mais informações sobre os cronogramas para a depreciação desses recursos serão comunicadas fora deste artigo.

Recomendamos que você **desative essas configurações de** ASF para os níveis **padrão** e **estrito** . Para obter mais informações sobre as configurações de ASF, consulte [Configurações avançadas de filtro de spam (ASF) no Office 365](advanced-spam-filtering-asf-options.md).

****

|Nome do recurso de segurança|Comentário|
|---|---|
|**Links de imagem para sites remotos** (_IncreaseScoreWithImageLinks_)||
|**Endereço IP numérico na URL** (_IncreaseScoreWithNumericIps_)||
|**UL redirecionar para outra porta** (_IncreaseScoreWithRedirectToOtherPort_)||
|**URL para sites. biz ou. info** (_IncreaseScoreWithBizOrInfoUrls_)||
|**Mensagens vazias** (_MarkAsSpamEmptyMessages_)||
|**JavaScript ou VBScript em HTML** (_MarkAsSpamJavaScriptInHtml_)||
|**Marcas de frame ou iframe em HTML** (_MarkAsSpamFramesInHtml_)||
|**Marcas de objeto em HTML** (_MarkAsSpamObjectTagsInHtml_)||
|**Inserir marcas em HTML** (_MarkAsSpamEmbedTagsInHtml_)||
|**Marcas de formulário em HTML** (_MarkAsSpamFormTagsInHtml_)||
|**Web bugs em HTML** (_MarkAsSpamWebBugsInHtml_)||
|**Aplicar lista de palavras confidenciais** (_MarkAsSpamSensitiveWordList_)||
|**Registro SPF: falha de hardware** (_MarkAsSpamSpfRecordHardFail_)||
|**Filtragem de ID de remetente condicional: falha de hardware** (_MarkAsSpamFromAddressAuthFail_)||
|**Inspersão de NDR** (_MarkAsSpamNdrBackscatter_)||
|

#### <a name="eop-outbound-spam-policy-settings"></a>Configurações de política de spam de saída do EOP

Para criar e configurar políticas de spam de saída, confira [Configure Outbound spam Filtering in Office 365](configure-the-outbound-spam-policy.md).

Para obter mais informações sobre os limites de envio padrão no serviço, consulte [enviando limites](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-1).

****

|Nome do recurso de segurança|Padrão|Padrão|Impede|Comentário|
|---|:---:|:---:|:---:|---|
|**Número máximo de destinatários por usuário: limite por hora externo** <p> _RecipientLimitExternalPerHour_|,0|500|400|O valor padrão 0 significa usar os padrões de serviço.|
|**Número máximo de destinatários por usuário: limite por hora interna** <p> _RecipientLimitInternalPerHour_|,0|1000|800|O valor padrão 0 significa usar os padrões de serviço.|
|**Número máximo de destinatários por usuário: limite diário** <p> _RecipientLimitPerDay_|,0|1000|800|O valor padrão 0 significa usar os padrões de serviço.|
|**Ação quando um usuário exceder os limites** <p> _ActionWhenThresholdReached_|**Impedir que o usuário envie email até o dia seguinte** <p> `BlockUserForToday`|**Impedir que o usuário envie emails** <p> `BlockUser`|**Impedir que o usuário envie emails** <p> `BlockUser`||
|

### <a name="eop-anti-malware-policy-settings"></a>Configurações de política antimalware do EOP

Para criar e configurar políticas Antimalware, consulte [Configure anti-malware Policies in Office 365](configure-anti-malware-policies.md).

****

|Nome do recurso de segurança|Padrão|Padrão|Impede|Comentário|
|---|:---:|:---:|:---:|---|
|**Deseja notificar destinatários se suas mensagens estiverem em quarentena?** <p> _Ação_|Não <p> _DeleteMessage_|Não <p> _DeleteMessage_|Não <p> _DeleteMessage_|Se o malware for detectado em um anexo de email, a mensagem será colocada em quarentena e só poderá ser liberada por um administrador.|
|**Filtro de tipos de anexo comuns** <p> _EnableFileFilter_|Desativada <p> `$false`|Ativada <p> `$true`|Habilitado <p> `$true`|Essa configuração coloca em quarentena mensagens que contêm anexos executáveis com base no tipo de arquivo, independentemente do conteúdo do anexo.|
|**Limpeza automática de malware zero-hora** <p> _ZapEnabled_|Habilitado <p> `$true`|Habilitado <p> `$true`|Habilitado <p> `$true`||
|**Notificar remetentes internos** da mensagem não entregue <p> _EnableInternalSenderNotifications_|Desabilitado <p> `$false`|Desabilitado <p> `$false`|Desabilitado <p> `$false`||
|**Notificar remetentes externos** da mensagem não entregue <p> _EnableExternalSenderNotifications_|Desabilitado <p> `$false`|Desabilitado <p> `$false`|Desabilitado <p> `$false`||
|

### <a name="eop-default-anti-phishing-policy-settings"></a>Configurações de política anti-phishing padrão do EOP

Para obter mais informações sobre essas configurações, consulte [configurações de spoof](set-up-anti-phishing-policies.md#spoof-settings). Para definir essas configurações, consulte [Configure anti-phishing Policies in EOP](configure-anti-phishing-policies-eop.md).

****

|Nome do recurso de segurança|Padrão|Padrão|Impede|Comentário|
|---|:---:|:---:|:---:|---|
|**Habilitar a proteção contra falsificação** <p> _EnableAntispoofEnforcement_|Habilitado <p> `$true`|Habilitado <p> `$true`|Habilitado <p> `$true`||
|**Habilitar remetente não autenticado** <p> _EnableUnauthenticatedSender_|Habilitado <p> `$true`|Habilitado <p> `$true`|Habilitado <p> `$true`|Adiciona um ponto de interrogação (?) à foto do remetente no Outlook para remetentes falsificados não identificados. Para obter mais informações, consulte [configurações de spoof em políticas anti-phishing](set-up-anti-phishing-policies.md).|
|**Se o email for enviado por alguém que não tenha permissão para falsificar seu domínio** <p> _AuthenticationFailAction_|**Mover mensagem para pastas de lixo eletrônico dos destinatários** <p> `MoveToJmf`|**Mover mensagem para pastas de lixo eletrônico dos destinatários** <p> `MoveToJmf`|**Colocar a mensagem em quarentena** <p> `Quarantine`|Essa configuração se aplica a remetentes bloqueados na [inteligência de falsificação](learn-about-spoof-intelligence.md).|
|

## <a name="microsoft-defender-for-office-365-security"></a>Segurança do Microsoft defender para Office 365

Outros benefícios de segurança são fornecidos com uma assinatura do Microsoft defender para Office 365. Para obter as notícias e informações mais recentes, você pode ver [o que há de novo no defender para Office 365](whats-new-in-office-365-atp.md).

> [!IMPORTANT]
>
> - A política anti-phishing padrão no Microsoft defender para Office 365 fornece [proteção contra falsificação](set-up-anti-phishing-policies.md#spoof-settings) e inteligência de caixa de correio para todos os destinatários. No entanto, os outros recursos de [proteção de representação](#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) disponíveis e [Configurações avançadas](#advanced-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) não estão configurados ou habilitados na política padrão. Para habilitar todos os recursos de proteção, modifique a política anti-phishing padrão ou crie políticas anti-phishing adicionais.
>
> - Não há políticas de links seguros padrão ou políticas de anexos seguros que protejam automaticamente todos os destinatários na organização. Para obter as proteções, você precisa criar pelo menos uma política de links seguros e uma política de anexos seguros.
>
> - [ATP para SharePoint, onedrive e Microsoft Teams](atp-for-spo-odb-and-teams.md) Protection e proteção de [documentos seguros](safe-docs.md) não têm dependências de políticas de links seguros.

Se sua assinatura incluir o Microsoft defender para Office 365 ou se você comprou o defender para Office 365 como um complemento, defina as seguintes configurações padrão ou estritas.

### <a name="anti-phishing-policy-settings-in-microsoft-defender-for-office-365"></a>Configurações de política anti-phishing no Microsoft defender para Office 365

Os clientes do EOP obtêm anti-phishing básico como descrito anteriormente, mas o Microsoft defender para Office 365 inclui mais recursos e controle para ajudar a prevenir, detectar e corrigir contra ataques. Para criar e configurar essas políticas, consulte [Configure anti-phishing Policies in defender for Office 365](configure-atp-anti-phishing-policies.md).

#### <a name="impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Configurações de representação em políticas anti-phishing no Microsoft defender para Office 365

Para obter mais informações sobre essas configurações, consulte [configurações de representação em políticas anti-phishing no Microsoft defender para Office 365](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365). Para definir essas configurações, consulte [Configure anti-phishing Policies in defender for Office 365](configure-atp-anti-phishing-policies.md).

****

|Nome do recurso de segurança|Padrão|Padrão|Impede|Comentário|
|---|:---:|:---:|:---:|---|
|Usuários protegidos: **Adicionar usuários para proteger** <p> _EnableTargetedUserProtection_ <p> _TargetedUsersToProtect_|Desabilitado <p> `$false` <p> nenhum|Habilitado <p> `$true` <p> \<list of users\>|Habilitado <p> `$true` <p> \<list of users\>|Dependendo da sua organização, é recomendável adicionar usuários (remetentes de mensagens) em funções principais. Os remetentes protegidos internamente podem ser o CEO, CFO e outros líderes seniores. Externamente, os remetentes protegidos podem incluir membros do Conselho ou seu Conselho de diretores.|
|Domínios protegidos: **incluir automaticamente os domínios que eu sou proprietário** <p> _EnableOrganizationDomainsProtection_|Desativada <p> `$false`|Ativada <p> `$true`|Habilitado <p> `$true`||
|Domínios protegidos: **incluir domínios personalizados** <p> _EnableTargetedDomainsProtection_ <p> _TargetedDomainsToProtect_|Desabilitado <p> `$false` <p> nenhum|Habilitado <p> `$true` <p> \<list of domains\>|Habilitado <p> `$true` <p> \<list of domains\>|Dependendo da sua organização, recomendamos adicionar domínios (domínios de remetente) que você não é proprietário, mas com as quais você interage com frequência.|
|Usuários protegidos: **se o email for enviado por um usuário representado** <p> _TargetedUserProtectionAction_|**Não aplicar nenhuma ação** <p> `NoAction`|**Colocar a mensagem em quarentena** <p> `Quarantine`|**Colocar a mensagem em quarentena** <p> `Quarantine`||
|Domínios protegidos: **se o email for enviado por um domínio representado** <p> _TargetedDomainProtectionAction_|**Não aplicar nenhuma ação** <p> `NoAction`|**Colocar a mensagem em quarentena** <p> `Quarantine`|**Colocar a mensagem em quarentena** <p> `Quarantine`||
|**Mostrar dica para usuários representados** <p> _EnableSimilarUsersSafetyTips_|Desativada <p> `$false`|Ativada <p> `$true`|Habilitado <p> `$true`||
|**Mostrar dica para domínios representados** <p> _EnableSimilarDomainsSafetyTips_|Desativada <p> `$false`|Ativada <p> `$true`|Habilitado <p> `$true`||
|**Mostrar dica para caracteres incomuns** <p> _EnableUnusualCharactersSafetyTips_|Desativada <p> `$false`|Ativada <p> `$true`|Habilitado <p> `$true`||
|**Habilitar o Mailbox Intelligence?** <p> _EnableMailboxIntelligence_|Habilitado <p> `$true`|Habilitado <p> `$true`|Habilitado <p> `$true`||
|**Habilitar a proteção de representação baseada em inteligência de caixa de correio?** <p> _EnableMailboxIntelligenceProtection_|Desativada <p> `$false`|Ativada <p> `$true`|Habilitado <p> `$true`||
|**Se o email for enviado por um usuário representado protegido por Mailbox Intelligence** <p> _MailboxIntelligenceProtectionAction_|**Não aplicar nenhuma ação** <p> `NoAction`|**Mover mensagem para pastas de lixo eletrônico dos destinatários** <p> `MoveToJmf`|**Colocar a mensagem em quarentena** <p> `Quarantine`||
|**Remetentes confiáveis** <p> _ExcludedSenders_|Nenhum|Nenhum|Nenhum|Dependendo da sua organização, recomendamos a adição de usuários que são marcados incorretamente como phishing devido à representação apenas e não a outros filtros.|
|**Domínios confiáveis** <p> _ExcludedDomains_|Nenhum|Nenhum|Nenhum|Dependendo da sua organização, recomendamos a adição de domínios que são marcados incorretamente como phishing devido à representação apenas e não a outros filtros.|
|

#### <a name="spoof-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Configurações de spoof em políticas anti-phishing no Microsoft defender para Office 365

Observe que essas são as mesmas configurações disponíveis nas configurações de [política antispam no EOP](#eop-anti-spam-policy-settings).

****

|Nome do recurso de segurança|Padrão|Padrão|Impede|Comentário|
|---|---|---|---|---|
|**Habilitar a proteção contra falsificação** <p> _EnableAntispoofEnforcement_|Habilitado <p> `$true`|Habilitado <p> `$true`|Habilitado <p> `$true`||
|**Habilitar remetente não autenticado** <p> _EnableUnauthenticatedSender_|Habilitado <p> `$true`|Habilitado <p> `$true`|Habilitado <p> `$true`|Adiciona um ponto de interrogação (?) à foto do remetente no Outlook para remetentes falsificados não identificados. Para obter mais informações, consulte [configurações de spoof em políticas anti-phishing](set-up-anti-phishing-policies.md).|
|**Se o email for enviado por alguém que não tenha permissão para falsificar seu domínio** <p> _AuthenticationFailAction_|**Mover mensagem para pastas de lixo eletrônico dos destinatários** <p> `MoveToJmf`|**Mover mensagem para pastas de lixo eletrônico dos destinatários** <p> `MoveToJmf`|**Colocar a mensagem em quarentena** <p> `Quarantine`|Essa configuração se aplica a remetentes bloqueados na [inteligência de falsificação](learn-about-spoof-intelligence.md).|
|

#### <a name="advanced-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Configurações avançadas em políticas anti-phishing no Microsoft defender para Office 365

Para obter mais informações sobre essa configuração, consulte [limites de phishing avançados nas políticas anti-phishing no Microsoft defender para Office 365](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365). Para definir essa configuração, consulte [Configure anti-phishing Policies in defender for Office 365](configure-atp-anti-phishing-policies.md).

****

|Nome do recurso de segurança|Padrão|Padrão|Impede|Comentário|
|---|:---:|:---:|:---:|---|
|**Limites avançados de phishing** <p> _PhishThresholdLevel_|**1-padrão** <p> `1`|**2-agressivo** <p> `2`|**3-mais agressivo** <p> `3`||
|

### <a name="safe-links-settings"></a>Configurações de links seguros

Links seguros no defender para Office 365 inclui configurações globais que se aplicam a todos os usuários incluídos em políticas de links seguros ativos e configurações específicas de cada política de links seguros. Para obter mais informações, consulte [links seguros no defender para Office 365](atp-safe-links.md).

#### <a name="global-settings-for-safe-links"></a>Configurações globais para links seguros

Para definir essas configurações, consulte [Configure Global Settings for Safe links in defender for Office 365](configure-global-settings-for-safe-links.md).

No PowerShell, você usa o cmdlet [set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365) para essas configurações.

****

|Nome do recurso de segurança|Padrão|Padrão|Impede|Comentário|
|---|:---:|:---:|:---:|---|
|**Usar links seguros no: aplicativos do Office 365** <p> _EnableSafeLinksForO365Clients_|Habilitado <p> `$true`|Habilitado <p> `$true`|Habilitado <p> `$true`|Use links seguros em aplicativos de área de trabalho do Office 365 e dispositivos móveis (iOS e Android) com suporte. Para obter mais informações, consulte [configurações de links seguros para aplicativos do Office 365](atp-safe-links.md#safe-links-settings-for-office-365-apps).|
|**Não rastrear quando os usuários clicarem em links seguros** <p> _TrackClicks_|Ativada <p> `$false`|Desativada <p> `$true`|Desabilitado <p> `$true`|A desativação dessa configuração (a definição de _TrackClicks_ como `$true` ) controla cliques do usuário em aplicativos do Office 365 com suporte.|
|**Não permitir que os usuários cliquem por meio de links seguros para a URL original** <p> _AllowClickThrough_|Habilitado <p> `$false`|Habilitado <p> `$false`|Habilitado <p> `$false`|Ativar essa configuração (a definição de _AllowClickThrough_ como `$false` ) impede o clique para a URL original em aplicativos do Office 365 com suporte.|
|

#### <a name="safe-links-policy-settings"></a>Configurações de política de links seguros

Para definir essas configurações, confira [Configurar políticas de links seguros no Microsoft defender para Office 365](set-up-atp-safe-links-policies.md).

No PowerShell, você usa os cmdlets [New-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/new-safelinkspolicy) e [set-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/set-safelinkspolicy) para essas configurações.

> [!NOTE]
> Conforme descrito anteriormente, não há uma política de links seguros padrão. Os valores na coluna padrão são os valores padrão em novas políticas de links seguros que você cria.

****

|Nome do recurso de segurança|Padrão|Padrão|Impede|Comentário|
|---|:---:|:---:|:---:|---|
|**Selecione a ação para URLs possivelmente mal-intencionadas desconhecidas em mensagens** <p> _IsEnabled_|Desativada <p> `$false`|Ativada <p> `$true`|Habilitado <p> `$true`||
|**Selecione a ação para URLs desconhecidas ou potencialmente mal-intencionadas no Microsoft Teams** <p> _EnableSafeLinksForTeams_|Desativada <p> `$false`|Ativada <p> `$true`|Habilitado <p> `$true`||
|**Aplicar verificação de URL em tempo real para links suspeitos e links que apontam para arquivos** <p> _ScanUrls_|Desativada <p> `$false`|Ativada <p> `$true`|Habilitado <p> `$true`||
|**Aguarde a conclusão da verificação de URL antes de entregar a mensagem** <p> _DeliverMessageAfterScan_|Desativada <p> `$false`|Ativada <p> `$true`|Habilitado <p> `$true`||
|**Aplicar links seguros a mensagens de email enviadas dentro da organização** <p> _EnableForInternalSenders_|Desativada <p> `$false`|Ativada <p> `$true`|Habilitado <p> `$true`||
|**Não rastrear cliques do usuário** <p> _DoNotTrackUserClicks_|Desabilitado <p> `$false`|Desabilitado <p> `$false`|Desabilitado <p> `$false`|A desativação dessa configuração (definindo _DoNotTrackUserClicks_ como `$false` ) controla os cliques dos usuários.|
|**Não permitir que os usuários cliquem através da URL original** <p> _DoNotAllowClickThrough_|Desativada <p> `$false`|Ativada <p> `$true`|Habilitado <p> `$true`|Ativar essa configuração (a definição de _DoNotAllowClickThrough_ como `$true` ) impede o clique até a URL original.|
|

### <a name="safe-attachments-settings"></a>Configurações de anexos seguros

Os anexos seguros no Microsoft defender para Office 365 inclui configurações globais que não têm relação com políticas de anexos seguros e configurações específicas de cada política de links seguros. Para obter mais informações, consulte [Safe Attachments in defender for Office 365](atp-safe-attachments.md).

#### <a name="global-settings-for-safe-attachments"></a>Configurações globais para anexos seguros

Para definir essas configurações, consulte [Ativar ATP para SharePoint, onedrive e Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md) e [documentos seguros no Microsoft 365 E5](safe-docs.md).

No PowerShell, você usa o cmdlet [set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365) para essas configurações.

****

|Nome do recurso de segurança|Padrão|Padrão|Impede|Comentário|
|---|:---:|:---:|:---:|---|
|**Ativar a ATP para SharePoint, OneDrive e Microsoft Teams** <p> _EnableATPForSPOTeamsODB_|Habilitado <p> `$true`|Habilitado <p> `$true`||
|**Ativar documentos seguros para clientes do Office** <p> _EnableSafeDocs_|Habilitado <p> `$true`|Habilitado <p> `$true`|Essa configuração só está disponível com as licenças de segurança do Microsoft 365 E5 ou Microsoft 365 e5. Para obter mais informações, consulte [documentos seguros no Microsoft defender para Office 365](safe-docs.md).|
|**Permitir que as pessoas cliquem no modo de exibição protegido, mesmo se os documentos seguros identificaram o arquivo como mal-intencionado** <p> _AllowSafeDocsOpen_|Desabilitado <p> `$false`|Desabilitado <p> `$false`|Essa configuração está relacionada a documentos seguros.|
|

#### <a name="safe-attachments-policy-settings"></a>Configurações de política de anexos seguros

Para definir essas configurações, consulte [Configurar políticas de anexos seguros no defender para Office 365](set-up-atp-safe-attachments-policies.md).

No PowerShell, você usa os cmdlets [New-SafeAttachmentPolicy](https://docs.microsoft.com/powershell/module/exchange/new-safeattachmentpolicy) e [set-SafeAttachmentPolicy](https://docs.microsoft.com/powershell/module/exchange/set-safelinkspolicy) para essas configurações.

> [!NOTE]
> Conforme descrito anteriormente, não há uma política de anexos seguros padrão. Os valores na coluna padrão são os valores padrão em novas políticas de anexos seguros que você cria.

****

|Nome do recurso de segurança|Padrão|Padrão|Impede|Comentário|
|---|:---:|:---:|:---:|---|
|**Resposta desconhecida de malware de anexos seguros** <p> _Ação_|Bloquear <p> `Block`|Bloquear <p> `Block`|Bloquear <p> `Block`||
|**Redirecionar o anexo na detecção** : **habilitar redirecionamento** <p> _Redirecionar_ <p> _RedirectAddress_|E nenhum endereço de email especificado. <p> `$true` <p> nenhum|Ativado e especifique um endereço de email. <p> `$true` <p> um endereço de email|Ativado e especifique um endereço de email. <p> `$true` <p> um endereço de email|Redirecionar mensagens para um administrador de segurança para revisão.|
|**Aplica a seleção acima se a verificação de malware para anexos expirar ou ocorrer erro.** <p> _ActionOnError_|Habilitado <p> `$true`|Habilitado <p> `$true`|Habilitado <p> `$true`||
|

## <a name="related-articles"></a>Artigos relacionados

- Você está procurando práticas recomendadas para **regras de fluxo de emails do Exchange (também conhecidas como regras de transporte**)? Consulte [práticas recomendadas para configurar regras de fluxo de email no Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/configuration-best-practices).

- Administradores e usuários podem enviar falsos positivos (emails satisfatórios marcados como defeituosos) e falsos negativos (emails inválidos permitidos) para a Microsoft para análise. Para mais informações, confira [Relatar mensagens e arquivos à Microsoft](report-junk-email-messages-to-microsoft.md).

- Use estes links para obter informações sobre como **Configurar** seu [serviço do EOP](set-up-your-eop-service.md)e **Configurar** o [Microsoft defender para Office 365](office-365-atp.md). Não se esqueça das orientações úteis em "[proteger contra ameaças no Office 365](protect-against-threats.md)".

- As **linhas de base de segurança do Windows** podem ser encontradas aqui: [onde posso obter as linhas de base de segurança?](https://docs.microsoft.com/windows/security/threat-protection/windows-security-baselines#where-can-i-get-the-security-baselines) para as opções de GPO/local e [usar as linhas de base de segurança para configurar os dispositivos Windows 10 no Intune](https://docs.microsoft.com/intune/protect/security-baselines) para segurança baseada no Intune. Por fim, uma comparação entre as linhas de base de segurança do Microsoft defender para ponto de extremidade e do Microsoft Intune está disponível em [Compare the Microsoft defender for Endpoint e as linhas de base de segurança do Windows Intune](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-machines-security-baseline#compare-the-microsoft-defender-atp-and-the-windows-intune-security-baselines).
