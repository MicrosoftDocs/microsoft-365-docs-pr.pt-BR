---
title: Ações de correção após a investigação automatizada no Microsoft defender para Office 365
keywords: AIR, autoIR, ATP, automatizado, investigação, resposta, correção, ameaças, avançado, ameaça, proteção
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Saiba mais sobre ações de correção seguindo a investigação automatizada no Microsoft defender para Office 365.
ms.date: 09/29/2020
ms.custom:
- air
ms.openlocfilehash: 7727d74642c7eb1798322c7c5c1845806f83ba7c
ms.sourcegitcommit: 474bd6a86c3692d11fb2c454591c89029ac5bbd5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/19/2020
ms.locfileid: "49357450"
---
# <a name="remediation-actions-following-automated-investigation-in-microsoft-defender-for-office-365"></a>Ações de correção após a investigação automatizada no Microsoft defender para Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


## <a name="remediation-actions"></a>Ações de correção

Os [recursos de investigação e resposta automatizados](office-365-air.md) (Air) no [Microsoft Defender para Office 365](office-365-atp.md) incluem determinadas ações de correção. Sempre que uma investigação automatizada estiver em andamento ou tiver sido concluída, você normalmente verá uma ou mais ações de remediação que requerem aprovação da sua equipe de operações de segurança para prosseguir. Essas ações de correção podem incluir o seguinte:

- Exclusão reversível de mensagens de emails ou clusters
- Bloquear URL (hora do clique)
- Desativar o encaminhamento de emails externo
- Desativar a delegação

> [!NOTE]
> No Microsoft defender para Office 365, as investigações automatizadas não resultam em ações de correção realizadas automaticamente. As ações de correção são executadas apenas após a aprovação da equipe de operações de segurança da sua organização.

## <a name="threats-and-remediation-actions"></a>Ameaças e ações de correção

A tabela a seguir resume as ameaças e as ações de correção apropriadas no Microsoft defender para Office 365. Em alguns casos, uma investigação automatizada não resulta em uma ação de correção específica. Sua equipe de operações de segurança pode investigar e tomar as ações apropriadas, conforme descrito na tabela abaixo.

****

|Categoria|Ameaça/risco|Ação (ões) de correção|
|---|---|---|
|Email|Malware|Exclusão reversível de email/cluster <p> Se mais de uma quantidade de mensagens de email em um cluster contiver malware, o cluster será considerado mal-intencionado.|
|Email|URL mal-intencionada<br/>(Uma URL maliciosa foi detectada por [links seguros no Microsoft defender para Office 365](atp-safe-links.md).|Exclusão reversível de email/cluster <p> O email que contém uma URL mal-intencionada é considerado mal-intencionado.|
|Email|Golpe|Exclusão reversível de email/cluster <p> Se mais de uma quantidade de mensagens de email em um cluster contiver tentativas de phishing, o cluster será considerado como phishing.|
|Email|Zapped Phish <br/>(Mensagens de email foram entregues e [zapped](zero-hour-auto-purge.md).)|Exclusão reversível de email/cluster <p> Os relatórios estão disponíveis para exibir mensagens do zapped. [Veja se zap moveu uma mensagem e perguntas frequentes](zero-hour-auto-purge.md#how-to-see-if-zap-moved-your-message).|
|Email|Email de phishing perdido [relatado](enable-the-report-message-add-in.md) por um usuário|[Investigação automatizada disparada pelo relatório do usuário](automated-investigation-response-office.md#example-a-user-reported-phish-message-launches-an-investigation-playbook)|
|Email|Anomalia de volume <br/>(Quantidades recentes de emails excedem os últimos 7-10 dias para critérios de correspondência.)|A investigação automatizada não resulta em uma ação específica pendente. <p> A anomalia do volume não é uma ameaça clara, mas é meramente uma indicação de grandes volumes de email em dias recentes, em comparação aos últimos 7-10 dias. Embora isso possa indicar possíveis problemas, a confirmação é necessária em termos de verdicts mal-intencionados ou uma revisão manual de mensagens/clusters de email. Confira [Localizar emails suspeitos que foram entregues](investigate-malicious-email-that-was-delivered.md#find-suspicious-email-that-was-delivered).|
|Email|Nenhuma ameaça encontrada <br/>(O sistema não encontrou ameaças com base em arquivos, URLs ou análises de verdicts de cluster de emails.)|A investigação automatizada não resulta em uma ação específica pendente. <p> Ameaças encontradas e [zapped](zero-hour-auto-purge.md) após a conclusão de uma investigação não são refletidas nas conclusões numéricas de uma investigação, mas essas ameaças podem ser visualizadas no [Explorador de ameaças](threat-explorer.md).|
|Usuário|Um usuário clicou em uma URL mal-intencionada <br/>(Um usuário navegou até uma página que foi encontrada mais tarde como mal-intencionado ou um usuário ignorou uma [página de aviso de links seguros](atp-safe-links.md#warning-pages-from-safe-links) para acessar uma página mal-intencionada.)|A investigação automatizada não resulta em uma ação específica pendente. <p> Use o explorador de ameaças para [exibir dados sobre URLs e clique em verdicts](threat-explorer.md#view-data-about-phishing-urls-and-click-verdict). <p> Se sua organização estiver usando o [Microsoft defender para ponto de extremidade](https://docs.microsoft.com/windows/security/threat-protection/), considere [investigar o usuário](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/investigate-user) para determinar se sua conta está comprometida.|
|Usuário|Um usuário está enviando malware/Phish|A investigação automatizada não resulta em uma ação específica pendente. <p> O usuário pode estar relatando malware/Phish ou alguém pode [falsificar o usuário](anti-spoofing-protection.md) como parte de um ataque. Use o [Explorador de ameaças](threat-explorer.md) para exibir e lidar com emails contendo [malware](threat-explorer-views.md#email--malware) ou [phishing](threat-explorer-views.md#email--phish).|
|Usuário|Encaminhamento de e-mail <br/>(As regras de encaminhamento de caixa de correio são configuradas, o que pode ser usado para os dados exfiltration.)|Remover regra de encaminhamento <p> Use as [informações do fluxo de emails](mail-flow-insights-v2.md), incluindo o [relatório de mensagens automaticamente](mfi-auto-forwarded-messages-report.md), para exibir detalhes mais específicos sobre emails encaminhados.|
|Usuário|Regras de delegação de email <br/>(Uma conta de usuário tem A delegação configurada.)|Remover regra de delegação <p> Se sua organização estiver usando o [Microsoft defender para ponto de extremidade](https://docs.microsoft.com/windows/security/threat-protection/), considere [investigar o usuário](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/investigate-user) que está obtendo a permissão de delegação.|
|Usuário|Exfiltração dos dados<br/>(Um usuário violou [políticas de DLP](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies)de compartilhamento de arquivos ou emails.)|A investigação automatizada não resulta em uma ação específica pendente. <p> [Exibir relatórios de DLP e realizar ações](https://docs.microsoft.com/microsoft-365/compliance/view-the-dlp-reports).|
|Usuário|Envio de emails anômalas <br/>(Um usuário enviou recentemente mais email do que nos últimos 7-10 dias.)|A investigação automatizada não resulta em uma ação específica pendente. <p> O envio de muitos emails não é mal-intencionado por si só; o usuário pode apenas enviar emails para um grupo grande de destinatários para um evento. Para investigar, use as [informações de fluxo de emails](mail-flow-insights-v2.md), incluindo o [relatório de mapa de fluxo de emails](mfi-mail-flow-map-report.md) para determinar o que está acontecendo e tomar as medidas.|
|

## <a name="next-steps"></a>Próximas etapas

- [Exibir detalhes e resultados de uma investigação automatizada no Microsoft defender para Office 365](air-view-investigation-results.md)

- [Exibir ações de correção pendentes ou concluídas após uma investigação automatizada no Microsoft defender para Office 365](air-review-approve-pending-completed-actions.md)

## <a name="related-articles"></a>Artigos relacionados

- [Saiba mais sobre a investigação automatizada no Microsoft defender para ponto de extremidade](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)

- [Saiba mais sobre os recursos adicionais no Microsoft 365 defender](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection)
