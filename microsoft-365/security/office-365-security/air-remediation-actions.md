---
title: Ações de correção no Microsoft Defender para Office 365
keywords: AIR, autoIR, ATP, automatizado, investigação, resposta, correção, ameaças, avançado, ameaça, proteção
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
description: Saiba mais sobre as ações de correção após a investigação automatizada no Microsoft Defender para Office 365.
ms.date: 02/09/2021
ms.custom:
- air
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: bef2fbd1e9e3d3525f9c274b5f9127acfb218396
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/18/2021
ms.locfileid: "50287120"
---
# <a name="remediation-actions-in-microsoft-defender-for-office-365"></a>Ações de correção no Microsoft Defender para Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
- [Plano 2 do Microsoft Defender para Office 365](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

## <a name="remediation-actions"></a>Ações de correção

Os recursos de proteção contra ameaças [no Microsoft Defender para Office 365](office-365-atp.md) incluem determinadas ações de correção. Essas ações de correção podem incluir:

- Exclusão reversível de mensagens de emails ou clusters
- Bloquear URL (hora do clique)
- Desativar o encaminhamento de emails externo
- Desativar a delegação

No Microsoft Defender para Office 365, as ações de correção não são realizadas automaticamente. Em vez disso, as ações de correção são tomadas somente mediante aprovação da equipe de operações de segurança da sua organização.

## <a name="threats-and-remediation-actions"></a>Ameaças e ações de correção

O Microsoft Defender para Office 365 inclui ações de correção para lidar com várias ameaças. Investigações automatizadas geralmente resultam em uma ou mais ações de correção para revisar e aprovar. Em alguns casos, uma investigação automatizada não resulta em uma ação de correção específica. Para investigar e tomar as medidas apropriadas, use as orientações na tabela a seguir.

|Categoria|Ameaça/risco|Ações de correção|
|:---|:---|:---|
|Email|Malware|Exclusão suave de email/cluster <p> Se mais de algumas mensagens de email em um cluster contêm malware, o cluster é considerado mal-intencionado.|
|Email|URL mal-intencionada<br/>(Uma URL mal-intencionada foi detectada por [Links seguros.)](atp-safe-links.md)|Exclusão suave de email/cluster <br/>Bloquear URL (verificação de hora de clique)<p> O email que contém uma URL mal-intencionada é considerado mal-intencionado.|
|Email|Golpe|Exclusão suave de email/cluster <p> Se mais de algumas mensagens de email em um cluster contêm tentativas de phishing, todo o cluster é considerado uma tentativa de phishing.|
|Email|Phishing em sua casa <br>(As mensagens de email foram entregues [e, em seguida, enviadas em massa.)](zero-hour-auto-purge.md)|Exclusão suave de email/cluster <p>Os relatórios estão disponíveis para exibir mensagens em massa. [Veja se a ZAP moveu uma mensagem e perguntas frequentes.](zero-hour-auto-purge.md#how-to-see-if-zap-moved-your-message)|
|Email|Email de [phishing perdido relatado](enable-the-report-message-add-in.md) por um usuário|[Investigação automatizada disparada pelo relatório do usuário](automated-investigation-response-office.md#example-a-user-reported-phish-message-launches-an-investigation-playbook)|
|Email|Anomalia de volume <br> (Quantidades recentes de email excedem os últimos 7 a 10 dias para correspondência de critérios.)|A investigação automatizada não resulta em uma ação pendente específica. <p>A anomalia de volume não é uma ameaça clara, mas é simplesmente uma indicação de volumes de email maiores nos últimos dias em comparação com os últimos 7 a 10 dias. <p>Embora um alto volume de email possa indicar possíveis problemas, a confirmação é necessária em termos de vereditos mal-intencionados ou de uma revisão manual de mensagens de email/clusters. Consulte [Encontrar emails suspeitos que foram entregues.](investigate-malicious-email-that-was-delivered.md#find-suspicious-email-that-was-delivered)|
|Email|Nenhuma ameaça encontrada <br> (O sistema não encontrou ameaças baseadas em arquivos, URLs ou análise de vereditos de cluster de email.)|A investigação automatizada não resulta em uma ação pendente específica. <p>As ameaças [encontradas](zero-hour-auto-purge.md) e descobertas após a conclusão de uma investigação não são refletidas nas descobertas numéricas de uma investigação, mas essas ameaças podem ser visualizadas no [Explorador de Ameaças.](threat-explorer.md)|
|Usuário|Um usuário clicou em uma URL mal-intencionada <br> (Um usuário navegue até uma página que posteriormente foi encontrada como sendo mal-intencionada ou um usuário desviou uma página de aviso de [Links](atp-safe-links.md#warning-pages-from-safe-links) seguros para chegar a uma página mal-intencionada.)|A investigação automatizada não resulta em uma ação pendente específica. <p>Bloquear URL (hora do clique) <p>Use o Explorador de [Ameaças para exibir dados sobre URLs e clique em vereditos.](threat-explorer.md#view-phishing-url-and-click-verdict-data) <p>Se sua organização estiver usando [o Microsoft Defender para o Ponto](https://docs.microsoft.com/windows/security/threat-protection/)de Extremidade, considere investigar o usuário para determinar se a conta está comprometida. [](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/investigate-user)|
|Usuário|Um usuário está enviando malware/phishing|A investigação automatizada não resulta em uma ação pendente específica. <p> O usuário pode estar relatando malware/phishing ou alguém pode [estar spoofando o usuário](anti-spoofing-protection.md) como parte de um ataque. Use [o Explorador de Ameaças](threat-explorer.md) para exibir e manipular emails contendo [malware](threat-explorer-views.md#email--malware) ou [phishing.](threat-explorer-views.md#email--phish)|
|Usuário|Encaminhamento de e-mail <br> (As regras de encaminhamento de caixa de correio estão configuradas, que podem ser usadas para exfiltração de dados.)|Remover regra de encaminhamento <p> Use [as informações de fluxo](mail-flow-insights-v2.md)de emails, incluindo o [relatório](mfi-auto-forwarded-messages-report.md)de mensagens com encaminhamento automático, para exibir detalhes mais específicos sobre emails encaminhados.|
|Usuário|Regras de delegação de email <br> (A conta de um usuário tem a delegação configurada.)|Remover regra de delegação <p> Se sua organização estiver usando [o Microsoft Defender para o Ponto](https://docs.microsoft.com/windows/security/threat-protection/)de Extremidade, considere investigar o usuário que está recebendo a permissão de delegação. [](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/investigate-user)|
|Usuário|Exfiltração dos dados <br> (Um usuário violou o email ou as políticas [DLP de](../../compliance/data-loss-prevention-policies.md)compartilhamento de arquivos.)|A investigação automatizada não resulta em uma ação pendente específica. <p> [Exibir relatórios DLP e tomar medidas.](../../compliance/view-the-dlp-reports.md)|
|Usuário|Envio de emails anômalos <br> (Um usuário enviou recentemente mais emails do que durante os últimos 7 a 10 dias.)|A investigação automatizada não resulta em uma ação pendente específica. <p> Enviar um grande volume de email não é mal-intencionado por si só; o usuário pode ter enviado emails para um grande grupo de destinatários de um evento. Para investigar, use informações [de fluxo de emails,](mail-flow-insights-v2.md)incluindo o relatório de [mapa](mfi-mail-flow-map-report.md) de fluxo de emails para determinar o que está acontecendo e tomar medidas.|

## <a name="next-steps"></a>Próximas etapas

- [Exibir detalhes e resultados de uma investigação automatizada no Microsoft Defender para Office 365](air-view-investigation-results.md)
- [Exibir ações de correção pendentes ou concluídas após uma investigação automatizada no Microsoft Defender para Office 365](air-review-approve-pending-completed-actions.md)

## <a name="related-articles"></a>Artigos relacionados

- [Saiba mais sobre a investigação automatizada no Microsoft Defender para Ponto de Extremidade](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)
- [Saiba mais sobre os recursos no Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)
