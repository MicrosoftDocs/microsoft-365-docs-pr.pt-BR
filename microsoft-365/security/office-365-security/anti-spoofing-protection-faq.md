---
title: Perguntas frequentes sobre a proteção antifalsificação
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: troubleshooting
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
- m365-initiative-defender-office365
description: Os administradores podem exibir perguntas frequentes e respostas sobre a proteção contra falsificação no Exchange Online Protection (EOP).
ms.openlocfilehash: 57ca258e2990719e50a84a402e0b4ff7db1c229e
ms.sourcegitcommit: 5e1b8c959a081022826fb09358730096248507ed
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/09/2020
ms.locfileid: "48411717"
---
# <a name="anti-spoofing-protection-faq"></a>Perguntas frequentes sobre a proteção antifalsificação

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Este artigo fornece perguntas frequentes e respostas sobre a proteção contra falsificação para organizações do Microsoft 365 com caixas de correio no Exchange Online, ou organizações autônomas do Exchange Online Protection (EOP), sem caixas de correio do Exchange Online.

Para perguntas e respostas sobre a proteção contra spam, confira [perguntas frequentes sobre proteção](anti-spam-protection-faq.md)contra spam.

Para perguntas e respostas sobre a proteção contra malware, consulte [Anti-Malware Protection FAQ](anti-malware-protection-faq-eop.md)

## <a name="why-did-microsoft-choose-to-junk-unauthenticated-inbound-email"></a>Por que a Microsoft optou por emails de entrada não autenticados de lixo eletrônico?

A Microsoft acredita que o risco de continuar a permitir emails de entrada não autenticados é maior do que o risco de perder emails de entrada legítimos.

## <a name="does-junking-unauthenticated-inbound-email-cause-legitimate-email-to-be-marked-as-spam"></a>O lixo eletrônico de entrada não autenticado faz com que emails legítimos sejam marcados como spam?

Quando a Microsoft habilitou este recurso no 2018, ocorreram alguns falsos positivos (mensagens boas foram marcadas como ruins). No entanto, ao longo do tempo, os remetentes ajustados para os requisitos. O número de mensagens que foram identificadas indevidos como falsificadas se tornaram insignificantes para a maioria dos caminhos de email.

A própria Microsoft primeiro adotou os novos requisitos de autenticação de email várias semanas antes de implantá-lo para os clientes. Embora tenha havido dificuldades no início, elas diminuíram gradualmente.

## <a name="is-spoof-intelligence-available-to-microsoft-365-customers-without-atp"></a>A inteligência de falsificação está disponível para clientes da Microsoft 365 sem ATP?

Sim. A partir de outubro de 2018, a inteligência de falsificação está disponível para todas as organizações com caixas de correio no Exchange Online e organizações EOP autônomas sem caixas de correio do Exchange Online.

A tecnologia antifalsificação estava inicialmente disponível apenas na proteção avançada contra ameaças do Office 365. Por exemplo, assinaturas do Microsoft E5 ou Complementos ATP.

## <a name="how-can-i-report-spam-or-non-spam-messages-back-to-microsoft"></a>Como relatar mensagens de spam ou não spam para a Microsoft?

Confira [Relatar mensagens e arquivos à Microsoft](report-junk-email-messages-to-microsoft.md).

## <a name="im-an-admin-and-i-dont-know-all-of-sources-for-messages-in-my-email-domain"></a>Sou um administrador e não sei todas as fontes de mensagens em meu domínio de email!

Confira [se você não conhece todas as fontes de email](email-validation-and-authentication.md#you-dont-know-all-sources-for-your-email).

## <a name="what-happens-if-i-disable-anti-spoofing-protection-for-my-organization"></a>O que acontece se eu desabilitar a proteção contra falsificação para minha organização?

Não recomendamos desabilitar a proteção contra falsificação. Desabilitar a proteção permitirá que mais mensagens de phishing e spam sejam entregues na sua organização. Nem todos os phishing são falsificações, e nem todas as mensagens falsificadas serão perdidas. No entanto, seu risco será maior.

Agora que a [filtragem avançada para conectores](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) está disponível, não recomendamos mais desativar a proteção contra falsificação quando o email é roteado por outro serviço antes do EOP.

## <a name="does-anti-spoofing-protection-mean-i-will-be-protected-from-all-phishing"></a>A proteção contra falsificação significa que eu será protegido contra todos os phishing?

Infelizmente, não. Os invasores se adaptarão ao uso de outras técnicas (por exemplo, contas comprometidas ou contas em serviços de email gratuitos). No entanto, a proteção anti-phishing funciona muito melhor para detectar esses outros tipos de métodos de phishing. As camadas de proteção no EOP são projetadas juntas e compiladas umas sobre as outras.

## <a name="do-other-large-email-services-block-unauthenticated-inbound-email"></a>Outros grandes serviços de email bloqueiam emails de entrada não autenticados?

Quase todos os grandes serviços de email implementam verificações tradicionais de SPF, DKIM e DMARC. Alguns serviços têm outras verificações mais estritas, mas poucos vão até o EOP para bloquear emails não autenticados e tratá-los como mensagens falsificadas. No entanto, o setor está se tornando mais atento a problemas com emails não autenticados, especialmente devido ao problema de phishing.

## <a name="do-i-still-need-to-enable-the-advanced-spam-filter-setting-spf-record-hard-fail-_markasspamspfrecordhardfail_-if-i-enable-anti-spoofing"></a>Ainda precisa habilitar a configuração avançada de filtro de spam "registro SPF: falha de hardware" (_MarkAsSpamSpfRecordHardFail_) se eu habilitar a antifalsificação?

Não. Essa configuração de ASF não é mais necessária. A proteção antifalsificação considera a falha de hardware SPF e um conjunto muito mais amplo de critérios. Se você habilitar a antifalsificação e ativado o **Registro SPF: ocorreu um erro no hardware** (_MarkAsSpamSpfRecordHardFail_), provavelmente obterá mais falsos positivos.

Recomendamos que você desabilite esse recurso, pois ele não fornecerá praticamente nenhum benefício adicional para detectar spam ou mensagens de phishing e, em vez disso, geraria quase todos os falsos positivos. Para obter mais informações, consulte [Configurações avançadas de filtro de spam (ASF) no EOP](advanced-spam-filtering-asf-options.md).

## <a name="does-sender-rewriting-scheme-help-fix-forwarded-email"></a>A ajuda do esquema de reconfiguração do remetente corrige emails encaminhados?

O SRS corrige apenas parcialmente o problema dos emails encaminhados. Ao reescrever o **email SMTP de**, o SRS pode garantir que a mensagem encaminhada passe SPF no próximo destino. No entanto, como a antifalsificação baseia-se no endereço **de** em combinação com o domínio de assinatura ou **email de** DKIM (ou outros sinais), não é suficiente impedir que emails enviados do SRS sejam marcados como falsificados.
