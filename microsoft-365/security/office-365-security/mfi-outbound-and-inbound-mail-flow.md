---
title: Visão geral do fluxo de emails de saída e de entrada no painel Fluxo de emails
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
description: Os administradores podem saber mais sobre o insight de fluxo de emails de saída e de entrada no painel de fluxo de emails no Centro de Conformidade & e Segurança.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: fcce6981369217f21ace5fdf2abbf23ca8606569
ms.sourcegitcommit: e920e68c8d0eac8b152039b52cfc139d478a67b3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/09/2021
ms.locfileid: "50150803"
---
# <a name="outbound-and-inbound-mail-flow-insight-in-the-security--compliance-center"></a>Visão do fluxo de emails de saída e de entrada no Centro de Conformidade e & Segurança

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
- [Proteção do Exchange Online](https://go.microsoft.com/fwlink/?linkid=2148611)
- [Microsoft Defender para Office 365 plano 1 e plano 2](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

O insight & **de** fluxo de [](mail-flow-insights-v2.md) emails de saída e de entrada no painel Fluxo [](view-mail-flow-reports.md#connector-report) de emails [no](https://protection.office.com) Centro de Conformidade e Segurança combina as informações do relatório do Conector e do relatório de visão geral do **TLS** anterior em um só lugar.

O widget exibe a criptografia TLS usada para a conexão quando as mensagens são entregues de e para sua organização. As conexões estabelecidas com outros serviços de email são criptografadas pelo TLS quando o TLS é oferecido por ambos os lados. O widget oferece um instantâneo da última semana de fluxo de emails.

![Widget de fluxo de emails de saída e de entrada no painel fluxo de emails no Centro de Conformidade e & Segurança](../../media/mfi-outbound-and-inbound-mail-flow-report-widget.png)

As informações no widget estão relacionadas aos conectores e à proteção de mensagens TLS no Microsoft 365. Para obter mais informações, consulte estes tópicos:

- [Configurar o fluxo de emails usando conectores](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)
- [Como o Exchange Online usa TLS para proteger conexões de e-mail](https://docs.microsoft.com/microsoft-365/compliance/exchange-online-uses-tls-to-secure-email-connections)
- [Detalhes de referência técnica sobre criptografia no Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/technical-reference-details-about-encryption)

## <a name="message-protected-in-transit-by-tls"></a>Mensagem protegida em trânsito (por TLS)

Quando você **clica** em Exibir Detalhes no widget, o flyout Mensagem protegida em trânsito **(por TLS)** mostra a proteção TLS para mensagens que entram e deixam sua organização.

![Mensagens protegidas em trânsito (por TLS) que aparecem depois que você clica em Exibir detalhes no widget email de saída e de entrada](../../media/mfi-outbound-and-inbound-mail-flow-report-details.png)

Atualmente, o TLS 1.2 é a versão mais segura do TLS oferecida pelo Microsoft 365. Muitas vezes, você precisará saber a criptografia TLS que está sendo usada para auditorias de conformidade. Você provavelmente não tem uma relação direta com a maioria dos servidores de email de origem e destino (você não os possui, nem a Microsoft), portanto, você não tem muitas opções para melhorar a criptografia TLS usada por esses servidores.

Porém, você pode usar [conectores](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) para garantir a melhor proteção TLS disponível para mensagens enviadas entre seus servidores de email e o Microsoft 365. O fluxo de emails entre o Microsoft 365 e seus próprios servidores de email ou servidores que pertencem a seus parceiros geralmente é mais importante e sensível do que as mensagens normais, portanto, você vai querer aplicar mais segurança e proteção a essas mensagens.

Você pode atualizar ou corrigir seus próprios servidores de email para melhorar a criptografia TLS que está sendo usada ou contatar seus parceiros para fazer o mesmo. O **Relatório do Conector** exibe o volume de fluxo de emails e a criptografia TLS para mensagens que usam os conectores do Microsoft 365.

Você pode clicar no link **do relatório do** Conector para ir para o relatório do [Conector.](view-mail-flow-reports.md#connector-report) As informações a seguir podem estar disponíveis na página de relatório **do** Conector se a condição associada tiver sido detectada:

- **Conector de parceiro de entrada vendo fluxo de emails TLS1.0 significativo**
- **Conector OnPremises de entrada vendo fluxo de emails TLS1.0 significativo**

Para conexões TLS 1.0, você realmente precisa atualizar o servidor de email ou o servidor do parceiro ou corrigi-lo para evitar problemas quando o suporte a TLS 1.0 for eventualmente preterido no Microsoft 365.

## <a name="see-also"></a>Confira também

Para obter informações sobre outros insights no painel de fluxo de emails, consulte Informações sobre o fluxo de emails no Centro de [Conformidade e & Segurança.](mail-flow-insights-v2.md)
