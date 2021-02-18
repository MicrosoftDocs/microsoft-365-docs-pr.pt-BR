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
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Os administradores podem exibir perguntas frequentes e respostas sobre a proteção anti-spoofing no Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: d2d307d201af8ad09a4faf7a865a29da8942bdf8
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/18/2021
ms.locfileid: "50288904"
---
# <a name="anti-spoofing-protection-faq"></a>Perguntas frequentes sobre a proteção antifalsificação

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
- [Proteção do Exchange Online](exchange-online-protection-overview.md)
- [Plano 1 e plano 2 do Microsoft Defender para Office 365](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Este artigo fornece perguntas frequentes e respostas sobre a proteção anti-spoofing para organizações do Microsoft 365 com caixas de correio no Exchange Online ou organizações autônomas do Exchange Online Protection (EOP) sem caixas de correio do Exchange Online.

Para perguntas e respostas sobre a proteção anti-spam, consulte Perguntas frequentes sobre [a proteção anti-spam.](anti-spam-protection-faq.md)

Para obter perguntas e respostas sobre a proteção anti-malware, consulte Perguntas frequentes sobre [a proteção anti-malware](anti-malware-protection-faq-eop.md)

## <a name="why-did-microsoft-choose-to-junk-unauthenticated-inbound-email"></a>Por que a Microsoft escolheu lixo eletrônico de entrada não autenticado?

A Microsoft acredita que o risco de continuar a permitir emails de entrada não autenticados é maior do que o risco de perder emails de entrada legítimos.

## <a name="does-junking-unauthenticated-inbound-email-cause-legitimate-email-to-be-marked-as-spam"></a>O lixo eletrônico não autenticado faz com que emails legítimos sejam marcados como spam?

Quando a Microsoft habilitar esse recurso em 2018, alguns falsos positivos aconteceram (mensagens boas foram marcadas como ruins). No entanto, com o tempo, os senders se ajustaram aos requisitos. O número de mensagens mal identificadas como falsas tornou-se insignificante para a maioria dos caminhos de email.

A própria Microsoft adotou primeiro os novos requisitos de autenticação de email várias semanas antes de implantá-lo para os clientes. Embora tenha havido dificuldades no início, elas diminuíram gradualmente.

## <a name="is-spoof-intelligence-available-to-microsoft-365-customers-without-defender-for-office-365"></a>A inteligência contra spoof está disponível para clientes do Microsoft 365 sem o Defender para Office 365?

Sim. A partir de outubro de 2018, a inteligência contra spoof está disponível para todas as organizações com caixas de correio no Exchange Online e organizações autônomas do EOP sem caixas de correio do Exchange Online.

## <a name="how-can-i-report-spam-or-non-spam-messages-back-to-microsoft"></a>Como relatar mensagens de spam ou não spam para a Microsoft?

Confira [Relatar mensagens e arquivos à Microsoft](report-junk-email-messages-to-microsoft.md).

## <a name="im-an-admin-and-i-dont-know-all-of-sources-for-messages-in-my-email-domain"></a>Sou um administrador e não sei todas as fontes para mensagens em meu domínio de email!

Você [não conhece todas as fontes para seu email.](email-validation-and-authentication.md#you-dont-know-all-sources-for-your-email)

## <a name="what-happens-if-i-disable-anti-spoofing-protection-for-my-organization"></a>O que acontece se eu desabilitar a proteção anti-spoofing para minha organização?

Não recomendamos desabilitar a proteção anti-spoofing. Desabilitar a proteção permitirá que mais mensagens de phishing e spam sejam entregues em sua organização. Nem todos os phishing são spoofing, e nem todas as mensagens falsas serão perdidas. No entanto, seu risco será maior.

Agora que [a](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) Filtragem Aprimorada para Conectores está disponível, não recomendamos mais desligar a proteção anti-spoofing quando seu email é roteado por outro serviço antes do EOP.

## <a name="does-anti-spoofing-protection-mean-i-will-be-protected-from-all-phishing"></a>A proteção anti-spoofing significa que eu vou ficar protegido contra todos os phishing?

Infelizmente, não. Os invasores se adaptarão para usar outras técnicas (por exemplo, contas comprometidas ou contas em serviços de email gratuitos). No entanto, a proteção anti-phishing funciona muito melhor para detectar esses outros tipos de métodos de phishing. As camadas de proteção no EOP são projetadas para trabalhar juntas e se baseam umas nas outras.

## <a name="do-other-large-email-services-block-unauthenticated-inbound-email"></a>Outros serviços de email grandes bloqueiam emails de entrada não autenticados?

Quase todos os serviços de email grandes implementam verificações tradicionais de SPF, DKIM e DMARC. Alguns serviços têm outras verificações mais estritas, mas poucos vão tão longe quanto o EOP para bloquear emails não autenticados e tratá-los como mensagens falsas. No entanto, o setor está se tornando mais ciente dos problemas com emails não autenticados, especialmente por causa do problema de phishing.

## <a name="do-i-still-need-to-enable-the-advanced-spam-filter-setting-spf-record-hard-fail-_markasspamspfrecordhardfail_-if-i-enable-anti-spoofing"></a>Ainda preciso habilitar a configuração de Filtro de Spam Avançado "Registro SPF: falha grave" (_MarkAsSpamSpfRecordHardFail_) se eu habilitar a anti-spoofing?

Não. Essa configuração ASF não é mais necessária. A proteção anti-spoofing considera ambas as falhas de disco rígido do SPF e um conjunto muito mais amplo de critérios. Se você habilitar a antifalsificação e ativado o **Registro SPF: ocorreu um erro no hardware** (_MarkAsSpamSpfRecordHardFail_), provavelmente obterá mais falsos positivos.

Recomendamos que você desabilite esse recurso, pois ele não oferece quase nenhum benefício adicional para detectar spam ou mensagem de phishing e, em vez disso, geraria principalmente falsos positivos. Para obter mais informações, consulte [AsF (Advanced Spam Filter) settings in EOP](advanced-spam-filtering-asf-options.md).

## <a name="does-sender-rewriting-scheme-help-fix-forwarded-email"></a>O Esquema de Reescrita de Remetente ajuda a corrigir emails encaminhados?

O SRS corrige apenas parcialmente o problema dos emails encaminhados. Ao reescrever o SMTP **MAIL FROM,** o SRS pode garantir que a mensagem encaminhada passe no SPF no próximo destino. No entanto, como a anti-spoofing baseia-se no endereço **De** em combinação com o domínio **MAIL FROM** ou DKIM-signing (ou outros sinais), não é suficiente impedir que emails encaminhados pelo SRS seja marcado como spoofed.
