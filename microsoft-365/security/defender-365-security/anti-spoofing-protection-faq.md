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
description: Os administradores podem exibir perguntas e respostas frequentes sobre a proteção anti-spoofing no Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a5843ee7f791fbc2c37914194b153fdd05866d0a
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51053729"
---
# <a name="anti-spoofing-protection-faq"></a>Perguntas frequentes sobre a proteção antifalsificação

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
- [Proteção do Exchange Online](exchange-online-protection-overview.md)
- [Plano 1 e plano 2 do Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Este artigo fornece perguntas e respostas frequentes sobre a proteção anti-spoofing para organizações do Microsoft 365 com caixas de correio no Exchange Online ou organizações autônomas do Exchange Online Protection (EOP) sem caixas de correio do Exchange Online.

Para obter perguntas e respostas sobre a proteção anti-spam, consulte Perguntas frequentes sobre proteção [anti-spam.](anti-spam-protection-faq.md)

Para obter perguntas e respostas sobre a proteção anti-malware, consulte Perguntas frequentes sobre proteção [contra malware](anti-malware-protection-faq-eop.md)

## <a name="why-did-microsoft-choose-to-junk-unauthenticated-inbound-email"></a>Por que a Microsoft escolheu o lixo eletrônico de entrada não autenticado?

A Microsoft acredita que o risco de continuar a permitir emails de entrada não autenticados é maior do que o risco de perder emails de entrada legítimos.

## <a name="does-junking-unauthenticated-inbound-email-cause-legitimate-email-to-be-marked-as-spam"></a>O lixo eletrônico não autenticado faz com que o email legítimo seja marcado como spam?

Quando a Microsoft habilitar esse recurso em 2018, alguns falsos positivos aconteceram (as mensagens boas foram marcadas como ruins). No entanto, com o passar do tempo, os envios foram ajustados aos requisitos. O número de mensagens que foram identificadas como falsas tornou-se insignificante para a maioria dos caminhos de email.

A própria Microsoft adotou pela primeira vez os novos requisitos de autenticação de email várias semanas antes de implantá-lo aos clientes. Embora tenha havido dificuldades no início, elas diminuíram gradualmente.

## <a name="is-spoof-intelligence-available-to-microsoft-365-customers-without-defender-for-office-365"></a>A inteligência de spoof está disponível para clientes do Microsoft 365 sem o Defender para Office 365?

Sim. A partir de outubro de 2018, a inteligência de spoof está disponível para todas as organizações com caixas de correio no Exchange Online e organizações EOP autônomas sem caixas de correio do Exchange Online.

## <a name="how-can-i-report-spam-or-non-spam-messages-back-to-microsoft"></a>Como relatar mensagens de spam ou não spam para a Microsoft?

Confira [Relatar mensagens e arquivos à Microsoft](report-junk-email-messages-to-microsoft.md).

## <a name="im-an-admin-and-i-dont-know-all-of-sources-for-messages-in-my-email-domain"></a>Sou um administrador e não sei todas as fontes para mensagens no meu domínio de email!

Consulte [Você não sabe todas as fontes para seu email](email-validation-and-authentication.md#you-dont-know-all-sources-for-your-email).

## <a name="what-happens-if-i-disable-anti-spoofing-protection-for-my-organization"></a>O que acontece se eu desabilitar a proteção anti-spoofing para minha organização?

Não recomendamos desabilitar a proteção anti-spoofing. Desabilitar a proteção permitirá que mais mensagens de phishing e spam sejam entregues em sua organização. Nem todos os phishing são falsas e nem todas as mensagens falsas serão perdidas. No entanto, seu risco será maior.

Agora que [a Filtragem](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) Aprimorada para Conectores está disponível, não é mais recomendável desligar a proteção anti-spoofing quando seu email é roteado por outro serviço antes do EOP.

## <a name="does-anti-spoofing-protection-mean-i-will-be-protected-from-all-phishing"></a>A proteção anti-spoofing significa que eu vou ser protegido contra todos os phishing?

Infelizmente, não. Os invasores se adaptarão para usar outras técnicas (por exemplo, contas comprometidas ou contas em serviços de email gratuitos). No entanto, a proteção anti-phishing funciona muito melhor para detectar esses outros tipos de métodos de phishing. As camadas de proteção no EOP são projetadas para trabalharem juntas e se desenvolverem umas sobre as outras.

## <a name="do-other-large-email-services-block-unauthenticated-inbound-email"></a>Outros serviços de email grandes bloqueiam emails de entrada não autenticados?

Quase todos os grandes serviços de email implementam verificações tradicionais de SPF, DKIM e DMARC. Alguns serviços têm outras verificações mais estritas, mas poucos vão até o EOP para bloquear emails não autenticados e tratá-los como mensagens falsas. No entanto, o setor está se tornando mais ciente dos problemas com emails não autenticados, especialmente por causa do problema do phishing.

## <a name="do-i-still-need-to-enable-the-advanced-spam-filter-setting-spf-record-hard-fail-_markasspamspfrecordhardfail_-if-i-enable-anti-spoofing"></a>Ainda preciso habilitar a configuração de Filtro de Spam Avançado "Registro SPF: falha grave" (_MarkAsSpamSpfRecordHardFail_) se eu habilitar anti-spoofing?

Não. Essa configuração ASF não é mais necessária. A proteção anti-spoofing considera a falha dura do SPF e um conjunto muito mais amplo de critérios. Se você habilitar a antifalsificação e ativado o **Registro SPF: ocorreu um erro no hardware** (_MarkAsSpamSpfRecordHardFail_), provavelmente obterá mais falsos positivos.

Recomendamos que você desabilite esse recurso, pois ele não oferece quase nenhum benefício adicional para detectar mensagens de spam ou phishing e, em vez disso, geraria principalmente falsos positivos. Para obter mais informações, consulte [AsF (Advanced Spam Filter) settings in EOP](advanced-spam-filtering-asf-options.md).

## <a name="does-sender-rewriting-scheme-help-fix-forwarded-email"></a>O Esquema de Reescrita do Remetente ajuda a corrigir emails encaminhados?

O SRS corrige apenas parcialmente o problema dos emails encaminhados. Ao reescrever o SMTP **MAIL FROM**, o SRS pode garantir que a mensagem encaminhada passe SPF no próximo destino. No entanto, como a anti-spoofing é baseada no endereço **From** em combinação com o domínio de assinatura **MAIL FROM** ou DKIM (ou outros sinais), não é suficiente impedir que o email encaminhado pelo SRS seja marcado como spoofed.