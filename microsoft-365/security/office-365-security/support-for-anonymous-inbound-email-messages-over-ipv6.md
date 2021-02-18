---
title: Adicionar suporte para mensagens anônimas de email de entrada por IPv6
f1.keywords:
- NOCSH
author: chrisda
ms.author: chrisda
manager: chrisda
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: b68df621-0a5f-4824-8abc-41e0c4fd1398
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: O administrador pode aprender a configurar o suporte para emails de entrada anônimos de fontes IPv6 no Exchange Online e no Exchange Online Protection.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 63c9434fbd1f69c0cbd3145717b712857eb17e28
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290268"
---
# <a name="add-support-for-anonymous-inbound-email-over-ipv6-in-microsoft-365"></a><span data-ttu-id="23f8a-103">Adicionar suporte para email de entrada anônimo sobre IPv6 no Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="23f8a-103">Add support for anonymous inbound email over IPv6 in Microsoft 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="23f8a-104">**Aplica-se a**</span><span class="sxs-lookup"><span data-stu-id="23f8a-104">**Applies to**</span></span>
- [<span data-ttu-id="23f8a-105">Proteção do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="23f8a-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="23f8a-106">Plano 1 e plano 2 do Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="23f8a-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="23f8a-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="23f8a-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="23f8a-108">As organizações do Microsoft 365 com caixas de correio do Exchange Online e organizações autônomas do Exchange Online Protection (EOP) sem caixas de correio do Exchange Online suportam emails de entrada anônimos por IPv6.</span><span class="sxs-lookup"><span data-stu-id="23f8a-108">Microsoft 365 organizations with Exchange Online mailboxes and standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes support anonymous inbound email over IPv6.</span></span> <span data-ttu-id="23f8a-109">O servidor de email IPv6 de origem deve atender a ambos os seguintes requisitos:</span><span class="sxs-lookup"><span data-stu-id="23f8a-109">The source IPv6 email server must meet both of the following requirements:</span></span>

- <span data-ttu-id="23f8a-110">O endereço IPv6 de origem deve ter um registro de busca de DNS reverso (PTR) válido que permita que o destino encontre o nome de domínio do endereço IPv6.</span><span class="sxs-lookup"><span data-stu-id="23f8a-110">The source IPv6 address must have a valid reverse DNS lookup (PTR) record that allows the destination to find the domain name from the IPv6 address.</span></span>

- <span data-ttu-id="23f8a-111">O remetente deve passar por verificação SPF (definida na [RFC 7208](https://tools.ietf.org/html/rfc7208)) ou [verificação DKIM](http://dkim.org/) (definida na [RFC 6376](https://www.rfc-editor.org/rfc/rfc6376.txt)).</span><span class="sxs-lookup"><span data-stu-id="23f8a-111">The sender must pass either SPF verification (defined in [RFC 7208](https://tools.ietf.org/html/rfc7208)) or [DKIM verification](http://dkim.org/) (defined in [RFC 6376](https://www.rfc-editor.org/rfc/rfc6376.txt)).</span></span>

<span data-ttu-id="23f8a-112">Para que sua organização possa receber emails de entrada anônimos por IPv6, um administrador precisa entrar em contato com o suporte da Microsoft e solicitar.</span><span class="sxs-lookup"><span data-stu-id="23f8a-112">Before your organization can receive anonymous inbound email over IPv6, an admin needs to contact Microsoft support and ask for it.</span></span> <span data-ttu-id="23f8a-113">Para obter instruções sobre como abrir uma solicitação de suporte, consulte Contatar o suporte para produtos comerciais [- Ajuda para Administradores.](../../admin/contact-support-for-business-products.md)</span><span class="sxs-lookup"><span data-stu-id="23f8a-113">For instructions about how to open a support request, see [Contact support for business products - Admin Help](../../admin/contact-support-for-business-products.md).</span></span>

<span data-ttu-id="23f8a-114">Depois que o suporte a mensagens IPv6 de entrada anônimas for habilitado em sua organização, a mensagem passará pela filtragem de mensagens normal fornecida pelo serviço.</span><span class="sxs-lookup"><span data-stu-id="23f8a-114">After anonymous inbound IPv6 message support is enabled in your organization, the message will go through the normal message filtering that's provided by the service.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="23f8a-115">Solução de problemas</span><span class="sxs-lookup"><span data-stu-id="23f8a-115">Troubleshooting</span></span>

- <span data-ttu-id="23f8a-116">Se o servidor de email de origem não tiver um registro de pesquisa de DNS reverso IPv6, as mensagens serão rejeitadas com o seguinte erro:</span><span class="sxs-lookup"><span data-stu-id="23f8a-116">If the source email server doesn't have an IPv6 reverse DNS lookup record, the messages will be rejected with the following error:</span></span>

  > <span data-ttu-id="23f8a-117">450 4.7.25 Serviço indisponível, o envio do endereço IPv6 [2a01:111:f200:2004::240] deve ter um registro DNS reverso.</span><span class="sxs-lookup"><span data-stu-id="23f8a-117">450 4.7.25 Service unavailable, sending IPv6 address [2a01:111:f200:2004::240] must have reverse DNS record.</span></span>

- <span data-ttu-id="23f8a-118">Se o remetente não passar na validação SPF ou DKIM, as mensagens serão rejeitadas com o seguinte erro:</span><span class="sxs-lookup"><span data-stu-id="23f8a-118">If the sender doesn't pass SPF or DKIM validation, the messages will be rejected with the following error:</span></span>

  > <span data-ttu-id="23f8a-119">450 4.7.26 Serviço indisponível, a mensagem enviada por IPv6 [2a01:111:f200:2004::240] deve passar na validação SPF ou DKIM.</span><span class="sxs-lookup"><span data-stu-id="23f8a-119">450 4.7.26 Service unavailable, message sent over IPv6 [2a01:111:f200:2004::240] must pass either SPF or DKIM validation.</span></span>

- <span data-ttu-id="23f8a-120">Se você tentar receber mensagens IPv6 anônimas antes de optar por ela, a mensagem será rejeitada com o seguinte erro:</span><span class="sxs-lookup"><span data-stu-id="23f8a-120">If you try to receive anonymous IPv6 messages before you've opted in, the message will be rejected with the following error:</span></span>

  > <span data-ttu-id="23f8a-121">550 5.2.1 Serviço indisponível, [contoso.com] não aceita email sobre IPv6.</span><span class="sxs-lookup"><span data-stu-id="23f8a-121">550 5.2.1 Service unavailable, [contoso.com] does not accept email over IPv6.</span></span>

## <a name="related-topics"></a><span data-ttu-id="23f8a-122">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="23f8a-122">Related topics</span></span>

[<span data-ttu-id="23f8a-123">Suporte para validação de mensagens assinadas por DKIM</span><span class="sxs-lookup"><span data-stu-id="23f8a-123">Support for validation of DKIM signed messages</span></span>](support-for-validation-of-dkim-signed-messages.md)
