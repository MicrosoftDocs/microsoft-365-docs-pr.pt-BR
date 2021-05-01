---
title: Ações de correção no Microsoft Defender para Office 365
keywords: AIR, autoIR, Microsoft Defender for Endpoint, automated, investigation, response, remediation, threats, advanced, threat, protection
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Saiba mais sobre ações de correção após investigação automatizada no Microsoft Defender para Office 365.
ms.date: 04/30/2021
ms.custom:
- air
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ffaa7c46d81070a6443bf2233bbfdfd741ceb915
ms.sourcegitcommit: 05f40904f8278f53643efa76a907968b5c662d9a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/30/2021
ms.locfileid: "52114325"
---
# <a name="remediation-actions-in-microsoft-defender-for-office-365"></a>Ações de correção no Microsoft Defender para Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
- [Plano 2 do Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

## <a name="remediation-actions"></a>Ações de correção

Os recursos de proteção contra ameaças no [Microsoft Defender para Office 365](defender-for-office-365.md) incluem determinadas ações de correção. Essas ações de correção podem incluir:

- Exclusão reversível de mensagens de emails ou clusters
- Bloquear URL (hora do clique)
- Desativar o encaminhamento de emails externo
- Desativar a delegação

No Microsoft Defender para Office 365, as ações de correção não são tomadas automaticamente. Em vez disso, as ações de correção são tomadas somente após a aprovação pela equipe de operações de segurança da sua organização.

## <a name="threats-and-remediation-actions"></a>Ações de ameaças e correção

O Microsoft Defender para Office 365 inclui ações de correção para lidar com várias ameaças. Investigações automatizadas geralmente resultam em uma ou mais ações de correção para revisar e aprovar. Em alguns casos, uma investigação automatizada não resulta em uma ação de correção específica. Para investigar e tomar as ações apropriadas, use as diretrizes na tabela a seguir.

|Categoria|Ameaça/risco|Ações de correção|
|:---|:---|:---|
|Email|Malware|Excluir email/cluster de exclusão suave <p> Se mais de algumas mensagens de email em um cluster contêm malware, o cluster é considerado mal-intencionado.|
|Email|URL mal-intencionada<br/>(Uma URL mal-intencionada foi detectada por [Cofre Links](safe-links.md).)|Excluir email/cluster de exclusão suave <br/>Bloquear URL (verificação de hora de clique)<p> O email que contém uma URL mal-intencionada é considerado mal-intencionado.|
|Email|Golpe|Excluir email/cluster de exclusão suave <p> Se mais de algumas mensagens de email em um cluster conterem tentativas de phishing, todo o cluster será considerado uma tentativa de phishing.|
|Email|Phishing com ataque de phishing <br>(As mensagens de email foram entregues e depois [enviadas .)](zero-hour-auto-purge.md)|Excluir email/cluster de exclusão suave <p>Os relatórios estão disponíveis para exibir mensagens sem visualização. [Veja se o ZAP moveu uma mensagem e perguntas frequentes.](zero-hour-auto-purge.md#how-to-see-if-zap-moved-your-message)|
|Email|Email de [phishing perdido relatado](enable-the-report-message-add-in.md) por um usuário|[Investigação automatizada disparada pelo relatório do usuário](automated-investigation-response-office.md#example-a-user-reported-phish-message-launches-an-investigation-playbook)|
|Email|Anomalia de volume <br> (Quantidades recentes de email excedem os 7 a 10 dias anteriores para critérios de correspondência.)|A investigação automatizada não resulta em uma ação pendente específica. <p>A anomalia de volume não é uma ameaça clara, mas é apenas uma indicação de volumes de email maiores nos últimos dias em comparação com os últimos 7 a 10 dias. <p>Embora um alto volume de emails possa indicar possíveis problemas, a confirmação é necessária em termos de vereditos mal-intencionados ou de uma revisão manual de mensagens de email/clusters. Consulte [Encontrar emails suspeitos que foram entregues](investigate-malicious-email-that-was-delivered.md#find-suspicious-email-that-was-delivered).|
|Email|Nenhuma ameaça encontrada <br> (O sistema não encontrou ameaças com base em arquivos, URLs ou análise de vereditos de cluster de email.)|A investigação automatizada não resulta em uma ação pendente específica. <p>As ameaças encontradas [e descobertas](zero-hour-auto-purge.md) após a conclusão de uma investigação não são refletidas nas descobertas numéricas de uma investigação, mas essas ameaças são visualizadas no [Explorador de Ameaças.](threat-explorer.md)|
|Usuário|Um usuário clicou em uma URL mal-intencionada <br> (Um usuário navegue até uma página que foi mais tarde considerado mal-intencionado, ou um usuário desviou uma página de aviso [de links](safe-links.md#warning-pages-from-safe-links) Cofre para acessar uma página mal-intencionada.)|A investigação automatizada não resulta em uma ação pendente específica. <p>Bloquear URL (hora do clique) <p>Use o Explorador de Ameaças [para exibir dados sobre URLs e clique em vereditos.](threat-explorer.md#view-phishing-url-and-click-verdict-data) <p>Se sua organização estiver usando [o Microsoft Defender para Ponto](/windows/security/threat-protection/)de Extremidade, considere investigar o [usuário](/microsoft-365/security/defender-endpoint/investigate-user) para determinar se a conta está comprometida.|
|Usuário|Um usuário está enviando malware/phish|A investigação automatizada não resulta em uma ação pendente específica. <p> O usuário pode estar relatando malware/phish, ou alguém pode estar [spoofando](anti-spoofing-protection.md) o usuário como parte de um ataque. Use [o Explorador de Ameaças](threat-explorer.md) para exibir e manipular emails contendo [malware](threat-explorer-views.md#email--malware) ou [phishing.](threat-explorer-views.md#email--phish)|
|Usuário|Encaminhamento de e-mail <br> (As regras de encaminhamento de caixa de correio são configuradas, que podem ser usadas para exfiltração de dados.)|Remover regra de encaminhamento <p> Use [as informações de fluxo de](mail-flow-insights-v2.md)emails , incluindo o relatório de mensagens [autoforwarded,](mfi-auto-forwarded-messages-report.md)para exibir detalhes mais específicos sobre emails encaminhados.|
|Usuário|Regras de delegação de email <br> (A conta de um usuário tem a delegação configurada.)|Remover regra de delegação <p> Se sua organização estiver usando [o Microsoft Defender para Ponto](/windows/security/threat-protection/)de Extremidade, considere investigar o [usuário](/microsoft-365/security/defender-endpoint/investigate-user) que está recebendo a permissão de delegação.|
|Usuário|Exfiltração dos dados <br> (Um usuário violou políticas de [DLP](../../compliance/dlp-learn-about-dlp.md) de email ou compartilhamento de arquivos |A investigação automatizada não resulta em uma ação pendente específica. <p> [Exibir relatórios de DLP e tomar medidas](../../compliance/view-the-dlp-reports.md).|
|Usuário|Envio de emails anômalos <br> (Um usuário enviou recentemente mais emails do que durante os últimos 7 a 10 dias.)|A investigação automatizada não resulta em uma ação pendente específica. <p> Enviar um grande volume de email não é mal-intencionado por si só; o usuário pode ter enviado emails para um grande grupo de destinatários para um evento. Para investigar, use insights de [](mfi-mail-flow-map-report.md) [fluxo de](mail-flow-insights-v2.md)emails , incluindo o relatório de mapa de fluxo de emails para determinar o que está acontecendo e tomar medidas.|

## <a name="next-steps"></a>Próximas etapas

- [Exibir detalhes e resultados de uma investigação automatizada no Microsoft Defender para Office 365](air-view-investigation-results.md)
- [Exibir ações de correção pendentes ou concluídas após uma investigação automatizada no Microsoft Defender para Office 365](air-review-approve-pending-completed-actions.md)

## <a name="related-articles"></a>Artigos relacionados

- [Saiba mais sobre investigação automatizada no Microsoft Defender para Ponto de Extremidade](/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)
- [Saiba mais sobre recursos no Microsoft 365 Defender](/microsoft-365/security/defender/microsoft-365-defender)
