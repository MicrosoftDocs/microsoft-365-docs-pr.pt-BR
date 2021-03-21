---
title: Visão do fluxo de emails de saída e de entrada no painel fluxo de emails
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: f2738dec-41b0-43c4-b814-84c0a4e45c6d
description: Os administradores podem aprender sobre o insight de fluxo de emails de saída e de entrada no painel de fluxo de email no Centro de Conformidade & Segurança.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 0fe073a314563e51389b087642f913ef099af53c
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50929331"
---
# <a name="outbound-and-inbound-mail-flow-insight-in-the-security--compliance-center"></a>Visão do fluxo de emails de saída e de entrada no Centro de Conformidade & Segurança

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
- [Proteção do Exchange Online](exchange-online-protection-overview.md)
- [Plano 1 e plano 2 do Microsoft Defender para Office 365](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

O **insight de** fluxo de emails [](mail-flow-insights-v2.md) de saída [](https://protection.office.com) e de entrada no painel de fluxo de email no Centro de Conformidade do & de Segurança combina as informações do relatório [conector](view-mail-flow-reports.md#connector-report) e do relatório de visão geral **TLS** anterior em um só lugar.

O widget exibe a criptografia TLS usada para a conexão quando as mensagens são entregues de e para sua organização. As conexões estabelecidas com outros serviços de email são criptografadas pelo TLS quando o TLS é oferecido por ambos os lados. O widget oferece um instantâneo da última semana de fluxo de emails.

![Widget de fluxo de emails de saída e de entrada no painel fluxo de email no Centro de Conformidade & Segurança](../../media/mfi-outbound-and-inbound-mail-flow-report-widget.png)

As informações no widget estão relacionadas a conectores e proteção de mensagens TLS no Microsoft 365. Para obter mais informações, consulte estes tópicos:

- [Configurar o fluxo de emails usando conectores](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)
- [Como o Exchange Online usa TLS para proteger conexões de e-mail](../../compliance/exchange-online-uses-tls-to-secure-email-connections.md)
- [Detalhes de referência técnica sobre criptografia no Microsoft 365](../../compliance/technical-reference-details-about-encryption.md)

## <a name="message-protected-in-transit-by-tls"></a>Mensagem protegida em trânsito (por TLS)

Quando você clica em **Exibir Detalhes** no widget, o flyout **Message protected in transit (by TLS)** mostra a proteção TLS para mensagens que entram e deixam sua organização.

![Mensagens protegidas em trânsito (por TLS) que aparecem depois de clicar em Exibir detalhes no widget de email de saída e de entrada](../../media/mfi-outbound-and-inbound-mail-flow-report-details.png)

Atualmente, o TLS 1.2 é a versão mais segura do TLS oferecida pelo Microsoft 365. Muitas vezes, você precisará saber a criptografia TLS que está sendo usada para auditorias de conformidade. Você provavelmente não tem uma relação direta com a maioria dos servidores de email de origem e destino (você não os possui e nem a Microsoft), portanto, você não tem muitas opções para melhorar a criptografia TLS usada por esses servidores.

No entanto, você pode usar [conectores](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) para garantir a melhor proteção TLS disponível para mensagens enviadas entre seus servidores de email e o Microsoft 365. O fluxo de emails entre o Microsoft 365 e seus próprios servidores de email ou servidores que pertencem aos seus parceiros geralmente é mais importante e sensível do que as mensagens regulares, portanto, você vai querer aplicar segurança extra e segurança a essas mensagens.

Você pode atualizar ou corrigir seus próprios servidores de email para melhorar a criptografia TLS que está sendo usada ou contatar seus parceiros para fazer o mesmo. O **Relatório do Conector** exibe o volume de fluxo de emails e a criptografia TLS para mensagens que usam seus conectores do Microsoft 365.

Você pode clicar no link **relatório conector** para ir para o [relatório conector](view-mail-flow-reports.md#connector-report). As informações a seguir podem estar disponíveis na página relatório **conector** se a condição associada tiver sido detectada:

- **Conector de parceiro de entrada vendo fluxo de email TLS1.0 significativo**
- **Conector OnPremises de entrada vendo fluxo de emails TLS1.0 significativo**

Para conexões TLS 1.0, você realmente precisa fazer com que o servidor de email ou o servidor do parceiro seja atualizado ou corrigido para evitar problemas quando o suporte ao TLS 1.0 for preterido no Microsoft 365.

## <a name="see-also"></a>Confira também

Para obter informações sobre outras informações no painel de fluxo de emails, consulte Informações de fluxo de email no Centro de Conformidade & [Segurança.](mail-flow-insights-v2.md)