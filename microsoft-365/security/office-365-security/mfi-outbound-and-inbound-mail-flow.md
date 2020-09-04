---
title: Percepção de fluxo de email de entrada e saída no painel de fluxo de emails
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: f2738dec-41b0-43c4-b814-84c0a4e45c6d
description: Os administradores podem saber mais sobre as informações de saída e de fluxo de email de entrada no painel de fluxo de emails no centro de conformidade de & de segurança.
ms.openlocfilehash: 87ea7faed2e2387c31fdb06abaf242a2a3aea76e
ms.sourcegitcommit: 9ce9001aa41172152458da27c1c52825355f426d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/03/2020
ms.locfileid: "47357417"
---
# <a name="outbound-and-inbound-mail-flow-insight-in-the-security--compliance-center"></a>Percepção de fluxo de email de entrada e de saída no centro de conformidade e segurança &

A percepção de **fluxo de email de entrada e de saída** no painel de fluxo de [emails](mail-flow-insights-v2.md) no [centro de conformidade e segurança &](https://protection.office.com) combina as informações do [relatório de conector](view-mail-flow-reports.md#connector-report) e o **relatório de visão geral de TLS** anterior em um só lugar.

O widget exibe a criptografia TLS que é usada para a conexão quando as mensagens são entregues na sua organização. As conexões estabelecidas com outros serviços de email são criptografadas por TLS quando o TLS é oferecido por ambos os lados. O widget oferece um instantâneo da última semana de fluxo de emails.

![Widget de fluxo de email de entrada e de saída no painel de fluxo de emails no centro de conformidade & segurança](../../media/mfi-outbound-and-inbound-mail-flow-report-widget.png)

As informações no widget estão relacionadas a conectores e proteção de mensagem TLS no Microsoft 365. Para obter mais informações, consulte estes tópicos:

- [Configurar o fluxo de email usando conectores](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)
- [Como o Exchange Online usa o TLS para proteger conexões de email](https://docs.microsoft.com/microsoft-365/compliance/exchange-online-uses-tls-to-secure-email-connections)
- [Detalhes técnicos de referência sobre criptografia no Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/technical-reference-details-about-encryption)

## <a name="message-protected-in-transit-by-tls"></a>Mensagem protegida em trânsito (por TLS)

Quando você clica em **Exibir detalhes** no widget, o submenu **mensagem protegido em trânsito (por TLS)** mostra a proteção TLS para mensagens que entram e saem da sua organização.

![Submenu mensagens protegidas em trânsito (por TLS) que aparece depois que você clica em Exibir detalhes no widget email de saída e de entrada](../../media/mfi-outbound-and-inbound-mail-flow-report-details.png)

Atualmente, o TLS 1,2 é a versão mais segura do TLS oferecida pela Microsoft 365. Muitas vezes, você precisará saber a criptografia TLS que está sendo usada para auditorias de conformidade. Provavelmente você não tem uma relação direta com a maioria dos servidores de email de origem e de destino (você não é proprietário deles, e nenhuma da Microsoft), portanto, você não tem muitas opções para melhorar a criptografia TLS usada por esses servidores.

No entanto, você pode usar [conectores](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) para garantir a melhor proteção TLS disponível para mensagens enviadas entre seus servidores de email e o Microsoft 365. O fluxo de email entre o Microsoft 365 e seus próprios servidores de email ou servidores que pertencem a seus parceiros é freqüentemente mais importante e confidencial do que as mensagens normais, portanto, você deve aplicar segurança e vigilância extra a essas mensagens.

Você pode atualizar ou corrigir seus próprios servidores de email para melhorar a criptografia TLS que está sendo usada ou acessar seus parceiros para fazer o mesmo. O **relatório do conector** exibe o volume de fluxo de emails e a criptografia TLS para mensagens que usam seus conectores do Microsoft 365.

Você pode clicar no link de **relatório do conector** para ir para o [relatório do conector](view-mail-flow-reports.md#connector-report). Os seguintes insights podem estar disponíveis na página de **relatório do conector** se a condição associada tiver sido detectada:

- **Conector de parceiro de entrada que enxerga o fluxo de emails TLS 1.0 significativo**
- **Conector local de entrada que enxerga o fluxo de emails do TLS 1.0 significativo**

Para conexões TLS 1,0, você realmente precisa obter o servidor de email ou o servidor de seu parceiro atualizado ou corrigido para evitar qualquer problema quando o suporte a TLS 1,0 for eventualmente preterido no Microsoft 365.

## <a name="see-also"></a>Confira também

Para obter informações sobre outras ideias no painel de fluxo de emails, consulte [Mail Flow insights no centro de conformidade de & de segurança](mail-flow-insights-v2.md).
