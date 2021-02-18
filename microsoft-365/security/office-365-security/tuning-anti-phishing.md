---
title: Ajustar a proteção anti-phishing
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid: ''
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
- MET150
description: Os administradores podem aprender a identificar os motivos por que e como uma mensagem de phishing foi obtida no Microsoft 365 e o que fazer para evitar mais mensagens de phishing no futuro.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: d3abbafce36c589f60eb164fb29c714c980f8b98
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/18/2021
ms.locfileid: "50286484"
---
# <a name="tune-anti-phishing-protection"></a>Ajustar a proteção anti-phishing

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
- [Proteção do Exchange Online](exchange-online-protection-overview.md)
- [Plano 1 e plano 2 do Microsoft Defender para Office 365](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Embora o Microsoft 365 venha com uma variedade de recursos anti-phishing habilitados por padrão, é possível que algumas mensagens de phishing ainda poderiam chegar às suas caixas de correio. Este tópico descreve o que você pode fazer para descobrir o motivo pelo qual uma mensagem de phishing passou e o que você pode fazer para ajustar as configurações anti-phishing em sua organização do Microsoft 365 sem acidentalmente tornar as coisas ainda mais _ruins._

## <a name="first-things-first-deal-with-any-compromised-accounts-and-make-sure-you-block-any-more-phishing-messages-from-getting-through"></a>Primeiro: lidar com contas comprometidas e garantir que você bloqueie a passagem de mais mensagens de phishing

Se a conta de um destinatário foi comprometida como resultado da mensagem de phishing, siga as etapas em Responder a uma conta de email comprometida no [Microsoft 365.](responding-to-a-compromised-email-account.md)

Se sua assinatura incluir o Microsoft Defender para Office 365, você poderá usar a Inteligência contra Ameaças do [Office 365](office-365-ti.md) para identificar outros usuários que também receberam a mensagem de phishing. Você tem opções adicionais para bloquear mensagens de phishing:

- [Links seguros no Microsoft Defender para Office 365](set-up-atp-safe-links-policies.md)

- [Anexos seguros no Microsoft Defender para Office 365](set-up-atp-safe-attachments-policies.md)

- [Políticas anti-phishing no Microsoft Defender para Office 365.](configure-atp-anti-phishing-policies.md) Observe que você pode aumentar temporariamente os limites avançados de  **phishing** na política de **Padrão** para **Agressivo,** Mais agressivo ou **mais agressivo.**

Verifique se esses recursos do Defender para Office 365 estão ligado.

## <a name="report-the-phishing-message-to-microsoft"></a>Relatar a mensagem de phishing à Microsoft

Relatar mensagens de phishing é útil para ajustar os filtros usados para proteger todos os clientes no Microsoft 365. Para obter instruções, confira [Relatar mensagens e arquivos para a Microsoft.](report-junk-email-messages-to-microsoft.md)

## <a name="inspect-the-message-headers"></a>Inspecionar os headers da mensagem

Você pode examinar os headers da mensagem de phishing para ver se há algo que você mesmo possa fazer para impedir que mais mensagens de phishing possam ser recebidas. Em outras palavras, examinar os headers de mensagens pode ajudá-lo a identificar as configurações em sua organização que foram responsáveis por permitir a entrada das mensagens de phishing.

Especificamente, você deve verificar o campo de header **X-Forefront-Antispam-Report** nos headers de mensagem para indicações de filtragem ignorada para spam ou phishing no valor do Veredito de Filtragem de Spam (SFV). As mensagens que ignorarem a filtragem terão uma entrada, o que significa que uma de suas configurações permitiu essa mensagem substituindo os vereditos de spam ou phishing que foram `SCL:-1` determinados pelo serviço. Para obter mais informações sobre como obter os headers de mensagens e a lista completa de todos os headers de mensagens anti-spam e anti-phishing disponíveis, consulte Os headers de mensagens [anti-spam no Microsoft 365.](anti-spam-message-headers.md)

## <a name="best-practices-to-stay-protected"></a>Práticas recomendadas para permanecer protegido

- Mensalmente, execute o [Secure Score](../mtp/microsoft-secure-score.md) para avaliar as configurações de segurança da sua organização.

- Para mensagens que terminam em quarentena por engano ou para mensagens [permitidas,](threat-explorer.md)recomendamos pesquisar essas mensagens no Explorador de Ameaças e detecções em tempo real. Você pode pesquisar por remetente, destinatário ou ID da mensagem. Depois de localizar a mensagem, vá para detalhes clicando no assunto. Para uma mensagem em quarentena, procure ver qual era a "tecnologia de detecção" para que você possa usar o método apropriado para substituir. Para uma mensagem permitida, veja qual política permitiu a mensagem.

- Os emails spoofed são marcados como phishing no Defender para Office 365. Às vezes, a spoof é benigna e, às vezes, os usuários não a querem em quarentena. Para minimizar o impacto para os usuários, revise periodicamente o [relatório de inteligência contra spoof.](learn-about-spoof-intelligence.md) Depois de revisar e fazer as substituições necessárias, você pode ter  certeza de configurar a inteligência contra [spoof](set-up-anti-phishing-policies.md#spoof-settings) para colocar mensagens suspeitas em quarentena em vez de entregá-las à pasta Lixo Eletrônico do usuário.

- Você pode repetir a etapa acima para Representação (domínio ou usuário). O relatório de Representação é encontrado em **Insights do Painel de Gerenciamento** \> **de** \> **Ameaças.**

- Revise periodicamente o relatório [de Status da Proteção contra Ameaças.](view-reports-for-atp.md#threat-protection-status-report)

- Alguns clientes inadvertidamente permitem mensagens de phishing colocando seus próprios domínios na lista Permitir remetente ou Permitir domínio em políticas anti-spam. Embora essa configuração permita algumas mensagens legítimas, ela também permitirá mensagens mal-intencionadas que normalmente seriam bloqueadas pelos filtros de spam e/ou phishing. Em vez de permitir o domínio, você deve corrigir o problema subjacente.

  A melhor maneira de lidar com mensagens legítimas bloqueadas pelo Microsoft 365 (falsos positivos) que envolvem os envios em seu domínio  é configurar totalmente os registros SPF, DKIM e DMARC no DNS para todos os seus domínios de email:

  - Verifique se seu registro SPF identifica _todas_ as fontes de email para os senders em seu domínio (não se esqueça de serviços de terceiros!).

  - Use falha im disco rígido (tudo) para garantir que os envios não autorizados sejam rejeitados por sistemas de \- email configurados para fazer isso. Você pode usar a inteligência contra [spoof](learn-about-spoof-intelligence.md) para ajudar a identificar os envios que estão usando seu domínio para que você possa incluir os envios autorizados de terceiros em seu registro SPF.

  Para obter instruções de configuração, consulte:

  - [Configurar o SPF para ajudar a prevenir falsificação](set-up-spf-in-office-365-to-help-prevent-spoofing.md)

  - [Usar o DKIM para validar emails enviados de seu domínio personalizado](use-dkim-to-validate-outbound-email.md)

  - [Usar DMARC para validar emails](use-dmarc-to-validate-email.md)

- Sempre que possível, recomendamos que você envie emails para seu domínio diretamente para o Microsoft 365. Em outras palavras, aponte o registro MX do seu domínio do Microsoft 365 para o Microsoft 365. O Proteção do Exchange Online (EOP) é capaz de fornecer a melhor proteção para os usuários em nuvem quando seus emails são entregues diretamente ao Microsoft 365. Se você deve usar um sistema de higienização de email de terceiros na frente do EOP, use a Filtragem Aprimorada para Conectores. Para obter instruções, consulte [Filtragem aprimorada para conectores no Exchange Online.](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)

- Os usuários devem usar o complemento Mensagem [de Relatório](enable-the-report-message-add-in.md) ou o complemento [Phishing](enable-the-report-phish-add-in.md) de Relatório para relatar mensagens à Microsoft, que pode treinar nosso sistema. Os administradores também devem aproveitar os recursos [de Envio de](admin-submission.md) Administrador.

- A MFA (autenticação multifatória) é uma boa maneira de evitar contas comprometidas. Você deve considerar fortemente a habilitação da MFA para todos os seus usuários. Para uma abordagem em fases, comece habilitando a MFA para seus usuários mais confidenciais (administradores, executivos etc.) antes de habilitar a MFA para todos. Para obter instruções, [consulte Configurar a autenticação multifa factor.](../../admin/security-and-compliance/set-up-multi-factor-authentication.md)

- As regras de encaminhamento para destinatários externos geralmente são usadas por invasores para extrair dados. Use a **revisão de informações de regras de** encaminhamento de caixa de correio no Microsoft Secure [Score](../mtp/microsoft-secure-score.md) para encontrar e até mesmo impedir o encaminhamento de regras para destinatários externos. Para obter mais informações, consulte [Mitigando regras de encaminhamento externo do cliente com a Classificação de Segurança.](https://docs.microsoft.com/archive/blogs/office365security/mitigating-client-external-forwarding-rules-with-secure-score)
