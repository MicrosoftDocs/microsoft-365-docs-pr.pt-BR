---
title: Gerenciar listas seguras de remetentes para mensageiros em massa
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 11/17/2014
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: d48db4a3-9fbe-45e2-bbaa-1017ffdf96f8
ms.collection:
- M365-security-compliance
description: 'Se quiser usar listas de remetentes seguros, você deve saber que o Exchange Online Protection (EOP) e o processamento do Outlook lidam de forma diferente. O serviço respeita os remetentes e domínios seguros inspecionando o endereço RFC 5321. MailFrom e o endereço RFC 5322. from, enquanto o Outlook adiciona o endereço RFC 5322. from à lista de remetentes seguros de um usuário. (Observação: o serviço inspeciona o endereço 5321. MailFrom e o endereço 5322. from para os remetentes e domínios bloqueados.)'
ms.openlocfilehash: 2dcfd73cc987290bbc8ca8111580a374216a843e
ms.sourcegitcommit: 5710ce729c55d95b8b452d99ffb7ea92b5cb254a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/11/2019
ms.locfileid: "39970297"
---
# <a name="manage-safe-sender-lists-for-bulk-mailers"></a><span data-ttu-id="af511-105">Gerenciar listas seguras de remetentes para mensageiros em massa</span><span class="sxs-lookup"><span data-stu-id="af511-105">Manage safe sender lists for bulk mailers</span></span>

<span data-ttu-id="af511-106">Se quiser usar listas de remetentes seguros, você deve saber que o Exchange Online Protection (EOP) e o processamento do Outlook lidam de forma diferente.</span><span class="sxs-lookup"><span data-stu-id="af511-106">If you want to use safe sender lists, you should know that Exchange Online Protection (EOP) and Outlook handle processing differently.</span></span> <span data-ttu-id="af511-107">O serviço do Office 365 respeita os remetentes e domínios seguros inspecionando `RFC 5321.MailFrom` o endereço e `RFC 5322.From` o endereço, enquanto o Outlook `RFC 5322.From` adiciona o endereço à lista de remetentes seguros de um usuário.</span><span class="sxs-lookup"><span data-stu-id="af511-107">The Office 365 service respects safe senders and domains by inspecting the `RFC 5321.MailFrom` address and the `RFC 5322.From` address, while Outlook adds the `RFC 5322.From` address to a user's safe sender list.</span></span> <span data-ttu-id="af511-108">(Observação: o serviço inspeciona o endereço e `5321.MailFrom` `5322.From` o endereço de remetentes e domínios bloqueados.)</span><span class="sxs-lookup"><span data-stu-id="af511-108">(Note: The service inspects both the `5321.MailFrom` address and `5322.From` address for blocked senders and domains.)</span></span>

<span data-ttu-id="af511-109">O `SMTP MAIL FROM` endereço, caso contrário, conhecido `RFC 5321.MailFrom address`como o, é o endereço de email usado para executar verificações de SPF e, se o email não puder ser entregue, o caminho para o qual a mensagem devolvida será entregue.</span><span class="sxs-lookup"><span data-stu-id="af511-109">The `SMTP MAIL FROM` address, otherwise known as the `RFC 5321.MailFrom address`, is the email address that's used to perform SPF checks, and if the mail can't be delivered, the path to which the bounced message is delivered.</span></span> <span data-ttu-id="af511-110">Esse endereço de email é colocado no `Return-Path` nos cabeçalhos da mensagem por padrão, embora seja possível que o remetente designe um endereço diferente. `Return-Path`</span><span class="sxs-lookup"><span data-stu-id="af511-110">It's this email address that is placed into the `Return-Path` in the message headers by default, though it's possible for the sender to designate a different `Return-Path` address.</span></span>

<span data-ttu-id="af511-111">O `From:` endereço nos cabeçalhos da mensagem, caso contrário, conhecido `RFC 5322.From` como endereço, é o endereço de email exibido no cliente de email, como o Outlook.</span><span class="sxs-lookup"><span data-stu-id="af511-111">The `From:` address in the message headers, otherwise known as the `RFC 5322.From` address, is the email address that is displayed in the mail client such as Outlook.</span></span>

<span data-ttu-id="af511-112">Na maioria das vezes, os `5321.MailFrom` endereços `5322.From` e são os mesmos.</span><span class="sxs-lookup"><span data-stu-id="af511-112">Much of the time, the `5321.MailFrom` and `5322.From` addresses are the same.</span></span> <span data-ttu-id="af511-113">Isso é típico para comunicação pessoa a pessoa.</span><span class="sxs-lookup"><span data-stu-id="af511-113">This is typical for person-to-person communication.</span></span> <span data-ttu-id="af511-114">No entanto, quando o email é enviado em nome de outra pessoa, os endereços são frequentemente diferentes.</span><span class="sxs-lookup"><span data-stu-id="af511-114">However, when email is sent on behalf of someone else, the addresses are frequently different.</span></span> <span data-ttu-id="af511-115">Isso geralmente acontece com mais frequência para mensagens de email em massa.</span><span class="sxs-lookup"><span data-stu-id="af511-115">This usually happens most often for bulk email messages.</span></span>

<span data-ttu-id="af511-116">Por exemplo, suponha que as companhias aéreas Yonder azuis contratam a viagem da Margie para enviar seu anúncio de email.</span><span class="sxs-lookup"><span data-stu-id="af511-116">For example, suppose that Blue Yonder Airlines has hired Margie's Travel to send out its email advertising.</span></span> <span data-ttu-id="af511-117">Você recebe uma mensagem em sua caixa de entrada do remetente blueyonder@news.blueyonderairlines.com.</span><span class="sxs-lookup"><span data-stu-id="af511-117">You then get a message in your inbox from sender blueyonder@news.blueyonderairlines.com.</span></span> <span data-ttu-id="af511-118">Neste exemplo:</span><span class="sxs-lookup"><span data-stu-id="af511-118">In this example:</span></span>

- <span data-ttu-id="af511-119">O `5321.MailFrom` endereço é blueyonder.Airlines@margiestravel.com.</span><span class="sxs-lookup"><span data-stu-id="af511-119">The `5321.MailFrom` address is blueyonder.airlines@margiestravel.com.</span></span>

- <span data-ttu-id="af511-120">O `5322.From` endereço é blueyonder@news.blueyonderairlines.com, que é o que você verá no Outlook.</span><span class="sxs-lookup"><span data-stu-id="af511-120">The `5322.From` address is blueyonder@news.blueyonderairlines.com, which is what you'll see in Outlook.</span></span>

<span data-ttu-id="af511-121">Para impedir que esta mensagem seja filtrada, você pode:</span><span class="sxs-lookup"><span data-stu-id="af511-121">To prevent this message from being filtered, you can:</span></span>

- <span data-ttu-id="af511-122">**Como um usuário**: Adicione o `RFC 5322.From` endereço como um remetente seguro no Outlook.</span><span class="sxs-lookup"><span data-stu-id="af511-122">**As a user**: Add the `RFC 5322.From` address as a Safe Sender in Outlook.</span></span>

- <span data-ttu-id="af511-123">**Como um administrador**: configurar uma [regra de fluxo de emails](anti-spam-protection.md#beyond-the-basics-more-ways-to-prevent-spam-in-office-365) (também conhecida como regra de transporte).</span><span class="sxs-lookup"><span data-stu-id="af511-123">**As an admin**: Set up a [mail flow rule](anti-spam-protection.md#beyond-the-basics-more-ways-to-prevent-spam-in-office-365) (also known as a transport rule).</span></span>
