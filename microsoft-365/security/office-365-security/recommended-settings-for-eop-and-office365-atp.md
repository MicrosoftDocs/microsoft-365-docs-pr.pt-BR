---
title: Recomendações da Microsoft para EOP e Office 365 configurações de segurança de ATP, recomendações, estrutura de política de remetente, relatórios e conformidade de mensagens baseadas em domínio, DomainKeys identificadas por email, etapas, como funciona, as linhas de base de segurança, as linhas de base para o EOP, as linhas de base para ATP, configurar ATP, configurar a configuração de segurança
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
description: Quais são as práticas recomendadas para as configurações de segurança do Exchange Online Protection (EOP) e da proteção avançada contra ameaças (ATP)? Quais são as recomendações atuais para a proteção padrão? O que deve ser usado se você deseja ser mais estrito? E quais são os extras obtidos se você também usa a proteção avançada contra ameaças (ATP)?
ms.openlocfilehash: af0e295b9b9ed7e71747556909cb181aa5af4833
ms.sourcegitcommit: 3a0accd616ca94d6ba7f50e502552b45e9661a95
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/03/2020
ms.locfileid: "48350802"
---
# <a name="recommended-settings-for-eop-and-office-365-atp-security"></a>Configurações recomendadas para o EOP e a segurança ATP do Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

O **Exchange Online Protection (EOP)** é o núcleo de segurança para assinaturas do Microsoft 365 e ajuda a impedir que emails mal-intencionados cheguem às caixas de entrada do funcionário. Mas com ataques novos e mais sofisticados surgindo todos os dias, as proteções aprimoradas costumam ser necessárias. **Proteção avançada contra ameaças do Office 365 (ATP)** O plano ATP 1 ou a ATP plano 2 contêm recursos adicionais que dão aos administradores mais camadas de segurança, controle e investigação.

Embora possamos permitir que os administradores de segurança personalizem suas configurações de segurança, há dois níveis de segurança no EOP e no Office 365 ATP que recomendamos: **padrão** e **estrito**. O ambiente e as necessidades de cada cliente são diferentes, mas acreditamos que esses níveis de filtragem ajudarão a impedir que emails indesejados cheguem à caixa de entrada dos seus funcionários na maioria das situações.

Para aplicar automaticamente as configurações padrão ou estritas aos usuários, confira [políticas de segurança predefinidas no EOP e no Office 365 ATP](preset-security-policies.md).

**Observação**: a regra de lixo eletrônico precisa estar habilitada em caixas de correio para que a filtragem funcione corretamente. Ele é habilitado por padrão, mas você deve verificá-lo se a filtragem não estiver funcionando. Para obter mais informações, confira [Definir as configurações de lixo eletrônico nas caixas de correio do Exchange Online no Office 365](configure-junk-email-settings-on-exo-mailboxes.md).

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
|Ação de detecção de **spam** <br/><br/> _Spam_|**Mover mensagem para a pasta Lixo Eletrônico** <br/><br/> `MoveToJmf`|**Mover mensagem para a pasta Lixo Eletrônico** <br/><br/> `MoveToJmf`|**Mensagem em quarentena** <br/><br/> `Quarantine`||
|Ação de detecção de **spam de alta confiança** <br/><br/> _HighConfidenceSpamAction_|**Mover mensagem para a pasta Lixo Eletrônico** <br/><br/> `MoveToJmf`|**Mensagem em quarentena** <br/><br/> `Quarantine`|**Mensagem em quarentena** <br/><br/> `Quarantine`||
|Ação de detecção de **email de phishing** <br/><br/> _PhishSpamAction_|**Mover mensagem para a pasta Lixo Eletrônico** <br/><br/> `MoveToJmf`|**Mensagem em quarentena** <br/><br/> `Quarantine`|**Mensagem em quarentena** <br/><br/> `Quarantine`||
|Ação de detecção de **email phishing de alta confiança** <br/><br/> _HighConfidencePhishAction_|**Mensagem em quarentena** <br/><br/> `Quarantine`|**Mensagem em quarentena** <br/><br/> `Quarantine`|**Mensagem em quarentena** <br/><br/> `Quarantine`||
|Ação de detecção de **email em massa** <br/><br/> _BulkSpamAction_|**Mover mensagem para a pasta Lixo Eletrônico** <br/><br/> `MoveToJmf`|**Mover mensagem para a pasta Lixo Eletrônico** <br/><br/> `MoveToJmf`|**Mensagem em quarentena** <br/><br/> `Quarantine`||
|Limite de email em massa <br/><br/> _BulkThreshold_|7 |6 |4 |Para obter detalhes, consulte o [nível de reclamação em massa (BCL) no Office 365](bulk-complaint-level-values.md).|
|Período de retenção de quarentena <br/><br/> _QuarantineRetentionPeriod_|15 dias|30 dias|30 dias||
|**Dicas de segurança** <br/><br/> _InlineSafetyTipsEnabled_|Habilitado <br/><br/> `$true`|Habilitado <br/><br/> `$true`|Habilitado <br/><br/> `$true`||
|Remetentes permitidos <br/><br/> _AllowedSenders_|Nenhum|Nenhum|Nenhum||
|Domínios de remetente permitidos <br/><br/> _AllowedSenderDomains_|Nenhum|Nenhum|Nenhum|Adicionar domínios que você possui (_domínios aceitos_) à lista de remetentes permitidos é uma boa ideia. Os invasores podem enviar emails que seriam filtrados de outra forma. <br/><br/> Use a [inteligência de falsificação](learn-about-spoof-intelligence.md) no centro de conformidade & segurança da página **configurações antispam** para examinar todos os remetentes que estão falsificando endereços de email de remetente nos domínios de email da sua organização ou endereços de email de remetentes falsificados em domínios externos.|
|Remetentes bloqueados <br/><br/> _BlockedSenders_|Nenhum|Nenhum|Nenhum||
|Domínios de remetentes bloqueados <br/><br/> _BlockedSenderDomains_|Nenhum|Nenhum|Nenhum||
|**Habilitar notificações de spam para o usuário final** <br/><br/> _EnableEndUserSpamNotifications_|Desabilitado <br/><br/> `$false`|Habilitado <br/><br/> `$true`|Habilitado <br/><br/> `$true`||
|**Envie notificações de spam para o usuário final a cada (dias)** <br/><br/> _EndUserSpamNotificationFrequency_|3 dias|3 dias|3 dias||
|**ZAP de spam** <br/><br/> _SpamZapEnabled_|Habilitado <br/><br/> `$true`|Habilitado <br/><br/> `$true`|Habilitado <br/><br/> `$true`||
|**Phish de phishing** <br/><br/> _PhishZapEnabled_|Habilitado <br/><br/> `$true`|Habilitado <br/><br/> `$true`|Habilitado <br/><br/> `$true`||
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
|**Número máximo de destinatários por usuário: limite por hora externo** <br/><br/> _RecipientLimitExternalPerHour_|,0|500|400|O valor padrão 0 significa usar os padrões de serviço.|
|**Número máximo de destinatários por usuário: limite por hora interna** <br/><br/> _RecipientLimitInternalPerHour_|,0|1000|800|O valor padrão 0 significa usar os padrões de serviço.|
|**Número máximo de destinatários por usuário: limite diário** <br/><br/> _RecipientLimitPerDay_|,0|1000|800|O valor padrão 0 significa usar os padrões de serviço.|
|**Ação quando um usuário exceder os limites** <br/><br/> _ActionWhenThresholdReached_|**Impedir que o usuário envie email até o dia seguinte** <br/><br/> `BlockUserForToday`|**Impedir que o usuário envie emails** <br/><br/> `BlockUser`|**Impedir que o usuário envie emails** <br/><br/> `BlockUser`||
|

### <a name="eop-anti-malware-policy-settings"></a>Configurações de política antimalware do EOP

Para criar e configurar políticas Antimalware, consulte [Configure anti-malware Policies in Office 365](configure-anti-malware-policies.md).

****

|Nome do recurso de segurança|Padrão|Padrão|Impede|Comentário|
|---|:---:|:---:|:---:|---|
|**Deseja notificar destinatários se suas mensagens estiverem em quarentena?** <br/><br/> _Ação_|Não <br/><br/> _DeleteMessage_|Não <br/><br/> _DeleteMessage_|Não <br/><br/> _DeleteMessage_|Se o malware for detectado em um anexo de email, a mensagem será colocada em quarentena e só poderá ser liberada por um administrador.|
|**Filtro de tipos de anexo comuns** <br/><br/> _EnableFileFilter_|Desativada <br/><br/> `$false`|Ativada <br/><br/> `$true`|Habilitado <br/><br/> `$true`|Essa configuração coloca em quarentena mensagens que contêm anexos executáveis com base no tipo de arquivo, independentemente do conteúdo do anexo.|
|**Limpeza automática de malware zero-hora** <br/><br/> _ZapEnabled_|Habilitado <br/><br/> `$true`|Habilitado <br/><br/> `$true`|Habilitado <br/><br/> `$true`||
|**Notificar remetentes internos** da mensagem não entregue <br/><br/> _EnableInternalSenderNotifications_|Desabilitado <br/><br/> `$false`|Desabilitado <br/><br/> `$false`|Desabilitado <br/><br/> `$false`||
|**Notificar remetentes externos** da mensagem não entregue <br/><br/> _EnableExternalSenderNotifications_|Desabilitado <br/><br/> `$false`|Desabilitado <br/><br/> `$false`|Desabilitado <br/><br/> `$false`||
|

### <a name="eop-default-anti-phishing-policy-settings"></a>Configurações de política anti-phishing padrão do EOP

Para obter mais informações sobre essas configurações, consulte [configurações de spoof](set-up-anti-phishing-policies.md#spoof-settings). Para definir essas configurações, consulte [Configure anti-phishing Policies in EOP](configure-anti-phishing-policies-eop.md).

****

|Nome do recurso de segurança|Padrão|Padrão|Impede|Comentário|
|---|:---:|:---:|:---:|---|
|**Habilitar a proteção contra falsificação** <br/><br/> _EnableAntispoofEnforcement_|Habilitado <br/><br/> `$true`|Habilitado <br/><br/> `$true`|Habilitado <br/><br/> `$true`||
|**Habilitar remetente não autenticado** <br/><br/> _EnableUnauthenticatedSender_|Habilitado <br/><br/> `$true`|Habilitado <br/><br/> `$true`|Habilitado <br/><br/> `$true`|Adiciona um ponto de interrogação (?) à foto do remetente no Outlook para remetentes falsificados não identificados. Para obter mais informações, consulte [configurações de spoof em políticas anti-phishing](set-up-anti-phishing-policies.md).|
|**Se o email for enviado por alguém que não tenha permissão para falsificar seu domínio** <br/><br/> _AuthenticationFailAction_|**Mover mensagem para pastas de lixo eletrônico dos destinatários** <br/><br/> `MoveToJmf`|**Mover mensagem para pastas de lixo eletrônico dos destinatários** <br/><br/> `MoveToJmf`|**Colocar a mensagem em quarentena** <br/><br/> `Quarantine`|Essa configuração se aplica a remetentes bloqueados na [inteligência de falsificação](learn-about-spoof-intelligence.md).|
|

## <a name="office-365-advanced-threat-protection-security"></a>Segurança avançada de proteção contra ameaças do Office 365

Outros benefícios de segurança são fornecidos com uma assinatura de proteção avançada contra ameaças (ATP) do Office 365. Para obter as notícias e informações mais recentes, você pode ver [o que há de novo no Office 365 ATP](whats-new-in-office-365-atp.md).

> [!IMPORTANT]
>
> - A política de anti-phishing padrão ATP oferece [proteção contra falsificação](set-up-anti-phishing-policies.md#spoof-settings) para todos os destinatários. No entanto, as configurações de [proteção de representação](#impersonation-settings-in-atp-anti-phishing-policies) disponíveis para remetentes específicos ou domínios de remetente não estão configuradas ou habilitadas na política padrão. Para habilitar a proteção de representação, configure a política padrão ou crie políticas anti-phishing adicionais da ATP.
>
> - Não há políticas de links seguros padrão ou políticas de anexos seguros que protejam automaticamente todos os destinatários na organização. Para obter as proteções, você precisa criar pelo menos uma política de links seguros e uma política de anexos seguros.
>
> - [ATP para SharePoint, onedrive e Microsoft Teams](atp-for-spo-odb-and-teams.md) Protection e proteção de [documentos seguros](safe-docs.md) não têm dependências de políticas de links seguros.

Se sua assinatura incluir o Office 365 ATP ou se você comprou o Office 365 ATP como um complemento, defina as seguintes configurações padrão ou estritas.

### <a name="atp-anti-phishing-policy-settings"></a>Configurações de política anti-phishing do ATP

Os clientes do EOP obtêm anti-phishing básico como descrito anteriormente, mas o Office 365 ATP inclui mais recursos e controle para ajudar a prevenir, detectar e corrigir contra ataques. Para criar e configurar essas políticas, consulte [Configure ATP anti-phishing Policies in Office 365](configure-atp-anti-phishing-policies.md).

#### <a name="impersonation-settings-in-atp-anti-phishing-policies"></a>Configurações de representação nas políticas anti-phishing da ATP

Para obter mais informações sobre essas configurações, consulte [configurações de representação em políticas anti-phishing do ATP](set-up-anti-phishing-policies.md#impersonation-settings-in-atp-anti-phishing-policies). Para definir essas configurações, consulte [Configure ATP anti-phishing Policies](configure-atp-anti-phishing-policies.md).

****

|Nome do recurso de segurança|Padrão|Padrão|Impede|Comentário|
|---|:---:|:---:|:---:|---|
|Usuários protegidos: **Adicionar usuários para proteger** <br/><br/> _EnableTargetedUserProtection_ <br/><br/> _TargetedUsersToProtect_|Desabilitado <br/><br/> `$false` <br/><br/> Nenhuma|Habilitado <br/><br/> `$true` <br/><br/> \<list of users\>|Habilitado <br/><br/> `$true` <br/><br/> \<list of users\>|Dependendo da sua organização, é recomendável adicionar usuários (remetentes de mensagens) em funções principais. Os remetentes protegidos internamente podem ser o CEO, CFO e outros líderes seniores. Externamente, os remetentes protegidos podem incluir membros do Conselho ou seu Conselho de diretores.|
|Domínios protegidos: **incluir automaticamente os domínios que eu sou proprietário** <br/><br/> _EnableOrganizationDomainsProtection_|Desativada <br/><br/> `$false`|Ativada <br/><br/> `$true`|Habilitado <br/><br/> `$true`||
|Domínios protegidos: **incluir domínios personalizados** <br/><br/> _EnableTargetedDomainsProtection_ <br/><br/> _TargetedDomainsToProtect_|Desabilitado <br/><br/> `$false` <br/><br/> Nenhuma|Habilitado <br/><br/> `$true` <br/><br/> \<list of domains\>|Habilitado <br/><br/> `$true` <br/><br/> \<list of domains\>|Dependendo da sua organização, recomendamos adicionar domínios (domínios de remetente) que você não é proprietário, mas com as quais você interage com frequência.|
|Usuários protegidos: **se o email for enviado por um usuário representado** <br/><br/> _TargetedUserProtectionAction_|**Não aplicar nenhuma ação** <br/><br/> `NoAction`|**Colocar a mensagem em quarentena** <br/><br/> `Quarantine`|**Colocar a mensagem em quarentena** <br/><br/> `Quarantine`||
|Domínios protegidos: **se o email for enviado por um domínio representado** <br/><br/> _TargetedDomainProtectionAction_|**Não aplicar nenhuma ação** <br/><br/> `NoAction`|**Colocar a mensagem em quarentena** <br/><br/> `Quarantine`|**Colocar a mensagem em quarentena** <br/><br/> `Quarantine`||
|**Mostrar dica para usuários representados** <br/><br/> _EnableSimilarUsersSafetyTips_|Desativada <br/><br/> `$false`|Ativada <br/><br/> `$true`|Habilitado <br/><br/> `$true`||
|**Mostrar dica para domínios representados** <br/><br/> _EnableSimilarDomainsSafetyTips_|Desativada <br/><br/> `$false`|Ativada <br/><br/> `$true`|Habilitado <br/><br/> `$true`||
|**Mostrar dica para caracteres incomuns** <br/><br/> _EnableUnusualCharactersSafetyTips_|Desativada <br/><br/> `$false`|Ativada <br/><br/> `$true`|Habilitado <br/><br/> `$true`||
|**Habilitar o Mailbox Intelligence?** <br/><br/> _EnableMailboxIntelligence_|Habilitado <br/><br/> `$true`|Habilitado <br/><br/> `$true`|Habilitado <br/><br/> `$true`||
|**Habilitar a proteção de representação baseada em inteligência de caixa de correio?** <br/><br/> _EnableMailboxIntelligenceProtection_|Desativada <br/><br/> `$false`|Ativada <br/><br/> `$true`|Habilitado <br/><br/> `$true`||
|**Se o email for enviado por um usuário representado protegido por Mailbox Intelligence** <br/><br/> _MailboxIntelligenceProtectionAction_|**Não aplicar nenhuma ação** <br/><br/> `NoAction`|**Mover mensagem para pastas de lixo eletrônico dos destinatários** <br/><br/> `MoveToJmf`|**Colocar a mensagem em quarentena** <br/><br/> `Quarantine`||
|**Remetentes confiáveis** <br/><br/> _ExcludedSenders_|Nenhum|Nenhum|Nenhum|Dependendo da sua organização, recomendamos a adição de usuários que são marcados incorretamente como phishing devido à representação apenas e não a outros filtros.|
|**Domínios confiáveis** <br/><br/> _ExcludedDomains_|Nenhum|Nenhum|Nenhum|Dependendo da sua organização, recomendamos a adição de domínios que são marcados incorretamente como phishing devido à representação apenas e não a outros filtros.|
|

#### <a name="spoof-settings-in-atp-anti-phishing-policies"></a>Configurações de spoof nas políticas anti-phishing da ATP

Observe que essas são as mesmas configurações disponíveis nas configurações de [política antispam no EOP](#eop-anti-spam-policy-settings).

****

|Nome do recurso de segurança|Padrão|Impede|Comentário|
|---|---|---|---|
|**Habilitar a proteção contra falsificação** <br/><br/> _EnableAntispoofEnforcement_|Habilitado <br/><br/> `$true`|Habilitado <br/><br/> `$true`||
|**Habilitar remetente não autenticado** <br/><br/> _EnableUnauthenticatedSender_|Habilitado <br/><br/> `$true`|Habilitado <br/><br/> `$true`|Adiciona um ponto de interrogação (?) à foto do remetente no Outlook para remetentes falsificados não identificados. Para obter mais informações, consulte [configurações de spoof em políticas anti-phishing](set-up-anti-phishing-policies.md).|
|**Se o email for enviado por alguém que não tenha permissão para falsificar seu domínio** <br/><br/> _AuthenticationFailAction_|**Mover mensagem para pastas de lixo eletrônico dos destinatários** <br/><br/> `MoveToJmf`|**Colocar a mensagem em quarentena** <br/><br/> `Quarantine`|Essa configuração se aplica a remetentes bloqueados na [inteligência de falsificação](learn-about-spoof-intelligence.md).|
|

#### <a name="advanced-settings-in-atp-anti-phishing-policies"></a>Configurações avançadas nas políticas anti-phishing da ATP

Para obter mais informações sobre essa configuração, consulte [limites de phishing avançados nas políticas anti-phishing do ATP](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-atp-anti-phishing-policies). Para definir essa configuração, consulte [Configure ATP anti-phishing Policies](configure-atp-anti-phishing-policies.md).

****

|Nome do recurso de segurança|Padrão|Padrão|Impede|Comentário|
|---|:---:|:---:|:---:|---|
|**Limites avançados de phishing** <br/><br/> _PhishThresholdLevel_|**1-padrão** <br/><br/> `1`|**2-agressivo** <br/><br/> `2`|**3-mais agressivo** <br/><br/> `3`||
|

### <a name="safe-links-settings"></a>Configurações de links seguros

Links seguros no Office 365 ATP inclui configurações globais que se aplicam a todos os usuários incluídos em políticas de links seguros ativos e configurações específicas de cada política de links seguros. Para obter mais informações, consulte [links seguros no Office 365 ATP](atp-safe-links.md).

#### <a name="global-settings-for-safe-links"></a>Configurações globais para links seguros

Para definir essas configurações, consulte [Configure Global Settings for Safe links in Office 365 ATP](configure-global-settings-for-safe-links.md).

No PowerShell, você usa o cmdlet [set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365) para essas configurações.

****

|Nome do recurso de segurança|Padrão|Padrão|Impede|Comentário|
|---|:---:|:---:|:---:|---|
|**Usar links seguros no: aplicativos do Office 365** <br/><br/> _EnableSafeLinksForO365Clients_|Habilitado <br/><br/> `$true`|Habilitado <br/><br/> `$true`|Habilitado <br/><br/> `$true`|Use links seguros de ATP em aplicativos de área de trabalho do Office 365 e dispositivos móveis (iOS e Android) com suporte. Para obter mais informações, consulte [configurações de links seguros para aplicativos do Office 365](atp-safe-links.md#safe-links-settings-for-office-365-apps).|
|**Não rastrear quando os usuários clicarem em links seguros** <br/><br/> _TrackClicks_|Ativada <br/><br/> `$false`|Desativada <br/><br/> `$true`|Desabilitado <br/><br/> `$true`|A desativação dessa configuração (a definição de _TrackClicks_ como `$true` ) controla cliques do usuário em aplicativos do Office 365 com suporte.|
|**Não permitir que os usuários cliquem por meio de links seguros para a URL original** <br/><br/> _AllowClickThrough_|Habilitado <br/><br/> `$false`|Habilitado <br/><br/> `$false`|Habilitado <br/><br/> `$false`|Ativar essa configuração (a definição de _AllowClickThrough_ como `$false` ) impede o clique para a URL original em aplicativos do Office 365 com suporte.|
|

#### <a name="safe-links-policy-settings"></a>Configurações de política de links seguros

Para definir essas configurações, confira [Configurar políticas de links seguros no Office 365 ATP](set-up-atp-safe-links-policies.md).

No PowerShell, você usa os cmdlets [New-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/new-safelinkspolicy) e [set-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/set-safelinkspolicy) para essas configurações.

**Observação**: conforme descrito anteriormente, não há uma política de links seguros padrão. Os valores na coluna padrão são os valores padrão em novas políticas de links seguros que você cria.

****

|Nome do recurso de segurança|Padrão|Padrão|Impede|Comentário|
|---|:---:|:---:|:---:|---|
|**Selecione a ação para URLs possivelmente mal-intencionadas desconhecidas em mensagens** <br/><br/> _IsEnabled_|Desativada <br/><br/> `$false`|Ativada <br/><br/> `$true`|Habilitado <br/><br/> `$true`||
|**Selecione a ação para URLs desconhecidas ou potencialmente mal-intencionadas no Microsoft Teams** <br/><br/> _EnableSafeLinksForTeams_|Desativada <br/><br/> `$false`|Ativada <br/><br/> `$true`|Habilitado <br/><br/> `$true`||
|**Aplicar verificação de URL em tempo real para links suspeitos e links que apontam para arquivos** <br/><br/> _ScanUrls_|Desativada <br/><br/> `$false`|Ativada <br/><br/> `$true`|Habilitado <br/><br/> `$true`||
|**Aguarde a conclusão da verificação de URL antes de entregar a mensagem** <br/><br/> _DeliverMessageAfterScan_|Desativada <br/><br/> `$false`|Ativada <br/><br/> `$true`|Habilitado <br/><br/> `$true`||
|**Aplicar links seguros a mensagens de email enviadas dentro da organização** <br/><br/> _EnableForInternalSenders_|Desativada <br/><br/> `$false`|Ativada <br/><br/> `$true`|Habilitado <br/><br/> `$true`||
|**Não rastrear cliques do usuário** <br/><br/> _DoNotTrackUserClicks_|Desabilitado <br/><br/> `$false`|Desabilitado <br/><br/> `$false`|Desabilitado <br/><br/> `$false`|A desativação dessa configuração (definindo _DoNotTrackUserClicks_ como `$false` ) controla os cliques dos usuários.|
|**Não permitir que os usuários cliquem através da URL original** <br/><br/> _DoNotAllowClickThrough_|Desativada <br/><br/> `$false`|Ativada <br/><br/> `$true`|Habilitado <br/><br/> `$true`|Ativar essa configuração (a definição de _DoNotAllowClickThrough_ como `$true` ) impede o clique até a URL original.|
|

### <a name="safe-attachments-settings"></a>Configurações de anexos seguros

Os anexos seguros no Office 365 ATP inclui configurações globais que não têm relação com políticas de anexos seguros e configurações específicas para cada política de links seguros. Para obter mais informações, consulte [Safe Attachments in Office 365 ATP](atp-safe-attachments.md).

#### <a name="global-settings-for-safe-attachments"></a>Configurações globais para anexos seguros

Para definir essas configurações, consulte [Ativar ATP para SharePoint, onedrive e Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md) e [documentos seguros no Microsoft 365 E5](safe-docs.md).

No PowerShell, você usa o cmdlet [set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365) para essas configurações.

****

|Nome do recurso de segurança|Padrão|Padrão|Impede|Comentário|
|---|:---:|:---:|:---:|---|
|**Ativar a ATP para SharePoint, OneDrive e Microsoft Teams** <br/><br/> _EnableATPForSPOTeamsODB_|Habilitado <br/><br/> `$true`|Habilitado <br/><br/> `$true`||
|**Ativar documentos seguros para clientes do Office**<bt/><br/> _EnableSafeDocs_|Habilitado <br/><br/> `$true`|Habilitado <br/><br/> `$true`|Essa configuração só está disponível com as licenças de segurança do Microsoft 365 E5 ou Microsoft 365 e5. Para obter mais informações, consulte [documentos seguros no Office 365 proteção avançada contra ameaças](safe-docs.md).|
|**Permitir que as pessoas cliquem no modo de exibição protegido, mesmo se os documentos seguros identificaram o arquivo como mal-intencionado**<bt/><br/> _AllowSafeDocsOpen_|Desabilitado <br/><br/> `$false`|Desabilitado <br/><br/> `$false`|Essa configuração está relacionada a documentos seguros.|
|

#### <a name="safe-attachments-policy-settings"></a>Configurações de política de anexos seguros

Para definir essas configurações, consulte [Configurar políticas de anexos seguros no Office 365 ATP](set-up-atp-safe-attachments-policies.md).

No PowerShell, você usa os cmdlets [New-SafeAttachmentPolicy](https://docs.microsoft.com/powershell/module/exchange/new-safeattachmentpolicy) e [set-SafeAttachmentPolicy](https://docs.microsoft.com/powershell/module/exchange/set-safelinkspolicy) para essas configurações.

**Observação**: conforme descrito anteriormente, não há uma política de anexos seguros padrão. Os valores na coluna padrão são os valores padrão em novas políticas de anexos seguros que você cria.

****

|Nome do recurso de segurança|Padrão|Padrão|Impede|Comentário|
|---|:---:|:---:|:---:|---|
|**Resposta desconhecida de malware de anexos seguros** <br/><br/> _Ação_|Bloquear <br/><br/> `Block`|Bloquear <br/><br/> `Block`|Bloquear <br/><br/> `Block`||
|**Redirecionar o anexo na detecção** : **habilitar redirecionamento** <br/><br/> _Redirecionar_ <br/><br/> _RedirectAddress_|E nenhum endereço de email especificado. <br/><br/> `$true` <br/><br/> Nenhuma|Ativado e especifique um endereço de email. <br/><br/> `$true` <br/><br/> um endereço de email|Ativado e especifique um endereço de email. <br/><br/> `$true` <br/><br/> um endereço de email|Redirecionar mensagens para um administrador de segurança para revisão.|
|**Aplica a seleção acima se a verificação de malware para anexos expirar ou ocorrer erro.** <br/><br/> _ActionOnError_|Habilitado <br/><br/> `$true`|Habilitado <br/><br/> `$true`|Habilitado <br/><br/> `$true`||
|

## <a name="related-articles"></a>Artigos relacionados

- Você está procurando práticas recomendadas para **regras de fluxo de emails do Exchange (também conhecidas como regras de transporte**)? Consulte [práticas recomendadas para configurar regras de fluxo de email no Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/configuration-best-practices).

- Administradores e usuários podem enviar falsos positivos (emails satisfatórios marcados como defeituosos) e falsos negativos (emails inválidos permitidos) para a Microsoft para análise. Para mais informações, confira [Relatar mensagens e arquivos à Microsoft](report-junk-email-messages-to-microsoft.md).

- Use estes links para obter informações sobre como **Configurar** seu [serviço do EOP](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-your-eop-service)e **Configurar** a [proteção avançada contra ameaças do Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp). Não se esqueça das orientações úteis em "[proteger contra ameaças no Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats)".

- As **linhas de base de segurança do Windows** podem ser encontradas [aqui](https://docs.microsoft.com/windows/security/threat-protection/windows-security-baselines#where-can-i-get-the-security-baselines) para as opções de GPO/local e [aqui](https://docs.microsoft.com/intune/protect/security-baselines) para a segurança baseada no Intune. Por fim, uma comparação entre a proteção avançada contra ameaças do Microsoft defender (ATP) e as linhas de base de segurança do Microsoft Intune estão disponíveis [aqui](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-machines-security-baseline#compare-the-microsoft-defender-atp-and-the-windows-intune-security-baselines).
