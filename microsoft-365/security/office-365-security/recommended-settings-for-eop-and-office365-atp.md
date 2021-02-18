---
title: Recomendações da Microsoft para configurações de segurança do EOP e do Defender para Office 365
keywords: Recomendações de segurança do Office 365, Sender Policy Framework, Relatórios e Conformidade de Mensagens baseados em domínio, Email Identificado por DomainKeys, etapas, como funciona, linhas de base de segurança, linhas de base para EOP, linhas de base do Defender para Office 365, configurar o Defender para Office 365, configurar o EOP, configurar o Defender para Office 365, configurar o EOP, configuração de segurança
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
ms.date: ''
manager: dansimp
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 6f64f2de-d626-48ed-8084-03cc72301aa4
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Quais são as práticas recomendadas para as configurações de segurança do Exchange Online Protection (EOP) e do Defender para Office 365? Quais são as recomendações atuais para proteção padrão? O que deve ser usado se você quiser ser mais estrito? E quais extras você obterá se também usar o Defender para Office 365?
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: d635a28c41c9aceb0e3c499301156e53a1e2fa68
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/18/2021
ms.locfileid: "50289348"
---
# <a name="recommended-settings-for-eop-and-microsoft-defender-for-office-365-security"></a>Configurações recomendadas para o EOP e o Microsoft Defender para segurança do Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
- [Proteção do Exchange Online](exchange-online-protection-overview.md)
- [Plano 1 e plano 2 do Microsoft Defender para Office 365](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

**O Proteção do Exchange Online (EOP)** é o núcleo de segurança para assinaturas do Microsoft 365 e ajuda a evitar que emails mal-intencionados chegam às caixas de entrada do funcionário. Porém, com ataques novos e mais sofisticados que surgem todos os dias, proteções aprimoradas são frequentemente necessárias. **Microsoft Defender para Office 365** O Plano 1 ou o Plano 2 contêm recursos adicionais que dão aos administradores mais camadas de segurança, controle e investigação.

Embora nós capacitamos os administradores de segurança a personalizar suas configurações de segurança, há dois níveis de segurança no EOP e no Microsoft Defender para Office 365 que recomendamos: **Padrão** e **Estrito.** O ambiente e as necessidades de cada cliente são diferentes, mas acreditamos que esses níveis de filtragem ajudarão a impedir que emails indesejados atinjam a Caixa de Entrada de seus funcionários na maioria das situações.

Para aplicar automaticamente as configurações Padrão ou Estrito aos usuários, consulte Políticas de segurança predefinidas no EOP e [no Microsoft Defender para Office 365.](preset-security-policies.md)

> [!NOTE]
> A regra de lixo eletrônico precisa ser habilitada em caixas de correio para que a filtragem funcione corretamente. Ela está habilitada por padrão, mas você deve verificar se a filtragem não parece estar funcionando. Para obter mais informações, confira [Definir as configurações de lixo eletrônico nas caixas de correio do Exchange Online no Office 365](configure-junk-email-settings-on-exo-mailboxes.md).

Este artigo descreve as configurações padrão e também as configurações Padrão e Estrito recomendadas para ajudar a proteger seus usuários.

> [!TIP]
> O módulo Analisador de Configuração Recomendada da Proteção Avançada contra Ameaças do Office 365 (ORCA) para PowerShell pode ajudá-lo (administradores) a encontrar os valores atuais dessas configurações. Especificamente, o cmdlet **Get-ORCAReport** gera uma avaliação de anti-spam, anti-phishing e outras configurações de higienização de mensagens. Você pode baixar o módulo ORCA em <https://www.powershellgallery.com/packages/ORCA/> .

## <a name="anti-spam-anti-malware-and-anti-phishing-protection-in-eop"></a>Proteção anti-spam, anti-malware e anti-phishing no EOP

Anti-spam, anti-malware e anti-phishing são recursos do EOP que podem ser configurados por administradores. Recomendamos as seguintes configurações Padrão ou Estrito.

### <a name="eop-anti-spam-policy-settings"></a>Configurações de política anti-spam do EOP

Para criar e configurar políticas anti-spam, confira [Configurar políticas anti-spam no Office 365.](configure-your-spam-filter-policies.md)

****

|Nome do recurso de segurança|Padrão|Padrão|Estrito|Comentário|
|---|:---:|:---:|:---:|---|
|**Ação de** detecção de spam <p> _SpamAction_|**Mover mensagem para a pasta Lixo Eletrônico** <p> `MoveToJmf`|**Mover mensagem para a pasta Lixo Eletrônico** <p> `MoveToJmf`|**Mensagem em quarentena** <p> `Quarantine`||
|**Ação de detecção de spam** de alta confiança <p> _HighConfidenceSpamAction_|**Mover mensagem para a pasta Lixo Eletrônico** <p> `MoveToJmf`|**Mensagem em quarentena** <p> `Quarantine`|**Mensagem em quarentena** <p> `Quarantine`||
|**Ação de detecção de email** de phishing <p> _PhishSpamAction_|**Mover mensagem para a pasta Lixo Eletrônico** <p> `MoveToJmf`|**Mensagem em quarentena** <p> `Quarantine`|**Mensagem em quarentena** <p> `Quarantine`||
|**Ação de detecção de email de phishing** de alta confiança <p> _HighConfidencePhishAction_|**Mensagem em quarentena** <p> `Quarantine`|**Mensagem em quarentena** <p> `Quarantine`|**Mensagem em quarentena** <p> `Quarantine`||
|**Ação de detecção de email** em massa <p> _BulkSpamAction_|**Mover mensagem para a pasta Lixo Eletrônico** <p> `MoveToJmf`|**Mover mensagem para a pasta Lixo Eletrônico** <p> `MoveToJmf`|**Mensagem em quarentena** <p> `Quarantine`||
|Limite de email em massa <p> _BulkThreshold_|7 |6 |4 |Para obter detalhes, consulte Nível de reclamação em massa [(BCL) no Office 365.](bulk-complaint-level-values.md)|
|Período de retenção de quarentena <p> _QuarantineRetentionPeriod_|15 dias|30 dias|30 dias||
|**Dicas de Segurança** <p> _InlineSafetyTipsEnabled_|Habilitado <p> `$true`|Habilitado <p> `$true`|Habilitado <p> `$true`||
|Envios Permitidos <p> _AllowedSenders_|Nenhum|Nenhum|Nenhum||
|Domínios permitidos do remetente <p> _AllowedSenderDomains_|Nenhum|Nenhum|Nenhum|Adicionar domínios à lista de envios permitidos é uma má ideia. Os invasores seriam capazes de enviar um email que seria filtrado de outra forma. <p> Use a inteligência de spoof no Centro de Conformidade de & segurança na página de configurações **anti-spam** para revisar todos os remetentes que estão [spoofando](learn-about-spoof-intelligence.md) endereços de email do remetente nos domínios de email da sua organização ou os endereços de email de remetentes de spoofing em domínios externos.|
|Bloqueados Senders <p> _BlockedSenders_|Nenhum|Nenhum|Nenhum||
|Domínios de Remetente Bloqueados <p> _BlockedSenderDomains_|Nenhum|Nenhum|Nenhum||
|**Habilitar notificações de spam para o usuário final** <p> _EnableEndUserSpamNotifications_|Desabilitado <p> `$false`|Habilitado <p> `$true`|Habilitado <p> `$true`||
|**Envie notificações de spam para o usuário final a cada (dias)** <p> _EndUserSpamNotificationFrequency_|3 dias|3 dias|3 dias||
|**Spam ZAP** <p> _SpamZapEnabled_|Habilitado <p> `$true`|Habilitado <p> `$true`|Habilitado <p> `$true`||
|**ZAP de phishing** <p> _PhishZapEnabled_|Habilitado <p> `$true`|Habilitado <p> `$true`|Habilitado <p> `$true`||
|_MarkAsSpamBulkMail_|Habilitado|Habilitado|Habilitado|Essa configuração só está disponível no PowerShell.|
|

Há várias outras configurações de Filtro de Spam Avançado (ASF) em políticas anti-spam que estão sendo preteridas. Mais informações sobre os cronogramas para a depreciação desses recursos serão comunicadas fora deste artigo.

Recomendamos desativar essas configurações ASF **para** os níveis **Padrão** **e Estrito.** Para obter mais informações sobre as configurações de ASF, consulte as configurações do Filtro de Spam Avançado [(ASF) no Office 365.](advanced-spam-filtering-asf-options.md)

****

|Nome do recurso de segurança|Comentário|
|---|---|
|**Links de imagem para sites remotos** (_IncreaseScoreWithImageLinks_)||
|**Endereço IP numérico na URL** (_IncreaseScoreWithNumericIps_)||
|**REDIRECIONAMENTO UL para outra porta** (_IncreaseScoreWithRedirectToOtherPort_)||
|**URL para sites .biz ou .info** (_IncreaseScoreWithBizOrInfoUrls_)||
|**Mensagens vazias** (_MarkAsSpamEmptyMessages_)||
|**JavaScript ou VBScript em HTML** (_MarkAsSpamJavaScriptInHtml_)||
|**Marcas frame ou IFrame em HTML** (_MarkAsSpamFramesInHtml_)||
|**Marcas de objeto em HTML** (_MarkAsSpamObjectTagsInHtml_)||
|**Inserir marcas em HTML** (_MarkAsSpamEmbedTagsInHtml_)||
|**Marcas de formulário em HTML** (_MarkAsSpamFormTagsInHtml_)||
|**Bugs da Web em HTML** (_MarkAsSpamWebBugsInHtml_)||
|**Aplicar lista de palavras confidenciais** (_MarkAsSpamSensitiveWordList_)||
|**Registro SPF: falha grave** (_MarkAsSpamSpfRecordHardFail_)||
|**Filtragem de ID de Remetente Condicional: falha grave** (_MarkAsSpamFromAddressAuthFail_)||
|**Backscatter de NDR** (_MarkAsSpamNdrBackscatter_)||
|

#### <a name="eop-outbound-spam-policy-settings"></a>Configurações de política de spam de saída do EOP

Para criar e configurar políticas de spam de saída, confira Configurar a filtragem de [spam de saída no Office 365.](configure-the-outbound-spam-policy.md)

Para obter mais informações sobre os limites de envio padrão no serviço, consulte [Limites de envio.](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-1)

****

|Nome do recurso de segurança|Padrão|Padrão|Estrito|Comentário|
|---|:---:|:---:|:---:|---|
|**Número máximo de destinatários por usuário: Limite de hora externa** <p> _RecipientLimitExternalPerHour_|0|500|400|O valor padrão 0 significa usar os padrões de serviço.|
|**Número máximo de destinatários por usuário: Limite interno por hora** <p> _RecipientLimitInternalPerHour_|0|1000|800|O valor padrão 0 significa usar os padrões de serviço.|
|**Número máximo de destinatários por usuário: Limite diário** <p> _RecipientLimitPerDay_|0|1000|800|O valor padrão 0 significa usar os padrões de serviço.|
|**Ação quando um usuário excede os limites** <p> _ActionWhenThresholdReached_|**Restringir o usuário de enviar emails até o dia seguinte** <p> `BlockUserForToday`|**Restringir o usuário de enviar emails** <p> `BlockUser`|**Restringir o usuário de enviar emails** <p> `BlockUser`||
|

### <a name="eop-anti-malware-policy-settings"></a>Configurações de política anti-malware do EOP

Para criar e configurar políticas anti-malware, confira [Configurar políticas anti-malware no Office 365.](configure-anti-malware-policies.md)

****

|Nome do recurso de segurança|Padrão|Padrão|Estrito|Comentário|
|---|:---:|:---:|:---:|---|
|**Deseja notificar os destinatários se suas mensagens estão em quarentena?** <p> _Ação_|Não <p> _DeleteMessage_|Não <p> _DeleteMessage_|Não <p> _DeleteMessage_|Se um malware for detectado em um anexo de email, a mensagem será colocada em quarentena e só poderá ser liberada por um administrador.|
|**Filtro tipos de anexo comuns** <p> _EnableFileFilter_|Desativada <p> `$false`|Ativada <p> `$true`|Habilitado <p> `$true`|Essa configuração coloca em quarentena as mensagens que contêm anexos executáveis com base no tipo de arquivo, independentemente do conteúdo do anexo.|
|**Limpeza Automática Zero Hora do Malware** <p> _ZapEnabled_|Habilitado <p> `$true`|Habilitado <p> `$true`|Habilitado <p> `$true`||
|**Notificar os envios** internos da mensagem não entregue <p> _EnableInternalSenderNotifications_|Desabilitado <p> `$false`|Desabilitado <p> `$false`|Desabilitado <p> `$false`||
|**Notificar os envios** externos da mensagem não entregue <p> _EnableExternalSenderNotifications_|Desabilitado <p> `$false`|Desabilitado <p> `$false`|Desabilitado <p> `$false`||
|

### <a name="eop-default-anti-phishing-policy-settings"></a>Configurações de política anti-phishing padrão do EOP

Para obter mais informações sobre essas configurações, consulte [Configurações de Spoof.](set-up-anti-phishing-policies.md#spoof-settings) Para definir essas configurações, consulte [Configurar políticas anti-phishing no EOP.](configure-anti-phishing-policies-eop.md)

****

|Nome do recurso de segurança|Padrão|Padrão|Estrito|Comentário|
|---|:---:|:---:|:---:|---|
|**Habilitar a proteção anti-spoofing** <p> _EnableSpoofIntelligence_|Habilitado <p> `$true`|Habilitado <p> `$true`|Habilitado <p> `$true`||
|**Habilitar Remetente Não Autenticado** <p> _EnableUnauthenticatedSender_|Habilitado <p> `$true`|Habilitado <p> `$true`|Habilitado <p> `$true`|Adiciona um ponto de interrogação (?) à foto do remetente no Outlook para remetentes não identificados. Para obter mais informações, consulte [Configurações de Spoof em políticas anti-phishing.](set-up-anti-phishing-policies.md)|
|**Se o email for enviado por alguém que não tem permissão para fazer spoof do seu domínio** <p> _AuthenticationFailAction_|**Mover mensagem para as pastas de Lixo Eletrônico dos destinatários** <p> `MoveToJmf`|**Mover mensagem para as pastas de Lixo Eletrônico dos destinatários** <p> `MoveToJmf`|**Colocar a mensagem em quarentena** <p> `Quarantine`|Esta configuração se aplica a senders bloqueados em [inteligência contra spoof intelligence.](learn-about-spoof-intelligence.md)|
|

## <a name="microsoft-defender-for-office-365-security"></a>Segurança do Microsoft Defender para Office 365

Benefícios adicionais de segurança vêm com uma assinatura do Microsoft Defender para Office 365. Para obter as últimas notícias e informações, você pode ver [novidades no Defender para Office 365.](whats-new-in-office-365-atp.md)

> [!IMPORTANT]
>
> - A política anti-phishing padrão no Microsoft Defender para Office 365 fornece proteção contra [spoof](set-up-anti-phishing-policies.md#spoof-settings) e inteligência de caixa de correio para todos os destinatários. No entanto, os outros recursos de proteção [contra](#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) representação disponíveis e configurações avançadas não estão configurados ou [habilitados](#advanced-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) na política padrão. Para habilitar todos os recursos de proteção, modifique a política anti-phishing padrão ou crie políticas anti-phishing adicionais.
>
> - Não há políticas de Links seguros padrão ou políticas de Anexos seguros que protejam automaticamente todos os destinatários na organização. Para obter as proteções, você precisa criar pelo menos uma Política de Links Seguros e uma política de Anexos Seguros.
>
> - A proteção de Anexos Seguros para o [](safe-docs.md) [SharePoint, OneDrive](atp-for-spo-odb-and-teams.md) e Proteção de Documentos Seguros do Microsoft Teams não tem dependências nas políticas de Links seguros.

Se sua assinatura inclui o Microsoft Defender para Office 365 ou se você comprou o Defender para Office 365 como um complemento, de definidas as seguintes configurações Padrão ou Estrito.

### <a name="anti-phishing-policy-settings-in-microsoft-defender-for-office-365"></a>Configurações de política anti-phishing no Microsoft Defender para Office 365

Os clientes do EOP têm anti-phishing básico conforme descrito anteriormente, mas o Microsoft Defender para Office 365 inclui mais recursos e controle para ajudar a evitar, detectar e remediar ataques. Para criar e configurar essas políticas, consulte Configurar políticas [anti-phishing no Defender para Office 365.](configure-atp-anti-phishing-policies.md)

#### <a name="impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Configurações de representação em políticas anti-phishing no Microsoft Defender para Office 365

Para obter mais informações sobre essas configurações, consulte Configurações de representação em políticas [anti-phishing no Microsoft Defender para Office 365.](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) Para definir essas configurações, consulte [Configurar políticas anti-phishing no Defender para Office 365.](configure-atp-anti-phishing-policies.md)

****

|Nome do recurso de segurança|Padrão|Padrão|Estrito|Comentário|
|---|:---:|:---:|:---:|---|
|Usuários protegidos: **Adicionar usuários para proteger** <p> _EnableTargetedUserProtection_ <p> _TargetedUsersToProtect_|Desabilitado <p> `$false` <p> nenhum|Habilitado <p> `$true` <p> \<list of users\>|Habilitado <p> `$true` <p> \<list of users\>|Dependendo da sua organização, recomendamos adicionar usuários (envios de mensagens) em funções principais. Internamente, os remententes protegidos podem ser seu CEO, CFO e outros líderes sênior. Externamente, os rementes protegidos podem incluir membros do conselho ou seu conselho de diretores.|
|Domínios protegidos: **Incluir automaticamente os domínios que eu tenho** <p> _EnableOrganizationDomainsProtection_|Desativada <p> `$false`|Ativada <p> `$true`|Habilitado <p> `$true`||
|Domínios protegidos: **Incluir domínios personalizados** <p> _EnableTargetedDomainsProtection_ <p> _TargetedDomainsToProtect_|Desabilitado <p> `$false` <p> nenhum|Habilitado <p> `$true` <p> \<list of domains\>|Habilitado <p> `$true` <p> \<list of domains\>|Dependendo da sua organização, recomendamos adicionar domínios (domínios de remetente) que você não possui, mas com os que você interage com frequência.|
|Usuários protegidos: **se o email for enviado por um usuário personificado** <p> _TargetedUserProtectionAction_|**Não aplicar nenhuma ação** <p> `NoAction`|**Colocar a mensagem em quarentena** <p> `Quarantine`|**Colocar a mensagem em quarentena** <p> `Quarantine`||
|Domínios protegidos: **se o email for enviado por um domínio personificado** <p> _TargetedDomainProtectionAction_|**Não aplicar nenhuma ação** <p> `NoAction`|**Colocar a mensagem em quarentena** <p> `Quarantine`|**Colocar a mensagem em quarentena** <p> `Quarantine`||
|**Mostrar dica para usuários personificados** <p> _EnableSimilarUsersSafetyTips_|Desativada <p> `$false`|Ativada <p> `$true`|Habilitado <p> `$true`||
|**Mostrar dica para domínios personificados** <p> _EnableSimilarDomainsSafetyTips_|Desativada <p> `$false`|Ativada <p> `$true`|Habilitado <p> `$true`||
|**Mostrar dica para caracteres incomuns** <p> _EnableUnusualCharactersSafetyTips_|Desativada <p> `$false`|Ativada <p> `$true`|Habilitado <p> `$true`||
|**Habilitar a inteligência de caixa de correio?** <p> _EnableMailboxIntelligence_|Habilitado <p> `$true`|Habilitado <p> `$true`|Habilitado <p> `$true`||
|**Habilitar a proteção contra representação baseada em inteligência de caixa de correio?** <p> _EnableMailboxIntelligenceProtection_|Desativada <p> `$false`|Ativada <p> `$true`|Habilitado <p> `$true`||
|**Se o email for enviado por um usuário personificado protegido pela inteligência de caixa de correio** <p> _MailboxIntelligenceProtectionAction_|**Não aplicar nenhuma ação** <p> `NoAction`|**Mover mensagem para as pastas de Lixo Eletrônico dos destinatários** <p> `MoveToJmf`|**Colocar a mensagem em quarentena** <p> `Quarantine`||
|**Senders confiáveis** <p> _ExcludedSenders_|Nenhum|Nenhum|Nenhum|Dependendo da sua organização, recomendamos adicionar usuários que são marcados incorretamente como phishing devido à representação apenas e não a outros filtros.|
|**Domínios confiáveis** <p> _ExcludedDomains_|Nenhum|Nenhum|Nenhum|Dependendo da sua organização, recomendamos adicionar domínios que são marcados incorretamente como phishing devido à representação apenas e não a outros filtros.|
|

#### <a name="spoof-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Configurações de spoof em políticas anti-phishing no Microsoft Defender para Office 365

Observe que essas são as mesmas configurações disponíveis nas configurações de política [anti-spam no EOP.](#eop-anti-spam-policy-settings)

****

|Nome do recurso de segurança|Padrão|Padrão|Estrito|Comentário|
|---|---|---|---|---|
|**Habilitar a proteção anti-spoofing** <p> _EnableSpoofIntelligence_|Habilitado <p> `$true`|Habilitado <p> `$true`|Habilitado <p> `$true`||
|**Habilitar Remetente Não Autenticado** <p> _EnableUnauthenticatedSender_|Habilitado <p> `$true`|Habilitado <p> `$true`|Habilitado <p> `$true`|Adiciona um ponto de interrogação (?) à foto do remetente no Outlook para remetentes não identificados. Para obter mais informações, consulte [Configurações de Spoof em políticas anti-phishing.](set-up-anti-phishing-policies.md)|
|**Se o email for enviado por alguém que não tem permissão para fazer spoof do seu domínio** <p> _AuthenticationFailAction_|**Mover mensagem para as pastas de Lixo Eletrônico dos destinatários** <p> `MoveToJmf`|**Mover mensagem para as pastas de Lixo Eletrônico dos destinatários** <p> `MoveToJmf`|**Colocar a mensagem em quarentena** <p> `Quarantine`|Esta configuração se aplica a senders bloqueados em [inteligência contra spoof intelligence.](learn-about-spoof-intelligence.md)|
|

#### <a name="advanced-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Configurações avançadas em políticas anti-phishing no Microsoft Defender para Office 365

Para obter mais informações sobre essa configuração, consulte Limites avançados de phishing em políticas [anti-phishing no Microsoft Defender para Office 365.](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365) Para definir essa configuração, consulte [Configurar políticas anti-phishing no Defender para Office 365.](configure-atp-anti-phishing-policies.md)

****

|Nome do recurso de segurança|Padrão|Padrão|Estrito|Comentário|
|---|:---:|:---:|:---:|---|
|**Limites avançados de phishing** <p> _PhishThresholdLevel_|**1 - Padrão** <p> `1`|**2 - Agressivo** <p> `2`|**3 - Mais agressivo** <p> `3`||
|

### <a name="safe-links-settings"></a>Configurações de Links Seguros

Os Links Seguros no Defender para Office 365 incluem configurações globais que se aplicam a todos os usuários incluídos nas políticas de Links seguros ativos e configurações específicas de cada política de Links seguros. Para obter mais informações, consulte [Links seguros no Defender para Office 365.](atp-safe-links.md)

#### <a name="global-settings-for-safe-links"></a>Configurações globais de Links seguros

Para definir essas configurações, consulte [Definir configurações globais para Links Seguros no Defender para Office 365.](configure-global-settings-for-safe-links.md)

No PowerShell, você usa o cmdlet [Set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365) para essas configurações.

****

|Nome do recurso de segurança|Padrão|Padrão|Estrito|Comentário|
|---|:---:|:---:|:---:|---|
|**Usar Links Seguros em: aplicativos do Office 365** <p> _EnableSafeLinksForO365Clients_|Habilitado <p> `$true`|Habilitado <p> `$true`|Habilitado <p> `$true`|Use Links seguros em aplicativos de área de trabalho e dispositivos móveis (iOS e Android) com suporte do Office 365. Para obter mais informações, consulte [Configurações de Links seguros para aplicativos do Office 365.](atp-safe-links.md#safe-links-settings-for-office-365-apps)|
|**Não rastrear quando os usuários clicam em Links Seguros** <p> _TrackClicks_|Ativada <p> `$false`|Desativada <p> `$true`|Desabilitado <p> `$true`|A opção de desligar essa configuração (definir _TrackClicks_ como) rastreia os cliques do usuário nos aplicativos do `$true` Office 365 com suporte.|
|**Não permitir que os usuários cliquem em Links Seguros para a URL original** <p> _AllowClickThrough_|Habilitado <p> `$false`|Habilitado <p> `$false`|Habilitado <p> `$false`|A ativá-la _(configurando AllowClickThrough_ como ) impede o clique na URL original nos aplicativos do `$false` Office 365 com suporte.|
|

#### <a name="safe-links-policy-settings"></a>Configurações de política de Links seguros

Para definir essas configurações, consulte [Configurar políticas de Links seguros no Microsoft Defender para Office 365.](set-up-atp-safe-links-policies.md)

No PowerShell, você usa os cmdlets [New-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/new-safelinkspolicy) e [Set-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/set-safelinkspolicy) para essas configurações.

> [!NOTE]
> Conforme descrito anteriormente, não há uma política de Links seguros padrão. Os valores na coluna Padrão são os valores padrão nas novas políticas de Links seguros que você cria.

****

|Nome do recurso de segurança|Padrão|Padrão|Estrito|Comentário|
|---|:---:|:---:|:---:|---|
|**Selecionar a ação para URLs potencialmente mal-intencionadas desconhecidas em mensagens** <p> _IsEnabled_|Desativada <p> `$false`|Ativada <p> `$true`|Habilitado <p> `$true`||
|**Selecione a ação para URLs desconhecidas ou potencialmente mal-intencionadas no Microsoft Teams** <p> _EnableSafeLinksForTeams_|Desativada <p> `$false`|Ativada <p> `$true`|Habilitado <p> `$true`||
|**Aplicar verificação de URL em tempo real para links suspeitos e links que apontam para arquivos** <p> _ScanUrls_|Desativada <p> `$false`|Ativada <p> `$true`|Habilitado <p> `$true`||
|**Aguarde a conclusão da verificação de URL antes de entregar a mensagem** <p> _DeliverMessageAfterScan_|Desativada <p> `$false`|Ativada <p> `$true`|Habilitado <p> `$true`||
|**Aplicar Links Seguros a mensagens de email enviadas dentro da organização** <p> _EnableForInternalSenders_|Desativada <p> `$false`|Ativada <p> `$true`|Habilitado <p> `$true`||
|**Não rastrear cliques do usuário** <p> _DoNotTrackUserClicks_|Desabilitado <p> `$false`|Desabilitado <p> `$false`|Desabilitado <p> `$false`|A opção de desligar essa configuração _(definir DoNotTrackUserClicks_ `$false` como ) rastreia os cliques dos usuários.|
|**Não permitir que os usuários cliquem na URL original** <p> _DoNotAllowClickThrough_|Desativada <p> `$false`|Ativada <p> `$true`|Habilitado <p> `$true`|A ativá-la _(definindo DoNotAllowClickThrough_ como ) impede o `$true` clique para a URL original.|
|

### <a name="safe-attachments-settings"></a>Configurações de Anexos Seguros

Os Anexos Seguros no Microsoft Defender para Office 365 incluem configurações globais que não têm relação com as políticas de Anexos Seguros e configurações específicas de cada política de Links seguros. Para obter mais informações, consulte [Anexos seguros no Defender para Office 365.](atp-safe-attachments.md)

#### <a name="global-settings-for-safe-attachments"></a>Configurações globais para anexos seguros

Para definir essas configurações, confira Ativar Anexos Seguros para [SharePoint, OneDrive e Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md) e Documentos Seguros no [Microsoft 365 E5.](safe-docs.md)

No PowerShell, você usa o cmdlet [Set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365) para essas configurações.

****

|Nome do recurso de segurança|Padrão|Padrão|Estrito|Comentário|
|---|:---:|:---:|:---:|---|
|**Ativar o Defender para Office 365, para SharePoint, OneDrive e Microsoft Teams.** <p> _EnableATPForSPOTeamsODB_|Habilitado <p> `$true`|Habilitado <p> `$true`||
|**Ativar Documentos Seguros para clientes do Office** <p> _EnableSafeDocs_|Habilitado <p> `$true`|Habilitado <p> `$true`|Essa configuração só está disponível com as licenças do Microsoft 365 E5 ou do Microsoft 365 E5 Security. Para obter mais informações, consulte [Documentos seguros no Microsoft Defender para Office 365.](safe-docs.md)|
|**Permitir que as pessoas cliquem no Exibição Protegido, mesmo se os Documentos Seguros identificarem o arquivo como mal-intencionado** <p> _AllowSafeDocsOpen_|Desabilitado <p> `$false`|Desabilitado <p> `$false`|Essa configuração está relacionada a Documentos Seguros.|
|

#### <a name="safe-attachments-policy-settings"></a>Configurações de política de Anexos Seguros

Para definir essas configurações, consulte Configurar políticas de [Anexos Seguros no Defender para Office 365.](set-up-atp-safe-attachments-policies.md)

No PowerShell, você usa os cmdlets [New-SafeAttachmentPolicy](https://docs.microsoft.com/powershell/module/exchange/new-safeattachmentpolicy) e [Set-SafeAttachmentPolicy](https://docs.microsoft.com/powershell/module/exchange/set-safelinkspolicy) para essas configurações.

> [!NOTE]
> Conforme descrito anteriormente, não há nenhuma política de Anexos seguros padrão. Os valores na coluna Padrão são os valores padrão nas novas políticas de Anexos seguros que você cria.

****

|Nome do recurso de segurança|Padrão|Padrão|Estrito|Comentário|
|---|:---:|:---:|:---:|---|
|**Resposta de malware desconhecida de Anexos Seguros** <p> _Ação_|Bloquear <p> `Block`|Bloquear <p> `Block`|Bloquear <p> `Block`||
|**Redirecionar anexo na detecção:** **Habilitar redirecionamento** <p> _Redirecionar_ <p> _RedirectAddress_|Desligado e nenhum endereço de email especificado. <p> `$true` <p> nenhum|Em e especifique um endereço de email. <p> `$true` <p> um endereço de email|Em e especifique um endereço de email. <p> `$true` <p> um endereço de email|Redirecionar mensagens para um administrador de segurança para revisão.|
|**Aplique a seleção acima se a verificação de anexos de malware e o erro ocorrer.** <p> _ActionOnError_|Habilitado <p> `$true`|Habilitado <p> `$true`|Habilitado <p> `$true`||
|

## <a name="related-articles"></a>Artigos relacionados

- Você está procurando práticas recomendadas para regras de fluxo de emails **do Exchange (também conhecidas como regras de transporte)?** Confira [as práticas recomendadas para configurar regras de fluxo de emails no Exchange Online.](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/configuration-best-practices)

- Administradores e usuários podem enviar falsos positivos (emails bons marcados como ruins) e falsos negativos (emails ruins permitidos) para análise da Microsoft. Para mais informações, confira [Relatar mensagens e arquivos à Microsoft](report-junk-email-messages-to-microsoft.md).

- Use estes links para obter informações sobre como **configurar seu** [serviço EOP](set-up-your-eop-service.md)e **configurar o** [Microsoft Defender para Office 365.](office-365-atp.md) Não se esqueça das instruções úteis em '[Protect Against Threats in Office 365](protect-against-threats.md)'.

- As linhas de base de segurança para **Windows** podem ser [encontradas](https://docs.microsoft.com/windows/security/threat-protection/windows-security-baselines#where-can-i-get-the-security-baselines) aqui: onde posso obter as linhas de base de segurança? para opções de GPO/no local e usar linhas de base de segurança para configurar [dispositivos Windows 10 no Intune](https://docs.microsoft.com/intune/protect/security-baselines) para segurança baseada no Intune. Por fim, uma comparação entre as linhas de base de segurança do Microsoft Defender para Ponto de Extremidade e do Microsoft Intune está disponível em Comparar o Microsoft Defender para Ponto de Extremidade e as linhas de base de segurança do [Windows Intune.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-machines-security-baseline#compare-the-microsoft-defender-atp-and-the-windows-intune-security-baselines)
