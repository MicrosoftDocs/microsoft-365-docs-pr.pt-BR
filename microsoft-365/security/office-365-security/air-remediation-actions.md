---
title: Ações de correção no Office 365 investigação e resposta automatizadas
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
ms.collection: M365-security-compliance
description: Saiba mais sobre as ações de correção em recursos de investigação e resposta automatizados no Office 365 Advanced Threat Protection Plan 2.
ms.openlocfilehash: d0f08c3e89882e21263c18246612949ea68ac1ad
ms.sourcegitcommit: 9ed3283dd6dd959faeca5c22613f9126261b9590
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/16/2020
ms.locfileid: "43528924"
---
# <a name="remediation-actions-in-office-365"></a>Ações de correção no Office 365

## <a name="remediation-actions"></a>Ações de correção

[Recursos de investigação e resposta automatizados](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air) (Air) no [Office 365 proteção avançada contra ameaças](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) (Office 365 ATP) plano 2 inclui determinadas ações de correção. Sempre que uma investigação automatizada estiver em execução ou concluída, você verá, em geral, uma ou mais ações de correção que exigem aprovação da equipe de operações de segurança para continuar. Essas ações de correção podem incluir o seguinte:

- Exclusão reversível de mensagens de emails ou clusters
- Bloquear URL (hora do clique)
- Desativar o encaminhamento de emails externo
- Desativar a delegação

> [!NOTE]
> No Office 365 ATP, as investigações automatizadas não são automaticamente corrigidas. As ações de correção são executadas apenas após a aprovação da equipe de segurança da sua organização.

## <a name="threats-and-remediation-actions"></a>Ameaças e ações de correção

A tabela a seguir resume as ameaças e as ações de correção apropriadas no Office 365 ATP. Em alguns casos, uma investigação automatizada não resulta em uma ação de correção específica. Sua equipe de operações de segurança pode investigar e tomar as ações apropriadas, conforme descrito na tabela abaixo.

||||
|---|---|---|
|**Categoria**|**Ameaça/risco**|**Ação (ões) de correção**|
|Email|Malware| Exclusão reversível de email/cluster <br/><br/>Se mais de uma quantidade de mensagens de email em um cluster contiver malware, o cluster será considerado mal-intencionado.|
|Email|URL mal-intencionada<br/>(Uma URL maliciosa foi detectada pelos [links seguros de ATP do Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/how-atp-safe-links-works).)|Exclusão reversível de email/cluster <br/><br/>O email que contém uma URL mal-intencionada é considerado mal-intencionado.|
|Email|Phish| Exclusão reversível de email/cluster <br/><br/>Se mais de uma quantidade de mensagens de email em um cluster contiver tentativas de phishing, o cluster será considerado como phishing.|
|Email|Zapped Phish <br/>(Mensagens de email foram entregues e [zapped](https://docs.microsoft.com/microsoft-365/security/office-365-security/zero-hour-auto-purge).)|Exclusão reversível de email/cluster <br/><br/>Os relatórios estão disponíveis para exibir mensagens do zapped. [Veja se zap moveu uma mensagem e perguntas frequentes](https://docs.microsoft.com/microsoft-365/security/office-365-security/zero-hour-auto-purge#how-to-see-if-zap-moved-your-message).|
|Email|Email de phishing perdido [relatado](https://docs.microsoft.com/microsoft-365/security/office-365-security/enable-the-report-message-add-in) por um usuário| [Investigação automatizada disparada pelo relatório do usuário](https://docs.microsoft.com/microsoft-365/security/office-365-security/automated-investigation-response-office#example-a-user-reported-phish-message-launches-an-investigation-playbook)|
|Email|Anomalia de volume <br/>(Quantidades recentes de emails excedem os últimos 7-10 dias para critérios de correspondência.)|A investigação automatizada não resulta em uma ação específica pendente. <br/><br/>A anomalia do volume não é uma ameaça clara, mas é meramente uma indicação de grandes volumes de email em dias recentes, em comparação aos últimos 7-10 dias. Embora isso possa indicar possíveis problemas, a confirmação é necessária em termos de verdicts mal-intencionados ou uma revisão manual de mensagens/clusters de email. Consulte [Localizar e excluir emails suspeitos que foram entregues](https://docs.microsoft.com/microsoft-365/security/office-365-security/investigate-malicious-email-that-was-delivered#find-and-delete-suspicious-email-that-was-delivered).|
|Email|Nenhuma ameaça encontrada <br/>(O sistema não encontrou ameaças com base em arquivos, URLs ou análises de verdicts de cluster de emails.)|A investigação automatizada não resulta em uma ação específica pendente. <br/><br/>Ameaças encontradas e [zapped](https://docs.microsoft.com/microsoft-365/security/office-365-security/zero-hour-auto-purge) após a conclusão de uma investigação não são refletidas nas conclusões numéricas de uma investigação, mas essas ameaças podem ser visualizadas no [Explorador de ameaças](https://docs.microsoft.com/microsoft-365/security/office-365-security/threat-explorer).|
|Usuário|Um usuário clicou em uma URL mal-intencionada <br/>(Um usuário navegou até uma página que foi encontrada mais tarde como mal-intencionado ou um usuário ignorou uma [página de aviso de links seguros](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links-warning-pages) para acessar uma página mal-intencionada.)|A investigação automatizada não resulta em uma ação específica pendente. <br/><br/>Use o explorador de ameaças para [exibir dados sobre URLs e clique em verdicts](https://docs.microsoft.com/microsoft-365/security/office-365-security/threat-explorer#view-data-about-phishing-urls-and-click-verdict). <br/><br/>Se sua organização estiver usando a [proteção avançada contra ameaças do Microsoft defender](https://docs.microsoft.com/windows/security/threat-protection/), considere [investigar o usuário](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/investigate-user) para determinar se sua conta está comprometida.|
|Usuário|Um usuário está enviando malware/Phish|A investigação automatizada não resulta em uma ação específica pendente. <br/><br/>O usuário pode estar relatando malware/Phish ou alguém pode [falsificar o usuário](https://docs.microsoft.com/microsoft-365/security/office-365-security/anti-spoofing-protection) como parte de um ataque. Use o [Explorador de ameaças](https://docs.microsoft.com/microsoft-365/security/office-365-security/threat-explorer) para exibir e lidar com emails contendo [malware](https://docs.microsoft.com/microsoft-365/security/office-365-security/threat-explorer-views#email--malware) ou [phishing](https://docs.microsoft.com/microsoft-365/security/office-365-security/threat-explorer-views#email--phish).|
|Usuário|Encaminhamento de e-mail <br/>(As regras de encaminhamento de caixa de correio são configuradas, o que pode ser usado para os dados exfiltration.)|Remover regra de encaminhamento <br/><br/>Use as [informações do fluxo de emails](https://docs.microsoft.com/microsoft-365/security/office-365-security/mail-flow-insights-v2), incluindo o [relatório de mensagens automaticamente](https://docs.microsoft.com/microsoft-365/security/office-365-security/mfi-auto-forwarded-messages-report), para exibir detalhes mais específicos sobre emails encaminhados.|
|Usuário|Regras de delegação de email <br/>(Uma conta de usuário tem A delegação configurada.)|Remover regra de delegação <br/><br/> Se sua organização estiver usando a [proteção avançada contra ameaças do Microsoft defender](https://docs.microsoft.com/windows/security/threat-protection/), considere [investigar o usuário](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/investigate-user) que está obtendo a permissão de delegação.|
|Usuário|Exfiltration de dados<br/>(Um usuário violou [políticas de DLP](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies)de compartilhamento de arquivos ou emails.)|A investigação automatizada não resulta em uma ação específica pendente. <br/><br/>[Exibir relatórios de DLP e realizar ações](https://docs.microsoft.com/microsoft-365/compliance/view-the-dlp-reports).|
|Usuário|Envio de emails anômalas <br/>(Um usuário enviou recentemente mais email do que nos últimos 7-10 dias.)|A investigação automatizada não resulta em uma ação específica pendente. <br/><br/>O envio de muitos emails não é mal-intencionado por si só; o usuário pode apenas enviar emails para um grupo grande de destinatários para um evento. Para investigar, use as [informações de fluxo de emails](https://docs.microsoft.com/microsoft-365/security/office-365-security/mail-flow-insights-v2), incluindo o [relatório de mapa de fluxo de emails](https://docs.microsoft.com/microsoft-365/security/office-365-security/mfi-mail-flow-map-report) para determinar o que está acontecendo e tomar as medidas.|
|

## <a name="next-steps"></a>Próximas etapas

- [Exibir detalhes e resultados de uma investigação automatizada no Office 365](air-view-investigation-results.md)

- [Exibir ações de correção pendentes ou concluídas após uma investigação automatizada no Office 365](air-review-approve-pending-completed-actions.md)


## <a name="related-articles"></a>Artigos relacionados

- [Investigação automatizada no Microsoft defender proteção avançada contra ameaças](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)

- [Saiba mais sobre a proteção contra ameaças da Microsoft](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection)
