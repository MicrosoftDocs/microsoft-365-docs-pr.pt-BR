---
title: Ações de correção após investigação automatizada no Microsoft Defender para Office 365
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
ms.date: 01/21/2021
ms.custom:
- air
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 39032cb187b2654b6ae03c048e706afb665a8761
ms.sourcegitcommit: ba830e85899f247e5a1e117d63e09e4d5b8a8020
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49939292"
---
# <a name="remediation-actions-following-automated-investigation-in-microsoft-defender-for-office-365"></a>Ações de correção após investigação automatizada no Microsoft Defender para Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


## <a name="remediation-actions"></a>Ações de correção

[Os recursos automatizados de investigação e](office-365-air.md) resposta (AIR) no [Microsoft Defender para Office 365](office-365-atp.md) incluem determinadas ações de correção. Sempre que uma investigação automatizada estiver em andamento ou tiver sido concluída, você normalmente verá uma ou mais ações de remediação que requerem aprovação da sua equipe de operações de segurança para prosseguir. Essas ações de correção podem incluir:

- Exclusão reversível de mensagens de emails ou clusters
- Bloquear URL (hora do clique)
- Desativar o encaminhamento de emails externo
- Desativar a delegação

> [!NOTE]
> No Microsoft Defender para Office 365, investigações automatizadas não resultam em ações de correção que são realizadas automaticamente. As ações de correção são tomadas somente mediante aprovação da equipe de operações de segurança da sua organização.

## <a name="threats-and-remediation-actions"></a>Ameaças e ações de correção

A tabela nesta seção resume as ameaças e as ações de correção apropriadas no Microsoft Defender para Office 365. Em alguns casos, uma investigação automatizada não resulta em uma ação de correção específica. Sua equipe de operações de segurança pode investigar e tomar as medidas apropriadas, conforme descrito na tabela abaixo.

|Categoria|Ameaça/risco|Ações de correção|
|:---|:---|:---|
|Email|Malware|Exclusão suave de email/cluster <br> Se mais de algumas mensagens de email em um cluster contêm malware, o cluster é considerado mal-intencionado.|
|Email|URL mal-intencionada <br> (Uma URL mal-intencionada foi detectada por [Links seguros no Microsoft Defender para Office 365).](atp-safe-links.md)|Exclusão suave de email/cluster <p> O email que contém uma URL mal-intencionada é considerado mal-intencionado.|
|Email|Golpe|Exclusão suave de email/cluster <br> Se mais de algumas mensagens de email em um cluster contêm tentativas de phishing, o cluster é considerado phishing.|
|Email|Phishing em estilo phishing <br> (As mensagens de email foram [entregues e com o mesmo texto.)](zero-hour-auto-purge.md)|Exclusão suave de email/cluster <p> Os relatórios estão disponíveis para exibir mensagens em massa. [Veja se a ZAP moveu uma mensagem e perguntas frequentes.](zero-hour-auto-purge.md#how-to-see-if-zap-moved-your-message)|
|Email|Email de [phishing perdido relatado](enable-the-report-message-add-in.md) por um usuário|[Investigação automatizada disparada pelo relatório do usuário](automated-investigation-response-office.md#example-a-user-reported-phish-message-launches-an-investigation-playbook)|
|Email|Anomalia de volume <br> (Quantidades recentes de email excedem os últimos 7 a 10 dias para correspondência de critérios.)|A investigação automatizada não resulta em uma ação pendente específica. <p> A anomalia de volume não é uma ameaça clara, mas é simplesmente uma indicação de volumes de email maiores nos últimos dias em comparação aos últimos 7 a 10 dias. Embora a anomalia de volume possa indicar possíveis problemas, a confirmação é necessária em termos de vereditos mal-intencionados ou uma revisão manual de mensagens de email/clusters. Consulte [Encontrar emails suspeitos que foram entregues.](investigate-malicious-email-that-was-delivered.md#find-suspicious-email-that-was-delivered)|
|Email|Nenhuma ameaça encontrada <br> (O sistema não encontrou ameaças baseadas em arquivos, URLs ou análise de vereditos de cluster de email.)|A investigação automatizada não resulta em uma ação pendente específica. <p> As ameaças [encontradas e](zero-hour-auto-purge.md) descobertas após a conclusão de uma investigação não são refletidas nas descobertas numéricas de uma investigação, mas essas ameaças podem ser visualizadas no [Explorador de Ameaças.](threat-explorer.md)|
|Usuário|Um usuário clicou em uma URL mal-intencionada <br> (Um usuário navegue até uma página que posteriormente foi encontrada como sendo mal-intencionada ou um usuário desviou uma página de aviso de [Links](atp-safe-links.md#warning-pages-from-safe-links) seguros para chegar a uma página mal-intencionada.)|A investigação automatizada não resulta em uma ação pendente específica. <p> Use o Explorador de [Ameaças para exibir dados sobre URLs e vereditos de clique.](threat-explorer.md#view-phishing-url-and-click-verdict-data) <p> Se sua organização estiver usando [o Microsoft Defender para o Ponto](https://docs.microsoft.com/windows/security/threat-protection/)de Extremidade, considere investigar o usuário para determinar se a conta está comprometida. [](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/investigate-user)|
|Usuário|Um usuário está enviando malware/phishing|A investigação automatizada não resulta em uma ação pendente específica. <p> O usuário pode estar relatando malware/phish, ou alguém pode [estar spoofando o usuário](anti-spoofing-protection.md) como parte de um ataque. Use [o Explorador de Ameaças](threat-explorer.md) para exibir e manipular emails contendo [malware](threat-explorer-views.md#email--malware) ou [phishing.](threat-explorer-views.md#email--phish)|
|Usuário|Encaminhamento de e-mail <br> (As regras de encaminhamento de caixa de correio estão configuradas, que podem ser usadas para exfiltração de dados.)|Remover regra de encaminhamento <p> Use [as informações de fluxo](mail-flow-insights-v2.md)de emails, incluindo o [relatório](mfi-auto-forwarded-messages-report.md)de mensagens com encaminhamento automático, para exibir detalhes mais específicos sobre emails encaminhados.|
|Usuário|Regras de delegação de email <br> (A conta de um usuário tem a delegação configurada.)|Remover regra de delegação <p> Se sua organização estiver usando [o Microsoft Defender para o Ponto](https://docs.microsoft.com/windows/security/threat-protection/)de Extremidade, considere investigar o usuário que está recebendo a permissão de delegação. [](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/investigate-user)|
|Usuário|Exfiltração dos dados <br> (Um usuário violou o email ou as políticas [DLP de](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies)compartilhamento de arquivos.)|A investigação automatizada não resulta em uma ação pendente específica. <p> [Exibir relatórios DLP e tomar medidas.](https://docs.microsoft.com/microsoft-365/compliance/view-the-dlp-reports)|
|Usuário|Envio de emails anômalos <br> (Um usuário enviou recentemente mais emails do que durante os últimos 7 a 10 dias.)|A investigação automatizada não resulta em uma ação pendente específica. <p> Enviar um grande volume de email não é mal-intencionado por si só; o usuário pode ter enviado emails para um grande grupo de destinatários de um evento. Para investigar, use informações [de fluxo de emails,](mail-flow-insights-v2.md)incluindo o relatório de [mapa](mfi-mail-flow-map-report.md) de fluxo de emails para determinar o que está acontecendo e tomar medidas.|
|

## <a name="next-steps"></a>Próximas etapas

- [Exibir detalhes e resultados de uma investigação automatizada no Microsoft Defender para Office 365](air-view-investigation-results.md)

- [Exibir ações de correção pendentes ou concluídas após uma investigação automatizada no Microsoft Defender para Office 365](air-review-approve-pending-completed-actions.md)

## <a name="related-articles"></a>Artigos relacionados

- [Saiba mais sobre a investigação automatizada no Microsoft Defender para Ponto de Extremidade](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)

- [Saiba mais sobre os recursos no Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection)
