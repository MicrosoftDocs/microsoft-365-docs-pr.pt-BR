---
title: Ajustar a proteção anti-phishing
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid: ''
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
- MET150
description: Os administradores podem aprender a identificar os motivos por que e como uma mensagem de phishing recebeu no Microsoft 365 e o que fazer para evitar mais mensagens de phishing no futuro.
ms.openlocfilehash: e933769b6bce9eb10765fb2b58025445432bed18
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/03/2020
ms.locfileid: "48845463"
---
# <a name="tune-anti-phishing-protection"></a>Ajustar a proteção anti-phishing

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Embora a Microsoft 365 tenha uma variedade de recursos antiphishing habilitados por padrão, é possível que algumas mensagens de phishing ainda possam ser obtidas por meio de suas caixas de correio. Este tópico descreve o que você pode fazer para descobrir por que uma mensagem de phishing foi obtida e o que você pode fazer para ajustar as configurações de anti-phishing na sua organização do Microsoft 365 _sem dificultar as coisas_.

## <a name="first-things-first-deal-with-any-compromised-accounts-and-make-sure-you-block-any-more-phishing-messages-from-getting-through"></a>As primeiras coisas primeiro: lidar com as contas comprometidas e certifique-se de bloquear qualquer mensagem de phishing para obter

Se a conta de um destinatário foi comprometida como resultado da mensagem de phishing, siga as etapas em [responder a uma conta de email comprometida no Microsoft 365](responding-to-a-compromised-email-account.md).

Se sua assinatura incluir o Microsoft defender para Office 365, você poderá usar o [Office 365 Threat Intelligence](office-365-ti.md) para identificar outros usuários que também receberam a mensagem de phishing. Você tem opções adicionais para bloquear mensagens de phishing:

- [Links seguros no Microsoft defender para Office 365](set-up-atp-safe-links-policies.md)

- [Anexos seguros no Microsoft defender para Office 365](set-up-atp-safe-attachments-policies.md)

- [Políticas anti-phishing no Microsoft defender para Office 365](configure-atp-anti-phishing-policies.md). Observe que você pode aumentar temporariamente os **limites de phishing avançados** na política de **padrão** para **agressivo** , **mais agressivo** ou **mais agressivo**.

Verifique se esses recursos do defender for Office 365 estão ativados.

## <a name="report-the-phishing-message-to-microsoft"></a>Relatar a mensagem de phishing para a Microsoft

Relatar mensagens de phishing é útil para ajustar os filtros usados para proteger todos os clientes no Microsoft 365. Para obter instruções, consulte [relatar mensagens e arquivos para a Microsoft](report-junk-email-messages-to-microsoft.md).

## <a name="inspect-the-message-headers"></a>Inspecionar os cabeçalhos da mensagem

Você pode examinar os cabeçalhos da mensagem de phishing para ver se há algo que você pode fazer sozinho para evitar que mais mensagens de phishing sejam recebidas. Em outras palavras, examinar os cabeçalhos das mensagens pode ajudá-lo a identificar quaisquer configurações na sua organização que foram responsáveis por permitir as mensagens de phishing no.

Especificamente, você deve verificar o campo de cabeçalho **X-Forefront-antispam-Report** nos cabeçalhos da mensagem para obter indicações de spam ignorado ou filtragem de phishing no valor de filtragem de spam veredicto (SFV). As mensagens que ignoram a filtragem terão uma entrada do `SCL:-1` , o que significa que uma de suas configurações permitia essa mensagem substituindo o spam ou phishing verdicts que foram determinados pelo serviço. Para obter mais informações sobre como obter cabeçalhos de mensagem e a lista completa de todos os cabeçalhos de mensagens antispam e anti-phishing disponíveis, consulte [anti-spam de cabeçalhos de mensagens no Microsoft 365](anti-spam-message-headers.md).

## <a name="best-practices-to-stay-protected"></a>Práticas recomendadas para permanecer protegidas

- Mensalmente, execute a [Pontuação segura](../mtp/microsoft-secure-score.md) para avaliar as configurações de segurança da sua organização.

- Para mensagens que terminam em quarentena por engano, ou para mensagens permitidas pelo, recomendamos que você pesquise essas mensagens no [Gerenciador de ameaças e nas detecções em tempo real](threat-explorer.md). Você pode pesquisar por remetente, destinatário ou ID da mensagem. Após localizar a mensagem, acesse os detalhes clicando no assunto. Para uma mensagem em quarentena, procure ver o que é a "tecnologia de detecção", para que você possa usar o método apropriado para substituir. Para obter uma mensagem permitida, procure ver qual política permitiu a mensagem. 

- Email falsificado está marcado como phishing no defender para Office 365. Às vezes, a falsificação é benigna e, às vezes, os usuários não a querem colocar em quarentena. Para minimizar o impacto para os usuários, revise periodicamente o [relatório de inteligência de falsificação](learn-about-spoof-intelligence.md). Depois de revisar e fazer as substituições necessárias, você pode ter certeza de [Configurar a inteligência de falsificação](set-up-anti-phishing-policies.md#spoof-settings) para **colocar em quarentena** mensagens suspeitas em vez de entregá-las na pasta lixo eletrônico do usuário.

- Você pode repetir a etapa acima para representação (domínio ou usuário). O relatório de representação é encontrado **Threat Management** em \> **Dashboard** \> **insights** do painel de gerenciamento de ameaças.

- Revise periodicamente o [relatório de status de proteção contra ameaças](view-reports-for-atp.md#threat-protection-status-report).

- Alguns clientes acidentalmente permitem mensagens de phishing por meio da colocação de seus próprios domínios na lista permitir remetente ou permitir domínio em políticas antispam. Embora essa configuração permita algumas mensagens legítimas, também permitirá mensagens mal-intencionadas que normalmente serão bloqueadas pelos filtros spam e/ou phishing. Em vez de permitir o domínio, você deve corrigir o problema subjacente.

  A melhor maneira de lidar com mensagens legítimas bloqueadas pelo Microsoft 365 (falsos positivos) que envolvem remetentes em seu domínio é configurar completamente e completamente os registros SPF, DKIM e DMARC no DNS para _todos os_ seus domínios de email:

  - Verifique se o registro SPF identifica _todas as_ fontes de email para remetentes em seu domínio (não esqueça de serviços de terceiros!).

  - Use a falha de hardware ( \- tudo) para garantir que os remetentes não autorizados sejam rejeitados por sistemas de email configurados para fazer isso. Você pode usar a [inteligência de falsificação](learn-about-spoof-intelligence.md) para ajudar a identificar remetentes que estejam usando seu domínio para que você possa incluir remetentes de terceiros autorizados em seu registro SPF.

  Para obter instruções de configuração, consulte:
  
  - [Configurar o SPF para ajudar a evitar falsificações](set-up-spf-in-office-365-to-help-prevent-spoofing.md)

  - [Usar o DKIM para validar emails enviados de seu domínio personalizado](use-dkim-to-validate-outbound-email.md)

  - [Usar DMARC para validar emails](use-dmarc-to-validate-email.md)

- Sempre que possível, recomendamos que você envie emails para seu domínio diretamente para o Microsoft 365. Em outras palavras, aponte o registro MX do seu domínio do Microsoft 365 para a Microsoft 365. O proteção do Exchange Online (EOP) é capaz de fornecer a melhor proteção para seus usuários de nuvem quando seus emails são entregues diretamente no Microsoft 365. Se você precisar usar um sistema de higiene de email de terceiros na frente do EOP, use a filtragem avançada para conectores. Para obter instruções, consulte [filtragem avançada para conectores no Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).

- Os usuários devem [relatar mensagens](enable-the-report-message-add-in.md) à Microsoft, que podem treinar nosso sistema. Os administradores também devem aproveitar os recursos de [envio de administrador](admin-submission.md) .

- A MFA (autenticação multifator) é uma boa maneira de evitar contas comprometidas. Você deve considerar fortemente habilitar a MFA para todos os seus usuários. Para obter uma abordagem em fases, comece habilitando a MFA para seus usuários mais confidenciais (administradores, executivos, etc.) antes de habilitar a MFA para todos. Para obter instruções, consulte [Configurar a autenticação multifator](../../admin/security-and-compliance/set-up-multi-factor-authentication.md).

- As regras de encaminhamento para destinatários externos costumam ser usadas por invasores para extrair dados. Use as informações **revisar regras de encaminhamento de caixa de correio** na [Pontuação segura da Microsoft](../mtp/microsoft-secure-score.md) para localizar e até mesmo impedir o encaminhamento de regras para destinatários externos. Para obter mais informações, consulte [mitigating Client external Forwarding Rules with Secure Score](https://docs.microsoft.com/archive/blogs/office365security/mitigating-client-external-forwarding-rules-with-secure-score).
