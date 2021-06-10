---
title: Remova-se da lista de envios bloqueados
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 04/18/2016
audience: ITPro
ms.topic: troubleshooting
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 0bcecdd4-3343-4cc0-9e58-e19d4de515e8
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
description: Neste artigo, você aprenderá a usar o portal de lista para remover a si mesmo da lista Microsoft 365 de envios bloqueados.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c4488f5e5607d71da35b2921e863fb02195467e2
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/25/2021
ms.locfileid: "51203113"
---
# <a name="use-the-delist-portal-to-remove-yourself-from-the-blocked-senders-list"></a><span data-ttu-id="2c9a1-103">Usar o portal de remoção da lista para ser removido da lista de remetentes bloqueados</span><span class="sxs-lookup"><span data-stu-id="2c9a1-103">Use the delist portal to remove yourself from the blocked senders list</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="2c9a1-104">**Aplica-se a**</span><span class="sxs-lookup"><span data-stu-id="2c9a1-104">**Applies to**</span></span>
- [<span data-ttu-id="2c9a1-105">Proteção do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="2c9a1-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="2c9a1-106">Plano 1 e plano 2 do Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="2c9a1-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="2c9a1-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2c9a1-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="2c9a1-108">Você está recebendo uma mensagem de erro ao tentar enviar um email para um destinatário cujo endereço de email está Microsoft 365?</span><span class="sxs-lookup"><span data-stu-id="2c9a1-108">Are you getting an error message when you try to send an email to a recipient whose email address is in Microsoft 365?</span></span> <span data-ttu-id="2c9a1-109">Se você acha que não deve receber a mensagem de erro, pode usar o portal de lista de listas para remover a si mesmo da lista de envios bloqueados.</span><span class="sxs-lookup"><span data-stu-id="2c9a1-109">If you think you should not be receiving the error message, you can use the delist portal to remove yourself from the blocked senders list.</span></span>

## <a name="what-is-the-blocked-senders-list"></a><span data-ttu-id="2c9a1-110">O que é a lista de envios bloqueados?</span><span class="sxs-lookup"><span data-stu-id="2c9a1-110">What is the blocked senders list?</span></span>

<span data-ttu-id="2c9a1-111">A Microsoft usa a lista de remetentes bloqueados para proteger seus clientes contra spam, falsificação e ataques de phishing.</span><span class="sxs-lookup"><span data-stu-id="2c9a1-111">Microsoft uses the blocked senders list to protect its customers from spam, spoofing, and phishing attacks.</span></span> <span data-ttu-id="2c9a1-112">O endereço IP do seu servidor de email, ou seja, o endereço que seu servidor de email usa para se identificar na Internet, foi marcado como uma possível ameaça para Microsoft 365 por um dos vários motivos.</span><span class="sxs-lookup"><span data-stu-id="2c9a1-112">Your mail server's IP address, that is, the address your mail server uses to identify itself on the Internet, was tagged as a potential threat to Microsoft 365 for one of a variety of reasons.</span></span> <span data-ttu-id="2c9a1-113">Quando Microsoft 365 adiciona o endereço IP à lista, impede toda a comunicação entre o endereço IP e qualquer um de nossos clientes por meio de nossos datacenters.</span><span class="sxs-lookup"><span data-stu-id="2c9a1-113">When Microsoft 365 adds the IP address to the list, it prevents all further communication between the IP address and any of our customers through our datacenters.</span></span>

<span data-ttu-id="2c9a1-114">Você saberá que foi adicionado à lista quando receber uma resposta a uma mensagem de email que inclui um erro parecido com o seguinte:</span><span class="sxs-lookup"><span data-stu-id="2c9a1-114">You will know you have been added to the list when you receive a response to a mail message that includes an error that looks something like this:</span></span>

> <span data-ttu-id="2c9a1-115">550 5.7.606-649 Acesso negado, proibiu o envio de IP [_endereço IP_]; Para solicitar a remoção dessa lista, visite <https://sender.office.com/> e siga as instruções.</span><span class="sxs-lookup"><span data-stu-id="2c9a1-115">550 5.7.606-649 Access denied, banned sending IP [_IP address_]; To request removal from this list please visit <https://sender.office.com/> and follow the directions.</span></span> <span data-ttu-id="2c9a1-116">Para obter mais informações, [consulte Email non-delivery reports in Exchange Online](/Exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/non-delivery-reports-in-exchange-online).</span><span class="sxs-lookup"><span data-stu-id="2c9a1-116">For more information see [Email non-delivery reports in Exchange Online](/Exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/non-delivery-reports-in-exchange-online).</span></span>

<span data-ttu-id="2c9a1-117">em que  _IP address_ é o endereço IP do computador no qual o servidor de email é executado.</span><span class="sxs-lookup"><span data-stu-id="2c9a1-117">where  _IP address_ is the IP address of the computer on which the mail server runs.</span></span>

### <a name="to-use-delist-portal-to-remove-yourself-from-the-blocked-senders-list"></a><span data-ttu-id="2c9a1-118">Para usar o portal de lista para remover a si mesmo da lista de envios bloqueados</span><span class="sxs-lookup"><span data-stu-id="2c9a1-118">To use delist portal to remove yourself from the blocked senders list</span></span>

1. <span data-ttu-id="2c9a1-119">Em um navegador da Web, acesse <https://sender.office.com>.</span><span class="sxs-lookup"><span data-stu-id="2c9a1-119">In a web browser, go to <https://sender.office.com>.</span></span>

2. <span data-ttu-id="2c9a1-p104">Siga as instruções descritas na página. Certifique-se de usar o endereço de email ao qual a mensagem de erro foi enviada e o endereço IP que é especificado na mensagem de erro. Você só pode inserir um endereço de email e um endereço IP por visita.</span><span class="sxs-lookup"><span data-stu-id="2c9a1-p104">Follow the instructions on the page. Ensure that you use the email address to which the error message was sent, and the IP address that is specified in the error message. You can only enter one email address and one IP address per visit.</span></span>

3. <span data-ttu-id="2c9a1-123">Clique em **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="2c9a1-123">Click **Submit**.</span></span>

    <span data-ttu-id="2c9a1-124">O portal envia um email para o endereço de email que você fornecer.</span><span class="sxs-lookup"><span data-stu-id="2c9a1-124">The portal sends an email to the email address that you supply.</span></span> <span data-ttu-id="2c9a1-125">O email será parecido com o seguinte: Captura de tela do email recebido ao enviar uma solicitação por meio ![ do portal de lista de espera](../../media/bf13e4f7-f68c-4e46-baa7-b6ab4cfc13f3.png)</span><span class="sxs-lookup"><span data-stu-id="2c9a1-125">The email will look something like the following: ![Screenshot of email received when you submit a request through the delist portal](../../media/bf13e4f7-f68c-4e46-baa7-b6ab4cfc13f3.png)</span></span>

4. <span data-ttu-id="2c9a1-126">Clique no link confirmação no email enviado a você pelo portal de remoção da lista.</span><span class="sxs-lookup"><span data-stu-id="2c9a1-126">Click the confirmation link in the email sent to you by the delisting portal.</span></span>

    <span data-ttu-id="2c9a1-127">Isso leva você de volta ao portal de remoção da lista.</span><span class="sxs-lookup"><span data-stu-id="2c9a1-127">This brings you back to the delist portal.</span></span>

5. <span data-ttu-id="2c9a1-128">No portal de remoção da lista, clique em **remover IP da lista**.</span><span class="sxs-lookup"><span data-stu-id="2c9a1-128">In the delist portal, click **Delist IP**.</span></span>

    <span data-ttu-id="2c9a1-129">Depois que o endereço IP for removido da lista de remetentes bloqueados, as mensagens de email desse endereço IP serão entregues aos destinatários que usam Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="2c9a1-129">After the IP address is removed from the blocked senders list, email messages from that IP address will be delivered to recipients who use Microsoft 365.</span></span> <span data-ttu-id="2c9a1-130">Portanto, certifique-se de que os emails enviados a partir desse endereço IP não sejam ofensivos ou mal-intencionados; caso contrário, o endereço IP pode ser bloqueado novamente.</span><span class="sxs-lookup"><span data-stu-id="2c9a1-130">So, make sure you're confident that email sent from that IP address won't be abusive or malicious; otherwise, the IP address might be blocked again.</span></span>

    > [!NOTE]
    > <span data-ttu-id="2c9a1-131">Pode levar até 24 horas ou os resultados podem variar bastante antes que as restrições sejam removidas.</span><span class="sxs-lookup"><span data-stu-id="2c9a1-131">It may take up to 24 hours or results can vary widely before restrictions are removed.</span></span>

<span data-ttu-id="2c9a1-132">Consulte [Create safe sender lists in EOP](create-safe-sender-lists-in-office-365.md) and [Outbound spam protection in EOP](outbound-spam-controls.md) to prevent an IP from being blocked.</span><span class="sxs-lookup"><span data-stu-id="2c9a1-132">See [Create safe sender lists in EOP](create-safe-sender-lists-in-office-365.md) and [Outbound spam protection in EOP](outbound-spam-controls.md) to prevent an IP from being blocked.</span></span>