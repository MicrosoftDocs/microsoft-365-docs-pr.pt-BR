---
title: Adicionar suporte para mensagens anônimas de e-mail de entrada por IPv6
f1.keywords:
- NOCSH
author: chrisda
ms.author: chrisda
manager: chrisda
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: b68df621-0a5f-4824-8abc-41e0c4fd1398
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: O administrador pode saber como configurar o suporte para emails de entrada anônimos de fontes IPv6 no Exchange Online e no Exchange Online Protection.
ms.openlocfilehash: fbbcba3631c7b2a7060f07011c119ee973fdf4af
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/19/2020
ms.locfileid: "44818704"
---
# <a name="add-support-for-anonymous-inbound-email-over-ipv6-in-microsoft-365"></a><span data-ttu-id="6949e-103">Adicionar suporte para email de entrada anônimo por IPv6 no Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="6949e-103">Add support for anonymous inbound email over IPv6 in Microsoft 365</span></span>

<span data-ttu-id="6949e-104">As organizações do Microsoft 365 com caixas de correio do Exchange Online e proteção autônoma do Exchange Online (EOP) sem caixas de correio do Exchange Online dão suporte a emails de entrada anônimos por IPv6.</span><span class="sxs-lookup"><span data-stu-id="6949e-104">Microsoft 365 organizations with Exchange Online mailboxes and standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes support anonymous inbound email over IPv6.</span></span> <span data-ttu-id="6949e-105">O servidor de email IPv6 de origem deve cumprir os seguintes requisitos:</span><span class="sxs-lookup"><span data-stu-id="6949e-105">The source IPv6 email server must meet both of the following requirements:</span></span>

- <span data-ttu-id="6949e-106">O endereço IPv6 de origem deve ter um registro de pesquisa de DNS reverso válido que permite que o destino encontre o nome de domínio do endereço IPv6.</span><span class="sxs-lookup"><span data-stu-id="6949e-106">The source IPv6 address must have a valid reverse DNS lookup (PTR) record that allows the destination to find the domain name from the IPv6 address.</span></span>

- <span data-ttu-id="6949e-107">O remetente deve passar por verificação SPF (definida na [RFC 7208](https://tools.ietf.org/html/rfc7208)) ou [verificação DKIM](https://dkim.org/) (definida na [RFC 6376](https://www.rfc-editor.org/rfc/rfc6376.txt)).</span><span class="sxs-lookup"><span data-stu-id="6949e-107">The sender must pass either SPF verification (defined in [RFC 7208](https://tools.ietf.org/html/rfc7208)) or [DKIM verification](https://dkim.org/) (defined in [RFC 6376](https://www.rfc-editor.org/rfc/rfc6376.txt)).</span></span>

<span data-ttu-id="6949e-108">Antes que sua organização possa receber emails de entrada anônimos por IPv6, um administrador precisa entrar em contato com o suporte da Microsoft e solicitá-lo.</span><span class="sxs-lookup"><span data-stu-id="6949e-108">Before your organization can receive anonymous inbound email over IPv6, an admin needs to contact Microsoft support and ask for it.</span></span> <span data-ttu-id="6949e-109">Para obter instruções sobre como abrir uma solicitação de suporte, consulte [contatar o suporte para produtos de negócios-ajuda para administradores](../../admin/contact-support-for-business-products.md).</span><span class="sxs-lookup"><span data-stu-id="6949e-109">For instructions about how to open a support request, see [Contact support for business products - Admin Help](../../admin/contact-support-for-business-products.md).</span></span>

<span data-ttu-id="6949e-110">Depois que o suporte à mensagem IPv6 de entrada anônima estiver habilitado em sua organização, a mensagem passará pela filtragem de mensagens normal fornecida pelo serviço.</span><span class="sxs-lookup"><span data-stu-id="6949e-110">After anonymous inbound IPv6 message support is enabled in your organization, the message will go through the normal message filtering that's provided by the service.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="6949e-111">Solução de problemas</span><span class="sxs-lookup"><span data-stu-id="6949e-111">Troubleshooting</span></span>

- <span data-ttu-id="6949e-112">Se o servidor de email de origem não tiver um registro de pesquisa de DNS reverso IPv6, as mensagens serão rejeitadas com o seguinte erro:</span><span class="sxs-lookup"><span data-stu-id="6949e-112">If the source email server doesn't have an IPv6 reverse DNS lookup record, the messages will be rejected with the following error:</span></span>

  > <span data-ttu-id="6949e-113">450 o serviço 4.7.25 não está disponível, enviando endereço IPv6 [2a01:111: F200: de 2004:: 240] deve ter um registro DNS reverso.</span><span class="sxs-lookup"><span data-stu-id="6949e-113">450 4.7.25 Service unavailable, sending IPv6 address [2a01:111:f200:2004::240] must have reverse DNS record.</span></span>

- <span data-ttu-id="6949e-114">Se o remetente não passar pela validação SPF ou DKIM, as mensagens serão rejeitadas com o seguinte erro:</span><span class="sxs-lookup"><span data-stu-id="6949e-114">If the sender doesn't pass SPF or DKIM validation, the messages will be rejected with the following error:</span></span>

  > <span data-ttu-id="6949e-115">450 4.7.26 serviço não disponível, a mensagem enviada por IPv6 [2a01:111: F200:2004:: 240] deve passar pela validação SPF ou DKIM.</span><span class="sxs-lookup"><span data-stu-id="6949e-115">450 4.7.26 Service unavailable, message sent over IPv6 [2a01:111:f200:2004::240] must pass either SPF or DKIM validation.</span></span>

- <span data-ttu-id="6949e-116">Se você tentar receber mensagens IPv6 anônimas antes de optar por você, a mensagem será rejeitada com o seguinte erro:</span><span class="sxs-lookup"><span data-stu-id="6949e-116">If you try to receive anonymous IPv6 messages before you've opted in, the message will be rejected with the following error:</span></span>

  > <span data-ttu-id="6949e-117">550 o serviço 5.2.1 não está disponível, [contoso.com] não aceita emails sobre IPv6.</span><span class="sxs-lookup"><span data-stu-id="6949e-117">550 5.2.1 Service unavailable, [contoso.com] does not accept email over IPv6.</span></span>

## <a name="related-topics"></a><span data-ttu-id="6949e-118">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="6949e-118">Related topics</span></span>

[<span data-ttu-id="6949e-119">Suporte para validação de mensagens assinadas por DKIM</span><span class="sxs-lookup"><span data-stu-id="6949e-119">Support for validation of DKIM signed messages</span></span>](support-for-validation-of-dkim-signed-messages.md)