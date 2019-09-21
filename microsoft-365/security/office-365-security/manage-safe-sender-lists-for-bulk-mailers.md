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
ms.openlocfilehash: f73cc3fc88318c4f625bf5579f73d92625624fd5
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/20/2019
ms.locfileid: "37073708"
---
# <a name="manage-safe-sender-lists-for-bulk-mailers"></a><span data-ttu-id="a326f-105">Gerenciar listas seguras de remetentes para mensageiros em massa</span><span class="sxs-lookup"><span data-stu-id="a326f-105">Manage safe sender lists for bulk mailers</span></span>

<span data-ttu-id="a326f-106">Se quiser usar listas de remetentes seguros, você deve saber que o Exchange Online Protection (EOP) e o processamento do Outlook lidam de forma diferente.</span><span class="sxs-lookup"><span data-stu-id="a326f-106">If you want to use safe sender lists, you should know that Exchange Online Protection (EOP) and Outlook handle processing differently.</span></span> <span data-ttu-id="a326f-107">O serviço do Office 365 respeita os remetentes e domínios seguros inspecionando o endereço RFC 5321. MailFrom e o endereço RFC 5322. from, enquanto o Outlook adiciona o endereço RFC 5322. from à lista de remetentes seguros de um usuário.</span><span class="sxs-lookup"><span data-stu-id="a326f-107">The Office 365 service respects safe senders and domains by inspecting the RFC 5321.MailFrom address and the RFC 5322.From address, while Outlook adds the RFC 5322.From address to a user's safe sender list.</span></span> <span data-ttu-id="a326f-108">(Observação: o serviço inspeciona o endereço 5321. MailFrom e o endereço 5322. from para os remetentes e domínios bloqueados.)</span><span class="sxs-lookup"><span data-stu-id="a326f-108">(Note: The service inspects both the 5321.MailFrom address and 5322.From address for blocked senders and domains.)</span></span>
  
<span data-ttu-id="a326f-109">O endereço de email SMTP, caso contrário, conhecido como o endereço RFC 5321. MailFrom, é o endereço de email usado para executar verificações de SPF e, se o email não puder ser entregue, o caminho para o qual a mensagem devolvida será entregue.</span><span class="sxs-lookup"><span data-stu-id="a326f-109">The SMTP MAIL FROM address, otherwise known as the RFC 5321.MailFrom address, is the email address that's used to perform SPF checks, and if the mail can't be delivered, the path to which the bounced message is delivered.</span></span> <span data-ttu-id="a326f-110">Esse endereço de email é colocado no caminho de retorno nos cabeçalhos de mensagem por padrão, embora seja possível para o remetente designar um endereço de caminho de retorno diferente.</span><span class="sxs-lookup"><span data-stu-id="a326f-110">It's this email address that is placed into the Return-Path in the message headers by default, though it's possible for the sender to designate a different Return-Path address.</span></span>
  
<span data-ttu-id="a326f-111">O endereço de: nos cabeçalhos da mensagem, caso contrário, conhecido como o endereço RFC 5322. from, é o endereço de email que é exibido no cliente de email, como o Outlook.</span><span class="sxs-lookup"><span data-stu-id="a326f-111">The From: address in the message headers, otherwise known as the RFC 5322.From address, is the email address that is displayed in the mail client such as Outlook.</span></span>
  
<span data-ttu-id="a326f-112">Na maioria das vezes, os endereços 5321. MailFrom e 5322. from são os mesmos.</span><span class="sxs-lookup"><span data-stu-id="a326f-112">Much of the time, the 5321.MailFrom and 5322.From addresses are the same.</span></span> <span data-ttu-id="a326f-113">Isso é típico para comunicação pessoa a pessoa.</span><span class="sxs-lookup"><span data-stu-id="a326f-113">This is typical for person-to-person communication.</span></span> <span data-ttu-id="a326f-114">No entanto, quando o email é enviado em nome de outra pessoa, os endereços são frequentemente diferentes.</span><span class="sxs-lookup"><span data-stu-id="a326f-114">However, when email is sent on behalf of someone else, the addresses are frequently different.</span></span> <span data-ttu-id="a326f-115">Isso geralmente acontece com mais frequência para mensagens de email em massa.</span><span class="sxs-lookup"><span data-stu-id="a326f-115">This usually happens most often for bulk email messages.</span></span>
  
<span data-ttu-id="a326f-116">Por exemplo, suponha que as companhias aéreas de Yonder azul de aviação tenham contratado a viagem da Margie para enviar seu anúncio de email.</span><span class="sxs-lookup"><span data-stu-id="a326f-116">For example, suppose that the airline Blue Yonder Airlines has contracted out Margie's Travel to send out its email advertising.</span></span> <span data-ttu-id="a326f-117">Você recebe uma mensagem em sua caixa de entrada do remetente blueyonder@news.blueyonderairlines.com.</span><span class="sxs-lookup"><span data-stu-id="a326f-117">You then get a message in your inbox from sender blueyonder@news.blueyonderairlines.com.</span></span> <span data-ttu-id="a326f-118">Nesse caso, o endereço 5321. MailFrom é blueyonder.airlines@margiestravel.com e blueyonder@news.blueyonderairlines.com é o endereço de 5322. from que é aquele, você vê no Outlook.</span><span class="sxs-lookup"><span data-stu-id="a326f-118">In this case, 5321.MailFrom address is blueyonder.airlines@margiestravel.com, and blueyonder@news.blueyonderairlines.com is the 5322.From address which is the one, you see in Outlook.</span></span> <span data-ttu-id="a326f-119">Como o serviço respeita o endereço RFC 5322. from, para evitar que esta mensagem seja filtrada, você pode adicionar o RFC 5322. from address como um remetente seguro no Outlook (como um usuário) ou, se você for um administrador configurar uma regra de fluxo conforme mostrado no [anti-spam Seção proteção](anti-spam-protection.md) .</span><span class="sxs-lookup"><span data-stu-id="a326f-119">Because the service respects the RFC 5322.From address, to prevent this message from getting filtered, you can add the RFC 5322.From address as a safe sender in Outlook (as a user) or, if you're an administrator set up a mailflow rule as shown on the [Anti-spam Protection](anti-spam-protection.md) section.</span></span>
  

