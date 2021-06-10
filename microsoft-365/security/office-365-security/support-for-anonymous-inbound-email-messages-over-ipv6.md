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
description: O administrador pode aprender a configurar o suporte para emails de entrada anônimos de fontes IPv6 em Exchange Online e Proteção do Exchange Online.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 80fdcc9dcfe3006ef8b21aa19856fe8c0ea3ff70
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/10/2021
ms.locfileid: "52300044"
---
# <a name="add-support-for-anonymous-inbound-email-over-ipv6-in-microsoft-365"></a><span data-ttu-id="47161-103">Adicione suporte para email de entrada anônimo por IPv6 no Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="47161-103">Add support for anonymous inbound email over IPv6 in Microsoft 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="47161-104">**Aplica-se a**</span><span class="sxs-lookup"><span data-stu-id="47161-104">**Applies to**</span></span>
- [<span data-ttu-id="47161-105">Proteção do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="47161-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="47161-106">Plano 1 e plano 2 do Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="47161-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="47161-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="47161-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="47161-108">Microsoft 365 com caixas de correio Exchange Online e organizações de Proteção do Exchange Online (EOP) autônomas sem Exchange Online de correio suportam emails de entrada anônimos por meio do IPv6.</span><span class="sxs-lookup"><span data-stu-id="47161-108">Microsoft 365 organizations with Exchange Online mailboxes and standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes support anonymous inbound email over IPv6.</span></span> <span data-ttu-id="47161-109">O servidor de email IPv6 de origem deve atender a ambos os seguintes requisitos:</span><span class="sxs-lookup"><span data-stu-id="47161-109">The source IPv6 email server must meet both of the following requirements:</span></span>

- <span data-ttu-id="47161-110">O endereço IPv6 de origem deve ter um registro válido de busca de DNS reverso (PTR) que permita ao destino encontrar o nome de domínio do endereço IPv6.</span><span class="sxs-lookup"><span data-stu-id="47161-110">The source IPv6 address must have a valid reverse DNS lookup (PTR) record that allows the destination to find the domain name from the IPv6 address.</span></span>

- <span data-ttu-id="47161-111">O remetente deve passar por verificação SPF (definida na [RFC 7208](https://tools.ietf.org/html/rfc7208)) ou [verificação DKIM](http://dkim.org/) (definida na [RFC 6376](https://www.rfc-editor.org/rfc/rfc6376.txt)).</span><span class="sxs-lookup"><span data-stu-id="47161-111">The sender must pass either SPF verification (defined in [RFC 7208](https://tools.ietf.org/html/rfc7208)) or [DKIM verification](http://dkim.org/) (defined in [RFC 6376](https://www.rfc-editor.org/rfc/rfc6376.txt)).</span></span>

<span data-ttu-id="47161-112">Para que sua organização possa receber emails de entrada anônimos pelo IPv6, um administrador precisa entrar em contato com o suporte da Microsoft e solicitar.</span><span class="sxs-lookup"><span data-stu-id="47161-112">Before your organization can receive anonymous inbound email over IPv6, an admin needs to contact Microsoft support and ask for it.</span></span> <span data-ttu-id="47161-113">Para obter instruções sobre como abrir uma solicitação de suporte, consulte [Contact support for business products - Admin Help](../../business-video/get-help-support.md).</span><span class="sxs-lookup"><span data-stu-id="47161-113">For instructions about how to open a support request, see [Contact support for business products - Admin Help](../../business-video/get-help-support.md).</span></span>

<span data-ttu-id="47161-114">Depois que o suporte à mensagem IPv6 de entrada anônima for habilitado em sua organização, a mensagem passará pela filtragem normal de mensagens fornecida pelo serviço.</span><span class="sxs-lookup"><span data-stu-id="47161-114">After anonymous inbound IPv6 message support is enabled in your organization, the message will go through the normal message filtering that's provided by the service.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="47161-115">Solução de problemas</span><span class="sxs-lookup"><span data-stu-id="47161-115">Troubleshooting</span></span>

- <span data-ttu-id="47161-116">Se o servidor de email de origem não tiver um registro de pesquisa DNS reverso IPv6, as mensagens serão rejeitadas com o seguinte erro:</span><span class="sxs-lookup"><span data-stu-id="47161-116">If the source email server doesn't have an IPv6 reverse DNS lookup record, the messages will be rejected with the following error:</span></span>

  > <span data-ttu-id="47161-117">450 4.7.25 O serviço indisponível, o envio do endereço IPv6 [2a01:111:f200:2004::240] deve ter o registro DNS reverso.</span><span class="sxs-lookup"><span data-stu-id="47161-117">450 4.7.25 Service unavailable, sending IPv6 address [2a01:111:f200:2004::240] must have reverse DNS record.</span></span>

- <span data-ttu-id="47161-118">Se o remetente não passar na validação SPF ou DKIM, as mensagens serão rejeitadas com o seguinte erro:</span><span class="sxs-lookup"><span data-stu-id="47161-118">If the sender doesn't pass SPF or DKIM validation, the messages will be rejected with the following error:</span></span>

  > <span data-ttu-id="47161-119">450 4.7.26 Serviço indisponível, mensagem enviada por IPv6 [2a01:111:f200:2004::240] deve passar na validação SPF ou DKIM.</span><span class="sxs-lookup"><span data-stu-id="47161-119">450 4.7.26 Service unavailable, message sent over IPv6 [2a01:111:f200:2004::240] must pass either SPF or DKIM validation.</span></span>

- <span data-ttu-id="47161-120">Se você tentar receber mensagens IPv6 anônimas antes de ter optado, a mensagem será rejeitada com o seguinte erro:</span><span class="sxs-lookup"><span data-stu-id="47161-120">If you try to receive anonymous IPv6 messages before you've opted in, the message will be rejected with the following error:</span></span>

  > <span data-ttu-id="47161-121">550 5.2.1 Serviço indisponível, [contoso.com] não aceita email por IPv6.</span><span class="sxs-lookup"><span data-stu-id="47161-121">550 5.2.1 Service unavailable, [contoso.com] does not accept email over IPv6.</span></span>

## <a name="related-topics"></a><span data-ttu-id="47161-122">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="47161-122">Related topics</span></span>

[<span data-ttu-id="47161-123">Suporte para validação de mensagens assinadas por DKIM</span><span class="sxs-lookup"><span data-stu-id="47161-123">Support for validation of DKIM signed messages</span></span>](support-for-validation-of-dkim-signed-messages.md)
