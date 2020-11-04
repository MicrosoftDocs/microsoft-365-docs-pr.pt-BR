---
title: Percepção de fluxo de email de entrada e saída no painel de fluxo de emails
f1.keywords:
- NOCSH
ms.author: siosulli
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: f2738dec-41b0-43c4-b814-84c0a4e45c6d
description: Os administradores podem saber mais sobre as informações de saída e de fluxo de email de entrada no painel de fluxo de emails no centro de conformidade de & de segurança.
ms.openlocfilehash: cff7c3a14b62475903729f4528652f192c2da09f
ms.sourcegitcommit: b64f36d3873fa0041b24bec029deb73ccfdfdbac
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/03/2020
ms.locfileid: "48877664"
---
# <a name="outbound-and-inbound-mail-flow-insight-in-the-security--compliance-center"></a><span data-ttu-id="783ec-103">Percepção de fluxo de email de entrada e de saída no centro de conformidade e segurança &</span><span class="sxs-lookup"><span data-stu-id="783ec-103">Outbound and inbound mail flow insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="783ec-104">A percepção de **fluxo de email de entrada e de saída** no painel de fluxo de [emails](mail-flow-insights-v2.md) no [centro de conformidade e segurança &](https://protection.office.com) combina as informações do [relatório de conector](view-mail-flow-reports.md#connector-report) e o **relatório de visão geral de TLS** anterior em um só lugar.</span><span class="sxs-lookup"><span data-stu-id="783ec-104">The **Outbound and inbound mail flow** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) combines the information from the [Connector report](view-mail-flow-reports.md#connector-report) and the former **TLS overview report** in one place.</span></span>

<span data-ttu-id="783ec-105">O widget exibe a criptografia TLS que é usada para a conexão quando as mensagens são entregues na sua organização.</span><span class="sxs-lookup"><span data-stu-id="783ec-105">The widget displays the TLS encryption that's used for the connection when messages are delivered to and from your organization.</span></span> <span data-ttu-id="783ec-106">As conexões estabelecidas com outros serviços de email são criptografadas por TLS quando o TLS é oferecido por ambos os lados.</span><span class="sxs-lookup"><span data-stu-id="783ec-106">The connections that are established with other email services are encrypted by TLS when TLS is offered by both sides.</span></span> <span data-ttu-id="783ec-107">O widget oferece um instantâneo da última semana de fluxo de emails.</span><span class="sxs-lookup"><span data-stu-id="783ec-107">The widget offers a snapshot of the last week of mail flow.</span></span>

![Widget de fluxo de email de entrada e de saída no painel de fluxo de emails no centro de conformidade & segurança](../../media/mfi-outbound-and-inbound-mail-flow-report-widget.png)

<span data-ttu-id="783ec-109">As informações no widget estão relacionadas a conectores e proteção de mensagem TLS no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="783ec-109">The information in the widget is related to connectors and TLS message protection in Microsoft 365.</span></span> <span data-ttu-id="783ec-110">Para obter mais informações, consulte estes tópicos:</span><span class="sxs-lookup"><span data-stu-id="783ec-110">For more information, see these topics:</span></span>

- [<span data-ttu-id="783ec-111">Configurar o fluxo de email usando conectores</span><span class="sxs-lookup"><span data-stu-id="783ec-111">Configure mail flow using connectors</span></span>](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)
- [<span data-ttu-id="783ec-112">Como o Exchange Online usa o TLS para proteger conexões de email</span><span class="sxs-lookup"><span data-stu-id="783ec-112">How Exchange Online uses TLS to secure email connections</span></span>](https://docs.microsoft.com/microsoft-365/compliance/exchange-online-uses-tls-to-secure-email-connections)
- [<span data-ttu-id="783ec-113">Detalhes técnicos de referência sobre criptografia no Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="783ec-113">Technical reference details about encryption in Microsoft 365</span></span>](https://docs.microsoft.com/microsoft-365/compliance/technical-reference-details-about-encryption)

## <a name="message-protected-in-transit-by-tls"></a><span data-ttu-id="783ec-114">Mensagem protegida em trânsito (por TLS)</span><span class="sxs-lookup"><span data-stu-id="783ec-114">Message protected in transit (by TLS)</span></span>

<span data-ttu-id="783ec-115">Quando você clica em **Exibir detalhes** no widget, o submenu **mensagem protegido em trânsito (por TLS)** mostra a proteção TLS para mensagens que entram e saem da sua organização.</span><span class="sxs-lookup"><span data-stu-id="783ec-115">When you click **View Details** on the widget, the **Message protected in transit (by TLS)** flyout shows you the TLS protection for messages entering and leaving your organization.</span></span>

![Submenu mensagens protegidas em trânsito (por TLS) que aparece depois que você clica em Exibir detalhes no widget email de saída e de entrada](../../media/mfi-outbound-and-inbound-mail-flow-report-details.png)

<span data-ttu-id="783ec-117">Atualmente, o TLS 1,2 é a versão mais segura do TLS oferecida pela Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="783ec-117">Currently, TLS 1.2 is the most secure version of TLS that's offered by Microsoft 365.</span></span> <span data-ttu-id="783ec-118">Muitas vezes, você precisará saber a criptografia TLS que está sendo usada para auditorias de conformidade.</span><span class="sxs-lookup"><span data-stu-id="783ec-118">Often, you'll need to know the TLS encryption that's being used for compliance audits.</span></span> <span data-ttu-id="783ec-119">Provavelmente você não tem uma relação direta com a maioria dos servidores de email de origem e de destino (você não é proprietário deles, e nenhuma da Microsoft), portanto, você não tem muitas opções para melhorar a criptografia TLS usada por esses servidores.</span><span class="sxs-lookup"><span data-stu-id="783ec-119">You probably don't have a direct relationship with most of the source and destination email servers (you don't own them, and neither does Microsoft), so you don't have many options to improve the TLS encryption that's used by those servers.</span></span>

<span data-ttu-id="783ec-120">No entanto, você pode usar [conectores](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) para garantir a melhor proteção TLS disponível para mensagens enviadas entre seus servidores de email e o Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="783ec-120">But, you can use [connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) to ensure the best available TLS protection for messages that are sent between your email servers and Microsoft 365.</span></span> <span data-ttu-id="783ec-121">O fluxo de email entre o Microsoft 365 e seus próprios servidores de email ou servidores que pertencem a seus parceiros é freqüentemente mais importante e confidencial do que as mensagens normais, portanto, você deve aplicar segurança e vigilância extra a essas mensagens.</span><span class="sxs-lookup"><span data-stu-id="783ec-121">Mail flow between Microsoft 365 and your own email servers or servers that belong to your partners is often more important and sensitive than regular messages, so you'll want to apply extra security and vigilance to those messages.</span></span>

<span data-ttu-id="783ec-122">Você pode atualizar ou corrigir seus próprios servidores de email para melhorar a criptografia TLS que está sendo usada ou acessar seus parceiros para fazer o mesmo.</span><span class="sxs-lookup"><span data-stu-id="783ec-122">You can upgrade or fix your own email servers to improve the TLS encryption that's being used, or reach out to your partners to do the same.</span></span> <span data-ttu-id="783ec-123">O **relatório do conector** exibe o volume de fluxo de emails e a criptografia TLS para mensagens que usam seus conectores do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="783ec-123">The **Connector Report** displays both mail flow volume and TLS encryption for messages that use your Microsoft 365 connectors.</span></span>

<span data-ttu-id="783ec-124">Você pode clicar no link de **relatório do conector** para ir para o [relatório do conector](view-mail-flow-reports.md#connector-report).</span><span class="sxs-lookup"><span data-stu-id="783ec-124">You can click the **Connector report** link to go to the [Connector report](view-mail-flow-reports.md#connector-report).</span></span> <span data-ttu-id="783ec-125">Os seguintes insights podem estar disponíveis na página de **relatório do conector** se a condição associada tiver sido detectada:</span><span class="sxs-lookup"><span data-stu-id="783ec-125">The following insights might be available on the **Connector report** page if the associated condition has been detected:</span></span>

- <span data-ttu-id="783ec-126">**Conector de parceiro de entrada que enxerga o fluxo de emails TLS 1.0 significativo**</span><span class="sxs-lookup"><span data-stu-id="783ec-126">**Inbound Partner connector seeing significant TLS1.0 mail flow**</span></span>
- <span data-ttu-id="783ec-127">**Conector local de entrada que enxerga o fluxo de emails do TLS 1.0 significativo**</span><span class="sxs-lookup"><span data-stu-id="783ec-127">**Inbound OnPremises connector seeing significant TLS1.0 mail flow**</span></span>

<span data-ttu-id="783ec-128">Para conexões TLS 1,0, você realmente precisa obter o servidor de email ou o servidor de seu parceiro atualizado ou corrigido para evitar qualquer problema quando o suporte a TLS 1,0 for eventualmente preterido no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="783ec-128">For TLS 1.0 connections, you really need to get your email server or your partner's server upgraded or fixed to avoid any issues when TLS 1.0 support is eventually deprecated in Microsoft 365.</span></span>

## <a name="see-also"></a><span data-ttu-id="783ec-129">Confira também</span><span class="sxs-lookup"><span data-stu-id="783ec-129">See also</span></span>

<span data-ttu-id="783ec-130">Para obter informações sobre outras ideias no painel de fluxo de emails, consulte [Mail Flow insights no centro de conformidade de & de segurança](mail-flow-insights-v2.md).</span><span class="sxs-lookup"><span data-stu-id="783ec-130">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
