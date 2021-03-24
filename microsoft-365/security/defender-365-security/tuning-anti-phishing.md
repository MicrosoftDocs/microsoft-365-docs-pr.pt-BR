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
description: Os administradores podem aprender a identificar os motivos e como uma mensagem de phishing foi recebida no Microsoft 365 e o que fazer para evitar mais mensagens de phishing no futuro.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 1772a0329825b8808352892c8d99f0d7680112f5
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51053444"
---
# <a name="tune-anti-phishing-protection"></a>Ajustar a proteção anti-phishing

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
- [Proteção do Exchange Online](exchange-online-protection-overview.md)
- [Plano 1 e plano 2 do Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Embora o Microsoft 365 venha com uma variedade de recursos anti-phishing que estão habilitados por padrão, é possível que algumas mensagens de phishing ainda sejam enviadas para suas caixas de correio. Este tópico descreve o que você pode fazer para descobrir por que uma mensagem de phishing passou e o que você pode fazer para ajustar as configurações anti-phishing em sua organização do Microsoft 365 sem acidentalmente tornar as coisas piores _._

## <a name="first-things-first-deal-with-any-compromised-accounts-and-make-sure-you-block-any-more-phishing-messages-from-getting-through"></a>Primeiro: lidar com contas comprometidas e impedir a passagem de mais mensagens de phishing

Se a conta de um destinatário foi comprometida como resultado da mensagem de phishing, siga as etapas em Responder a uma conta de email comprometida [no Microsoft 365](responding-to-a-compromised-email-account.md).

Se sua assinatura incluir o Microsoft Defender para Office 365, você poderá usar o [Office 365 Threat Intelligence](office-365-ti.md) para identificar outros usuários que também receberam a mensagem de phishing. Você tem opções adicionais para bloquear mensagens de phishing:

- [Links seguros no Microsoft Defender para Office 365](set-up-safe-links-policies.md)

- [Anexos seguros no Microsoft Defender para Office 365](set-up-safe-attachments-policies.md)

- [Políticas anti-phishing no Microsoft Defender para Office 365](configure-atp-anti-phishing-policies.md). Observe que você pode aumentar temporariamente os limites avançados de **phishing** na política de **Standard** para **Aggressive, More** **aggressive** ou **Most aggressive**.

Verifique se esses recursos do Defender para Office 365 estão a turned on.

## <a name="report-the-phishing-message-to-microsoft"></a>Relatar a mensagem de phishing para a Microsoft

Relatar mensagens de phishing é útil para ajustar os filtros usados para proteger todos os clientes no Microsoft 365. Para obter instruções, consulte [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).

## <a name="inspect-the-message-headers"></a>Inspecionar os headers da mensagem

Você pode examinar os headers da mensagem de phishing para ver se há algo que você pode fazer sozinho para impedir que mais mensagens de phishing possam ser enviadas. Em outras palavras, examinar os headers de mensagens pode ajudá-lo a identificar as configurações em sua organização que foram responsáveis por permitir as mensagens de phishing.

Especificamente, você deve verificar o campo de header **X-Forefront-Antispam-Report** nos headers da mensagem para ver se há indicações de filtragem ignorada para spam ou phishing no valor SFV (Veredito de Filtragem de Spam). As mensagens que ignoram a filtragem terão uma entrada de , o que significa que uma de suas configurações permitiu a passagem dessa mensagem substituindo os vereditos de spam ou phishing que foram `SCL:-1` determinados pelo serviço. Para obter mais informações sobre como obter os headers de mensagens e a lista completa de todos os headers de mensagens anti-spam e anti-phishing disponíveis, consulte Headers de mensagens [anti-spam no Microsoft 365](anti-spam-message-headers.md).

## <a name="best-practices-to-stay-protected"></a>Práticas recomendadas para manter-se protegido

- Mensalmente, execute a [Pontuação](../defender/microsoft-secure-score.md) Segura para avaliar as configurações de segurança da sua organização.

- Para mensagens que terminam em quarentena por engano ou para mensagens [permitidas,](threat-explorer.md)recomendamos que você pesquise essas mensagens no Explorador de Ameaças e detecções em tempo real. Você pode pesquisar por remetente, destinatário ou ID de mensagem. Depois de localizar a mensagem, vá para detalhes clicando no assunto. Para uma mensagem em quarentena, procure ver o que era a "tecnologia de detecção" para que você possa usar o método apropriado para substituir. Para uma mensagem permitida, procure ver qual política permitiu a mensagem.

- Email com spoofed é marcado como phishing no Defender para Office 365. Às vezes, a spoof é benigna e, às vezes, os usuários não o querem em quarentena. Para minimizar o impacto para os usuários, revise periodicamente o [relatório de inteligência Spoof.](learn-about-spoof-intelligence.md) Depois de revisar e fazer quaisquer substituições necessárias, [](set-up-anti-phishing-policies.md#spoof-settings) você pode ter  certeza de configurar a inteligência falsa para colocar em quarentena mensagens suspeitas em vez de entregá-las à pasta Lixo Eletrônico do usuário.

- Você pode repetir a etapa acima para Representação (domínio ou usuário). O relatório de representação é encontrado em Insights do Painel **de Gerenciamento** \> **de** \> **Ameaças.**

- Revise periodicamente o relatório [de Status da Proteção contra Ameaças.](view-reports-for-mdo.md#threat-protection-status-report)

- Alguns clientes inadvertidamente permitem mensagens de phishing colocando seus próprios domínios na lista Permitir remetente ou Permitir domínio em políticas anti-spam. Embora essa configuração permita a passagem de algumas mensagens legítimas, ela também permitirá mensagens mal-intencionadas que normalmente seriam bloqueadas pelos filtros de spam e/ou phishing. Em vez de permitir o domínio, você deve corrigir o problema subjacente.

  A melhor maneira de lidar com mensagens legítimas bloqueadas pelo Microsoft 365 (falsos positivos) que envolvem os envios em seu domínio  é configurar totalmente os registros SPF, DKIM e DMARC no DNS para todos os seus domínios de email:

  - Verifique se seu registro SPF identifica _todas_ as fontes de email para os envios em seu domínio (não se esqueça de serviços de terceiros!).

  - Use o fail rígido ( todos) para garantir que os envios não autorizados sejam rejeitados por sistemas de \- email configurados para fazer isso. Você pode usar a inteligência de [spoof](learn-about-spoof-intelligence.md) para ajudar a identificar os envios que estão usando seu domínio para que você possa incluir os envios autorizados de terceiros no registro SPF.

  Para obter instruções de configuração, consulte:

  - [Configurar o SPF para ajudar a prevenir falsificação](set-up-spf-in-office-365-to-help-prevent-spoofing.md)

  - [Usar o DKIM para validar emails enviados de seu domínio personalizado](use-dkim-to-validate-outbound-email.md)

  - [Usar DMARC para validar emails](use-dmarc-to-validate-email.md)

- Sempre que possível, recomendamos que você entregue emails para seu domínio diretamente para o Microsoft 365. Em outras palavras, aponte o registro MX do domínio microsoft 365 para o Microsoft 365. O Exchange Online Protection (EOP) é capaz de fornecer a melhor proteção para os usuários de nuvem quando seus emails são entregues diretamente ao Microsoft 365. Se você deve usar um sistema de higienização de email de terceiros em frente ao EOP, use Filtragem Aprimorada para Conectores. Para obter instruções, consulte [Enhanced Filtering for Connectors in Exchange Online](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).

- Os usuários devem usar o [complemento Mensagem de Relatório](enable-the-report-message-add-in.md) ou o complemento Relatar [Phishing](enable-the-report-phish-add-in.md) para relatar mensagens para a Microsoft, que pode treinar nosso sistema. Os administradores também devem aproveitar os recursos [de Envio de](admin-submission.md) Administrador.

- A autenticação de vários fatores (MFA) é uma boa maneira de evitar contas comprometidas. Você deve considerar habilmente a habilitação do MFA para todos os seus usuários. Para uma abordagem em fases, comece habilitando o MFA para os usuários mais confidenciais (administradores, executivos, etc.) antes de habilitar o MFA para todos. Para obter instruções, consulte [Set up multi-factor authentication](../../admin/security-and-compliance/set-up-multi-factor-authentication.md).

- O encaminhamento de regras para destinatários externos geralmente é usado por invasores para extrair dados. Use as **informações de regras** de encaminhamento de caixa de correio de revisão no Microsoft Secure [Score](../defender/microsoft-secure-score.md) para encontrar e até mesmo impedir o encaminhamento de regras para destinatários externos. Para obter mais informações, consulte Mitigando regras de [encaminhamento externo do cliente com pontuação segura.](/archive/blogs/office365security/mitigating-client-external-forwarding-rules-with-secure-score)
