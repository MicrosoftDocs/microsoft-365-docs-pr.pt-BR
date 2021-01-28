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
ms.openlocfilehash: e46a0ebf0c14e31462d1e86d8a8d8c08486337af
ms.sourcegitcommit: 537e513a4a232a01e44ecbc76d86a8bcaf142482
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/27/2021
ms.locfileid: "50029817"
---
# <a name="outbound-and-inbound-mail-flow-insight-in-the-security--compliance-center"></a><span data-ttu-id="fa870-103">Visão do fluxo de emails de saída e de entrada no Centro de Conformidade e & Segurança</span><span class="sxs-lookup"><span data-stu-id="fa870-103">Outbound and inbound mail flow insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="fa870-104">O insight & **de** fluxo de [](mail-flow-insights-v2.md) emails de saída e de entrada no painel fluxo [](view-mail-flow-reports.md#connector-report) de emails [no](https://protection.office.com) Centro de Conformidade e Segurança combina as informações do relatório conector e do relatório de visão geral **do TLS** anterior em um só lugar.</span><span class="sxs-lookup"><span data-stu-id="fa870-104">The **Outbound and inbound mail flow** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) combines the information from the [Connector report](view-mail-flow-reports.md#connector-report) and the former **TLS overview report** in one place.</span></span>

<span data-ttu-id="fa870-105">O widget exibe a criptografia TLS usada para a conexão quando as mensagens são entregues de e para sua organização.</span><span class="sxs-lookup"><span data-stu-id="fa870-105">The widget displays the TLS encryption that's used for the connection when messages are delivered to and from your organization.</span></span> <span data-ttu-id="fa870-106">As conexões estabelecidas com outros serviços de email são criptografadas pelo TLS quando o TLS é oferecido por ambos os lados.</span><span class="sxs-lookup"><span data-stu-id="fa870-106">The connections that are established with other email services are encrypted by TLS when TLS is offered by both sides.</span></span> <span data-ttu-id="fa870-107">O widget oferece um instantâneo da última semana de fluxo de emails.</span><span class="sxs-lookup"><span data-stu-id="fa870-107">The widget offers a snapshot of the last week of mail flow.</span></span>

![Widget de fluxo de emails de saída e de entrada no painel de fluxo de emails no Centro de Conformidade e & Segurança](../../media/mfi-outbound-and-inbound-mail-flow-report-widget.png)

<span data-ttu-id="fa870-109">As informações no widget estão relacionadas aos conectores e à proteção de mensagens TLS no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="fa870-109">The information in the widget is related to connectors and TLS message protection in Microsoft 365.</span></span> <span data-ttu-id="fa870-110">Para obter mais informações, consulte estes tópicos:</span><span class="sxs-lookup"><span data-stu-id="fa870-110">For more information, see these topics:</span></span>

- [<span data-ttu-id="fa870-111">Configurar o fluxo de emails usando conectores</span><span class="sxs-lookup"><span data-stu-id="fa870-111">Configure mail flow using connectors</span></span>](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)
- [<span data-ttu-id="fa870-112">Como o Exchange Online usa TLS para proteger conexões de e-mail</span><span class="sxs-lookup"><span data-stu-id="fa870-112">How Exchange Online uses TLS to secure email connections</span></span>](https://docs.microsoft.com/microsoft-365/compliance/exchange-online-uses-tls-to-secure-email-connections)
- [<span data-ttu-id="fa870-113">Detalhes de referência técnica sobre criptografia no Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="fa870-113">Technical reference details about encryption in Microsoft 365</span></span>](https://docs.microsoft.com/microsoft-365/compliance/technical-reference-details-about-encryption)

## <a name="message-protected-in-transit-by-tls"></a><span data-ttu-id="fa870-114">Mensagem protegida em trânsito (por TLS)</span><span class="sxs-lookup"><span data-stu-id="fa870-114">Message protected in transit (by TLS)</span></span>

<span data-ttu-id="fa870-115">Quando você **clica** em Exibir Detalhes no widget, o flyout Mensagem protegida em trânsito **(por TLS)** mostra a proteção TLS para mensagens que entram e deixam sua organização.</span><span class="sxs-lookup"><span data-stu-id="fa870-115">When you click **View Details** on the widget, the **Message protected in transit (by TLS)** flyout shows you the TLS protection for messages entering and leaving your organization.</span></span>

![Mensagens protegidas em trânsito (por TLS) que aparecem depois que você clica em Exibir detalhes no widget email de saída e de entrada](../../media/mfi-outbound-and-inbound-mail-flow-report-details.png)

<span data-ttu-id="fa870-117">Atualmente, o TLS 1.2 é a versão mais segura do TLS oferecida pelo Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="fa870-117">Currently, TLS 1.2 is the most secure version of TLS that's offered by Microsoft 365.</span></span> <span data-ttu-id="fa870-118">Muitas vezes, você precisará saber a criptografia TLS que está sendo usada para auditorias de conformidade.</span><span class="sxs-lookup"><span data-stu-id="fa870-118">Often, you'll need to know the TLS encryption that's being used for compliance audits.</span></span> <span data-ttu-id="fa870-119">Você provavelmente não tem uma relação direta com a maioria dos servidores de email de origem e destino (você não os possui, nem a Microsoft), portanto, você não tem muitas opções para melhorar a criptografia TLS usada por esses servidores.</span><span class="sxs-lookup"><span data-stu-id="fa870-119">You probably don't have a direct relationship with most of the source and destination email servers (you don't own them, and neither does Microsoft), so you don't have many options to improve the TLS encryption that's used by those servers.</span></span>

<span data-ttu-id="fa870-120">Porém, você pode usar [conectores](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) para garantir a melhor proteção TLS disponível para mensagens enviadas entre seus servidores de email e o Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="fa870-120">But, you can use [connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) to ensure the best available TLS protection for messages that are sent between your email servers and Microsoft 365.</span></span> <span data-ttu-id="fa870-121">O fluxo de emails entre o Microsoft 365 e seus próprios servidores de email ou servidores que pertencem a seus parceiros geralmente é mais importante e sensível do que as mensagens normais, portanto, você vai querer aplicar mais segurança e proteção a essas mensagens.</span><span class="sxs-lookup"><span data-stu-id="fa870-121">Mail flow between Microsoft 365 and your own email servers or servers that belong to your partners is often more important and sensitive than regular messages, so you'll want to apply extra security and vigilance to those messages.</span></span>

<span data-ttu-id="fa870-122">Você pode atualizar ou corrigir seus próprios servidores de email para melhorar a criptografia TLS que está sendo usada ou contatar seus parceiros para fazer o mesmo.</span><span class="sxs-lookup"><span data-stu-id="fa870-122">You can upgrade or fix your own email servers to improve the TLS encryption that's being used, or reach out to your partners to do the same.</span></span> <span data-ttu-id="fa870-123">O **Relatório do Conector** exibe o volume de fluxo de emails e a criptografia TLS para mensagens que usam os conectores do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="fa870-123">The **Connector Report** displays both mail flow volume and TLS encryption for messages that use your Microsoft 365 connectors.</span></span>

<span data-ttu-id="fa870-124">Você pode clicar no link **do relatório do** Conector para ir para o relatório do [Conector.](view-mail-flow-reports.md#connector-report)</span><span class="sxs-lookup"><span data-stu-id="fa870-124">You can click the **Connector report** link to go to the [Connector report](view-mail-flow-reports.md#connector-report).</span></span> <span data-ttu-id="fa870-125">As informações a seguir podem estar disponíveis na página de relatório **do** Conector se a condição associada tiver sido detectada:</span><span class="sxs-lookup"><span data-stu-id="fa870-125">The following insights might be available on the **Connector report** page if the associated condition has been detected:</span></span>

- <span data-ttu-id="fa870-126">**Conector de parceiro de entrada vendo fluxo de emails TLS1.0 significativo**</span><span class="sxs-lookup"><span data-stu-id="fa870-126">**Inbound Partner connector seeing significant TLS1.0 mail flow**</span></span>
- <span data-ttu-id="fa870-127">**Conector OnPremises de entrada vendo fluxo de emails TLS1.0 significativo**</span><span class="sxs-lookup"><span data-stu-id="fa870-127">**Inbound OnPremises connector seeing significant TLS1.0 mail flow**</span></span>

<span data-ttu-id="fa870-128">Para conexões TLS 1.0, você realmente precisa atualizar o servidor de email ou o servidor do parceiro ou corrigi-lo para evitar problemas quando o suporte a TLS 1.0 for eventualmente preterido no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="fa870-128">For TLS 1.0 connections, you really need to get your email server or your partner's server upgraded or fixed to avoid any issues when TLS 1.0 support is eventually deprecated in Microsoft 365.</span></span>

## <a name="see-also"></a><span data-ttu-id="fa870-129">Confira também</span><span class="sxs-lookup"><span data-stu-id="fa870-129">See also</span></span>

<span data-ttu-id="fa870-130">Para obter informações sobre outros insights no painel de fluxo de emails, consulte Informações sobre o fluxo de emails no Centro de [Conformidade e & Segurança.](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="fa870-130">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
