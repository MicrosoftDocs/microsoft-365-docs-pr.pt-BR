---
title: Recomendações da Microsoft para EOP e Office 365 configurações de segurança de ATP, recomendações, estrutura de política de remetente, relatórios e conformidade de mensagens baseadas em domínio, DomainKeys identificadas por email, etapas, como funciona, as linhas de base de segurança, linhas de base para o EOP linhas de base para ATP, configuração ATP, configuração EOP, configurar ATP, configurar EOP, configuração de segurança
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
ms.openlocfilehash: b7c98fe4b362a5be72be9e103a2602cd4954e028
ms.sourcegitcommit: 3b6e226d07b5227054d5c8d1a012694caf88f50a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/10/2020
ms.locfileid: "42587287"
---
# <a name="recommended-settings-for-eop-and-office-365-atp-security"></a>Configurações recomendadas para o EOP e a segurança ATP do Office 365

O **proteção do Exchange Online (EOP)** é o núcleo de segurança para assinaturas do Office 365 e ajuda a impedir que emails mal-intencionados cheguem às caixas de entrada do funcionário. Mas com ataques novos e mais sofisticados surgindo todos os dias, as proteções aprimoradas costumam ser necessárias. **Proteção avançada contra ameaças do Office 365 (ATP)** O plano ATP 1 ou a ATP plano 2 contêm recursos adicionais que dão aos administradores mais camadas de segurança, controle e investigação.

Embora possamos permitir que os administradores de segurança personalizem suas configurações de segurança, há dois níveis de segurança no EOP e no Office 365 ATP que recomendamos: **padrão** e **estrito**. O ambiente e as necessidades de cada cliente são diferentes, mas acreditamos que esses níveis de configurações de filtragem de email ajudarão a impedir que emails indesejados cheguem à caixa de entrada de seus funcionários na maioria das situações.

> [!IMPORTANT]
> A configuração de lixo eletrônico deve estar habilitada na caixa de correio para que a filtragem funcione corretamente. Isso é habilitado por padrão, mas deve ser verificado se a filtragem não está funcionando. Leia [set-MailboxJunkEmailConfiguration](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-mailboxjunkemailconfiguration) para saber mais. 

Este tópico descreve estas configurações recomendadas pela Microsoft para ajudar a proteger os usuários do Office 365.

> [!TIP]
> Há um novo módulo do PowerShell que você pode baixar chamado Office 365 Advanced Threat Protection Configuration Analyzer (ORCA), que ajuda a determinar algumas dessas configurações. Ao executar como um administrador em seu locatário, o Get-ORCAReport ajudará a gerar uma avaliação das configurações de higiene de antispam, anti-phishing e outras mensagens. Você pode baixar este módulo em https://www.powershellgallery.com/packages/ORCA/.

## <a name="anti-spam-anti-malware-and-anti-phishing-protection-in-eop"></a>Anti-spam, Antimalware e proteção contra phishing no EOP

Anti-spam, Antimalware e anti-phishing são recursos do EOP que podem ser configurados pelos administradores. Recomendamos as seguintes configurações.

### <a name="eop-anti-spam-policy-settings"></a>Configurações de política antispam do EOP

|Nome do recurso de segurança|Standard|Impede|Comentário|
|---------|---------|---------|---------|
|Ação de detecção de spam|Mover mensagem para a pasta Lixo Eletrônico|Mensagem em quarentena||
|Ação de detecção de spam de alta confiança|Mensagem em quarentena|Mensagem em quarentena||
|Ação de detecção de email de phishing|Mensagem em quarentena|Mensagem em quarentena||
|Ação de detecção de email de phishing de alta confiança|Mensagem em quarentena|Mensagem em quarentena||
|Ação de detecção de email em massa|Mover mensagem para a pasta Lixo Eletrônico|Mensagem em quarentena||
|Definir o limite de email em massa para|6 |4 |No momento, o valor padrão é 7, mas é recomendável alterá-lo para 6. Para obter detalhes, consulte [valores de nível de reclamação em massa](bulk-complaint-level-values.md).|
|Período de retenção de quarentena|30 dias|30 dias||
|Dicas de segurança|Habilitado|Habilitado||
|Remetentes permitidos|Nenhum|Nenhum||
|Domínios de remetentes permitidos|Nenhum|Nenhum|A adição de domínios que você possui (também conhecido como _domínios aceitos_) à lista de remetentes permitidos não é necessária. Na verdade, ele é considerado de alto risco, pois cria oportunidades de atores incorretos para enviar emails que seriam filtrados de outra forma. Use a [inteligência de spoof](learn-about-spoof-intelligence.md) no centro de conformidade & segurança da página **configurações antispam** para examinar todos os remetentes que estão falsificando os domínios que fazem parte da sua organização ou falsificando domínios externos.|
|Remetentes bloqueados|Nenhum|Nenhum||
|Domínios de remetentes bloqueados|Nenhum|Nenhum||
|Frequência de notificação de spam do usuário final|Habilitado|Habilitado|3 dias|
|Limpeza automática de zero hora|Habilitado|Habilitado|Para obter spam e ZAP de phishing|
|MarkAsSpamBulkMail|Habilitado|Habilitado|Essa configuração só está disponível no PowerShell|

Há vários outros parâmetros na política antispam chamado filtro de spam avançado (ASF) que estão no processo de serem preteridos. Mais informações sobre os cronogramas para a depreciação desses recursos serão comunicadas fora deste tópico.

Recomendamos que você **desative essas configurações para** os níveis padrão e estrito:

|Nome do recurso de segurança|Comentários|
|---------|---------|
|IncreaseScoreWithImageLinks||
|IncreaseScoreWithNumericIps||
|IncreaseScoreWithRedirectToOtherPort||
|IncreaseScoreWithBizOrInfoUrls||
|MarkAsSpamEmptyMessages||
|MarkAsSpamJavaScriptInHtml||
|MarkAsSpamFramesInHtml||
|MarkAsSpamObjectTagsInHtml||
|MarkAsSpamEmbedTagsInHtml||
|MarkAsSpamFormTagsInHtml||
|MarkAsSpamWebBugsInHtml||
|MarkAsSpamSensitiveWordList||
|MarkAsSpamFromAddressAuthFail||
|MarkAsSpamNdrBackscatter||
|MarkAsSpamSpfRecordHardFail||

#### <a name="eop-outbound-spam-filter-policy-settings"></a>Configurações de política de filtro de spam de saída do EOP

|Nome do recurso de segurança|Standard|Impede|Comentário|
|---------|---------|---------|---------|
|Limites de destinatários de política de spam de saída-limite por hora externa|500|400||
|Limites de destinatários de política de spam de saída-limite por hora interna|1000|800||
|Limites de destinatários de política de spam de saída-limite diário|1000|800||
|Ação quando um usuário exceder os limites|Impedir que o usuário envie emails|Impedir que o usuário envie emails||

### <a name="eop-anti-malware-policy-settings"></a>Configurações de política antimalware do EOP

|Nome do recurso de segurança|Standard|Impede|Comentário|
|---------|---------|---------|---------|
|Resposta de detecção de malware|Não|Não|Se o malware for detectado em um anexo de email, a mensagem será colocada em quarentena e só poderá ser liberada por um administrador.|
|"Filtro de tipos de anexo comuns" para bloquear tipos de arquivo suspeitos|Habilitado|Habilitado||
|Limpeza automática de malware zero-hora|Habilitado|Habilitado||
|Notificar remetentes internos da mensagem não entregue|Desabilitado|Desabilitado||
|Notificar remetentes externos da mensagem não entregue|Desabilitado|Desabilitado||

### <a name="eop-anti-phishing-policy-settings"></a>Configurações de política de anti-phishing do EOP

|Nome do recurso de segurança|Standard|Impede|Comentário|
|---------|---------|---------|---------|
|Habilitar a proteção contra falsificação|Habilitado|Habilitado||
|Habilitar remetente não autenticado (marcação)|Habilitado|Habilitado||
|Se o email for enviado por alguém que não tenha permissão para falsificar seu domínio|Mover mensagem para pastas de lixo eletrônico dos destinatários|Colocar a mensagem em quarentena||

## <a name="office-365-advanced-threat-protection-security"></a>Segurança avançada de proteção contra ameaças do Office 365

Outros benefícios de segurança são fornecidos com uma assinatura de proteção avançada contra ameaças (ATP) do Office 365. Para obter as notícias e informações mais recentes, você pode ver [o que há de novo no Office 365 ATP](whats-new-in-office-365-atp.md).

O Office 365 ATP inclui as políticas de anexo seguro e links seguros para impedir que emails com anexos possivelmente mal-intencionados sejam entregues e para impedir que os usuários cliquem em URLs potencialmente não seguras.

> [!IMPORTANT]
> O anti-phishing avançado é um dos benefícios de uma assinatura ATP do Office 365. Embora esteja habilitado por padrão, você ***deve*** configurar pelo menos uma política anti-phishing antes de poder iniciar a filtragem de email. Esquecer de configurar políticas anti-phishing pode expor os usuários a emails arriscados. Certifique-se de configurar suas políticas anti-phishing após adicionar uma assinatura ATP do Office 365.

Se você tiver adicionado uma assinatura ATP do Office 365 ao seu EOP, defina as seguintes configurações.

### <a name="office-atp-anti-phishing-policy-settings"></a>Configurações de política anti-phishing do Office ATP

Os clientes do EOP obtêm anti-phishing básico como descrito anteriormente, mas o Office 365 ATP inclui mais recursos e controle para ajudar a prevenir, detectar e corrigir contra ataques.

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
|EnableSuspiciousSafetyTip|Falso|Verdadeiro|Essa configuração só está disponível no PowerShell|
|TreatSoftPassAsAuthenticated|True|Falso|Essa configuração só está disponível no PowerShell|


|Nome do recurso de segurança de configurações avançadas|Standard|Impede|Comentário|
|---------|---------|---------|---------|
|Limites avançados de phishing|2-agressivo|3-mais agressivo||

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

### <a name="safe-attachments"></a>Anexos Seguros

|Nome do recurso de segurança|Standard|Impede|Comentário|
|---------|---------|---------|---------|
|Ative a ATP para SharePoint, OneDrive e Microsoft Teams|Habilitado|Habilitado||
|Resposta de malware desconhecida de anexos seguros de ATP|Bloquear|Bloquear||
|Redirecionar o anexo na detecção|Habilitado|Habilitado|Redirecionar para o endereço de email de um administrador de segurança que sabe como determinar se o anexo é malware ou não|
|Resposta de anexos seguros de ATP se a verificação de malware para anexos expirar ou o erro ocorrer|Habilitado|Habilitado||


## <a name="related-topics"></a>Tópicos relacionados

- Você está procurando práticas recomendadas com **regras de transporte de fluxo de mensagens do Exchange/Exchange**? Confira [Este artigo](https://docs.microsoft.com/microsoft-365/security/office-365-security/best-practices-for-configuring-eop) para obter detalhes.

- Envie emails suspeitos, spam, phishing ou URLs suspeitas à Microsoft para verificação. Use as direções de **envios de administrador** neste [artigo](https://docs.microsoft.com/microsoft-365/security/office-365-security/admin-submission).

- Use estes links para obter informações sobre como **Configurar** seu [serviço do EOP](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-your-eop-service)e **Configurar** a [proteção avançada contra ameaças do Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp). (Não se esqueça de ver as orientações úteis em '[proteger contra ameaças no Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats)'.)

- As **linhas de base de segurança do Windows** podem ser encontradas [aqui](https://docs.microsoft.com/windows/security/threat-protection/windows-security-baselines#where-can-i-get-the-security-baselines) para opções de GPO/local e para segurança baseada no Intune, [aqui](https://docs.microsoft.com/intune/protect/security-baselines). Por fim, uma comparação entre a proteção avançada contra ameaças do Microsoft defender (ATP) e as linhas de base de segurança do Windows Intune podem ser encontradas [aqui](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-machines-security-baseline#compare-the-microsoft-defender-atp-and-the-windows-intune-security-baselines).
