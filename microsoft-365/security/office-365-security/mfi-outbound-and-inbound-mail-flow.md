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
ms.openlocfilehash: 4a3117223e466a4a7aad7edf25ecdbcf0a3de719
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/25/2021
ms.locfileid: "51202977"
---
# <a name="outbound-and-inbound-mail-flow-insight-in-the-security--compliance-center"></a><span data-ttu-id="1230a-103">Visão do fluxo de emails de saída e de entrada no Centro de Conformidade & Segurança</span><span class="sxs-lookup"><span data-stu-id="1230a-103">Outbound and inbound mail flow insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="1230a-104">**Aplica-se a**</span><span class="sxs-lookup"><span data-stu-id="1230a-104">**Applies to**</span></span>
- [<span data-ttu-id="1230a-105">Proteção do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="1230a-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="1230a-106">Plano 1 e plano 2 do Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="1230a-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="1230a-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1230a-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="1230a-108">O **insight de** fluxo de emails [](mail-flow-insights-v2.md) de saída [](https://protection.office.com) e de entrada no painel de fluxo de email no Centro de Conformidade do & de Segurança combina as informações do relatório [conector](view-mail-flow-reports.md#connector-report) e do relatório de visão geral **TLS** anterior em um só lugar.</span><span class="sxs-lookup"><span data-stu-id="1230a-108">The **Outbound and inbound mail flow** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) combines the information from the [Connector report](view-mail-flow-reports.md#connector-report) and the former **TLS overview report** in one place.</span></span>

<span data-ttu-id="1230a-109">O widget exibe a criptografia TLS usada para a conexão quando as mensagens são entregues de e para sua organização.</span><span class="sxs-lookup"><span data-stu-id="1230a-109">The widget displays the TLS encryption that's used for the connection when messages are delivered to and from your organization.</span></span> <span data-ttu-id="1230a-110">As conexões estabelecidas com outros serviços de email são criptografadas pelo TLS quando o TLS é oferecido por ambos os lados.</span><span class="sxs-lookup"><span data-stu-id="1230a-110">The connections that are established with other email services are encrypted by TLS when TLS is offered by both sides.</span></span> <span data-ttu-id="1230a-111">O widget oferece um instantâneo da última semana de fluxo de emails.</span><span class="sxs-lookup"><span data-stu-id="1230a-111">The widget offers a snapshot of the last week of mail flow.</span></span>

![Widget de fluxo de emails de saída e de entrada no painel fluxo de email no Centro de Conformidade & Segurança](../../media/mfi-outbound-and-inbound-mail-flow-report-widget.png)

<span data-ttu-id="1230a-113">As informações no widget estão relacionadas a conectores e proteção de mensagens TLS em Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1230a-113">The information in the widget is related to connectors and TLS message protection in Microsoft 365.</span></span> <span data-ttu-id="1230a-114">Para obter mais informações, consulte estes tópicos:</span><span class="sxs-lookup"><span data-stu-id="1230a-114">For more information, see these topics:</span></span>

- [<span data-ttu-id="1230a-115">Configurar o fluxo de e-mails usando conectores</span><span class="sxs-lookup"><span data-stu-id="1230a-115">Configure mail flow using connectors</span></span>](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)
- [<span data-ttu-id="1230a-116">Como o Exchange Online usa TLS para proteger conexões de e-mail</span><span class="sxs-lookup"><span data-stu-id="1230a-116">How Exchange Online uses TLS to secure email connections</span></span>](../../compliance/exchange-online-uses-tls-to-secure-email-connections.md)
- [<span data-ttu-id="1230a-117">Detalhes de referência técnica sobre criptografia em Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="1230a-117">Technical reference details about encryption in Microsoft 365</span></span>](../../compliance/technical-reference-details-about-encryption.md)

## <a name="message-protected-in-transit-by-tls"></a><span data-ttu-id="1230a-118">Mensagem protegida em trânsito (por TLS)</span><span class="sxs-lookup"><span data-stu-id="1230a-118">Message protected in transit (by TLS)</span></span>

<span data-ttu-id="1230a-119">Quando você clica em **Exibir Detalhes** no widget, o flyout **Message protected in transit (by TLS)** mostra a proteção TLS para mensagens que entram e deixam sua organização.</span><span class="sxs-lookup"><span data-stu-id="1230a-119">When you click **View Details** on the widget, the **Message protected in transit (by TLS)** flyout shows you the TLS protection for messages entering and leaving your organization.</span></span>

![Mensagens protegidas em trânsito (por TLS) que aparecem depois de clicar em Exibir detalhes no widget de email de saída e de entrada](../../media/mfi-outbound-and-inbound-mail-flow-report-details.png)

<span data-ttu-id="1230a-121">Atualmente, o TLS 1.2 é a versão mais segura do TLS oferecida pelo Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1230a-121">Currently, TLS 1.2 is the most secure version of TLS that's offered by Microsoft 365.</span></span> <span data-ttu-id="1230a-122">Muitas vezes, você precisará saber a criptografia TLS que está sendo usada para auditorias de conformidade.</span><span class="sxs-lookup"><span data-stu-id="1230a-122">Often, you'll need to know the TLS encryption that's being used for compliance audits.</span></span> <span data-ttu-id="1230a-123">Você provavelmente não tem uma relação direta com a maioria dos servidores de email de origem e destino (você não os possui e nem a Microsoft), portanto, você não tem muitas opções para melhorar a criptografia TLS usada por esses servidores.</span><span class="sxs-lookup"><span data-stu-id="1230a-123">You probably don't have a direct relationship with most of the source and destination email servers (you don't own them, and neither does Microsoft), so you don't have many options to improve the TLS encryption that's used by those servers.</span></span>

<span data-ttu-id="1230a-124">Porém, você pode usar [conectores](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) para garantir a melhor proteção TLS disponível para mensagens enviadas entre seus servidores de email e Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1230a-124">But, you can use [connectors](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) to ensure the best available TLS protection for messages that are sent between your email servers and Microsoft 365.</span></span> <span data-ttu-id="1230a-125">O fluxo de emails entre Microsoft 365 e seus próprios servidores de email ou servidores que pertencem aos seus parceiros geralmente é mais importante e sensível do que as mensagens regulares, portanto, você vai querer aplicar segurança extra e segurança a essas mensagens.</span><span class="sxs-lookup"><span data-stu-id="1230a-125">Mail flow between Microsoft 365 and your own email servers or servers that belong to your partners is often more important and sensitive than regular messages, so you'll want to apply extra security and vigilance to those messages.</span></span>

<span data-ttu-id="1230a-126">Você pode atualizar ou corrigir seus próprios servidores de email para melhorar a criptografia TLS que está sendo usada ou contatar seus parceiros para fazer o mesmo.</span><span class="sxs-lookup"><span data-stu-id="1230a-126">You can upgrade or fix your own email servers to improve the TLS encryption that's being used, or reach out to your partners to do the same.</span></span> <span data-ttu-id="1230a-127">O **Relatório do Conector** exibe o volume de fluxo de emails e a criptografia TLS para mensagens que usam seus conectores Microsoft 365 de email.</span><span class="sxs-lookup"><span data-stu-id="1230a-127">The **Connector Report** displays both mail flow volume and TLS encryption for messages that use your Microsoft 365 connectors.</span></span>

<span data-ttu-id="1230a-128">Você pode clicar no link **relatório conector** para ir para o [relatório conector](view-mail-flow-reports.md#connector-report).</span><span class="sxs-lookup"><span data-stu-id="1230a-128">You can click the **Connector report** link to go to the [Connector report](view-mail-flow-reports.md#connector-report).</span></span> <span data-ttu-id="1230a-129">As informações a seguir podem estar disponíveis na página relatório **conector** se a condição associada tiver sido detectada:</span><span class="sxs-lookup"><span data-stu-id="1230a-129">The following insights might be available on the **Connector report** page if the associated condition has been detected:</span></span>

- <span data-ttu-id="1230a-130">**Conector de parceiro de entrada vendo fluxo de email TLS1.0 significativo**</span><span class="sxs-lookup"><span data-stu-id="1230a-130">**Inbound Partner connector seeing significant TLS1.0 mail flow**</span></span>
- <span data-ttu-id="1230a-131">**Conector OnPremises de entrada vendo fluxo de emails TLS1.0 significativo**</span><span class="sxs-lookup"><span data-stu-id="1230a-131">**Inbound OnPremises connector seeing significant TLS1.0 mail flow**</span></span>

<span data-ttu-id="1230a-132">Para conexões TLS 1.0, você realmente precisa fazer com que o servidor de email ou o servidor do parceiro seja atualizado ou corrigido para evitar problemas quando o suporte ao TLS 1.0 for preterido no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1230a-132">For TLS 1.0 connections, you really need to get your email server or your partner's server upgraded or fixed to avoid any issues when TLS 1.0 support is eventually deprecated in Microsoft 365.</span></span>

## <a name="see-also"></a><span data-ttu-id="1230a-133">Confira também</span><span class="sxs-lookup"><span data-stu-id="1230a-133">See also</span></span>

<span data-ttu-id="1230a-134">Para obter informações sobre outras informações no painel de fluxo de emails, consulte Informações de fluxo de email no Centro de Conformidade & [Segurança.](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="1230a-134">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>