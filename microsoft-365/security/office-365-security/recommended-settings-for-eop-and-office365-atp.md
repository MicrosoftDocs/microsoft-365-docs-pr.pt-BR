---
title: Recomendações da Microsoft para EOP e Office 365 configuração de segurança ATP, recomendações, estrutura de política de remetente, relatórios e conformidade de mensagens baseadas em domínio, DomainKeys identificadas por email, etapas, como funciona, as linhas de base de segurança, as linhas de base para o EOP, as linhas de base para ATP, configurar ATP, configuração EOP, configurar ATP, definir EOP, configuração de segurança
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
ms.date: 12/12/2019
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 6f64f2de-d626-48ed-8084-03cc72301aa4
ms.collection:
- M365-security-compliance
description: Quais são as práticas recomendadas para as configurações de segurança do Exchange Online Protection (EOP) e da proteção avançada contra ameaças (ATP)? Quais são as recomendações atuais para a proteção padrão? O que deve ser usado se você deseja ser mais estrito? E quais são os extras obtidos se você também usa a proteção avançada contra ameaças (ATP)?
ms.openlocfilehash: a88d58db68816cd6aeb9173c36b964f3f97653db
ms.sourcegitcommit: f5cecd77e63ae8b47743d4f6dc3135f5decaf28b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/30/2020
ms.locfileid: "43949220"
---
# <a name="recommended-settings-for-eop-and-office-365-atp-security"></a>Configurações recomendadas para o EOP e a segurança ATP do Office 365

O **Exchange Online Protection (EOP)** é o núcleo de segurança para assinaturas do Microsoft 365 e ajuda a impedir que emails mal-intencionados cheguem às caixas de entrada do funcionário. Mas com ataques novos e mais sofisticados surgindo todos os dias, as proteções aprimoradas costumam ser necessárias. **Proteção avançada contra ameaças do Office 365 (ATP)** O plano ATP 1 ou a ATP plano 2 contêm recursos adicionais que dão aos administradores mais camadas de segurança, controle e investigação.

Embora possamos permitir que os administradores de segurança personalizem suas configurações de segurança, há dois níveis de segurança no EOP e no Office 365 ATP que recomendamos: **padrão** e **estrito**. O ambiente e as necessidades de cada cliente são diferentes, mas acreditamos que esses níveis de configurações de filtragem de email ajudarão a impedir que emails indesejados cheguem à caixa de entrada de seus funcionários na maioria das situações.

> [!IMPORTANT]
> A regra de lixo eletrônico precisa estar habilitada em uma caixa de correio para que a filtragem funcione corretamente. Ele é habilitado por padrão, mas você deve verificá-lo se a filtragem não estiver funcionando. Para obter mais informações, confira [Definir as configurações de lixo eletrônico nas caixas de correio do Exchange Online no Office 365](configure-junk-email-settings-on-exo-mailboxes.md).

Este tópico descreve estas configurações recomendadas pela Microsoft para ajudar a proteger seus usuários.

> [!TIP]
> Há um novo módulo do PowerShell que você pode baixar chamado Office 365 Advanced Threat Protection Configuration Analyzer (ORCA), que ajuda a determinar algumas dessas configurações. Ao executar como um administrador em seu locatário, o Get-ORCAReport ajudará a gerar uma avaliação das configurações de higiene de antispam, anti-phishing e outras mensagens. Você pode baixar este módulo em https://www.powershellgallery.com/packages/ORCA/.

## <a name="anti-spam-anti-malware-and-anti-phishing-protection-in-eop"></a>Anti-spam, Antimalware e proteção contra phishing no EOP

Anti-spam, Antimalware e anti-phishing são recursos do EOP que podem ser configurados pelos administradores. Recomendamos as seguintes configurações.

### <a name="eop-anti-spam-policy-settings"></a>Configurações de política antispam do EOP

Para criar e configurar políticas antispam, consulte [Configure anti-spam Policies in Office 365](configure-your-spam-filter-policies.md).

|Nome do recurso de segurança|Standard|Impede|Comentário|
|---|---|---|---|
|Ação de detecção de **spam** <br/><br/> _Spam_|**Mover mensagem para a pasta Lixo Eletrônico** <br/><br/> `MoveToJmf`|**Mensagem em quarentena** <br/><br/> `Quarantine`||
|Ação de detecção de **spam de alta confiança** <br/><br/> _HighConfidenceSpamAction_|**Mensagem em quarentena** <br/><br/> `Quarantine`|**Mensagem em quarentena** <br/><br/> `Quarantine`||
|Ação de detecção de **email de phishing** <br/><br/> _PhishSpamAction_|**Mensagem em quarentena** <br/><br/> `Quarantine`|**Mensagem em quarentena** <br/><br/> `Quarantine`||
|Ação de detecção de **email phishing de alta confiança** <br/><br/> _HighConfidencePhishAction_|**Mensagem em quarentena** <br/><br/> `Quarantine`|**Mensagem em quarentena** <br/><br/> `Quarantine`||
|Ação de detecção de **email em massa** <br/><br/> _BulkSpamAction_|**Mover mensagem para a pasta Lixo Eletrônico** <br/><br/> `MoveToJmf`|**Mensagem em quarentena** <br/><br/> `Quarantine`||
|Limite de email em massa <br/><br/> _BulkThreshold_|6 |4 |No momento, o valor padrão é 7, mas é recomendável alterá-lo para 6. Para obter detalhes, consulte o [nível de reclamação em massa (BCL) no Office 365](bulk-complaint-level-values.md).|
|Período de retenção de quarentena <br/><br/> _QuarantineRetentionPeriod_|30 dias|30 dias||
|**Dicas de segurança** <br/><br/> _InlineSafetyTipsEnabled_|Habilitado <br/><br/> `$true`|Habilitado <br/><br/> `$true`||
|Remetentes permitidos <br/><br/> _AllowedSenders_|Nenhum|Nenhum||
|Domínios de remetente permitidos <br/><br/> _AllowedSenderDomains_|Nenhum|Nenhum|A adição de domínios que você possui (também conhecido como _domínios aceitos_) à lista de remetentes permitidos não é necessária. Na verdade, ele é considerado de alto risco, pois cria oportunidades de atores incorretos para enviar emails que seriam filtrados de outra forma. Use a [inteligência de falsificação](learn-about-spoof-intelligence.md) no centro de conformidade & segurança da página **configurações antispam** para examinar todos os remetentes que estão falsificando endereços de email de remetente nos domínios de email da sua organização ou endereços de email de remetentes falsificados em domínios externos.|
|Remetentes bloqueados <br/><br/> _BlockedSenders_|Nenhum|Nenhum||
|Domínios de remetentes bloqueados <br/><br/> _BlockedSenderDomains_|Nenhum|Nenhum||
|**Habilitar notificações de spam para o usuário final** <br/><br/> _EnableEndUserSpamNotifications_|Habilitado <br/><br/> `$true`|Habilitado <br/><br/> `$true`||
|**Envie notificações de spam para o usuário final a cada (dias)** <br/><br/> _EndUserSpamNotificationFrequency_|3 dias|3 dias||
|**ZAP de spam** <br/><br/> _SpamZapEnabled_|Habilitado <br/><br/> `$true`|Habilitado <br/><br/> `$true`||
|**Phish de phishing** <br/><br/> _PhishZapEnabled_|Habilitado <br/><br/> `$true`|Habilitado <br/><br/> `$true`||
|_MarkAsSpamBulkMail_|Habilitado|Habilitado|Essa configuração só está disponível no PowerShell.|

Há várias outras configurações avançadas de filtro de spam (ASF) em políticas antispam que estão em processo de ser preteridas. Mais informações sobre os cronogramas para a depreciação desses recursos serão comunicadas fora deste tópico.

Recomendamos que você **desative essas configurações de** ASF para os níveis **padrão** e **estrito** . Para obter mais informações sobre as configurações de ASF, consulte [Configurações avançadas de filtro de spam (ASF) no Office 365](advanced-spam-filtering-asf-options.md).

|Nome do recurso de segurança|Comments|
|----|---|
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

#### <a name="eop-outbound-spam-policy-settings"></a>Configurações de política de spam de saída do EOP

Para criar e configurar políticas de spam de saída, confira [Configure Outbound spam Filtering in Office 365](configure-the-outbound-spam-policy.md).

|Nome do recurso de segurança|Standard|Impede|Comentário|
|---|---|---|---|
|**Número máximo de destinatários por usuário: limite por hora externo** <br/><br/> _RecipientLimitExternalPerHour_|500|400||
|**Número máximo de destinatários por usuário: limite por hora interna** <br/><br/> _RecipientLimitInternalPerHour_|1000|800||
|**Número máximo de destinatários por usuário: limite diário** <br/><br/> _RecipientLimitPerDay_|1000|800||
|**Ação quando um usuário exceder os limites** <br/><br/> _ActionWhenThresholdReached_|**Impedir que o usuário envie emails** <br/><br/> `BlockUser`|**Impedir que o usuário envie emails** <br/><br/> `BlockUser`||

### <a name="eop-anti-malware-policy-settings"></a>Configurações de política antimalware do EOP

Para criar e configurar políticas Antimalware, consulte [Configure anti-malware Policies in Office 365](configure-anti-malware-policies.md).

|Nome do recurso de segurança|Standard|Impede|Comentário|
|---|---|---|---|
|**Deseja notificar destinatários se suas mensagens estiverem em quarentena?** <br/><br/> _Ação_|Não <br/><br/> _DeleteMessage_|Não <br/><br/> _DeleteMessage_|Se o malware for detectado em um anexo de email, a mensagem será colocada em quarentena e só poderá ser liberada por um administrador.|
|**Filtro de tipos de anexo comuns** <br/><br/> _EnableFileFilter_|Habilitado <br/><br/> `$true`|Habilitado <br/><br/> `$true`|Essa configuração coloca em quarentena mensagens que contêm anexos executáveis com base no tipo de arquivo, independentemente do conteúdo do anexo.|
|**Limpeza automática de malware zero-hora** <br/><br/> _ZapEnabled_|Habilitado <br/><br/> `$true`|Habilitado <br/><br/> `$true`||
|**Notificar remetentes internos** da mensagem não entregue <br/><br/> _EnableInternalSenderNotifications_|Desabilitado <br/><br/> `$false`|Desabilitado <br/><br/> `$false`||
|**Notificar remetentes externos** da mensagem não entregue <br/><br/> _EnableExternalSenderNotifications_|Desabilitado <br/><br/> `$false`|Desabilitado <br/><br/> `$false`||

### <a name="eop-default-anti-phishing-policy-settings"></a>Configurações de política anti-phishing padrão do EOP

Para definir essas configurações, consulte [Configure anti-phishing Policies in EOP](configure-anti-phishing-policies-eop.md).

|Nome do recurso de segurança|Standard|Impede|Comentário|
|---|---|---|---|
|**Habilitar a proteção contra falsificação** <br/><br/> _EnableAntispoofEnforcement_|Habilitado <br/><br/> `$true`|Habilitado <br/><br/> `$true`||
|**Habilitar remetente não autenticado** <br/><br/> _EnableUnauthenticatedSender_|Habilitado <br/><br/> `$true`|Habilitado <br/><br/> `$true`|Adiciona um ponto de interrogação (?) à foto do remetente no Outlook para remetentes falsificados não identificados. Para obter mais informações, consulte [configurações de spoof em políticas anti-phishing](set-up-anti-phishing-policies.md).|
|**Se o email for enviado por alguém que não tenha permissão para falsificar seu domínio** <br/><br/> _AuthenticationFailAction_|**Mover mensagem para pastas de lixo eletrônico dos destinatários** <br/><br/> `MoveToJmf`|**Colocar a mensagem em quarentena** <br/><br/> `Quarantine`|Isso se aplica a remetentes bloqueados na [inteligência de falsificação](learn-about-spoof-intelligence.md).|

## <a name="office-365-advanced-threat-protection-security"></a>Segurança avançada de proteção contra ameaças do Office 365

Outros benefícios de segurança são fornecidos com uma assinatura de proteção avançada contra ameaças (ATP) do Office 365. Para obter as notícias e informações mais recentes, você pode ver [o que há de novo no Office 365 ATP](whats-new-in-office-365-atp.md).

O Office 365 ATP inclui as políticas de anexo seguro e links seguros para impedir que emails com anexos possivelmente mal-intencionados sejam entregues e para impedir que os usuários cliquem em URLs potencialmente não seguras.

> [!IMPORTANT]
> O anti-phishing avançado é um dos benefícios de uma assinatura ATP do Office 365. Embora esteja habilitado por padrão, você ***deve*** configurar pelo menos uma política anti-phishing antes de poder iniciar a filtragem de email. Esquecer de configurar políticas anti-phishing pode expor os usuários a emails arriscados. Certifique-se de configurar suas políticas anti-phishing após adicionar uma assinatura ATP do Office 365.

Se você tiver adicionado uma assinatura ATP do Office 365 ao seu EOP, defina as seguintes configurações.

### <a name="office-atp-anti-phishing-policy-settings"></a>Configurações de política anti-phishing do Office ATP

Os clientes do EOP obtêm anti-phishing básico como descrito anteriormente, mas o Office 365 ATP inclui mais recursos e controle para ajudar a prevenir, detectar e corrigir contra ataques. Para criar e configurar essas políticas, consulte [Configure ATP anti-phishing Policies in Office 365](configure-atp-anti-phishing-policies.md).

|Nome do recurso de segurança de representação|Standard|Impede|Comentário|
|---------|---------|---------|---------|
|(Editar política de representação) Adicionar usuários para proteger|Habilitado|Habilitado|Depende da sua organização, mas recomendamos adicionar usuários em funções principais. Internamente, esses podem ser o CEO, CFO e outros líderes seniores. Externamente, elas podem incluir membros do Conselho ou seu Conselho de diretores.|
|(Editar política de representação) Incluir automaticamente os domínios que sou proprietário|Habilitado|Habilitado||
|(Editar política de representação) Incluir domínios personalizados|Habilitado|Habilitado|Depende da sua organização, mas recomendamos adicionar domínios que você interagem com a maioria que você não possui.|
|Se o email for enviado por um usuário representado que você especificou|Colocar a mensagem em quarentena|Colocar a mensagem em quarentena||
|Se o email for enviado por um domínio representado que você especificou|Colocar a mensagem em quarentena|Colocar a mensagem em quarentena||
|Mostrar dica para usuários representados|Habilitado|Habilitado||
|Mostrar dica para domínios representados|Habilitado|Habilitado||
|Mostrar dica para caracteres incomuns|Habilitado|Habilitado||
|Habilitar inteligência de caixa de correio|Habilitado|Habilitado||
|Habilitar proteção de representação baseada em inteligência de caixa de correio|Habilitado|Habilitado||
|Se o email for enviado por um usuário representado protegido por Mailbox Intelligence|Mover mensagem para pastas de lixo eletrônico dos destinatários|Colocar a mensagem em quarentena||
|(Editar política de representação) Adicionar domínios e remetentes confiáveis|Nenhum|Nenhum|Depende da sua organização, mas é recomendável adicionar usuários ou domínios que são marcados incorretamente como phishing devido à representação apenas e não a outros filtros.|

|Nome do recurso de segurança de spoof|Standard|Impede|Comentário|
|---------|---------|---------|---------|
|Habilitar a proteção contra falsificação|Habilitado|Habilitado||
|Habilitar remetente não autenticado (marcação)|Habilitado|Habilitado||
|Se o email for enviado por alguém que não tenha permissão para falsificar seu domínio|Mover mensagem para pastas de lixo eletrônico dos destinatários|Colocar a mensagem em quarentena||

#### <a name="impersonation-settings-in-atp-anti-phishing-policies"></a>Configurações de representação nas políticas anti-phishing da ATP

|Nome do recurso de segurança|Standard|Impede|Comentário|
|---|---|---|---|
|Usuários protegidos: **Adicionar usuários para proteger** <br/><br/> _EnableTargetedUserProtection_ <br/><br/> _TargetedUsersToProtect_|Habilitado <br/><br/> `$true` <br/><br/> \<lista de usuários\>|Habilitado <br/><br/> `$true` <br/><br/> \<lista de usuários\>|Depende da sua organização, mas recomendamos adicionar usuários em funções principais. Internamente, esses podem ser o CEO, CFO e outros líderes seniores. Externamente, elas podem incluir membros do Conselho ou seu Conselho de diretores.|
|Domínios protegidos: **incluir automaticamente os domínios que eu sou proprietário** <br/><br/> _EnableOrganizationDomainsProtection_|Habilitado <br/><br/> `$true`|Habilitado <br/><br/> `$true`||
|Domínios protegidos: **incluir domínios personalizados** <br/><br/> _EnableTargetedDomainsProtection_ <br/><br/> _TargetedDomainsToProtect_|Habilitado <br/><br/> `$true` <br/><br/> \<lista de domínios\>|Habilitado <br/><br/> `$true` <br/><br/> \<lista de domínios\>|Depende da sua organização, mas recomendamos a adição de domínios com os quais você não é proprietário.|
|Usuários protegidos: **se o email for enviado por um usuário representado** <br/><br/> _TargetedUserProtectionAction_|**Colocar a mensagem em quarentena** <br/><br/> `Quarantine`|**Colocar a mensagem em quarentena** <br/><br/> `Quarantine`||
|Domínios protegidos: **se o email for enviado por um domínio representado** <br/><br/> _TargetedUserProtectionAction_|**Colocar a mensagem em quarentena** <br/><br/> `Quarantine`|**Colocar a mensagem em quarentena** <br/><br/> `Quarantine`||
|**Mostrar dica para usuários representados** <br/><br/> _EnableSimilarUsersSafetyTips_|Habilitado <br/><br/> `$true`|Habilitado <br/><br/> `$true`||
|**Mostrar dica para domínios representados** <br/><br/> _EnableSimilarDomainsSafetyTips_|Habilitado <br/><br/> `$true`|Habilitado <br/><br/> `$true`||
|**Mostrar dica para caracteres incomuns** <br/><br/> _EnableUnusualCharactersSafetyTips_|Habilitado <br/><br/> `$true`|Habilitado <br/><br/> `$true`||
|**Habilitar o Mailbox Intelligence?** <br/><br/> _EnableMailboxIntelligence_|Habilitado <br/><br/> `$true`|Habilitado <br/><br/> `$true`||
|**Habilitar a proteção de representação baseada em inteligência de caixa de correio?** <br/><br/> _EnableMailboxIntelligenceProtection_|Habilitado <br/><br/> `$true`|Habilitado <br/><br/> `$true`||
|**Se o email for enviado por um usuário representado protegido por Mailbox Intelligence** <br/><br/> _MailboxIntelligenceProtectionAction_|**Mover mensagem para pastas de lixo eletrônico dos destinatários** <br/><br/> `MoveToJmf`|**Colocar a mensagem em quarentena** <br/><br/> `Quarantine`||
|**Remetentes confiáveis** <br/><br/> _ExcludedSenders_|Nenhum|Nenhum|Depende da sua organização, mas é recomendável adicionar usuários que são marcados incorretamente como phishing devido à representação apenas e não a outros filtros.|
|**Domínios confiáveis** <br/><br/> _ExcludedDomains_|Nenhum|Nenhum|Depende da sua organização, mas é recomendável adicionar domínios que são marcados incorretamente como phishing devido à representação apenas e não a outros filtros.|

#### <a name="spoof-settings-in-atp-anti-phishing-policies"></a>Configurações de spoof nas políticas anti-phishing da ATP

Observe que essas são as mesmas configurações disponíveis nas configurações de [política antispam no EOP](#eop-anti-spam-policy-settings).

|Nome do recurso de segurança|Standard|Impede|Comentário|
|---|---|---|---|
|**Habilitar a proteção contra falsificação** <br/><br/> _EnableAntispoofEnforcement_|Habilitado <br/><br/> `$true`|Habilitado <br/><br/> `$true`||
|**Habilitar remetente não autenticado** <br/><br/> _EnableUnauthenticatedSender_|Habilitado <br/><br/> `$true`|Habilitado <br/><br/> `$true`|Adiciona um ponto de interrogação (?) à foto do remetente no Outlook para remetentes falsificados não identificados. Para obter mais informações, consulte [configurações de spoof em políticas anti-phishing](set-up-anti-phishing-policies.md).|
|**Se o email for enviado por alguém que não tenha permissão para falsificar seu domínio** <br/><br/> _AuthenticationFailAction_|**Mover mensagem para pastas de lixo eletrônico dos destinatários** <br/><br/> `MoveToJmf`|**Colocar a mensagem em quarentena** <br/><br/> `Quarantine`|Isso se aplica a remetentes bloqueados na [inteligência de falsificação](learn-about-spoof-intelligence.md).|

#### <a name="advanced-settings-in-atp-anti-phishing-policies"></a>Configurações avançadas nas políticas anti-phishing da ATP

|Nome do recurso de segurança|Standard|Impede|Comentário|
|---|---|---|---|
|**Limites avançados de phishing** <br/><br/> _PhishThresholdLevel_|**2-agressivo** <br/><br/> `2`|**3-mais agressivo** <br/><br/> `3`||

### <a name="safe-links-settings"></a>Configurações de links seguros

|Nome do recurso de segurança|Standard|Impede|Comentário|
|---------|---------|---------|---------|
|Usar links seguros de ATP nos aplicativos do Office 365, Office para iOS e Android|Habilitado|Habilitado|Isso se enquadra nas políticas de links seguros de ATP que se aplicam a toda a organização|
Não rastrear quando os usuários clicarem em links seguros|Desabilitado|Desabilitado|Isso é para as duas políticas que se aplicam a toda a organização e quaisquer políticas que se aplicam a destinatários específicos|
|Não permitir que os usuários cliquem por meio de links seguros para a URL original|Habilitado|Habilitado|Isso é para as políticas que se aplicam a toda a organização e quaisquer políticas que se aplicam a destinatários específicos|
|Ação para URLs potencialmente mal-intencionadas desconhecidas em mensagens|Habilitado|Habilitado||
|Aplicar verificação de URL em tempo real para links suspeitos e links que apontam para arquivos|Habilitado|Habilitado||
|Aguarde a conclusão da verificação de URL antes de entregar a mensagem|Habilitado|Habilitado||
|Aplicar links seguros a mensagens de email enviadas dentro da organização|Habilitado|Habilitado||

### <a name="safe-attachments"></a>Anexos seguros

|Nome do recurso de segurança|Standard|Impede|Comentário|
|---------|---------|---------|---------|
|Ative a ATP para SharePoint, OneDrive e Microsoft Teams|Habilitado|Habilitado||
|Resposta de malware desconhecida de anexos seguros de ATP|Bloquear|Bloquear||
|Redirecionar o anexo na detecção|Habilitado|Habilitado|Redirecionar para o endereço de email de um administrador de segurança que sabe como determinar se o anexo é malware ou não|
|Resposta de anexos seguros de ATP se a verificação de malware para anexos expirar ou o erro ocorrer|Habilitado|Habilitado||

## <a name="related-topics"></a>Tópicos relacionados

- Você está procurando práticas recomendadas com **regras de transporte de fluxo de mensagens do Exchange/Exchange**? Confira [Este artigo](https://docs.microsoft.com/microsoft-365/security/office-365-security/best-practices-for-configuring-eop) para obter detalhes.

- Administradores e usuários podem enviar falsos positivos (emails satisfatórios marcados como defeituosos) e falsos negativos (emails inválidos permitidos) para a Microsoft para análise. Para mais informações, confira [Relatar mensagens e arquivos à Microsoft](report-junk-email-messages-to-microsoft.md).

- Use estes links para obter informações sobre como **Configurar** seu [serviço do EOP](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-your-eop-service)e **Configurar** a [proteção avançada contra ameaças do Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp). (Não se esqueça de ver as orientações úteis em '[proteger contra ameaças no Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats)'.)

- As **linhas de base de segurança do Windows** podem ser encontradas [aqui](https://docs.microsoft.com/windows/security/threat-protection/windows-security-baselines#where-can-i-get-the-security-baselines) para opções de GPO/local e para segurança baseada no Intune, [aqui](https://docs.microsoft.com/intune/protect/security-baselines). Por fim, uma comparação entre a proteção avançada contra ameaças do Microsoft defender (ATP) e as linhas de base de segurança do Windows Intune podem ser encontradas [aqui](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-machines-security-baseline#compare-the-microsoft-defender-atp-and-the-windows-intune-security-baselines).
