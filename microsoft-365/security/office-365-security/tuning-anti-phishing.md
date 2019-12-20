---
title: Ajustar a proteção contra phishing no Office 365
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
description: Os administradores podem aprender a identificar os motivos por que e como as mensagens de phishing foram recebidas e o que fazer para evitar mais mensagens de phishing no futuro.
ms.openlocfilehash: 03f4df5f552dab48283f18ec367ee6979afd9c89
ms.sourcegitcommit: 6ae69c40bafa6aef633789c3df0fa20590bdcf40
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/20/2019
ms.locfileid: "40823843"
---
# <a name="tune-anti-phishing-protection-in-office-365"></a>Ajustar a proteção contra phishing no Office 365

Embora o Office 365 seja fornecido com uma variedade de recursos antiphishing habilitados por padrão, é possível que algumas mensagens de phishing ainda possam ser acessadas pelas suas caixas de correio. Este tópico descreve o que você pode fazer para descobrir por que uma mensagem de phishing foi obtida e o que você pode fazer para ajustar as configurações de anti-phishing em sua organização do Exchange Online _sem dificultar as coisas_.

## <a name="first-things-first-deal-with-any-compromised-accounts-and-make-sure-you-block-any-more-phishing-messages-from-getting-through"></a>As primeiras coisas primeiro: lidar com as contas comprometidas e certifique-se de bloquear qualquer mensagem de phishing para obter

Se a conta de um destinatário foi comprometida como resultado da mensagem de phishing, siga as etapas em [responder a uma conta de email comprometida no Office 365](responding-to-a-compromised-email-account.md).

Se sua assinatura incluir a proteção avançada contra ameaças (ATP), você poderá usar o [Office 365 Threat Intelligence](office-365-ti.md) para identificar outros usuários que também receberam a mensagem de phishing. Você tem opções adicionais para bloquear mensagens de phishing:

- [Links seguros da ATP](set-up-atp-safe-links-policies.md)

- [Anexos Seguros da ATP](set-up-atp-safe-attachments-policies.md)

- [Políticas anti-phishing do ATP](set-up-anti-phishing-policies.md). Observe que você pode aumentar temporariamente os **limites de phishing avançados** na política de **padrão** para **agressivo**, **mais agressivo**ou **mais agressivo**.

Verifique se esses recursos ATP estão ativados.

## <a name="report-the-phishing-message-to-microsoft"></a>Relatar a mensagem de phishing para a Microsoft

Relatar mensagens de phishing é útil para ajustar os filtros usados para proteger todos os clientes do Office 365.

Envie a mensagem de phishing _como um anexo_ em uma nova mensagem, caso contrário, vazia para o **Phish@office365.microsoft.com**. Não encaminhe apenas a mensagem original; caso contrário, não é possível examinar os cabeçalhos da mensagem original. Ou você pode usar o suplemento de [mensagem de relatório](https://docs.microsoft.com/office365/securitycompliance/enable-the-report-message-add-in) no Outlook ou no Outlook na Web (anteriormente conhecido como Outlook Web App).

Para obter mais informações, consulte [enviar mensagens de spam, não spam e golpes de phishing para a Microsoft para análise](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md).

## <a name="inspect-the-message-headers"></a>Inspecionar os cabeçalhos da mensagem

Você pode examinar os cabeçalhos da mensagem de phishing para ver se há algo que você pode fazer sozinho para evitar que mais mensagens de phishing sejam recebidas. Em outras palavras, examinar os cabeçalhos das mensagens pode ajudá-lo a identificar quaisquer configurações na sua organização que foram responsáveis por permitir as mensagens de phishing no.

Especificamente, você deve verificar o campo de cabeçalho **X-Forefront-antispam-Report** nos cabeçalhos da mensagem para obter indicações de spam ignorado ou filtragem de phishing no valor de filtragem de spam veredicto (SFV). As mensagens que ignoram a filtragem terão uma `SCL:-1`entrada do, o que significa que uma de suas configurações permitia essa mensagem substituindo o spam ou phishing verdicts que foram determinados pelo serviço. Para obter mais detalhes sobre como obter cabeçalhos de mensagem e a lista completa de todos os cabeçalhos de mensagens antispam e antispam disponíveis, consulte [anti-spam](https://docs.microsoft.com/office365/SecurityCompliance/anti-spam-message-headers).

## <a name="best-practices-to-stay-protected"></a>Práticas recomendadas para permanecer protegidas

- Mensalmente, execute a [Pontuação segura](../mtp/microsoft-secure-score.md) para avaliar as configurações de segurança da sua organização do Office 365.

- Revise periodicamente o [relatório de inteligência de falsificação](learn-about-spoof-intelligence.md) e [habilite a proteção contra falsificação na política](learn-about-spoof-intelligence.md#configuring-the-anti-spoofing-policy) anti-phishing para **colocar em quarentena** mensagens suspeitas, em vez de entregá-las na pasta lixo eletrônico do usuário.

- Revise periodicamente o [relatório de status de proteção contra ameaças](view-reports-for-atp.md#threat-protection-status-report).

- Alguns clientes acidentalmente permitem mensagens de phishing por meio da colocação de seus próprios domínios na lista permitir remetente ou permitir domínio em políticas antispam. Se você optar por fazer isso, você deve usar muito cuidado. Embora essa configuração permita algumas mensagens legítimas, ela também permitirá mensagens mal-intencionadas que normalmente serão bloqueadas pelos filtros de spam e/ou phishing do Office 365.

  A melhor maneira de lidar com mensagens legítimas bloqueadas pelo Office 365 (falsos positivos) que envolvem remetentes em seu domínio é configurar completamente e completamente os registros SPF, DKIM e DMARC no DNS para _todos os_ seus domínios de email no Office 365:

  - Verifique se o registro SPF identifica _todas as_ fontes de email para remetentes em seu domínio (não esqueça de serviços de terceiros!).

  - Use a falha de\-hardware () para garantir que os remetentes não autorizados sejam rejeitados por sistemas de email configurados para fazer isso. Você pode usar a [inteligência de falsificação](https://docs.microsoft.com/office365/securitycompliance/learn-about-spoof-intelligence) para ajudar a identificar remetentes que estejam usando seu domínio para que você possa incluir remetentes de terceiros autorizados em seu registro SPF.

  Para obter instruções de configuração, consulte:
  
  - [Configurar o SPF no Office 365 para ajudar a evitar falsificações](set-up-spf-in-office-365-to-help-prevent-spoofing.md)

  - [Usar DKIM para validar emails enviados de seu domínio personalizado no Office 365](use-dkim-to-validate-outbound-email.md)

  - [Usar DMARC para validar emails no Office 365](use-dmarc-to-validate-email.md)

- Sempre que possível, recomendamos que você envie emails para seu domínio diretamente para o Office 365. Em outras palavras, aponte o registro MX do seu domínio do Office 365 para o Office 365. O proteção do Exchange Online (EOP) é capaz de fornecer a melhor proteção para seus usuários de nuvem quando seus emails são entregues diretamente no Office 365. Se você precisar usar um sistema de higiene de email de terceiros na frente do EOP, verifique se você seguiu as orientações [aqui](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-mail-flow-using-third-party-cloud).

- A MFA (autenticação multifator) é uma ótima maneira de evitar contas comprometidas. Você deve considerar fortemente habilitar a MFA para todos os seus usuários. Para obter uma abordagem em fases, comece habilitando a MFA para seus usuários mais confidenciais (administradores, executivos, etc.) antes de habilitar a MFA para todos. Para obter instruções, consulte [Configurar a autenticação multifator](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication).

- As regras de encaminhamento para destinatários externos costumam ser usadas por invasores para extrair dados. Use as informações **revisar regras de encaminhamento de caixa de correio** na [Pontuação segura da Microsoft](../mtp/microsoft-secure-score.md) para localizar e até mesmo impedir o encaminhamento de regras para destinatários externos. Para obter mais informações, consulte [mitigating Client external Forwarding Rules with Secure Score](https://blogs.technet.microsoft.com/office365security/mitigating-client-external-forwarding-rules-with-secure-score/).
